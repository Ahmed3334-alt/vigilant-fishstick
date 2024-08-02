
using System;
using JetBrains.Annotations;
using Unity.VisualScripting;
using UnityEngine;
using UnityEngine.UIElements;

public class bog : MonoBehaviour
{    
   public Transform[] objs = new Transform[3];
  public float RotateSpeed = 0.5f; 
  public float speed = 0.5f;
  public void Start()
    {
      
      //orr.GetComponent<Transform>().position = new Vector3(2,4,4);
      //for(int i = 0;i < orr.Length;++i)
      //  orr[i].SetActive (false);
    
    }
    
   private void Update() 
    { 
     for(int i=0;i<objs.Length;i++)  
     {
      if(objs[i] == null)
        continue; 
      
      objs[i].Translate(new Vector3 (-1,0,0) * speed * Time.deltaTime);
      objs[i].Rotate(new Vector3 (-1,0,0) * speed * Time.deltaTime);
     
       float poz = objs[i].position.x;
       if(poz < -25 && objs[i].gameObject.name == "Cube")  
        Destroy(objs[i].gameObject);
        
   
      }
    }
    
}
