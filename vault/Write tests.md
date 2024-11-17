
[[Data Structures]]

Test-Driven Development - write tests first, then use those to drive design and development of your software
## Motivations
Why Write Tests
- To prove that our code works as we expect.
- To provide documentation on how a function or class is used.
- To provide a guard rail when refactoring code or adding new features.

Why Test-Driven Development
- Clearer abstractions because you start development knowing how the function should look like
- Progress easier to communicate with percent of tests passed, vs developing small functions continuously without knowing how many small functions you need
- Documentation (via how functions should be used based on what's written on the test) is done first and is not an afterthought
- Easier to identify minimum working code vs improvements that can be backlogged in the meantime

## Process
1. (if unknown) [Write Spike solution](https://qualitycoding.org/spike-solution/) - figure out how the code works 
1. Red — think about what you want to develop, define expected output
1. Green — think about how to make your tests pass, implement your solution
1. Refactor — think about how to improve your existing implementation

Structure of Test Code - Arrange Act Assert
- Arrange
	- How to import the module
	- What should the input look like
- Act
	- How to use it
- Assert
	- What should the output look like

Rule of thumb
- Unit tests 70%
- Integration tests 20%
- UI tests 10%

Software life, POC>MVP
- Explore
- Dev
- Test
- Deploy

## Concepts
- Feedback loop - small cases first, get feedback quickly from small parts then build out to larger tests
- Dependency management - checking software components if has the right version
- Mocking - used in unit testing. An object under test may have dependencies on other (complex) objects. To isolate the behavior of the object you want to replace the other objects by mocks that simulate the behavior of the real objects.
- Hermetic testing - test is ran without any external dependency or external service calls

Testing Principles
- Don’t just test for success, test for expected failures
- When testing, think  of all the ways someone will interact with your system. (e.g. different file sizes)
- Good practice if you can also put the “expectation” in the params e.g. test_input=2+4, expected=6
- Keep your tests idempotent (function can be applied multiple times without changing the result) and isolated (loose coupling)
- Keep your tests organized and readable

Characteristics of a Good Test (MC-FIRE)
- Maintainable - able to add, change, or remove tests with ease
- Complete - code coverage
- Fast - provides feedback quickly, complete unit tests select integration tests only
- Isolated - tests run without impacting other tests in suite e.g. clean up persisting data
- Reliable - (idempotent) provides consistent feedback, regardless of changes that may occur outside the scope of a given test, (to avoid: run code without changing anything, then failed tests are different)
- Expressive - easy to read documentation

Testing in Practice
- Identify scope of tests - unit/integration, “Write tests, not too many, mostly integration”
- Measure test coverage - what percentage of your business logic was covered by your tests? Percentage is measured by Lines of Code (LOC)

Scopes in testing
- Unit testing - testing modular pieces of the code
- Integration testing - testing multiple units working together, test interfaces only like [this](https://martinfowler.com/articles/microservice-testing/#testing-progress-3)
- Functional testing - testing multiple pieces to perform one function
- Regression testing - after a change does the original code work, tests written to ensure that a bug won’t happen again
- User Acceptance Test - automated way to check business requirements


## Resources
TDD by Kent Beck [Amazon](https://www.amazon.com/Test-Driven-Development-Kent-Beck/dp/0321146530)
[[Build Frontend UI]] testing https://www.browserstack.com/guide/front-end-testing
[Robot testing framework](https://github.com/robotology/robot-testing-framework)
