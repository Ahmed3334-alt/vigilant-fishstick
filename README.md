using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class MovePlayer : MonoBehaviour
{ 
   public CharacterController controller;
   public float graviti = 4.734673f;
   private Vector3 velosity;
   public float speed = 10f;
      

   private void Update() 
   {
      float v = Input.GetAxis("Vertical");
      float h = Input.GetAxis("Horizontal");
      Vector3 move = transform.right*h + transform.forward*v;
      controller.Move(move*speed*Time.deltaTime);

      velosity.y += graviti*Time.deltaTime;
      controller.Move(velosity*Time.deltaTime);     
     
   isGraunded = Physics.CheckSphere(sfera.position,chekSphera,sloy);
      
      if(isGraunded&&velosity.y <0)
      {
      velosity.y += -2f;
      }
   
      if(Input.GetButtonDown("Jump")&&isGraunded)
      {
      velosity.y = Mathf.Sqrt(jumpPower*-2f*graviti);
      }
      
      if(Input.GetKey("c"))
      controller.height = 1f;
      else
      {
      controller.height = 2f;
      }

      if(Input.GetKey("left shift"))
       speed = 20f;
      else
      {
       speed = 10f;
      }  
  }
  public Transform sfera;
  public float chekSphera = 0.4f;
  public LayerMask sloy;
  public float jumpPower = 3f;
  private bool isGraunded;
}
