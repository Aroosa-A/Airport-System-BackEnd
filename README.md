Airport Challenge
=================

```
         ______
        __\____\___
=  = ==(____DFA____)
           \_____\__________________,-~~~~~~~`-.._
          /     o o o o o o o o o o o o o o o o  |\_
          `~-.__       __..----..__                  )
                `---~~\___________/------------`````
                =  ===(_________)

```
About the Project:
------------------

- Airport control system
- First challenge of Digital Futures training
- Used TDD methodology


Build With:
-------------------

### IDE
- Visual Studio Code

### Language
- JavaScript

Getting Started:
---------------

Follow these steps to run this project locally on your machine

1. Clone the repo
    
    You can copy project link from *green* button named as **Code**, link should be like this
    ```
    git clone http://github.com/your-username/Project-name.git
    ```
 
2. Install dependencies

    You can install them by writing this command in terminal or by right clicking on **Package.json** file and selecting *Install dependencies*
    ```
    npm install
    ```
3. Test

    You can run tests by opening integrated terminal in **specRunner** file and running this command in terminal
    ```
    node specRunner
    ```
    
Problem Statements
-------------------

### Problem

    ```
    Write a software to control the flow of planes at an airport. The planes can land and take off provided that the weather is sunny. Occasionally it may be stormy, in which case no planes can land or take off.
    ```
### User stories

1.
```
As an air traffic controller
So I can get passengers to a destination
I want to instruct the airport to land a plane
```
Domain Model

| Objects    |  Properties                         |     Messages                             | Output      |
|------------|-------------------------------------|------------------------------------------|-------------|
|airport     |planeObject@instanceOfPlaneClass     |addPlaneInAirport(Plane@Object)           |             |
|            |#planesInAirport[@planesObjects]     |                                          |             |
|plane       |planeID@number                       |                                          |             |
|            |                                     |                                          |             |

2.
```
As the system designer
So that the software can be used for many different airports
I would like a default airport capacity that can be overridden as appropriate
```
Domain Model

| Objects    |  Properties        |     Messages   | Output      |
|------------|--------------------|----------------|-------------|
|airport     |airportID@number    |                |             |
|            |capacity@number     |                |             |
|            |                    |                |             |

3.
```
As an air traffic controller
To ensure safety
I want to prevent landing when the airport is full
```
Domain model
| Objects    |  Properties                         |     Messages             | Output      |
|------------|-------------------------------------|--------------------------|-------------|
|airport     |capacity@number                      |landAPlan(Plane@Object)   |             |
|            |#planesInAirport[@planesObjects]     |                          |             |
|            |                                     |                          |             |


4.
```
As an air traffic controller
So I can get passengers on the way to their destination
I want to instruct the airport to let a plane take off and confirm that it is no longer in the airport
```
Domain model
| Objects    |  Properties                         |     Messages                         | Output        |
|------------|-------------------------------------|--------------------------------------|---------------|
|airport     |                                     |takeOffPlaneFromAirport(Plane@Object) |message@String |
|            |                                     |                                      |               |

5.
```
As an air traffic controller
To avoid confusion
I want to prevent asking the airport to let planes take-off which are not at the airport, or land a plane that's already landed
```
Domain Model
| Objects    |  Properties                         |     Messages                         | Output              |
|------------|-------------------------------------|--------------------------------------|---------------------|
|airport     |                                     |getPlanesInAirport()                  |Array[@PlaneObjects] |
|            |                                     |                                      |                     |
Explanation for user story five
```
 i think if traffic controller wants to prevent asking airport to land or take off plane when they already landed or taken off, traffic controller should be able to access the list of planes in airport so he can get know the planes in list cannot be landed again and planes not in list cannot be taken off
 ```

6.
```
As an air traffic controller
To ensure safety
I want to prevent takeoff when weather is stormy
```
Domain model
| Objects    |  Properties                 |     Messages                                           | Output              |
|------------|-----------------------------|--------------------------------------------------------|---------------------|
|weather     |weather@String               |takeOffPlaneFromAirport(Plane@Object)                   |                     |
|            |                             |                                                        |                     |

7.
```
As an air traffic controller
To ensure safety
I want to prevent landing when weather is stormy
```
Domain model
| Objects    |  Properties                 |     Messages                     | Output              |
|------------|-----------------------------|----------------------------------|---------------------|
|weather     |weather@String               |landAPlan(Plane@Object)           |                     |
|            |                             |                                  |                     |

8.
```
As an air traffic controller
To count planes easily
Planes that have landed must be at an airport
```
Domain model
| Objects    |  Properties                 |     Messages                     | Output              |
|------------|-----------------------------|----------------------------------|---------------------|
|Count       |#countPlanes@Number          |getCountPlanes()                  |@Number              |
|            |                             |                                  |                     |

Project Review:
------------

- Could have wrote tests independent from code files(classess)
- Next time i would like to write code which is more efficient (less line of code with more productivity)
