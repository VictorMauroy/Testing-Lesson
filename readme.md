# Lesson on ***Development code testing***

**TABLE OF CONTENTS**
* [**Unit test**](#unit-test)
    - [Definition](#definition)
    - [Example](#example-in-c)

Vocabulary:
- Unit test
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


