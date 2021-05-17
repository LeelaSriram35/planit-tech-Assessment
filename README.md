# planit-tech-Assessment
This report contains Planit technical assessment implemented using Selenium with TestNG framework



selenium-testng-framework
---
@Author - Leela Sriram
---
A sample framework based on Page Object Model, Selenium, TestNG using Java.

This framework is based in **Page Object Model (POM).**

The framework uses:

1. Java
2. Selenium
3. TestNG
4. ExtentReport
5. Log4j
6. Maven 

3.Add the test class in testng.xml file under the folder `src/test/resources/suites/`

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd">
<suite name="Suite">
	<listeners></listeners>
	<test thread-count="5" name="Test">
		<classes>			
			<class name="planit.tests.ContactTest"></class>
			<class name="planit.tests.SubmissionTest"></class>
		</classes>
	</test> <!-- Test -->
</suite> <!-- Suite -->

```
4.Execute the test cases by maven command `mvn clean test`
5. the same maven configs are extendable to run using Command Line Interface to support CI/CD
6. The tests should target a browser of your choice (e.g. Chrome, Firefox) - This can be achieved by 2 ways; 
	1. Can be defined in testData sheet on what browser are we prefering to execute
	2. we can define in TestNG.xml under suite --> ex: Browser="Chrome".

---

Reporting
---
The framework gives report in two ways,

1. Log - In file `logfile.log`.
2. A html report - Which is generated using extent reports, under the folder `ExtentReports`.
---

Key Points:
---

1. The class `WebDriverContext` is responsible for maintaining the same WebDriver instance throughout the test. So whenever you require a webdriver instance which has been using for current test (In current thread) always call `WebDriverContext.getDriver()`.
2. Always use `PageinstancesFactory.getInstance(type)` to get the instance of particular Page Object. (Of course you can use `new` but it's better use a single approach across the framework.

---





