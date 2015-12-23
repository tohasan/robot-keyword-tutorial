# Robot Framework - Keyword Tutorial

The main idea of this project is to have easy and out-of-the-box working examples on how to work with the [Robot Framework](http://www.robotframework.org). And here especially with its most central feature, namely, _Keywords_.

Therefore the tutorial is splitted into really small sections and is always only using those _Keywords_ that are part of the Robot Framework out-of-the-box. Thus no additional installation is required beside having a running _Robot Framework_ installation and forking/cloning this repository to try around with the examples.

## sample-0-trivial

This contains the most basic example on how to define a testcase using keywords (here only the __Log__ keyword is used that prints to the generated log-file).

### Test execution
pybot --outputdir ./report sample-0-trivial.txt

The next example shows how to import a Library (in this case the String Library). It also shows a simple for-loop.

### Test Execution
pybot --outputdir ./report sample-1-trivial-extended.txt
