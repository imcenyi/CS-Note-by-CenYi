==实际上虚函数就类似于初省值==

### ==抽象函数只能定义在抽象类中，并且不能在基类中写入方法体，只能写在子类实现==
[[抽象方法的方法体只能在子类中实现，而不能写在基类中]]
抽象方法和虚函数都是面向对象编程中的重要概念，它们都可以在基类中声明，然后在派生类中进行实现。它们的主要区别在于：

1. 抽象方法必须在派生类中进行实现，而虚函数可以选择在派生类中进行重写。
2. 抽象方法没有实现，只有方法签名，而虚函数有默认的实现==（必须）==，可以在基类中提供。
3. 抽象方法只能在抽象类中声明，而虚函数可以在普通的类中声明。

下面是一个示例，演示了如何在抽象类中声明抽象方法和在普通类中声明虚函数：

```C#
abstract class Shape

{

    public abstract double GetArea();//这里的方法体必须是空

}

class Rectangle : Shape

{

    public double Width { get; set; }

    public double Height { get; set; }

    public override double GetArea()//子类写入方法体实现

    {

        return Width * Height;

    }

}
class Circle : Shape

{

    public double Radius { get; set; }

    public override double GetArea(）

    {

        return Math.PI * Radius * Radius;

    }

}

class Square : Shape

{

    public double Side { get; set; }

    public override double GetArea()

    {

        return Side * Side;

    }

}

class Triangle : Shape

{

    public double Base { get; set; }

    public double Height { get; set; }

    public override double GetArea()

    {

        return 0.5 * Base * Height;

    }

}

// 使用示例

Shape shape1 = new Rectangle { Width = 10, Height = 20 };

Shape shape2 = new Circle { Radius = 5 };

Shape shape3 = new Square { Side = 10 };

Shape shape4 = new Triangle { Base = 10, Height = 5 };

Console.WriteLine(shape1.GetArea()); // 输出：200

Console.WriteLine(shape2.GetArea()); // 输出：78.53981633974483

Console.WriteLine(shape3.GetArea()); // 输出：100

Console.WriteLine(shape4.GetArea()); // 输出：25
```

在这个示例中，我们定义了一个抽象类`Shape`和四个子类`Rectangle`、`Circle`、`Square`和`Triangle`，它们都重写了`GetArea`方法。`GetArea`方法是一个抽象方法，必须在子类中实现。在使用示例中，我们创建了四个不同的形状对象，并分别调用它们的`GetArea`方法，输出了它们的面积。

`abstract`和`virtual`都是C#中用于实现多态的关键字，它们的主要区别在于：

1. `abstract`用于声明抽象方法，它必须在派生类中进行实现，而`virtual`用于声明虚方法，它可以在派生类中进行重写，但不是必须的。
2. `abstract`方法没有实现，只有方法签名，而`virtual`方法有默认的实现，可以在基类中提供。
3. `abstract`方法只能在抽象类中声明，而`virtual`方法可以在普通的类中声明。
