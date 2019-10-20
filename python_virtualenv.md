# Running Jupyter and other Python code in an environment

Condas broken in the middle of a lab session and no one can fix it?

This is a simple alternative that I use at work sometimes, and it's reliable.

This is not meant to try and convert anyone, but if you're short for time and machine problems are getting in the way, this is why I wrote this.

The below material was written for MacOS. If you want to add something for Windows, write me.

## Setup


Install virtualenv on your machine.

```
pip install virtualenv
```

It's best to go to the folder where you have your code or notebooks that you want to run.

View the folder in finder, then literally drag the folder into your Terminal/iTerm2 window (on Mac). You'll magically see your path in there.

Now add this in front of it. This is to change to that directory (cd = change directory):

```
cd (the path that magically appeared)
```

Now create your new virtual environment.
```
python3 -m virtualenv venv3
```

OR

```
python -m virtualenv venv3
```
Where `venv3` is the name of your new environment.

This will create a new folder with the name of your environment, with some default stuff inside.

## Start your new environment

```
source venv3/bin/activate
```

You should now see that your environment has started up.

As it's a new environment, you want to install the packages you need in that environment:
```
pip install pandas
pip install jupyter
```

OR

You can just install multiple packages in your environment:
```
pip install pandas jupyter
```

To run Jupyter notebooks, enter:
```
jupyter notebook
```

To stop the notebook, hit Ctrl+C.

If you find a missing package while your Jupyter notebook is running, go to your terminal, stop the notebook, and `pip install` the missing package.

## Record what was installed in your environment

View the packages installed in this environment `venv3`:
```
pip list
```

Record what you installed in this environment:
```
pip freeze > requirements.text
```
This creates a `requirements.txt` file where you can view everything and recreate your environment easily next time. This is not an autosave process, so if you install a new package in this environment, make sure to run this again.

## Exit your environment

Enter:
```
deactivate
```

## Recreating your environment elsewhere

Let's say your environment is broken or lost. You can emulate this by deleting the `venv3` folder you created (it's in there!)

You can still recreate exactly the same environment (named here as `new_venv3`) by using your `requirements.txt` that you wisely made earlier:

```
source new_venv3/bin/activate
pip install -r requirements.txt
```

You can even pass this .txt file on to a friend and they can run these above commands to have the same environment you had. This means that if you pass on some code or a Jupyter notebook to them, you can ensure that they can replicate the same conditions you had, to run it.


## Feedback/issues

Happy coding, and any mistakes or feedback, lemme know - Fei Phoon
