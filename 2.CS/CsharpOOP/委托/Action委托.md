## Action的委托不能有返回值
```C#
using System.Collections;

using System.Collections.Generic;

using UnityEngine;

using System;

  

//Action是一个委托，它是没有返回值的泛型委托，它可以用来替代没有参数和返回值的委托

public class Delegate_ex : MonoBehaviour

{

    public delegate void Mydelegate1(int a,int b);

    public delegate int Mydelegate2();

    public delegate void Mydelegate3<T>(T a);

    // Start is called before the first frame update

    void Start()

    {

        Mydelegate1 showAdd = Add;

        showAdd(1,2);

        Action showAdd2 = Subtract;

        showAdd2();

        Action<int,int> showAdd3 = Add;

        showAdd3(1,2);

        Mydelegate2 Showten = ten;

        int a=Showten();

        Debug.Log(a);

        Mydelegate3<string>show3=Show3;

        show3("Show3");

        Action<string> show4 = Show3;

        show4("Hello World");

        Action show5 = Show4;//Action是一个委托，它是没有返回值的泛型委托，它可以用来替代没有参数和返回值的委托

        Mydelegate2 show6 = Show4;

        int b=show6();

        Debug.Log(b);

    }

    void Update()

    {

    }

    public void Add(int a,int b)

    {

        Debug.Log(a+b);

    }

    public void Subtract()

    {

        Debug.Log("Subtract");

    }

    public int ten()

    {

        return 10;

    }

    public void Show3(string a)

    {

        Debug.Log(a);

    }

    public int Show4()（这个语段是错误的）//Action委托不可以用这个函数，因为Action委托是没有返回值的泛型委托，而这个函数有返回值

    {

        return 114514;

    }

}
```
## Action 是==没有返回值==的泛型委托