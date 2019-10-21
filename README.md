# SOLID PRINCEPLES

by Uncle BOB!


# Single Responsibility Principle
  Mean: It states that each software module should have one and only one responsibility or reason to change. We should increase cohesion, and decrease coupling.
  
  Cohesion: Degree of focusing to one thing within module.
  Coupling: Degree of connection between modules.
```
public class Person{

    pushTheSofa();
    pullTheSofa();
    closeTheDoor();
    openTheDoor();
    closeTheLights();
    openTheLights();
    openTV();
    closeTV();
    

}
```
In the above there are 8 methods which are about 4 different objects. According to the SRP, if we want to change anything in this class, we have 4 reasons. Because of sofa, because of door, because of lights and because of TV.
```
public class Sofa{

  pullTheSofa(); 
  pushTheSofa();
  
}

public class Door{

  closeTheDoor();
  openTheDoor();
  
}
public class Lights{

  closeTheLights();
  openTheLights();
  
}
public class Tv{

  openTV();
  closeTV();
  
}
public class Person{
  
    Sofa.pushTheSofa();
    Sofa.pullTheSofa();
    Door.closeTheDoor();
    Door.openTheDoor();
    Lights.closeTheLights();
    Lights.openTheLights();
    Tv.openTV();
    Tv.closeTV();
  
}
```

Why I can't increase the cohesion anymore in the first 4 classes?
  
  In my opinion(it can be true or false), imagine a method like :
  
  ```
  public class Sofa{
  
    operation(String state){
    
        if(state=="pull"){
        
            //pull the sofa
        }
        else if(state=="push"){
        
            //push the sofa
        }
        else{
            //do nothing
        }
    
    
    }
  
  
  }
  ```
  **So, pullTheSofa and pushTheSofa methods are the focused way of operation method.
  
  ## Open Close Principle
  
  Modules, functions, entities are open for extension but closed for modification.
  
  Why?
  As I observed from the internet, if the project code does not obey this rule, there could be problems in the future.
  ```
    - Bugs
    - nonworking features
    - errors
    - hard to fix
    - hard to add new features(after 2 or 3 new features)
    - violation of SRP (your functions or modules or classes won't be focused to one responsibility)
    - hard to read
    
 
  Please open this page and look at the salary example: https://code-maze.com/open-closed-principle/
  
  After violated OCP principle, he fixed that issue by using inheritance. How?
  
  He created BaseSalaryCalculator that includes calculateSalary abstract function.
  
  Then he separated responsibilities as JuniorSalaryCalculator and SeniorSalaryCalcutor.
  
  Those classes inherit the method calculateSalary and implement it.
  
  So, when customer wants new features about salary the code can be extendable easily without modifiying old code!
  
  Also code is more focused now!
  
  ```
  
  ## Liskov Substitution Principle
  
  According to my research, if a class is child, it should react at least its parent. It means that inherited methods should work.
  
  So, this means that upper classes and lower classes can be used interchangeably. Otherwise, it violates LSP!
  
  ```
  abstract class phone
  {
  
    call();
    takePicture();
  
  }
  
  class modelX EXTENDS phone {
  
    call(){
      
      print "modelX calling..."
    
    }
    takePicture(){
    
      print "modelX is taking a picture"
    }
  
  }
  
  class model1990 EXTENDS phone {
  
    call(){
    
      print "model1990 calling..."
      
    }
    takePicture{
    
      return "False"
    
    }
  }
  
  ```
  Example in the above violates LSP. Because model1990 does not takePicture but it inherits that function!
  
  Also, there will be future consequences of this situation.
  
  When you are using phone objects and its functions you should control the model1990. It means this violated both OCP and SRP.
  
  Because there will be modification and multiple responsibilities.
  
  How can we solve this situation?
  
  We can create new interfaces for both functions, ITakePicture and ICall.
  
  modelX will implement both and model1999 will implement just ICall.
  
  By this way we achieved separation of objects.
  
  ```
  List<ICall> allPhones;
  List<ITakePicture> newPhones;
  .
  .
  .
  ```
  
  
  
  

