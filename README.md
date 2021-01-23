# **OOPS-Interview-Questions**

# **_Q. What is use of 'this' keyword?_**

- this is a reference variable which stores the reference of the method-calling-object.
- Every class contains only one "this" keyword irrespective of number of objects.
  (incomplete)

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

# **_Q. What will be the output of the following code?_**

```java
class Demo {
    int val;
    Demo(){
        val = 10;
    }
    void fun(){
        int val = 5;
        System.out.println("Val = "+val);
    }
}

class DemoTest {
    public static void main(String args){
        Demo obj = new Demo();
        obj.fun();
    }
}
```

Output: `Val = 5`

This is the example of Instance Variable Hiding. Since, the name of local variable inside function fun, is same as the name of an instance variable (val), It means local variable will override instance member variable.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

# **_Q. What is meant by explicit use of "this" keyword?_**

Suppose In the scenario where we have the same name of local variable and instance variable, If we wanted to print the value of instance variable, we would have to prefix "this" and the dot operator before member name. This is called the explicit use of "this" keyword
Example:

```java
class Demo {
    int val;
    Demo(){
        val = 10;
    }
    void fun(){
        int val = 5;
        System.out.println("Value of local variable Val = " + val);
        System.out.println("Value of Instance variable Val = " + this.val); //Notice here
    }
}

class DemoTest {
    public static void main(String args){
        Demo obj = new Demo();
        obj.fun();
    }
}
```

##### Output will be

```
Value of local variable Val = 5
Value of Instance variable Val = 10
```

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

# **_Q. What will be the Output?_**

```java
class Vehicle {
    void drive(){
        System.out.println("Vehicle is Driving");
    }
}

class Car extends Vehicle {
    void drive(){
        System.out.println("Car is driving");
    }
}

class Tester{
    public static void main(String args){
        Vehicle v1 = new Vehicle();
        v1.drive();

        Car c1 = new Car();
        c1.drive();

        Vehicle v2 = new Car();
        v2.drive();
    }
}
```

Output will be:

```
Vehicle is driving
Car is driving
Car is driving
```

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

# **_Q. What will be the Output?_**

```java
class Vehicle {
    void drive(){
        System.out.println("Vehicle is Driving");
    }
}

class Car extends Vehicle {
    void drive(){
        System.out.println("Car is driving");
    }
}

class Tester{
    public static void main(String args){

        Car c2 = new Vehicle();
        c2.drive();
    }
}
```

Output will be:

```
Error Because we are storing an object of super class in the object reference of subclass. (Upcasting)
```
