# typescript_basics
1. What is type script?
  - **Type script is runtime js with comiple time type checker**
  - **Superset of JS** - we can copy a js file into a ts file and run without error - but expect some legitimate error
  - **Static type checker**
  - JS + type checking rules
    - For JS 10/[] is ok but in ts, it is not as denominator is array which is not a valid type for division.
  - Foundational promise of type script is *"Keep same runtime behaviour as JS"*
  - It earases all types before producing compiled code. Hnce *No ts runtime libs* are there
2. Type inference:
  - Derive the type based on the value assigned.
  - Eg: let name = "Asha"; //- here name has type *string*
3. Defining types:
  - Use Type (from ts. Not recommended over interface)
  - Use *interface* - part of TS, not JS. **Most recommended**. Gets erased after compilation
  - Use *class* - part of JS itself. Not recommended if only purpose is type checking. Th reason is, the js file become bulky just because of type check as classes are not erased while transpiling the ts code.
  - Eg: **Define types using interface**
  ```
  interface User{ 
      name: string;
      id: number;
   }   
  ```
  valid:
  ```
  const user: User = {
      name: "Asha";
      id: 1;
    }
  ```
  invalid:
  ```
  const user: User = {
      username: "Asha"; //- type error comes as username is not a defined attribute in User interface.
      id: 1;
    }
  ```
  - How to use class equivalent to an interface
  ```
  interface User{ 
      name: string;
      id: number;
   }  
   
   class TestUser{ 
      name: string;
      id: number;
      
      constructor(name: string, id: number){
        this.name = name;
        this.id = id;
      }
   } 
  ```
  Use it as
  `const user: User = new TestUser("Asha", 1);`
  
4. Type with function:
    `function f1(): User{} //- returns type User`
    `function f2(user: User){} //- parameter type User`
5. JS Primitives:
    - number
    - null
    - boolean
    - bigint
    - symbol
    - string
    - undefined
6. TS primitives:
    - JS Primitives (all 7 above) + 4 below
    - any (- allow anything)
    - void (a function that returns undefined or no return value)
    - unknown (a type should be definied by someone using this type )
    - never (type not possible to happen ever)
7. **Defining types using <u>type</u>**  
    2 ways
    - use union
      * type user = "Admin" | "Normal" | "Special" //-inference to String. But possible only 3 values
      * type approved = true | false //- inference to boolean. Possible only true or false
    - use generics
      * type 
  
