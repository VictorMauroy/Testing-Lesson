# Lesson on ***Development code testing***

**TABLE OF CONTENTS**
* [**Unit test**](#unit-test)
    - [Definition](#definition)
    - [Example](#example-in-c)

Vocabulary:
- regression
- refactorisation
- dette technique
- coverage
- branch coverage
- mock
- stub
- entropy
- test doubles
- test d'intégration
- test test end to end (E2E)

Note: <br>
Some texts and examples are provided by chatGPT. 

## ***Unit test***
### **Definition**
Unit testing is a testing approach that involves **testing individual units of code**, typically **at the function or method level**, in isolation from the rest of the system. It aims to validate the correctness of individual units and **verify that they produce the expected output for a given input**.

### **Example in C#**

The above example uses **NUnit framework**.
```csharp
using NUnit.Framework;

public class Calculator
{
    public int Add(int a, int b)
    {
        return a + b;
    }
}

[TestFixture]
public class CalculatorTests
{
    [Test]
    public void Add_ReturnsCorrectSum()
    {
        // Arrange
        Calculator calculator = new Calculator();

        // Act
        int result = calculator.Add(2, 3);

        // Assert
        Assert.AreEqual(5, result);
    }
}
```
***Explaination:*** <br>
The test method `Add_ReturnsCorrectSum` uses the `[Test]` attribute from the NUnit framework to mark it as a test. Inside the test method, we create an instance of the `Calculator` class (Arrange), call the Add method with input values of 2 and 3 (Act), and then use the Assert class from the NUnit framework to verify that the result is equal to the expected sum of 5.

***How to run it:*** <br> you need to have NUnit installed and use an appropriate test runner, such as the **NUnit console runner**, the **NUnit Test Adapter for Visual Studio**, or the **dotnet test command-line interface**. These runners execute the unit tests and provide the test results.

## ***Regression***
### **Definition**
Regression testing **focuses on detecting unintended side effects or bugs caused by changes in the codebase**. When new code is added or existing code is modified, it can inadvertently introduce defects or disrupt the behavior of other components within the system.

### **Implementation**
Implementing regression tests in C# involves **creating a set of tests that specifically target the previously working functionality** of your code to ensure it remains intact after introducing changes.

***Steps:***
1) **Identify an area of regression**. Which critical functionalities could be affected by recent changes and be subject to a regression.
2) **Create a test suite** to organize your regression test suite or test class into a separate area from other tests. 
3) **Replicate and update previous test cases** and add some to **target the area that could be affected by changes**.
4) **Execute the regression test suite.** Automate regression testing could be a good idea. In C#, you can use NUnit, xUnit or MSTest for that purpose.
5) **Update your test suite whenever new changes are made** to keep it up to date and efficient.

***Note:*** Remember that regression testing should be an ongoing process, performed as part of your software development lifecycle. By regularly executing regression tests, you can detect and address regressions early, ensuring the stability and reliability of your codebase.