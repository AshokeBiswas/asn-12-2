Q1. Explanation of using the Exception class for Custom Exceptions
The Exception class in Python serves as the base class for all exceptions. When creating custom exceptions, inheriting from Exception ensures that our custom exception inherits standard behavior and attributes from Python's exception hierarchy. This includes standard methods like __str__() for string representation and allows our custom exception to be caught by generic except clauses or specific handling.
Q2. Python Exception Hierarchy
Python's exception hierarchy starts with the base class BaseException, from which all built-in exceptions inherit. Here's a brief overview:
•	BaseException
o	Exception
	ArithmeticError
	FloatingPointError, OverflowError, ZeroDivisionError
	LookupError
	IndexError, KeyError
	AssertionError
	AttributeError
	EOFError
	ImportError
	ModuleNotFoundError
	TypeError
	ValueError
	... (many more)
Q3. Errors Defined in ArithmeticError Class
The ArithmeticError class in Python includes errors related to arithmetic operations. Two examples are:
1.	ZeroDivisionError: Raised when attempting to divide by zero.
python
Copy code
try:
    result = 10 / 0
except ZeroDivisionError as e:
    print("Error:", e)
2.	OverflowError: Raised when a calculation exceeds the maximum limit for a numerical type.
python
Copy code
import sys
try:
    result = sys.maxsize + 1
except OverflowError as e:
    print("Error:", e)
Q4. LookupError Class and Examples (KeyError and IndexError)
The LookupError class is used to handle errors related to key or index lookup operations. Examples include:
•	KeyError: Raised when a dictionary key is not found.
python
Copy code
try:
    my_dict = {"name": "Alice", "age": 30}
    print(my_dict["city"])
except KeyError as e:
    print("KeyError:", e)
•	IndexError: Raised when trying to access an index that does not exist in a sequence.
python
Copy code
try:
    my_list = [1, 2, 3]
    print(my_list[5])
except IndexError as e:
    print("IndexError:", e)
Q5. ImportError and ModuleNotFoundError
•	ImportError: Raised when an imported module cannot be found or loaded.
•	ModuleNotFoundError: A subclass of ImportError, specifically raised when a module is not found during import.
Example:
python
Copy code
try:
    import non_existing_module
except ImportError as e:
    print("ImportError:", e)

try:
    import non_existing_module
except ModuleNotFoundError as e:
    print("ModuleNotFoundError:", e)
Q6. Best Practices for Exception Handling in Python
1.	Use Specific Exceptions: Catch specific exceptions rather than generic ones to handle errors more precisely.
2.	Avoid Bare Excepts: Avoid using except: without specifying the exception type, as it can catch unintended exceptions and mask bugs.
3.	Cleanup with Finally: Use finally: blocks to ensure cleanup code (like closing files or releasing resources) runs regardless of whether an exception occurs.
4.	Exception Propagation: Consider allowing exceptions to propagate up the call stack if they cannot be handled at the current level.
5.	Logging: Use logging to record exceptions and debug information for easier troubleshooting.

