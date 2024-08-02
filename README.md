using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class RotatCamer : MonoBehaviour
{   public Transform tfrm;
    private float LimitationX = 0f;
    public float SensitivitiMouse = 100f;
    

    void Update()
    {
     float mouseX = Input.GetAxis("Mouse X")*SensitivitiMouse*Time.deltaTime;
     float mouseY = Input.GetAxis("Mouse Y")*SensitivitiMouse*Time.deltaTime;
     LimitationX -= mouseY;
      
     transform.localRotation= Quaternion.Euler(LimitationX,0f,0f);
     LimitationX = Mathf.Clamp(LimitationX,-90,90);
     tfrm.Rotate(Vector3.up * mouseX);
    }
}
