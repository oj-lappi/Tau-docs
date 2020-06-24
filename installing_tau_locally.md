Installing Tau on your desktop for analysis
===========================================

To analyze your results, you need Tau analysis utilities which are distributed in the same package as Tau.

Installation of perfexplorer (and other tau utilities)
------------------------------------------------------

 - Download the Tau distribution from uoregon <https://www.cs.uoregon.edu/research/tau/downloads.php>
   - You don't need to sign up
 - gunzip, tar -x -f, and cd into the directory
 - Install Tau by running ./installtau (configure it if you like but you don't need to unless you are doing local benchmarks)
   - Don't move the tau directory after you've run install scripts, some of the programs are shell scripts that generate path variables at install-time which are passed to java
 - Add the tau-X.XX/x86_64/bin dir to your PATH

You should now have a local Tau installation, but you still need to configure your tools.

Configuring taudb/perfdmf
-------------------------

taudb is just a brand change, taudb_configure links to perfdmf_configure. taudb == perfdmf, despite what the documentation says.

 - Create a database according to <https://www.cs.uoregon.edu/research/tau/docs/newguide/bk01pt04ch28s02.html>
   - Note, it does not have to be called taudb
   - If using pg, create a login user with a password
 - run taudb_configure or perfdmf_configure, 
 - Give your project a name (e.g. astaroth_profiles)
   - You need to input this name later
 - Choose a database according to what you did before
 - If the configuration script reports success, you should be good to go


Configuring perfexplorer
------------------------

You may have to download this one dependency (weka) manually.

### Download weka dependency

The perfexplorer_configure runs an interpreted java program to Wget a custom format file containing a second url pointing to sourceforge.     
The operation will likely fail unless the stars align.                

 - At the time of writing the weka dependency is hosted at:              
     <https://sourceforge.net/projects/weka/>                            
   download it.                                                          
   - To doublecheck for an up to date distribution,                      
     check the perfexplorer_configure script.                            
 - Unzip the download                                                    
 - Move the weka-3-6-1 directory somewhere sensible, maybe ~/.local      
 - Move, copy or link weka-3-6-1/weka.jar to ~/.ParaProf/weka-3-6-1.jar  


perfexplorer_configure
----------------------

 - Run perfexplorer_configure
 - Give the name of your taudb configuration (The same as ~/.ParaProf/perfdmf.cfg.__THIS NAME HERE__)
 - If the weka download fails, install it manually according to the instructions above (Download weka dependency)
 - Luckily the other dependencies should download fine
 - You should now be done, if the configuration script says so
 

Adding trials
=============

Now you can start adding profiles to your project

 - through the GUI application paraprof (the project shows up as a perfdmf connection)
 - using the taudb_loadtrial (perfdmf_loadtrial) tool from the command line

If you have run tau using tau commander, the default output is a set of .profile files.
These can be loaded from ParaProf by:

 - Right clicking the taudb/perfdmf database with the name (perfdmf conf name)
 - Add Trial
 - In the drop down, change ParaProf packed profile to Tau profiles
 - Select the directory with the .profile files in it
 - Every trial must be added separately


Running PerfExplorer
--------------------

Run `perfexplorer`, happy exploring!
