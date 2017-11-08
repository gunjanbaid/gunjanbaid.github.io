---
layout: page
title: DSEP Decal Presentation
---

## DSEP Decal Presentation

11/7/17 

### Lab

The purpose of this lab is to give you practice with creating interact links, setting up OK submission, and creating OK tests. Here are the [starter files](https://github.com/gunjanbaid/decal-lab/tree/master/module1) and some [reference files](https://github.com/gunjanbaid/course-repo-example/tree/master/fa17/hw/hw02).

1. Import the [starter files](https://github.com/gunjanbaid/decal-lab/tree/master/module1) into your DataHub account by creating an [interact link](https://url-to-interact.herokuapp.com). It is recommended that you use DataHub to complete this lab because it already has the required Python libraries. After using the link, you should see the following files in the `~/decal-lab/module1` directory on DataHub:

	* `module1.ipynb` - the assignment
	* `tests` - folder that will contain OK tests
	* `module1.ok` -  OK configuration files  
<br>

1. Add import statements into `module1.ipynb`. This is the code under **Import modules** in the reference files.
<br>

1. Add OK setup code. This is the code under **Load OKpy** in the reference files. Change the line `ok = Notebook('hw02.ok')` to `ok = Notebook('module1.ok')`. Try running this code. It should error since we have not set up the `module1.ok` file. We will set up this file in the next few steps.
<br>

1. Update the `module1.ok` configuration file. First, rename this file to `module1.py`. JupyterHub does not allow for easy editing of `.ok` files, so using the `.py` extension allows us to easily edit this file. This is a JupyterHub hack; we are not actually writing any Python. The renaming is done to trick Jupyter into letting us edit this file in the browser, which is not possible with a `.ok` file. You will rename this file back to `module1.ok` when you are done modifying it. Copy and paste the code from the reference `.ok` file into `module1.py`.
<br>

1. After you have copied and pasted the contents of the reference OK file into `module1.py`, you will need to modify the following:

	* `name`: "Module 1"
	* `endpoint`: "cal/ds101/su17/module1"
	* `src`: "module1.ipynb"   
<br>

1. Rename `module1.py` back to `module1.ok`. Restart your kernel, and try running the OK code again. It should still error because we have not yet set up the tests. You will add tests in the next few steps. 
<br>

1. Adding tests is a longer task and is broken up into the next few bullets. The `tests` folder in the starter files contains three files: `__init__.py`, `q1.py`, and `q2.py`. You can leave the `__init__.py` file blank. Note, even though this file is blank, it must be present so that OK does not error out. 
<br>

1. OK tests work by checking the value of some variable in the notebook. Before adding tests, write some code in `module1.ipynb` that contains two variables. Your tests will then check that the values of these two variables are correct. See the reference files for examples. Here is another simple example:
	
	```
	foo = 10
	bar = 20
	```

1. Once you have written some code in `module1.ipynb` file, set up two tests for this code in the `q1.py` and `q2.py` files. Copy and paste the contents of the reference files into `q1.py` and `q2.py`. Then, modify [lines 9 and 10](https://github.com/gunjanbaid/course-repo-example/blob/master/fa17/hw/hw02/tests/q2.py#L9) to match the code you wrote in `module1.ipynb`. For instructional purposes, please make sure to change the notebook code and the tests, rather than just using the reference files as is.
<br>

1. Restart your kernel, and run the OK setup code again. It should no longer error. 
<br>

1. Add code to run tests in `module1.ipynb`. See the code under **Test your solutions** and **Run all tests** in the reference files.
<br>

1. Add code to submit the assignment. This is the code under **Submit to OKpy** in the reference files.
<br>

1. Run all tests, and submit the notebook. If submission is successfulyou will see output that looks something like this in your notebook: 

	```
	Saving notebook... Saved 'hw02.ipynb'.
	Submit... 100% complete
	Backup... 100% completete
	Submission successful for user: gunjan_baid@berkeley.edu
	URL: https://okpy.org/cal/ds101/su17/lab01/submissions/Z9urDv
	```

All done!

### Links

* [Interact Link Generator](https://url-to-interact.herokuapp.com) - quickly generate interact links from GitHub URLs
* [`nbgitpuller` repo](https://github.com/data-8/nbgitpuller) - extension needed to support interact links
* [OK](https://okpy.org) - autograding, submission
* [Connector Guide](http://data8.org/connector-instructors) - contains some general information that may be useful for modules as well
* [Jupyter Deployment Guide](https://zero-to-jupyterhub-with-kubernetes.readthedocs.io) - deploying JupyterHub

### Slides

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vTCTC7WR-d9KRDe0DUfJGOef3lSbaj8wiC8Rc9GeG_UvB4FH71fLTny4LN5bLPsaFtS_hOqOea-mkbZ/embed?start=false&loop=false&delayms=3000" frameborder="0" width="100%" height="389" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
