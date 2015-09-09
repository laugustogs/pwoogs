# pwoogs

### Work in progress ###

pwoogs is a Python wrapper for MOOG synth, an application widely used in astronomy for synthesis of spectral lines. I recently started working on this after being fed up with the usual interface and plotting of MOOG. The code is very bare bones at the moment, but I'll be working on improving it, adding more features and a proper documentation as time goes on. Now it has a rotation estimator!

Dependencies
------------

Unfortunately, pwoogs depends on a full installation of MOOGSILENT, which does require superMONGO (SM), a very old and clunky closed-source plotting routine that we don't even use. I know, this is kind of bullshit, but in the future I'll try to figure out a way to avoid an installation of SM. For now, this is what you need installed on your machine:

* MOOG silent (therefore, also superMONGO, Fortran and C compilers)
* numpy
* matplotlib
* pip (optional: only for [un-]installation)

If you have problems installing SM or MOOG, which you most certainly will, take a look at the documentation of pwoogs. There is a bunch of tips there.

(Un-)Installation
------------

You might need superuser privileges to perform (un-)installation. If you have python installed through Anaconda, you won't need them.

Once you have the dependencies installed, you should declare the path of the MOOGSILENT installation to your system. One way to do this, for example, on Debian-based systems, is to open your .bashrc profile and put this line inside it:

    PATH=/whatever/path/you/installed/moogjul2014:$PATH

In order to install pwoogs, download it and run the setup:
 
    python setup.py install

After that, running pwoogs should be as simple as:

    from pwoogs import moog
    m = moog.run()
    
You can run pwoogs in silent mode (no plot) by using (contrary to the original MOOG, you don't need to compile a different version of the program! Horray!)

    m = moog.run(silent=True)

You can uninstall pwoogs simply by entering the following line on your terminal:

    pip uninstall pwoogs
    
Latest additions and corrections
------------

* estimate.rotation now has a much faster, better and efficient find() routine
* plotter now has an option to save plot as a file

Known issues
------------

* The code is not fully optimized and still needs polishing on handling files

To-do list
------------

* Examples
* Documentation for estimate
* A silent version of estimate
* Better error handling
* Maybe changing the code so that it does not need installation?

Version
------------

pwoogs 0.1 (Alpha) build 1508
