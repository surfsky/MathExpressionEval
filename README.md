# 1. About MathEval.NET

MathEval.NET is a mathematical expressions evaluator library written in C#. Allows to evaluate mathematical, boolean, string and datetime expressions
Code is written in pure C#, run on the fly. We don't use any third party libraries or packages.


This respository forks from: https://github.com/matheval/expression-evaluator-c-sharp
And make many changes:

1. Reconstruct solution, eg. refolder, csharp-like renaming, simply, and more readable.
2. Support more DateTime functions, eg: date, now, year, weekday, adddays...
3. Support more operator, eg: ! !=
4. Support more text function,  eg: like 
3. Support regist custom function.

[TOC]


# 2. Installation

Using Package Manager

```bash
PM> Install-Package MathEval.NET -Version 4.5.0.0
```

# 3. Supported operators, contants, functions

## 3.1 Supported Operators

| Operator | Description                                                              
|----------|----------------------------------------------------------------------
| +        | Additive  / Unary plus / Concatenate string / Datetime addition
| -        | Subtraction  / Unary minus / Datetime subtraction
| *        | Multiplication , can be omitted in front of an open bracket
| /        | Division 
| %        | Remainder  (Modulo)
| ^        | Power 
| &        | Concatenate string
| !        | Not operator for boolean
| >        | Greater
| >=       | Greater equal
| <        | Less
| <=       | Less equal
| <>       | Not equal
| !=       | Not equal


## 3.2 Supported Constants

| Constant | Description                                                              
|----------|---------------------------------------------------------
| E        | The value of _e_
| PI       | The value of _PI_
| TRUE     | The boolean true value
| FALSE    | The boolean false value
| NULL     | The null value



## 3.3 Supported conditional statements


| Conditional statement                                             | Description                                              
|-------------------------------------------------------------------|----------------------------------------------------------
| IF(condition, valueIfTrue, valueIfFalse)                          | Example: `IF(2>1,"Pass","Fail")`
| SWITCH(expression, val1, result1, [val2,result2], …, [default])  | Example: `SWITCH(3+2,5,"Apple",7,"Mango",3,"Good","N/A")`



## 3.4 Supported logical functions


| Function                         | Description                                              
|----------------------------------|----------------------------------------------------------
| AND(logical1, [logical2], …)    | Determine if all conditions are TRUE
| OR(logical1, [logical2], …)     | Determine if any conditions in a test are TRUE
| NOT(_logical_)                   | To confirm one value is not equal to another
| XOR(logical1, [logical2], …)    | Exclusive OR function


## 3.5 Supported math functions

| Function                         | Description                                              
|----------------------------------|----------------------------------------------------------
| MOD(number, divisor)             |  Get remainder of two given numbers after division operator.
| ROUND(number, num_digits)        |  Returns the rounded approximation of given number using half-even rounding mode  ( you can change to another rounding mode)
| FLOOR(number, significance)      |  Rounds a given number towards zero to the nearest multiple of a specified significance
| CEILING(number, significance)    |  Rounds a given number away from zero, to the nearest multiple of a given number
| POWER(number, power)             |  Returns the result of a number raised to a given power
| RAND()                           |  Produces a random number between 0 and 1
| SQRT(number)                     |  Returns the correctly rounded positive square root of given number
| LN(number)                       |  Returns the natural logarithm (base _e_) of given number
| LOG10(number)                    |  Returns the logarithm (base 10) of given number
| EXP(number)                      |  Returns e raised to the power of given number
| ABS(number)                      |  Returns the absolute value of given number
| FACT(number)                     |  Returns the factorial of a given number
| INT(number)                      |  Returns the Integer value of given number


## 3.6 Supported math trigonomatric functions

| Function                         | Description                                              
|----------------------------------|----------------------------------------------------------
| PI()                             |  Return value of Pi
| SIN(number)                      |  Returns the trigonometric sine of the angle given in radians
| SINH(number)                     |  Returns the hyperbolic sine of a number
| ASIN(number)                     |  Returns the arc sine of an angle, in the range of -pi/2 through pi/2
| COS(number)                      |  Returns the trigonometric cos of the angle given in radians
| COSH(number)                     |  Returns the hyperbolic cos of a number
| ACOS(number)                     |  Returns the arc cosine of an angle, in the range of 0.0 through pi
| TAN(number)                      |  Returns the tangent of the angle given in radians
| TANH(number)                     |  Returns the hyperbolic tangent of a number
| ATAN(number)                     |  Returns the arc tangent of an angle given in radians
| ATAN2(x_number, y_number)        |  Returns the arctangent from x- and y-coordinates
| COT(number)                      |  Returns the cotangent of an angle given in radians
| COTH(number)                     |  Returns the hyperbolic cotangent of a number
| SEC(number)                      |  Returns the secant of an angle given in radians
| CSC(number)                      |  Returns the cosecant of an angle given in radians
| RADIANS(degrees)                 |  Convert degrees to radians
| DEGREES(radians)                 |  Convert radians to degrees


## 3.7 Supported math statistic functions

| Function                         | Description                                              
|----------------------------------|----------------------------------------------------------
| COUNT(number1, [number2],…)      |  Return count of numbers supplied
| SUM(number1, [number2],…)        |  Return sum of numbers supplied
| AVERAGE(number1, [number2],…)    |  Return average of numbers supplied
| MIN(number1, [number2],…)        |  Return the smallest value from the numbers supplied
| MAX(number1, [number2],…)        |  Return the biggest value from the numbers supplied


## 3.8 Supported text functions

| Function                                             | Description                                              
|------------------------------------------------------|----------------------------------------------------------
| LEFT(text, num_chars)                                | Extracts a given number of characters from the left side of a supplied text string
| RIGHT(text, num_chars)                               | Extracts a given number of characters from the right side of a supplied text string
| MID(text, start_num, num_chars)                      | Extracts a given number of characters from the middle of a supplied text string
| REVERSE(text)                                        | Reverse a string
| LOWER(text)                                          | Converts all letters in the specified string to lowercase
| UPPER(text)                                          | Converts all letters in the specified string to uppercase
| PROPER(text)                                         | Capitalizes words given text string
| TRIM(text)                                           | Removes extra spaces from text
| TEXT(value, [format_text])                           | Convert a numeric value into a text string. You can use the TEXT function to embed formatted numbers inside text 
| REPLACE(old_text, start_num, num_chars, new_text)    | Replaces characters specified by location in a given text string with another text string
| SUBSTITUTE(text, old_text, new_text)                 | Replaces a set of characters with another
| FIND(find_text, within_text, [start_num])            | Returns the location of a substring in a string (case sensitive)
| SEARCH(find_text, within_text, [start_num])          | Returns the location of a substring in a string (case insensitive)
| CONCAT(text1, text2, text3,…)                       | Combines the text from multiple strings
| REPT(text, repeat_time)                              | Repeats characters a given number of times
|------------------------------------------------------|----------------------------------------------------------
| ISBLANK(text)                                        | Returns TRUE when a given string is null or empty, otherwise return FALSE
| ISNUMBER(text)                                       | Check if a value is a number
| LEN(text)                                            | Returns the length of a string/ text
| CHAR(ascii-code)                                     | Return character from ascii code
| CODE(char)                                           | Returns a ascii code of a character
| VALUE(text)                                          | Convert numbers stored as text to numbers
| LIKE(text, sqlpattern)                               | Returns TRUE when a given string match the sqlpattern string(support _*%). eg: like("Abcd", "_bc%")


Text() Example:  

| Function                                                                      | Description
|-------------------------------------------------------------------------------|---------------------------------------------------
| TEXT(123)                                                                     | 123
| TEXT(DATEVALUE("2021-01-23"),"dd-MM-yyyy")                                    | 23-01-2021
| TEXT(2.61,"hh:mm")                                                            | 14:38
| TEXT(2.61,"[hh]")                                                             | 62
| TEXT(2.61,"hh-mm-ss")                                                         | 14-38-24
| TEXT(DATEVALUE("2021-01-03")-DATEVALUE("2021-01-01"),"[h]")                   | 48
| TEXT(TIME(12,00,00)-TIME(10,30,10),"hh hours and mm minutes and ss seconds")  | 01 hours and 29 minutes and 50 seconds



# 3.9 Supported DateTime functions

| Function           | Description                               
|--------------------|----------------------------------------------------------
| Today()            | Today()
| Now()              | Now()
| Date(.)            | Date('2024-01-01 12:00')
| Year(.)            | Year('2024-01-01 12:00')
| Month(.)           | Month(Today())
| Day(.)             | Day(Today())
| Hour(.)            | Hour(Today())
| Minute(.)          | Minute(Today())
| Second(.)          | Second(Today())
| Weekday(.)         | Weekday(Today())
| Age(.)             | Age(Today())
| AddYears(..)       | AddYears(Today(), 1)
| AddMonths(..)      | AddMonths(Today(), 1)
| AddDays(..)        | AddDays(Today(), 1)
| AddHours(..)       | AddHours(Today(), 1)
| AddMinutes(..)     | AddMinutes(Today(), 1)
| AddSeconds(..)     | AddSeconds(Today(), 1)
| AddDate(.......)   | AddDate(Today(), 1,0,0,0,0,0)


DateTime functions examples:

```csharp
var expr = new Expression();
Assert.AreEqual(DateTime.Parse("2020-01-01"),           expr.SetFormular("Date('2020-01-01')").Eval<DateTime>());
Assert.AreEqual(DateTime.Today,                         expr.SetFormular("Today()").Eval<DateTime>());
Assert.AreEqual(DateTime.Now.Day,                       expr.SetFormular("Now()").Eval<DateTime>().Day);
//											            
Assert.AreEqual(DateTime.Today.Year,                    expr.SetFormular("Year(Today())").Eval<int>());
Assert.AreEqual(DateTime.Today.Month,                   expr.SetFormular("Month(Today())").Eval<int>());
Assert.AreEqual(DateTime.Today.Day,                     expr.SetFormular("Day(Today())").Eval<int>());
Assert.AreEqual(DateTime.Today.Hour,                    expr.SetFormular("Hour(Today())").Eval<int>());
Assert.AreEqual(DateTime.Today.Minute,                  expr.SetFormular("Minute(Today())").Eval<int>());
Assert.AreEqual(DateTime.Today.Second,                  expr.SetFormular("Second(Today())").Eval<int>());
Assert.AreEqual(0,                                      expr.SetFormular("Age(Today())").Eval<int>());
Assert.AreEqual(DateTime.Today.DayOfWeek,               expr.SetFormular("Weekday(Today())").Eval<DayOfWeek>());
Assert.AreEqual(DateTime.Today.AddYears(1),             expr.SetFormular("AddYears(Today(), 1)").Eval<DateTime>());
Assert.AreEqual(DateTime.Today.AddMonths(1),            expr.SetFormular("AddMonths(Today(), 1)").Eval<DateTime>());
Assert.AreEqual(DateTime.Today.AddDays(1),              expr.SetFormular("AddDays(Today(), 1)").Eval<DateTime>());
Assert.AreEqual(DateTime.Today.AddHours(1),             expr.SetFormular("AddHours(Today(), 1)").Eval<DateTime>());
Assert.AreEqual(DateTime.Today.AddMinutes(1),           expr.SetFormular("AddMinutes(Today(), 1)").Eval<DateTime>());
Assert.AreEqual(DateTime.Today.AddSeconds(1),           expr.SetFormular("AddSeconds(Today(), 1)").Eval<DateTime>());
Assert.AreEqual(DateTime.Today.AddYears(1),             expr.SetFormular("AddDate(Today(), 1,0,0,0,0,0)").Eval<DateTime>());
//
Assert.AreEqual(2020,                                   expr.SetFormular("Year('2020-01-01 12:00')").Eval<int>());
Assert.AreEqual(1,                                      expr.SetFormular("Month('2020-01-01 12:00')").Eval<int>());
Assert.AreEqual(1,                                      expr.SetFormular("Day('2020-01-01 12:00')").Eval<int>());
Assert.AreEqual(12,                                     expr.SetFormular("Hour('2020-01-01 12:00')").Eval<int>());
Assert.AreEqual(0,                                      expr.SetFormular("Minute('2020-01-01 12:00')").Eval<int>());
Assert.AreEqual(0,                                      expr.SetFormular("Second('2020-01-01 12:00')").Eval<int>());
Assert.AreEqual(DateTime.Now.Year-2020,                 expr.SetFormular("Age('2020-01-01 12:00')").Eval<int>());
Assert.AreEqual(DayOfWeek.Wednesday,                    expr.SetFormular("Weekday('2020-01-01 12:00')").Eval<DayOfWeek>());
Assert.AreEqual(DateTime.Parse("2021-01-01 12:00:00"),  expr.SetFormular("AddYears('2020-01-01 12:00', 1)").Eval<DateTime>());
Assert.AreEqual(DateTime.Parse("2020-02-01 12:00:00"),  expr.SetFormular("AddMonths('2020-01-01 12:00', 1)").Eval<DateTime>());
Assert.AreEqual(DateTime.Parse("2020-01-02 12:00:00"),  expr.SetFormular("AddDays('2020-01-01 12:00', 1)").Eval<DateTime>());
Assert.AreEqual(DateTime.Parse("2020-01-01 13:00:00"),  expr.SetFormular("AddHours('2020-01-01 12:00', 1)").Eval<DateTime>());
Assert.AreEqual(DateTime.Parse("2020-01-01 12:01:00"),  expr.SetFormular("AddMinutes('2020-01-01 12:00', 1)").Eval<DateTime>());
Assert.AreEqual(DateTime.Parse("2020-01-01 12:00:01"),  expr.SetFormular("AddSeconds('2020-01-01 12:00', 1)").Eval<DateTime>());
Assert.AreEqual(DateTime.Parse("2021-01-01 12:00:00"),  expr.SetFormular("AddDate('2020-01-01 12:00', 1,0,0,0,0,0)").Eval<DateTime>());

```

# 4. Custom functions

MathEval.NET support custom functions:

1. Create class to implements IFunction.
2. Regist this class to Expresson object using RegistFunction() or RegistFunctions().
3. OK, run eval().

Examples:

``` csharp
using System;
using System.Collections.Generic;
using Org.MathEval.Common.Functions;
using static Org.MathEval.Common;
public class DateFunctions : IFunction
{
    public List<FunctionDef> GetDefs()
    {
        return new List<FunctionDef> {
            new FunctionDef("now",        typeof(DateTime), 0, null),
            new FunctionDef("year",       typeof(int),      1, typeof(DateTime)),
            new FunctionDef("AddYears",   typeof(DateTime), 2, typeof(DateTime), typeof(int)),
        };
    }
    public object Execute(List<object> args, ExpressionContext dc, string funcName = "")
    {
        var name = funcName.ToLower();
        switch (name)
        {
            case "now":        return DateTime.Now;
            case "year":       return ToDateTime(args[0]).Year;
            case "addyears":   return ToDateTime(args[0]).AddYears(ToInt(args[1]));
        }
        return DateTime.Now;
    }
}

// regist and use this functions
var expression = new Expression().RegistFunction(new DateFunctions());  // regist date functions
var dt = expression.SetFormula("Now()").Eval<DateTime>();               // eval now() function
```



# 5. Usage examples

## 5.1 Basic evaluator
```cs
using System;
using org.matheval;
					
public class Program
{
	public static void Main()
	{
		var expression = new Expression("(a + b) / 2 ");
		expression.Bind("a", 3);
		expression.Bind("b",5);
		Object value = expression.Eval();
		Console.WriteLine("Result: "+value); //Result: 4
		
	}
}
```

## 5.2 Conditional statements

```cs
using System;
using org.matheval;
					
public class Program
{
	public static void Main()
	{
		Expression expression = new Expression("IF(time>8, (HOUR_SALARY*8) + (HOUR_SALARY*1.25*(time-8)), HOUR_SALARY*time)");
		//bind variable
		expression.Bind("HOUR_SALARY", 10);
		expression.Bind("time", 9);
		//eval
		Decimal salary = expression.Eval<Decimal>();	
		Console.WriteLine(salary); //return 92.5
	}
}
```

## 5.3 Validate expression
```cs
Expression expression = new Expression("SUM(1,2,3) + true");
List<String> errors = expression.GetError(); 
if(errors.Count > 0)
{
  foreach(String error in errors)
  {
  	Console.WriteLine(error);
  }
}	
```

## 5.4 Min, max, sum, avg
```cs
using System;
using org.matheval;
					
public class Program
{
	public static void Main()
	{
		Expression expr = new Expression("MIN(2,3,16)");
		int min = expr.Eval<int>(); 
		Console.WriteLine(min);// return 2 (min)
		
		expr.SetFomular("Max(2,3,16)");
		int max = expr.Eval<int>(); 
		Console.WriteLine(max);// return 16 (max)
		
		expr.SetFomular("Sum(2,3,16)");
		decimal sum = expr.Eval<decimal>(); 
		Console.WriteLine(sum);// return 21	(sum)
		
		expr.SetFomular("average(2,3,16)");
		decimal average = expr.Eval<decimal>(); 
		Console.WriteLine(average);// return 7 (average)	
	}
}
```
## 5.5 Round, floor, ceiling
```cs
using System;
using org.matheval;
					
public class Program
{
	public static void Main()
	{
		Expression expr = new Expression("ROUND(2.149, 1)");
		Object value = expr.Eval<Decimal>(); 
		Console.WriteLine("ROUND(2.149, 1) = "+value); //return 2.1
		
		expr = new Expression("FLOOR(2.149)");
		value = expr.Eval(); 
		Console.WriteLine("FLOOR(2.149) = "+value); //return 2	
		
		expr = new Expression("FLOOR(3.7,2)");
		value = expr.Eval(); 
		Console.WriteLine("FLOOR(3.7,2) = "+value);	//return 2
		
		expr = new Expression("CEILING(2.149)");
		value = expr.Eval(); 
		Console.WriteLine("CEILING(2.149) = "+value); //return 3
		
		expr = new Expression("CEILING(1.5, 0.1)");
		value = expr.Eval(); 
		Console.WriteLine("CEILING(1.5, 0.1) = "+value); //return 1.5	
	}
}
```
## 5.6 Trigonometry
```cs
using System;
using org.matheval;
					
public class Program
{
	public static void Main()
	{
		Expression expr = new Expression("tan(a)^3-((3*sin(a)-sin(3*a))/(3*cos(a)+cos(3*a)))");
		Decimal value = expr.Bind("a", Math.PI/6).Eval<Decimal>(); 
		Console.WriteLine(value); //return 0		
	}
}
```

## 5.7 Deal with string
```cs
using System;
using org.matheval;
					
public class Program
{
	public static void Main()
	{
		Expression taxExpr = new Expression("IF(LOWER(TAX_CODE)='vat',amount*10/100,IF(LOWER(TAX_CODE)='gst',amount*15/100,0))");
		taxExpr.Bind("TAX_CODE","GST");
		taxExpr.Bind("amount", 5005m);
		Decimal value = taxExpr.Eval<Decimal>();
		Console.WriteLine(value);
	}
}
```
## 5.8 Concatenate strings
```cs
using System;
using org.matheval;
					
public class Program
{
	public static void Main()
	{
		Expression expr = new Expression("CONCAT('The United States of ', 'America')");
		String value = expr.Eval<String>();	
		Console.WriteLine(value);//The United States of America	
	}
}
```

# 6.License
MIT license
