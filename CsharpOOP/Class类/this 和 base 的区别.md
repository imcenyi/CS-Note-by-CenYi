`this`和`base`都是C#中的关键字，它们的主要区别在于：

1. `this`关键字用于引用当前对象，可以用来访问当前对象的成员变量、成员方法和构造函数等。`this`关键字可以用于区分局部变量和成员变量、调用其他构造函数、实现链式调用等场景。
2. `base`关键字用于引用基类对象，可以用来访问基类的成员变量、成员方法和构造函数等。`base`关键字可以用于在派生类中调用基类的构造函数、访问基类中被隐藏的成员等场景。

以下是一个示例，演示了如何使用`this`和`base`关键字：
```C#
class Person

{

    public string Name { get; set; }

    public int Age { get; set; }

    public Person(string name, int age)

    {

        this.Name = name;

        this.Age = age;

    }

}

class Student : Person

{

    public string School { get; set; }

    public Student(string name, int age, string school) : base(name, age)

    {

        this.School = school;

    }

    public void Study()

    {

        Console.WriteLine("{0} is studying at {1}.", this.Name, this.School);

    }

    public void ShowInfo()

    {

        Console.WriteLine("Name: {0}, Age: {1}, School: {2}", this.Name, this.Age, this.School);

    }

}

// 使用示例

Student student = new Student("Tom", 18, "ABC School");

student.Study(); // 输出：Tom is studying at ABC School.

student.ShowInfo(); // 输出：Name: Tom, Age: 18, School: ABC School
```
在这个示例中，我们定义了一个`Person`类和一个`Student`类，`Student`类继承自`Person`类。在`Person`类中，我们定义了一个构造函数，使用`this`关键字来引用当前对象的成员变量。在`Student`类中，我们定义了一个构造函数，使用`base`关键字来调用基类的构造函数。在`Student`类中，我们还定义了两个方法`Study`和`ShowInfo`，分别使用`this`关键字和`base`关键字来访问当前对象和基类对象的成员变量。在使用示例中，我们创建了一个`Student`对象，并调用了它的`Study`和`ShowInfo`方法，输出了相应的信息。

总的来说，`this`关键字用于引用当前对象，`base`关键字用于引用基类对象。它们的应用场景不同，`this`关键字通常用于访问当前对象的成员，`base`关键字通常用于在派生类中调用基类的构造函数或访问基类中被隐藏的成员。