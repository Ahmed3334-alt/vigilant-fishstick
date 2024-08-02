
using System.Collections;
using System.Security.Cryptography;
using UnityEngine;
using UnityEngine.UIElements;

public class BOBY : MonoBehaviour
{
public GameObject[]obj ;


private void Update () 
{
 

 if(Input.GetKeyDown(KeyCode.Q))
 
  StartCoroutine(call(3f));      
     //  Invoke("Create",2f);        
 
}
// private void Create()
// {    
//         for(int i=0;i<5;i++)
//         {
//          Instantiate(obj[Random.Range(0,obj.Length)], new Vector3(RandomNumber(),RandomNumber(),RandomNumber()),
//          Quaternion.Euler(RandomNumber(),-15f,40));
         
//         }

 
// }
 private IEnumerator call(float wait)
 {
  while(true)
  {
   Instantiate(obj[Random.Range(0,obj.Length)], new Vector3(RandomNumber(),RandomNumber(),RandomNumber()),
         Quaternion.Euler(RandomNumber(),-15f,40));
  //   Create();
  Debug.Log("hi ahmed");
 yield return new WaitForSeconds(wait);     
  }
  
 }


private int RandomNumber()
 {
return Random.Range(0,10);
 }    

   

}
     



 // если они не связаны (           векторы                                  )то он не будет работать
       //  GameObject.Instantiate(obj,new Vector3(0,0,0), Quaternion.Euler(-59.489f,0f,-55.01f));
       
    //    book.GetComponent<Transform>().position = new Vector3(-3,1.480775f,18.46f);



