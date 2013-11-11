---
title: 3D 物件的自然旋轉
layout: post
tags: math unity3d 
---
 
{% highlight csharp linenos %}

using UnityEngine;
using System.Collections;

public class Rotator : MonoBehaviour {
    
    private Vector3 lastMousePosition = Vector3.zero;
    private bool mousePressed;
    private Vector3 rotation = Vector3.zero;
    private GameObject target = null;
    
    public void Start() {
        target = GameObject.CreatePrimitive(PrimitiveType.Cube);
    }
    
    public void Update () {
        if(Input.GetMouseButtonDown(0)) {
            mousePressed = true;
        } else if(Input.GetMouseButtonUp(0)) {
            mousePressed = false;
            lastMousePosition = Vector3.zero;
        }
        if(mousePressed) {
            Vector3 newPos = Input.mousePosition;
            if(lastMousePosition != Vector3.zero) {
                Rotate(newPos - lastMousePosition);
            }
            lastMousePosition = newPos;
        }
    }
    
    private void Rotate(Vector3 diff) {
        rotation += diff;
        target.transform.rotation = 
                Quaternion.Euler(rotation.y, -rotation.x, rotation.z);
    }
}

{% endhighlight %}
