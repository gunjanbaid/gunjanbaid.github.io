---
layout: page
title: DSEP Decal Presentation
---

## DSEP Decal Presentation

11/7/17 

### Lab

The purpose of this lab is to give you practice with creating interact links, setting up OK submission, and creating OK tests. Here are the [starter files](https://github.com/gunjanbaid/decal-lab/module1) and some [reference files](https://github.com/gunjanbaid/course-repo-example/tree/master/fa17/hw/hw02).

1. Import the [starter files](https://github.com/gunjanbaid/decal-lab/module1) into your DataHub account by creating an [interact link](https://url-to-interact.herokuapp.com). It is recommended that you use DataHub to complete this lab because it already has the required Python libraries. After using the link, you should see the following files in the `~/decal-lab/module1` directory on DataHub:

	* [`module1.ipynb`]() - the assignment
	* [`tests`]() - folder that will contain OK tests
	* [`module1.ok`]() -  OK configuration files  
<br>

2. Add import statements into `module1.ipynb`. This is the code under "Import modules" in the reference files.
<br>

3. Add code to set up OK. This is the code under "Load OKpy" in the reference files.
<br>

4. Now we will add two tests. This is a longer task and is broken up into the next few bullets. The `tests` folder in the starter files contains three files: `__init__.py`, `q1.py`, and `q2.py`. You can leave the `__init__.py` file blank. Note, even though this file is blank, it must be present so that OK does not error out. 
<br>

5. OK tests work by checking the value of some variable in the notebook. Before adding tests, write some code in `module1.ipynb` that contains two variables. Your tests will then check that the values of these two variables are correct. See the reference files for examples.
<br>

6. Once you have written some code in `module1.ipynb` file, set up two tests for this code in the `q1.py` and `q2.py` files. Take a look the reference files to see how these tests are set up. Copy and paste the contents of the reference files into `q1.py` and `q2.py`. Then, modify [lines 8 and 9](https://github.com/gunjanbaid/course-repo-example/blob/master/fa17/hw/hw02/tests/q2.py#L9) to test the code you wrote in `module1.ipynb`. For instructional purposes, please do change the notbeook code and the tests, rather than just using the reference files as is.
<br>

7. Add code to run tests in `module1.ipynb`. See the code under "Test your solutions" and "Run all tests" in the reference files.
<br>

8. Add code to submit the assignment. This is the code under `Submit to OKpy` in the reference files.
<br>

9. You are not yet ready to submit. In order to submit, you will need to add some code to `module1.ok`. First, rename this file to `module1.py`. JupyterHub is annoying and does not allow for easy editing of `.ok` files, so using the `.py` extension allows us to easily edit this file. This is temporary; you will rename this file back to `module1.ok` when you are done modifying it. Copy and paste the code from the reference OK file into `module1.py`.
<br>

10. After you have copied and pasted the contents of the reference OK file into `module1.py`, you will need to modify the following:

	* `name`: "Module 1"
	* `endpoint`: "cal/ds101/su17/module1"
	* `src`: "module1.ipynb"   
<br>

11. Rename `module1.py` back to `module1.ok`. 
<br>

12. You are done! Go back to the `module1.ipynb`, run all tests, and submit the notebook. If submission is successful, you will see output that looks something like this in your notebook:

```
Saving notebook... Saved 'hw02.ipynb'.
Submit... 100% complete
Backup... 100% completete
Submission successful for user: gunjan_baid@berkeley.edu
URL: https://okpy.org/cal/ds101/su17/lab01/submissions/Z9urDv
```

<br>
### Links

* [Interact Link Generator](https://url-to-interact.herokuapp.com) - quickly generate interact links from GitHub URLs
* [`nbgitpuller` repo](https://github.com/data-8/nbgitpuller) - extension needed to support interact links
* [OK](https://okpy.org) - autograding, submission
* [Connector Guide](https://data8.org/connector-instructors) - contains some general information that may be useful for modules as well
* [Jupyter Deployment Guide](https://zero-to-jupyterhub-with-kubernetes.readthedocs.io) - deploying JupyterHub

<br>
### Slides

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vTCTC7WR-d9KRDe0DUfJGOef3lSbaj8wiC8Rc9GeG_UvB4FH71fLTny4LN5bLPsaFtS_hOqOea-mkbZ/embed?start=false&loop=false&delayms=3000" frameborder="0" width="100%" height="389" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
