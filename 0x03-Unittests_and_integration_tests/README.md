iUnittests and Integration Tests Project (0x03)
Overview
This project is a hands-on exploration of creating unit and integration tests in Python. The goal is to build a testing suite that ensures the reliability of backend functions, using common testing patterns like mocking, parameterization, and fixtures. Through these tests, we can verify that individual functions behave as expected and ensure smooth interactions across different modules.

Project Specifications
Requirements
Python Version: 3.7 on Ubuntu 18.04 LTS
Testing Framework: unittest module
Coding Style: pycodestyle (version 2.5)
All modules, classes, and functions should include clear, concise documentation.

Objectives
By the end of this project, you should be able to:

Differentiate between unit and integration tests.
Utilize testing techniques such as mocking, parameterization, and fixtures.
Key Concepts
1. Unit Tests
Unit tests ensure that each function performs correctly in isolation. They:

Test individual functions with various inputs, including edge cases.
Use mocking to bypass dependencies on external calls (e.g., network requests, database interactions).
2. Integration Tests
Integration tests validate the complete code workflow and interactions between different components:

They mock only the functions that make external calls, testing end-to-end execution paths.
Execution
To run the tests:

bash
Copy code
python -m unittest path/to/test_file.py
Project Tasks
Task 0: Parameterized Unit Test for access_nested_map
File: test_utils.py
Objective: Test the function access_nested_map with a variety of inputs, ensuring it returns the expected results for each.
Method: Use @parameterized.expand for input variation and assertEqual for result validation.
Task 1: Test for KeyError in access_nested_map
File: test_utils.py
Objective: Ensure access_nested_map raises a KeyError with specific inputs.
Method: Use assertRaises with @parameterized.expand.
Task 2: Mock HTTP Calls in get_json
File: test_utils.py
Objective: Validate the get_json function's return value without making real HTTP requests.
Method: Mock requests.get and verify it was called with the correct URL. Check if get_json outputs the expected data.
Task 3: Memoization Testing with memoize
File: test_utils.py
Objective: Test the caching behavior of the memoize decorator.
Method: Mock the a_method call and validate it is called only once when accessing a_property twice.
Task 4: Testing GithubOrgClient.org with @patch and Parameterization
File: test_client.py
Objective: Test GithubOrgClient.org to ensure it returns the expected data.
Method: Use @patch and @parameterized.expand to avoid real HTTP calls and test various organization examples.
Task 5: Mocking a Property for GithubOrgClient._public_repos_url
File: test_client.py
Objective: Ensure _public_repos_url returns the correct value based on mocked data.
Method: Patch GithubOrgClient.org to provide a known payload and validate _public_repos_url.
Task 6: Testing GithubOrgClient.public_repos
File: test_client.py
Objective: Test public_repos function with mock values.
Method: Use @patch and assert_called_once for get_json and _public_repos_url.
Task 7: Test License Check with has_license
File: test_client.py
Objective: Ensure has_license correctly checks for a license key.
Method: Parametrize the license test inputs and expected results.
Task 8: Integration Testing for GithubOrgClient.public_repos
File: test_client.py
Objective: Integration test for public_repos, using setup and teardown of fixtures.
Method: Use @parameterized_class for parameterized fixtures and mock requests.get.
Resources
unittest: Core unit testing framework.
unittest.mock: Mocking library.
parameterized: Parameterization for test cases.
Memoization: Caching technique.

