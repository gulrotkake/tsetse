Tsetse
------

Tsetse is a dead simple, single header, and fast to compile unit test framework for C++. I wrote it so I could easily
create unit tests without pulling in Boost.Unit or something equally heavy.

The functionality Tsetse has to offer is the following:
  * Process exit code based on success/failure
  * Summary of what/where something failed
  * Simple macros to easily create and automatically run tests
  * Console colours
  * Less than 100 lines of code
  * MIT License

Example test (test_tsetse.cpp):
    #include <tsetse.hpp>

    TEST(not_ok) {
        CHECK(1 == 2);
    }

    TEST(ok) {
        CHECK(1 == 1);
    }

Compiling:

    g++ -I/path/to/tsetse test_tsetse.cpp -o test_tsetse

Running:

    $ ./test_tsetse

Output:

    Executing test not_ok... failed
    Executing test ok... ok
    Failures:
    test_tsetse.cpp:4 In test 'not_ok', expression '1 == 2' failed.

Exit Code: 1
