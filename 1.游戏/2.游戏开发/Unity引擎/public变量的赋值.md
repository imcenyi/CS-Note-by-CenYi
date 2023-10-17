如果在Unity引擎中的对象中挂在的脚本里。
有public访问修饰符。会在脚本模块下看到这个变量，并进行赋值。
这个赋值的优先级很高，会覆盖掉脚本代码之中初始化定义的赋值。
~~~C#
    public enum emAction

    {

        None=0,

        GetUp,//1

        Wash,//2

        Eat,//3

        Work,//4

    }

    public emAction mAction = emAction.Work;
    Debug.Log((int)mAction);
~~~
我们对`mAction`的初始划定义是Work，照理来说的应该在终端打印出4，但实际上。
![Pasted image 20230616154518.png](https://cenyi-picture-1317709115.cos.ap-shanghai.myqcloud.com/picture/202306230139957.png)


如果我们在脚本的选项中，选择了`mAction`的==初值==，那么这个值将覆盖脚本代码中的==初始值==（注意，只是初始值）。

上面那个举得实例中，我们在Unity选择了None 覆盖了我们初始化定义`mAction`所附的Work。所以打印出来的还是None的0。