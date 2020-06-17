# CLeanCode
chapter 1

![](https://www.aliens-sci.com/wp-content/uploads/2019/01/CleanCode.jpg)

I used this summary of some key points that I made to study the book Clean Code.<br/>
I hope it helps others.<br/>
(Note: this summary doesn't exclude the need to read the book.)<br/>

first of all , I would like to highlight a few quotes
![](https://miro.medium.com/max/1000/1*5xBL_Z1k8hIifUA3maiFlA.gif)

Strongly support!  

## Why bad code ?! <br/>
# What makes me write a bad code ?! <br/>

 * your boss does not give you time 
 * you want to finish faster to get more backlog's stories finished
 * don't have experince 
 * I will clean it later 
 
# be carful 

“Later equals never.” <br/>
Bad code can bring a company down. <br/>
“The only way to make the deadline — the only way to go fast — is to keep the code as clean as possible at all times.”

## What Is Clean Code?

* The code can be measured with either "good" or "bad" in the code review or by how many minutes it takes you to talk about it.

* A clean code should be elegant, efficient, readable, simple, without duplications, and well-written. 

* You should add value to the business with your code.

* Clean code offers quality and understanding when we open a class.

* It is necessary that your code is clean and readable for anyone to find and easily understand. Avoid wasting others' time.

## How could i write clean code ?!
 there are rules aand tips you can take it in consideration while coding 
 
# General rules

* Follow standard conventions.
* Keep it simple stupid  ( KISS ) <br/>
   Simpler is always better.<br/>
   Reduce complexity as much as possible.
* Boy scout rule " Leave the campground cleaner than you found it."
* Always find root cause. <br/>
  Always look for the root cause of a problem.
  
# Design rules

* Separate multi-threading code.
* Prevent over-configurability.
* Keep configurable data at high levels.
  Keep all constants, read-only variables and other configurable data at high level of abstraction
* Use dependency injection.
  Dependency injection separates the creation of a client's dependencies from the client's behavior, which allows program designs to be loosely coupled  and to follow the dependency inversion and single responsibility principles. It directly contrasts with the service locator pattern, which allows clients to know about the system they use to find dependencies.
* Follow Law of Demeter.
 A class should know only its direct dependencies.
* Prefer polymorphism to if/else or switch/case.
```swift
// switch
class Bird {
  // ...
  func getSpeed()-> Double {
    switch (type) {
      case EUROPEAN:
        return getBaseSpeed()
      case AFRICAN:
        return getBaseSpeed() - getLoadFactor() * numberOfCoconuts
      case NORWEGIAN_BLUE:
        return getBaseSpeed()
    default:
        return 0.0
    }
  }
}

//  polymorphism 
class Bird {
    func getSpeed() -> Double {
        return 0.0
    }
}
class European : Bird {
    override func getSpeed()-> Double{
        return getBaseSpeed()
    }
    func getBaseSpeed()-> Double{
        return 8
    }
}
class African : Bird {
    override func getSpeed() -> Double {
        return getBaseSpeed() - getLoadFactor() * numberOfCoconuts;
    }
}
class NorwegianBlue : Bird {
    override func getSpeed() -> Double  {
        return getBaseSpeed()
    }
    func   getBaseSpeed() -> Double {
        return 10.8
    }
}
```

# Understandability tips
* Be consistent.
  If you do something a certain way, do all similar things in the same way.
* Use explanatory variables.
* Encapsulate boundary conditions.
  Boundary conditions are hard to keep track of. Put the processing for them in one place.
* Prefer dedicated value objects to primitive type.
* Avoid logical dependency.
  Don't write methods which works correctly depending on something else in the same class.
* Avoid negative conditionals.

