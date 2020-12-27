# Utimate Class(Design Class)

## 

## Basic Concepts

Class: a blueprint for a data type, scheme

Object: a specific realization of any class, instance

```java
public class Employee {
    // field
    static double bonusRate = 0.1;
    
    final String name;
    final String id;
    int age;
    int salary;
    int level;
    
    Employee(String name, int age, String id, int level) {
        this.name = name;
        this.age = age;
        this.id = id;
        this.level = level;
    }
    
    void printInfo() {
        System.out.printIn("Name:" + name + "; Age:" + age + "; ID:" + id);
    }
    
    void setAge(int age) {
        this.age = age;
    }
    
    public int calculateSalary(double performanceScore) {
    }
    
    public static void main(String[] args) {
        Employee e1 = new Employee("shifu Lv", 29, "111-11-1111", 2);
        e1.printInfo();
        Employee e2 = new Employee("shifu Li", 30, "222-22-2222", 3);
        e2.printInfo();
        
        System.out.printIn("Bonus rate:" + Employ.bonusRate);
    }
}
```



## Access Levels

|  Modifier   | Class | Package | Subclass | World |
| :---------: | :---: | :-----: | :------: | :---: |
|   public    |   Y   |    Y    |    Y     |   Y   |
|  protected  |   Y   |    Y    |    Y     |   N   |
| no modifier |   Y   |    Y    |    N     |   N   |
|   private   |   Y   |    N    |    N     |   N   |



### How to select approriate labels?

1.  API: public
2.  Internal implementation: private
3.  Class inheritance: do we need to use protected for methods/attributes
    1.  Protected methods: sometimes useful when we want to override an implementation in subclasses
    2.  Protected attributesL be careful, try to use private first
4.  "default" in java (package-private): declare a class as public only when we define public API in it, otherwise package-private is good enough



不能直接instantiate **Interface** and **abstract class**

```java
Employee e = new Employee(); Wrong!!
    
public class Manager extends Employee {
    ...
}
Employee e2 = new Manager(); correct!!
```



### In java, for your base class, Interface v.s. Abstract Class v.s. Concrete Class?

1.  An abstract class provides a common base class implementation to derived classes.

    Use abstract class (or even concrete class) for base class **if the derived classes share common implementation**

    Example:
    Base class: Car
    Derived class: ElectricCar, GasCar



2.  Interface helps you (or enforces you) to focus on the API signature definition

    Example:

    interface Collection: add(E), size(), contains(Object)...

    Collection's subclasses may share No common implementation at all

3.  Multiple inheritance: implement multiple interfaces

    Example: 

    ArrayList implements:

    Serializable, Cloneable, Iterable<E>, Collection<E>, List<E>, RandomAccess

4.  The relationship between the interface itself and the class implementing the interface is not necessarily strong (capability)

    Example:

    class House implements AirConditioning

    class Car implements AirConditioning

    ArrayList implements Seriablizable

## Polymorphism and Overriding

Ploymorphism (多态): A call to a member function will cause a different function to be executed depending on the type of object that invokes the function. (subtype polymorphism)

```java
List<Integer> myList = new LinkedList<>();
myList.add(...); // O(1)
List<Integer> myList = new ArrayList<>();
myList.add(...); // amortized O(1)
```



Override: a subclass or child class to provide a specific implementation of a method that is already provided by one of its superclasses or parent classes



## Design a Parking Lot

**Step**

1.**Understand/Analyze** the **functionality** and its **Use case**

Describle the parking lot building? Vehicle monitoring? What kind of parking lot?





simulation 

use case & functionality  -> input, output

框架

complete code