# Course software

You need a laptop for this course, but all the required software is free and open-source.


## Get to know your terminal

Your computer comes with a "terminal" app that lets you type commands for your computer to run (on Windows, the terminal is the "Anaconda command prompt"). Before you complete the initial software setup below, make sure you have read Module 1's assigned readings on how to use the terminal.


## Initial software setup

At the beginning of the semester, you need to do a one-time setup process to install and configure the course software on your computer. The two important pieces of software that you need to install are Conda and Git. Conda is a package manager we will use to set up your Python environment. Git is a tool that lets you pull in the latest versions of the course files each week.

Install and configure the software by following the steps below.


### Step 1a: Rosetta Terminal (M1 Macs Only)

If you are using a Mac with an M1 chip, you will need to create a copy of your terminal that emulates an x86 terminal. If you are not using an M1 Mac, skip ahead to Step 1b. If you do not know whether your Mac has an M1 chip or an Intel chip, the “Chip” field in System Information will tell you.

To create an emulated x86 terminal, go to Finder, find and control-click on Terminal, and select “Duplicate”. Name your duplicated terminal “Rosetta Terminal”. Rosetta is Apple’s x86 emulator. Control-click on Rosetta Terminal, select “Get Info”, and check the box that says “Open using Rosetta”. 

Make sure to only use Rosetta Terminal for the rest of the installation process and for future coursework. 


### Step 1b: Git

Download and install [git](https://git-scm.com/downloads) (64-bit, use default options). Then, on your computer, open a terminal window, change directories to your desktop, and clone the course repo to your desktop by running the following command in your terminal:

```
git clone https://github.com/gboeing/ppd534.git
```

You now have a `ppd534` folder on your desktop containing the course repo.


### Step 2: Conda

Download and install [miniconda](https://docs.conda.io/en/latest/miniconda.html) (64-bit, use default options). Then open a terminal window (or Anaconda command prompt if on Windows), change directories to the `ppd534` folder on your desktop, and run the following commands, one at a time:

```
git pull
conda config --prepend channels conda-forge
conda config --set channel_priority strict
conda clean --all --yes
conda env create --file environment.yml --force
conda activate ppd534
python -m ipykernel install --sys-prefix --name ppd534 --display-name "Python (ppd534)"
```

Some of these steps take a long time to execute. Just let it run until it's done. You now have a conda environment with all the packages needed for this course, and a Jupyter kernel installed in the environment.


## How to run Jupyter

First make sure you've completed the "initial software setup" instructions above.

When you come into class each day, before the lecture begins, do the following steps (takes <1 minute):

  1. Open a terminal, change directories to the `ppd534` folder on your desktop that you created in step 1 of the initial software setup
  1. Run `git pull` to bring your local clone of the course repo up to date with the remote
  1. Run `conda activate ppd534 && jupyter lab` to start your Jupyter server
  1. In your web browser, visit http://localhost:8888

When you're all done using Jupyter at the end of a session, in the menu click File > Shut Down. Do not just close your browser tab or terminal window without stopping Jupyter first. Note that you can only type commands into a terminal window when its cursor is blinking. Otherwise it's busy.


## Troubleshooting

If you run into software problems down the road, close all open programs, restart your computer, then try your task again. If the problem persists, uninstall Conda, uninstall Git, restart your computer, then re-do the "initial software setup" instructions above. For further troubleshooting, Google and StackOverflow are your friends!
