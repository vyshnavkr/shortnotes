# EXCEPTIONS:

## Exception Hierarchy Pic: 
- pg 404

## Checked Exception: 	
- include all subtypes of Exception, excluding classes
	that extend RuntimeException.
- subject to handle/declare rule (try-catch or throws)

## Unchecked Exception: 	
- Subtypes of Error or Runtime Exception are unchecked.

## try:
- Note that if an exception occurred on, say, line 3 of the
try block, the rest of the lines in the try block (4 and 5) would 
never be executed. Once control jumps try to the block, it 
never returns to complete the balance of the try block.

## finally:
- clean-up code goes inside this (like closing files, closing 
databases etc that were opened in try block)
- always invoked except for JVM shutdown -> System.exit().
Even if there is a return statement in the try block, the finally
block executes right after the return statement is encountered, 
and before the return executes!

## throws:
- If a method doesn't provide a catch clause for a particular 
exception, that method is said to be "ducking" the exception 
(or "passing the buck") using throws() declaration. 

## User-defined Custom Exception:
- You can create your own exceptions, normally by extending Exception or
one of its subtypes. Your exception will then be considered a checked exception.
- eg:
  ```
    class MyException extends Exception {		//1. extend Exception class
      public MyException (String s){		//2. param constructor, this string is obtained using getMessage() of object created
        super(s);			//3. super constructor
      }
    }
    public class Main {
      public static void main (String args[]){
        try{
          throw new MyException("bow bow");				//4. throw object of exception created
        }catch(MyException ex){
          System.out.println("Caught exception: " +  ex.getMessage());	//5. getMessage() of Exception class is printed
        }
      }
    }
  ```

## throw:
- If you throw a checked exception from a catch clause, you must also 
declare that exception! In other words, you must handle and declare, 
as opposed to handle or declare

## Rules:
- All catch blocks must be ordered from most specific to most general.
- either catch or finally is a must.
- order: try -> catch -> finally. Also no codes in between these.
- You are expected to know that Exception, Error, RuntimeException, and
Throwable types can all be thrown using the throw keyword, and can all be caught

## println(exception) vs exception.printsStackTrace() :
- println(e): -> java.lang.NullPointerException
- e.printStackTrace(): -> java.lang.NullPointerException at package.Test.main(Test.java:74)

## Unchecked Exception eg: 
- ArrayIndexOutOfBoundsException
- ClassCastException 
- IllegalArgumentException 
- NumberFormatException (sub of IllegalArgument)
- IllegalStateException 
- NullPointerException 
- AssertionError 
- ExceptionInInitializerError 
- StackOverflowError 
- NoClassDefFoundError 

## Checked Exception eg:
- Exception 
- ClassNotFoundException 
- IOException 
- FileNotFoundException (sub of IO) 
- EOFException (sub of IO) 
- InterruptedException
- ParseException 


