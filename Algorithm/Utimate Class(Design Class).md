# Utimate Class(Design Class)

## Access Levels

|  Modifier   | Class | Package | Subclass | World |
| :---------: | :---: | :-----: | :------: | :---: |
|   public    |   Y   |    Y    |    Y     |   Y   |
|  protected  |   Y   |    Y    |    Y     |   N   |
| no modifier |   Y   |    Y    |    N     |   N   |
|   private   |   Y   |    N    |    N     |   N   |

### Basic Concepts

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



simulation 

use case & functionality  -> input, output

框架

complete code