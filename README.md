using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class BehaviourScript : MonoBehaviour
{
  public Transform sfera;
  public float chekSphera = 0.4f;
  public LayerMask sloy;
  public float jumpPower = 3f;
  private Vector3 velosity;
  private bool isGraunded;
  public float graviti = 4.734673f;
    void Update()
    {
      isGraunded = Physics.CheckSphere(sfera.position,chekSphera,sloy);
      if(isGraunded&&velosity.y <0)
      {
        velosity.y += -2f;
      }
   
       if(Input.GetButtonDown("Jump")&&isGraunded)
     {
       velosity.y = Mathf.Sqrt(jumpPower*-2f*graviti);
     }
    }
}
