[[C++]]
[[Write tests]]

cassert
GTest
CTest

Steps
1. write CMakeLists.txt
2. run
```
cmake -S . -B build
cmake --build build
cd build
ctest
```
[Sample test file .cc](https://google.github.io/googletest/quickstart-cmake.html#create-and-run-a-binary)
```
#include <gtest/gtest.h>

// Demonstrate some basic assertions.
TEST(HelloTest, BasicAssertions) {
  // Expect two strings not to be equal.
  EXPECT_STRNE("hello", "world");
  // Expect equality.
  EXPECT_EQ(7 * 6, 42);
}
```

Sample CMakeLists
```
enable_testing()

add_executable(
  hello_test
  hello_test.cc
)
target_link_libraries(
  hello_test
  GTest::gtest_main
)

include(GoogleTest)
gtest_discover_tests(hello_test)
```
[Assertions](https://google.github.io/googletest/reference/assertions.html) - e.g. EXPECT_TRUE, EXPECT_EQ - comparing 2 numbers

Definitions
Test - Exercise a particular program path with specific input values and verify the results
Test Case - ISTQB name for Test
Test Suite - collection of tests

Tools
gcov - coverage