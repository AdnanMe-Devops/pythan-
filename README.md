The unittest.mock module is Python's built-in mocking and patching module. Used to replace objects with fake implementations during testing.

Mock objects -- or mocks -- can replace objects with fake implementations and make assertions about how mock objects are used.

Mocks are commonly used to replace objects and external resources such as files, databases, and web APIs.

Replacing functionality with mock implementations allows code to be tested independently of its dependencies.

Key Features of Mocks

Mocks are callable.
Non-callable varients exist:
NonCallableMock
NonCallableMagicMock
Mocks create attributes and methods when first accessed.
Mocks record all calls along with arguments.
Mocks include assertion methods used to ensure calls are made as expected.
Failed assertions raise an AssertionError
////
calls 
Mock objects are callable allowing them to replace callable objects with a fake implementation. Mocks accept any number of arguments and can return a value when called.
/////
call asseration 
Mocks record calls and provide different mechanisms for inspecting how calls were made.
Mock objects include methods used to make assertions about calls. Assertion methods raise an AssertionError for False assertions.
////
inspecting calls 
Mock records all calls made along with arguments. Assertion methods can make claims about how calls are made. However, they're unable to provide detailed insights into calls.
Mocks include attributes used to access more detailed call information.
The unittest.mock module includes a helper object named call used as a means of creating calls for comparison against recorded calls. Providing call the same arguments provided to a mock call makes the two calls comparable.
////
magic mock 
Mock objects don't implement magic methods by default. Magic methods are special methods used to allow objects to leverage different language features.
////
Side Effects
Mocks return values directly by setting a mock's return_value attribute. Mock objects include another mechanism which allows for more complex call behaviors referred to as side effects. Side effects are able to raise exceptions, return multiple values, and call callables.
Side effects can be set when creating a mock using the side_effect keyword argument. They can also be set after creation using the side_effect attribute.
////
Attributes
Mock objects allow attributes to be set when created using keyword arguments. Attributes can also be set after an object is created.
Mocks create attributes dynamically when accessed if they don't already exist. Removed attributes are not dynamically recreated on subsequent attempts to access.
////
Mock objects create attributes and methods on-demand giving them the ability to replace other objects. Allowing for maximum flexibility, mocks don't enforce restrictions on allowed attributes or callable parameters. These allowed differences can lead to tests which are tightly coupled to mock objects rather than the objects being mocked.
The unittest.mock module includes mechanisms used to ensure mock objects adhere more closely to the object being mocked.
///
mock inside test cases 
Mock objects commonly replace external resources and services. Imagine functionality is built around a callable that connects to a REST API, transforms the data, and returns the results to the caller. The REST API shouldn't be required in order to test the surrounding functionality.






