# SOLID PRINCEPLES

by Uncle BOB!


# Single Responsibility Principle
  Mean: It states that each software module should have one and only one responsibility or reason to change. We should increase cohesion, and decrease coupling.
  
  Cohesion: Degree of focusing to one thing within module.
  Coupling: Degree of connection between modules.

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

In the above there are 8 methods which are about 4 different objects. According to the SRP, if we want to change anything in this class, we have 4 reasons. Because of sofa, because of door, because of lights and because of TV.

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

Why I can't increase the cohesion anymore in the first 4 classes?
  
  In my opinion(it can be true or false), imagine a method like :
  
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
  
  *So, pullTheSofa and pushTheSofa methods are the focused way of operation method.
  
  ## Open Close Principle
  
  
  
  
  

