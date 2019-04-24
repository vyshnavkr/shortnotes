# SWITCH-CASE

## STEPS TO FOLLOW IN ORDER:
1. check if switch, {}, case, : and ; are present <br>
2. check if the switch expression follows its rules <br> <br>
3. check if the case constant follows its rules <br>

## Switch RULES:
1. Switch expression must be:  <br>
	- char/byte/short/int  (all these will be implicitly converted to int inside switch expression) 
				(or 'their' Wrappers, which will be implicitly unboxed and then converted to int)
	- enum/String/Wrappers 
2. for enum ---> switch(enumClassName.enumValue)

## Case RULES:
1. Note: switch expression and case constant must be of same type, between 'implicitly converted int - String - enum'  <br>
(ie, no problem for char, byte, short or int types)  <br>
2. Case constant must be a compile time constant! You can use only a 'constant'  <br>
(eg: 5,'c', "vyshnav") or 'final variable that is assigned a literal value upon declaration' (final int i = 5).  <br>
3. It's also illegal to have more than one case label using the same value.  <br>
(eg: i=5 and j=5,  4 and 4,  i=6 and 6)  <br>
Note:  <br>
	- case: 'A'; case 65;
This produces compiler error since both are same for compiler  <br>
4. for enum ---> case enumValue : ....	(not -> case enumClassName.enumValue : ....)

## WORKING:
Best explanation ever!!: Enters at matching Case. If no matching case in entire Switch block, then enters at default(if present). Then falls through until break or last case end.

## NOTE:  
1. Case blocks may/may not use paranthesis.  <br>
2. Multiple lines of code are possible in case blocks without paranthesis  <br>
3. Look at pg 375 question at top: switch expressionil byte int-ilek convert ayalum,  <br>
compilerin aryam "switchil ullad serikum oru byte aan. case-l anenkil oru 128-um ind.  <br>
byte-l orikalum adu kollilla. So njn error adikum"
