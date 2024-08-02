using System;
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CONT : MonoBehaviour
{
    public MeshRenderer loo;


    private void Awake() 
   {
     loo = GetComponent<MeshRenderer>();
   }
    

   private void Update() 
   {
    
    if(Input.GetKeyUp(KeyCode.G))
    {
      loo.material.color= Color.black;
    }
  
if(Input.GetKeyUp(KeyCode.H))
    {
      loo.material.color= Color.green;
    }

if(Input.GetKeyUp(KeyCode.J))
    {
      loo.material.color= Color.red;
    }
   }
   
   
                 
 
}











