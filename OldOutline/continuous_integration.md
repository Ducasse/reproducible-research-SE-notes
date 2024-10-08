## Continuous Integration

@continuous_integration

This is always good practice to test some features of your application e.g. some functions, methods, etc.
And it is even better practice to guaranty the project will run under a given configuration i.e. a given OS' and associated packages' version.

Imagine you are developing on a Mac machine but wish your application to be run on Linux, too. Besides, your project may rely on many dependencies and some could even require to be compiled beforehand.

Continuous integration tools e.g. [Travis](https://travis-ci.com/) or [Jenkins](https://jenkins.io/) will allow to automate these tasks and certify that your project can not only be run on your own machine but also under different configurations i.e. it is portable and your code is reproducible.

Once the configuration is set you can run a bunch of tests on your code and report the results to identify some bugs at different scales.

All this is performed on an remote machine that may be physically far distant from your personal computer.
You can configure the integration tool to execute this whole list of operations after each commit :\)

In this booklet we consider [Travis](https://travis-ci.com/)

### Configuration of Travis


The associated configuration file `.travis.yml` collects all info required for testing the project on various configurations

```language=yaml
language: python

sudo: require # In case you need to use apt-get

matrix: # matrix os/Python version
	include:
		## Linux
		- os: linux
		  python: 2.7
		- os: linux
			python: 3.4
		## OSX
		- os: osx
		  language: generic 
		  env: PYTHON=2.7 # Environment variable associated the Python version
		- os: osx
			language: generic
			env: PYTHON=3.4.6

install:
	- python -m pip install -U pip # Update pip
	- python -m easy_install -U setuptools # Update setuptools
	- pip install . # Install the project
```


!!note For more detailed information see the _Getting started_ [tutorial](https://docs.travis-ci.com/user/getting-started/) 

### Usecases of Travis


- Check installation of the project of several machine configurations
- Test parts of code 
- Build LaTex project


See section *@workflows_for_researchers@*