# Robot Framework - Keyword Tutorial

## Table of contents

[Introduction](#introduction)




<a name="introduction"></a>
## Introduction and Purpose

The main idea of this project is to have easy and out-of-the-box working examples on how to work with the [Robot Framework](http://www.robotframework.org). And here especially with its most central feature, namely, _Keywords_.

Therefore the tutorial is splitted into really small sections and is always only using those _Keywords_ that are part of the Robot Framework out-of-the-box. Thus no additional installation is required beside having a running _Robot Framework_ installation and forking/cloning this repository to try around with the examples.

I hope this tutorial can help on the one hand side to get a basic understanding how _Testsuites_ are written with the _Robot Framework_ using _Keywords_. Furthermore this might serve as a quick reference for more experienced users to just quickly take a look on how a certain feature is used (or a certain syntax).

__Note:__ All examples are shortly explained in the following and it is shown how to start the example either using _pybot_ or the _Java installation_ of the _Robot Framework_. It is required that _pybot_ can be found from the PATH on your machine for this to work and the path to the Robot-JAR will most likely differ ;-). __It is expected that the execution is always triggered from the directory containing the _Testsuite_-files.__


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


## sample-2-remote-keywords

Using a remote library can be extremely helpful as it allows writing Keyword-Libraries in any programming language as long as it offers a XML-RPC interface. The example make use of a [very simple example of such a remote library that has been written in Java](https://github.com/ThomasJaspers/remote-keyword-library). 

To make this example usable out of the box the corresponding JAR-File (implementing the remote library) is part of the example directory and can be started right away.

__Preparation__  
Start the Remote Keyword Server by issuing (__Note:__ The sample server is using port 8270):  
java -jar server/sample-remote-library-1.0-server.jar  

__Test execution__  | [VIEW FILE](https://github.com/ThomasJaspers/robot-keyword-tutorial/blob/master/sample-2-remote-keywords/sample-0-remote.txt)      
pybot --outputdir ./report sample-0-remote.txt  
java -jar /usr/local/opt/robotframework/robotframework-2.9.2.jar --outputdir ./report sample-0-remote.txt




----------------------------------------------------------------------------------------------------------------



