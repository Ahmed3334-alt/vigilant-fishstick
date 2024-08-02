using System.Collections;
using System.Collections.Generic;
using JetBrains.Annotations;
using UnityEngine;
public class NewBehaviour : MonoBehaviour
{
    public CharacterController controller;
    public float speed = 10f;
    public float JumpPower = 3f;
    public float gravity = 18.692f;
    public LayerMask sloy;
    private Vector3 velosity;
    public Transform sfera;
    private float cheksphera = 3;
    private bool isGraunded;

    void Start()
    {
     Cursor.lockState=CursorLockMode.Locked;
    }

    // Update is called once per frame
    void Update()
    {
     float v = Input.GetAxis("Vertical");//Движение персонажа
     float h = Input.GetAxis("Horizontal");
     Vector3 move = transform.right*h +transform.forward*v;
     controller.Move(move*speed*Time.deltaTime);
    
     velosity.y+=gravity*Time.deltaTime; //Создаём физику
     controller.Move(velosity*Time.deltaTime);
     isGraunded=Physics.CheckSphere(sfera.position,cheksphera ,sloy);//CheckSphere Этот метод проверяет пересекаются
                                                                     // ли наша сфера с заданным объектом
       if(isGraunded&&velosity.y<0)
       {
        velosity.y += -2f;
       }                                                               
       if(Input.GetButtonDown("Jump")&&isGraunded)
       {
        velosity.y = Mathf.Sqrt(JumpPower*-2f*gravity);
       }
      
       if(Input.GetKey("left shift"))
       {
        speed = 50f;
       
       }
        else
        {
         speed = 10f;
        }
       
       if(Input.GetKey("c"))
       {
        controller.height = 1f;
       
       }
        else
        {
         controller.height = 2f;
        }
        
        

    }
}
