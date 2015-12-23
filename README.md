# Robot Framework - Keyword Tutorial

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


