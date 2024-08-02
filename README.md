using System.Collections;
using System.Collections.Generic;
using TreeEditor;
using UnityEngine;

public class VESHON : MonoBehaviour
{
public Transform body;
public float Sensitiviti = 0f;
private float limitation = 0f;

    void Start()
    {
     Cursor.lockState = CursorLockMode.Locked;   
    }

    void Update()
    {
      float mouseX = Input.GetAxis("Mouse X") * Sensitiviti * Time.deltaTime;
      float mouseY = Input.GetAxis("Mouse Y") * Sensitiviti * Time.deltaTime;
      
      limitation -= mouseY;
      limitation = Mathf.Clamp(limitation,-90,90);
      transform.localRotation = Quaternion.Euler(limitation,0,0);
      body.Rotate(Vector3.up,+mouseX);
    }

}