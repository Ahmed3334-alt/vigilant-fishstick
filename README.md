
using UnityEngine;


public class MovePlaer : MonoBehaviour
{
     
    
    
    private Rigidbody rb;
    
    private void Awake()
    {
     rb = GetComponent<Rigidbody>();
    }
  public float speed1 = 4,speed2 = 4;
    private void FixedUpdate() 
    {
     float h = Input.GetAxis("Horizontal") * speed1 * Time.fixedDeltaTime ;
     float v = Input.GetAxis("Vertical") * speed2 * Time.fixedDeltaTime;
     
      rb.velocity = transform.TransformDirection(new Vector3(-v,rb.velocity.y,h));
    }
public float thrust = 500f;

    private void OnCollisionEnter(Collision other)
    {
      if(other.gameObject.name == "Cube (8)")
      {
       rb.AddForce(new Vector3 (0,1,0) * thrust);
      } 
    }

    private void OnCollisionExit(Collision other)
    {
    //  Debug.Log("HELLO"); 
    }

    private void OnTriggerEnter(Collider other) 
    {
     if(other.gameObject.name == "box")
     {
      Debug.Log("box by");
      
     }
    }
}


  

//  КОРЗИНА\/
// float m = Input.GetAxis("Vertical");
  //  transform.Translate(new Vector3(-1,0,0) * SpeedPlayer * Time.deltaTime * m );

    //  float o = Input.GetAxis("Horizontal");
    //  transform.Translate(new Vector3(0,1,0) * SpeedPlayer * Time.deltaTime * o );










