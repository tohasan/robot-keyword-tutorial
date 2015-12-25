# Robot Framework - Keyword Tutorial


<a name="toc"></a>
## Table of Contents

* [Introduction](#introduction)
* [sample-0-trivial](#sample-0-trivial)
* [sample-1-own-keyword](#sample-1-own-keyword)
* [sample-2-remote-keywords](#sample-2-remote-keywords)
* [sample-3-variables](#sample-3-variables)
* [sample-4-tagging](#sample-4-tagging)
* [sample-5-setup-teardown](#sample-5-setup-teardown)
* [sample-6-parameter](#sample-6-parameter)


<a name="introduction"></a>
## Introduction and Purpose

The main idea of this project is to have easy and out-of-the-box working examples on how to work with the [Robot Framework](http://www.robotframework.org). And here especially with its most central feature, namely, _Keywords_.

Therefore the tutorial is splitted into really small sections and is always only using those _Keywords_ that are part of the Robot Framework out-of-the-box. Thus no additional installation is required beside having a running _Robot Framework_ installation and forking/cloning this repository to try around with the examples.
I hope this tutorial can help on the one hand side to get a basic understanding how _Testsuites_ are written with the _Robot Framework_ using _Keywords_. Furthermore this might serve as a quick reference for more experienced users to just quickly take a look on how a certain feature is used (or a certain syntax).

__Note:__ All examples are shortly explained in the following and it is shown how to start the example either using _pybot_ or the _Java installation_ of the _Robot Framework_. It is required that _pybot_ can be found from the PATH on your machine for this to work and the path to the Robot-JAR will most likely differ ;-). __It is expected that the execution is always triggered from the directory containing the _Testsuite_-files.__

[top](#toc)

<a name="sample-0-trivial"></a>
## sample-0-trivial

This contains the most basic example on how to define a testcase using keywords (here only the __Log__ keyword is used that prints to the generated log-file). __Note:__ There must be at least two spaces to separate arguments from keywords and arguments from each other. Furthermore there must be always an indention of two spaces in the beginning of each line below a testcase.  

__Test execution__  | [VIEW FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-0-trivial/sample-0-trivial.txt)  
pybot --outputdir ./report sample-0-trivial.txt  
java -jar /usr/local/opt/robotframework/robotframework-2.9.2.jar --outputdir ./report sample-0-trivial.txt

----------------------------------------------------------------------------------------------------------------

The next example shows how to import a Library (in this case the String Library). It also shows a simple for-loop. __Please note__ that the "\" are required in the lines belonging to the loop.

__Test execution__  | [VIEW FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-0-trivial/sample-1-trivial-extended.txt)  
pybot --outputdir ./report sample-1-trivial-extended.txt  
java -jar /usr/local/opt/robotframework/robotframework-2.9.2.jar --outputdir ./report sample-0-trivial.txt

[top](#toc)

<a name="sample-1-own-keyword"></a>
## sample-1-own-keyword

One of the key features of the _Robot Framework_ is the possibility to combine existing _Keywords_ into new _Keywords_ within some text files. This first example shows the most simple way of defining a customized keyword within the _Testsuite_-file.

__Test execution__  | [VIEW FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-1-own-keyword/sample-0-own-keyword.txt)    
pybot --outputdir ./report sample-0-own-keyword.txt  
java -jar /usr/local/opt/robotframework/robotframework-2.9.2.jar --outputdir ./report sample-0-own-keyword.txt

----------------------------------------------------------------------------------------------------------------

The second example shows the usage of an array as a parameter for a customized _Keyword_.

__Test execution__  | [VIEW FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-1-own-keyword/sample-1-own-keyword.txt)    
pybot --outputdir ./report sample-1-own-keyword.txt  
java -jar /usr/local/opt/robotframework/robotframework-2.9.2.jar --outputdir ./report sample-1-own-keyword.txt

----------------------------------------------------------------------------------------------------------------

In this example the customized _Keyword_ is moved to an external _Resource_-file that is then used from within the _Testsuite_.

__Test execution__  | [VIEW FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-1-own-keyword/sample-2-own-keyword-resource.txt)  |  [VIEW RESOURCE FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-1-own-keyword/resource-2.txt)      
pybot --outputdir ./report sample-2-own-keyword-resource.txt  
java -jar /usr/local/opt/robotframework/robotframework-2.9.2.jar --outputdir ./report sample-2-own-keyword-resource.txt

[top](#toc)

<a name="sample-2-remote-keywords"></a>
## sample-2-remote-keywords

Using a remote library can be extremely helpful as it allows writing Keyword-Libraries in any programming language as long as it offers a XML-RPC interface. The example make use of a [very simple example of such a remote library that has been written in Java](https://github.com/ThomasJaspers/remote-keyword-library). 

To make this example usable out of the box the corresponding JAR-File (implementing the remote library) is part of the example directory and can be started right away.

__Test Preparation__  
Start the Remote Keyword Server by issuing (__Note:__ The sample server is using port 8270):  
java -jar server/sample-remote-library-1.0-server.jar  

__Test execution__  | [VIEW FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-2-remote-keywords/sample-0-remote.txt)      
pybot --outputdir ./report sample-0-remote.txt  
java -jar /usr/local/opt/robotframework/robotframework-2.9.2.jar --outputdir ./report sample-0-remote.txt

[top](#toc)

<a name="sample-3-variables"></a>
## sample-3-variables

Variables are offering a lot of possibilities when writing tests with the Robot Framework. The following sample shows a most basic example on how to use variables.

__Test execution__  | [VIEW FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-3-variables/sample-0-variables.txt)      
pybot --outputdir ./report sample-0-variables.txt  
java -jar /usr/local/opt/robotframework/robotframework-2.9.2.jar --outputdir ./report sample-0-variables.txt

----------------------------------------------------------------------------------------------------------------

This example gives an example on how global variable values can be temporarily overwritten in the scope of a testcase. Note that this does not permanently change the value of the globally defined variable.

__Test execution__  | [VIEW FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-3-variables/sample-1-variables-scope.txt)      
pybot --outputdir ./report sample-1-variables-scope.txt  
java -jar /usr/local/opt/robotframework/robotframework-2.9.2.jar --outputdir ./report sample-1-variables-scope.txt

----------------------------------------------------------------------------------------------------------------

This example shows the usage of variable files. This is especially useful to define certain values (like URLs or database connections) differently for different test environments. The variable files are then passed in via a command line option.

__Test execution__  | [VIEW FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-3-variables/sample-2-variables-file.txt) | [VIEW LOCAL VARIABALE FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-3-variables/variable-file-env-local.py) | [VIEW TEST VARIABLE FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-3-variables/variable-file-env-test.py)      
pybot --outputdir ./report --variablefile ./variable-file-env-local.py sample-2-variables-file.txt  
java -jar /usr/local/opt/robotframework/robotframework-2.9.2.jar --outputdir ./report --variablefile ./variable-file-env-local.py sample-2-variables-file.txt

__Note:__ Change the variable-file passed in and take a look at the resulting log-file.

[top](#toc)

<a name="sample-4-tagging"></a>
## sample-4-tagging

Tagging is a useful feature to have some kind of test coverage in the generated report. Just _tag_ each testcase with the proper - uhm - _tags_. __Note:__ Make sure you are using unique tag-names for the same features.

__Test execution__  | [VIEW FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-4-tagging/sample-0-tagging.txt)      
pybot --outputdir ./report sample-0-tagging.txt  
java -jar /usr/local/opt/robotframework/robotframework-2.9.2.jar --outputdir ./report sample-0-tagging.txt

[top](#toc)

<a name="sample-5-setup-teardown"></a>
## sample-5-setup-teardown

_Setup-_ and _Teardown_-functions (_Keywords_) are very helpful to separate preparation tasks from the real test execution. Furthermore it allows to perform global steps for a testsuite once (in the beginning and end). This is shown in the following example.

__Test execution__  | [VIEW FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-5-setup-teardown/sample-0-suite.txt)      
pybot --outputdir ./report sample-0-suite.txt  
java -jar /usr/local/opt/robotframework/robotframework-2.9.2.jar --outputdir ./report sample-0-suite.txt

----------------------------------------------------------------------------------------------------------------

It is also possible to define _Setup-_ and _Teardown-_functions that are executed bevore and after the execution of every _Testcase_ of a _Testsuite_. Can be helpful if the same preparation/cleanup steps are required for each test.

__Test execution__  | [VIEW FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-5-setup-teardown/sample-1-test.txt)      
pybot --outputdir ./report sample-1-test.txt  
java -jar /usr/local/opt/robotframework/robotframework-2.9.2.jar --outputdir ./report sample-1-test.txt

----------------------------------------------------------------------------------------------------------------

Finally some testcases might need specific preparation/cleanup functionality that is not part of the test itsself. This can be achieved as follows.

__Test execution__  | [VIEW FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-5-setup-teardown/sample-2-testcase.txt)      
pybot --outputdir ./report sample-2-testcase.txt  
java -jar /usr/local/opt/robotframework/robotframework-2.9.2.jar --outputdir ./report sample-2-testcase.txt

[top](#toc)

<a name="sample-6-parameter"></a>
## sample-6-parameter

Sometimes it might make sense to have _Keywords_ that can work with a lot of parameters. For example all the parameters that might be processed in a form of a web application. Using the "..."-syntax it is possible to split paramters to one _Keyword_ to sevaral lines and thus increase readability.

__Test execution__  | [VIEW FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-6-parameter/sample-0-parameters-divided.txt)      
pybot --outputdir ./report sample-0-parameters-divided.txt  
java -jar /usr/local/opt/robotframework/robotframework-2.9.2.jar --outputdir ./report sample-0-parameters-divided.txt

[top](#toc)
