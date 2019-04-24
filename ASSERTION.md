# ASSERTION:


## Why Assertions?
 - used for testing
 - alternative for if-else, runtime exceptions etc.. <br>
   advantage: no performance issue unlike the others, though assertions will be present in the code always once written, but when disabled for deploying code it will be ignored by JVM as if it weren't there.

## When/When-Not to use Assertion?
 - use IllegalArgumentException to validate public method parameters, don't use assertions
 - use assertion to validate private method parameters
   
## Basics:
 1. syntax:
 ```
  assert expression1;
```
```
  assert expression1 : expression2; 
```  
  Expression1 is a boolean. <br>
  Expression2 is an expression that has a value (primitive/String/enum/even CONSTRUCTOR too, 
  remember no S.O.P/variable declaration). (It cannot be an invocation of a method that is declared void) <br>
  Brackets are not compulsory for expression <br>
 2. error message: AssertionError

## How to use Assertion (Enabling and Disabling):
0. assertions are inactive unless specifically "turned on" (enabled),
1. ea/da (or enableassertions/disableassertions): java -ea com.geeksanonymous.TestClass
2. enabling/disabling with: (no arguments-all classes)/class/package
3. mixing ea and dsa
4. asa/dsa -> for system classes

## Appropriate-Unappropriate usages of assertions:
Dont: 
- assertion using public method's argument
- side-effect causing things 

Do:   
- assertion using private method's argument
- case/default of switch-case 

