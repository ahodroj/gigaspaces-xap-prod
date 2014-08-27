# GigaSpaces Production Checklist Tool

http://docs.gigaspaces.com/sbp/moving-into-production-checklist.html


The goals of this tool are:

  - To ensure that all XAP-required environment variables have been set properly.

  - To point out production setup mistakes at the JVM/OS/LRMI level.

  - To point out subtle caveats, corner cases and pitfalls, that may cause a
    GigaSpaces XAP grid to fail under future circumstances.

This tool is written in Autoconf and M4 macros, so it should be supported by any Unix/Linux machine.

## Building the tool

On any system:

    autoconf configure-xap-prod.ac > configure-xap-prod
    chmod u+x configure-xap-prod


## Running Tests 

The purpose of this script is to be run on each grid machine that will host XAP

First, make sure you are logged in as the user which will run XAP:

    $ sudo su - <xap_user>

Source your XAP configuration scripts (ones that set GSA_JAVA_OPTIONS, NIC_ADDR....etc):

    $ . ./setAppEnv.sh

Launch the tool:

    $ ./configure-xap-prod

Verify the test results:

    $ cat config.log


## Enabling/Disabling specific tests

To enable/disable specific tests, simply edit the configure-xap-prod.ac script to uncomment certain sections and re-build:

 
