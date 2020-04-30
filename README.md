[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/agrodet/Tatoeba-playground/master)
# Tatoeba-playground

Tatoeba playground is an environment developed to help people with or without programming knowledge explore data provided by [Tatoeba](https://tatoeba.org).

## How it works
The playground is fully accessible online. You don't need to install anything. It consists of several [Jupyter notebooks](https://jupyter.org/) and the files they use. Thanks to the technology provided by [binder](https://mybinder.org), all you have to do is to click on this URL https://mybinder.org/v2/gh/agrodet/Tatoeba-playground/master, wait for binder to build your environment, and there you go!

The environment is interactive. This means that you can run, modify, or add any code to suit your needs. You don't have any impact on other user's environment, or on your local machine.

If you're new to Tatoeba playground or to Jupyter notebooks, open any of the notebooks (the `.ipynb` files), and follow the explanations.

## Using it locally
If you would like to use Tatoeba playground in your local environment, follow these steps.

1. First of all, you need [Python 3](https://www.python.org/downloads/) on your machine. If you use Python for other projects, it is recommended to use [virtual environments](https://docs.python.org/3/tutorial/venv.html).
2. Make sure you can run [Jupyter notebooks](https://jupyter.org/). The simplest way to install these is described in the [installation guide](https://jupyter.org/install.html).
3. Clone or download this repository. 
4. Execute `pip install -r requirements.txt` (from inside the project folder) to install necessary packages.

## FAQ
### Can I use the playground if I don't have any programming knowledge?
Yes. No programming knowledge is required to use the default playground. Everything is explained inside each notebook so one just has to follow the instructions. Python knowledge is only required for users who want to tune the notebooks to fit their needs more precisely.

### I don't understand how to "run" cells.
The simplest way is to click inside the cell and press Shift + Enter. You can also run all the cells of a notebook by clicking on Cell > Run All from the top menu.

### I'm not sure that I actually ran a cell. I cannot see any feedback.
When you open a fresh notebook, cells containing code have an `In[]` on their left. When you run a cell, this will become `In[*]` while the notebook is working, and `In[n]` when it has finished, where `n` is the number of cells you've executed until now.  
Only cells actually displaying something will have an `Out[]` cell below them.

Another indication that the notebook is working is the tab icon of your browser. During work, the usual notebook icon becomes an hourglass.

### It's not clear to me what items I can or should modify.
Basically, there are four kinds of cells: explanation cells, function definition cells, variable definition cells, and output cells. Note that these are custom names, not conventional ones.  
**Explanation cells** contain only text, usually explaining what the following cells do. There is no reason to modify them.  
**Output cells** display results or information about the results. They cannot be modified and appear after execution of cells providing results.  
**Function definition cells** define functions called with the variables you will set in variable definition cells. They are the ones starting with **def**. These can be modified if you know what you are doing, but in general, they provide the default results as detailed in the explanation cell(s) above them.  
**Variable definition cells** are the ones you should modify. Set your target language, the user whose sentences you want to check, etc. Usually, explanation cells explain which part of the variable definition cell should be modified (in most cases, the part to the right of the equal `=` sign).

A common pattern is the following
```
# Explanation cell #
First, run the following cell 
--
# Function definition cell #
def function(param1, param2):
  code ...
--
# Explanation cell #
Choose the word you want to search, run the cell, and all sentences (from your sentences set) containing your word will be displayed. Any occurrence of your word, regardless of capitalization, will match.
For example, if you search for "beauty", sentences containing "Beauty" will also match.
--
# Variable definition cell #
word = "skis"                   <-- Modify this
get_sentences(word, sentences)  <-- No need to modify this
```

### Is the data from Tatoeba used in the playground always from the latest weekly download?
Yes. But there might be a few days' delay. Tatoeba exports its data on Saturday morning 06:00 UTC, so expect the playground to be updated between that time and the next Monday morning.

### I've noticed a "Trusted" setting. I don't feel like trusting something I don't understand.
In general, (local) Jupyter notebooks open in the user's browser and can therefore pose a security threat. That setting is to prevent (malicious) code from running on the user's local machine without their consent. It would take a while to explain, but you can find more information in the [Jupyter documentation](https://jupyter-notebook.readthedocs.io/en/latest/security.html). However, the playground's notebooks do not run on your local machine, but inside a container provided by binder. Therefore, you do not have to worry about trusting the notebook or anything else. You can safely run anything inside a closed environment.  

Note: Experienced users may run any UNIX command inside a Jupyter notebook by prefixing it with an exclamation mark. As an example, try to run "!ls" inside a cell to see the contents of the current folder :)

### I'd like to request a new function.
Please create an issue to ask for the implementation of a new function. Please describe what you want as precisely as possible.

### I'd like to request a new function that I already implemented.
If you're familiar with Python and pandas, you may have created your very own function, and think that it would be useful to others. If you want your function to be added to the default notebooks, you have two options: 
1. Fork the repository, add your function where you think it fits best, and open a pull request explaining in detail what it does. Please open one pull request per function.
2. Open an issue, describe what your function does and copy-paste your code directly. Your function will then be added to a notebook.

### I found a bug. I'd like to give a feedback. I'm getting an error instead of the expected output.
For any of these concerns, please open an issue describing your problem as precisely as possible.
