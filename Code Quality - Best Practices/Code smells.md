# Code smells

`Code smells` are the scenario where the the code is poorly written, not necessarily to produce wrong output or buggy result, rather the code may introduce complexities in managing, extending.

Over time, code smells can lead to code that is harder to maintain, scale, or debug, which increases the technical debt of a project. Identifying and refactoring code smells is key to maintaining long-term code quality.

**Types of code smells**:

1. **Duplicated Code**  
   Same or similar code exists in multiple places, making it harder to maintain and update consistently.

2. **Long Method/Function**  
   A method or function is too long and does too many things, making it difficult to understand and maintain.

3. **Large Class**  
   A class that has too many responsibilities, violating the Single Responsibility Principle (SRP) and making the class difficult to manage.

4. **Long Parameter List**
   A function or method takes too many parameters, It can lead to confusion, increased chances of passing incorrect values, and it violates the "Law of Demeter" (don't talk to strangers).

5. **God Object**
   A class or object that knows too much or does too much in the system.

6. **Shotgun Surgery**
   A small change in the code requires changes in many different places in the system. [Link](https://refactoring.guru/smells/shotgun-surgery)

