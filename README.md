using System;
using UnityEngine;
 
using TMPro;



public class PleyerCont : MonoBehaviour
{
     public Rigidbody or;
    public TMP_Text scoreText;
    private int count = 0;
        public float speed = 6f;

    private void Awake() 
    {
     or=GetComponent<Rigidbody>();  
     
    }      

  
    private void FixedUpdate()      
    {
     float h = Input.GetAxis("Horizontal");
     float v = Input.GetAxis("Vertical"); 
     or.velocity = new Vector3(h,or.velocity.y,v) * speed * Time.fixedDeltaTime;
     
    }
     private void OnTriggerEnter(Collider other) 
     {
      if(other.gameObject.tag=="production")
      { count++;
        Destroy(other.gameObject);
        if(count != 5)
          scoreText.text = "production" + count;           
        else
        scoreText.text = "you Win";

      } 
     }
    
  
} 


   

