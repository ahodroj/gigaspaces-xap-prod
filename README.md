# GigaSpaces Production Checklist Tool

http://docs.gigaspaces.com/sbp/moving-into-production-checklist.html


The goals of this tool are:

  - To point out and clarify typical beginner's syntax issues,
    that causes a shell to give cryptic error messages.

  - To point out and clarify typical intermediate level semantic problems,
    that causes a shell to behave strangely and counter-intuitively.

  - To point out subtle caveats, corner cases and pitfalls, that may cause an
    advanced user's otherwise working script to fail under future circumstances.

ShellCheck is written in Autoconf and M4 macros, so it should be supported by any Unix/Linux machine.

## Building the tool

On any system:

    autoconf configure-xap-prod.ac > configure-xap-prod
    chmod u+x configure-xap-prod


## Running tests (Checking that a XAP machine is production ready)

This sections describes how to build ShellCheck from a source directory.

First, make sure you are logged in as the user which will run XAP:

    $ sudo su - <xap_user>

Source your XAP configuration scripts (ones that set GSA_JAVA_OPTIONS, NIC_ADDR....etc):

    $ . ./setAppEnv.sh

Launch the tool:

    brew install cabal-install

Verify that your PATH is set up correctly:

    $ cat config.log


## Enabling/Disabling specific tests

To enable/disable specific tests, simply edit the configure-xap-prod.ac script to uncomment certain sections and re-build:

 
