# Commandline Options

## Run specify tests

### by file

- -p, --pattern=PATTERN
- -x, --exclude=PATTERN

Here are examples of the `--pattern` option:

    $ ls test/
      : (TODO)
    $ grep -r class test/
      : (TODO)
    $ ruby test/run_test.rb -v --pattern=FILENAME
    $ ruby test/run_test.rb -v --pattern=/PATTERN/

### by test case (class)

- -t, --testcase=TESTCASE
- --ignore-testcase=TESTCASE

Here are examples of the `--testcase` option:

    $ grep -r class test/
      : (TODO)
    $ ruby test/run_test.rb -v --testcase=TESTCASE
    $ ruby test/run_test.rb -v --testcase=/PATTERN/
    $ ruby test/run_test.rb -v --testcase=/PATTERN/ --ignore-testcase=/PATTERN/

### by test (method)

- -n, name=NAME
- --ignore-name=NAME
- --location=LOCATION
- --attribute=EXPRESSION

Here are examples of the `--name` option:

    $ cat test/test_name.rb
      : (TODO)
    $ ruby test/test_name.rb -v --name=NAME
    $ ruby test/test_name.rb -v --name=/PATTERN/

Here are examples of the `--location` option:

    $ cat -n test/test_location.rb
      : (TODO)
    $ ruby test/test_location.rb -v --location=NN
    $ ruby test/run_test.rb -v --location=test_location.rb:NN

Here are examples of the `--attribute` option:

    $ cat test/test_attribute.rb
      : (TODO)
    $ ruby test/test_attribute.rb -v --attribute='priority == :critical'
    $ ruby test/test_attribute.rb -v --attribute='!slow'
    $ ruby test/test_attribute.rb -v --attribute='descripyion =~ //'

## All options

Test::Unit prints help message with the `-h` or `--help` option.

    $ ruby test/run_test.rb --help
    Test::Unit automatic runner.
    Usage: -e [options] [-- untouched arguments]
        -r, --runner=RUNNER              Use the given RUNNER.
                                         (c[onsole], e[macs], x[ml])
            --collector=COLLECTOR        Use the given COLLECTOR.
                                         (de[scendant], di[r], l[oad], o[bject]_space)
        -b, --basedir=DIR                Base directory of test suites.
        -w, --workdir=DIR                Working directory to run tests.
        -a, --add=TORUN                  Add TORUN to the list of things to run;
                                         can be a file or a directory.
        -p, --pattern=PATTERN            Match files to collect against PATTERN.
        -x, --exclude=PATTERN            Ignore files to collect against PATTERN.
        -n, --name=NAME                  Runs tests matching NAME.
                                         Use '/PATTERN/' for NAME to use regular expression.
            --ignore-name=NAME           Ignores tests matching NAME.
                                         Use '/PATTERN/' for NAME to use regular expression.
        -t, --testcase=TESTCASE          Runs tests in TestCases matching TESTCASE.
                                         Use '/PATTERN/' for TESTCASE to use regular expression.
            --ignore-testcase=TESTCASE   Ignores tests in TestCases matching TESTCASE.
                                         Use '/PATTERN/' for TESTCASE to use regular expression.
            --location=LOCATION          Runs tests that defined in LOCATION.
                                         LOCATION is one of PATH:LINE, PATH or LINE
            --attribute=EXPRESSION       Runs tests that matches EXPRESSION.
                                         EXPRESSION is evaluated as Ruby's expression.
                                         Test attribute name can be used with no receiver in EXPRESSION.
                                         EXPRESSION examples:
                                           !slow
                                           tag == 'important' and !slow
            --[no-]priority-mode         Runs some tests based on their priority.
            --default-priority=PRIORITY  Uses PRIORITY as default priority
                                         (h[igh], i[mportant], l[ow], m[ust], ne[ver], no[rmal])
        -I, --load-path=DIR[:DIR...]     Appends directory list to $LOAD_PATH.
            --color-scheme=SCHEME        Use SCHEME as color scheme.
                                         (d[efault])
            --config=FILE                Use YAML fomat FILE content as configuration file.
            --order=ORDER                Run tests in a test case in ORDER order.
                                         (a[lphabetic], d[efined], r[andom])
            --max-diff-target-string-size=SIZE
                                         Shows diff if both expected result string size and actual result string size are less than or equal SIZE in bytes.
                                         (1000)
        -v, --verbose=[LEVEL]            Set the output level (default is verbose).
                                         (important-only, n[ormal], p[rogress], s[ilent], v[erbose])
            --[no-]use-color=[auto]      Uses color output
                                         (default is auto)
            --progress-row-max=MAX       Uses MAX as max terminal width for progress mark
                                         (default is auto)
            --no-show-detail-immediately Shows not passed test details immediately.
                                         (default is yes)
            --output-file-descriptor=FD  Outputs to file descriptor FD
            --                           Stop processing options so that the
                                         remaining options will be passed to the
                                         test.
        -h, --help                       Display this help.
    
    Deprecated options:
	    --console                    Console runner (use --runner).

