Installing Tau on the server
============================

Tau comes in two flavors:

 - regular Tau: <https://www.cs.uoregon.edu/research/tau/home.php>
 - Tau Commander: 

Tau Commander wraps Tau into a guided experience, whereas Tau is a little harder to configure and manage.

For the server (system where experiments are run), I would recommend tau commander, but regular tau will work as well.

Installing tau commander is as simple as running:

```
git clone https://github.com/ParaToolsInc/taucmdr.git
cd taucmdr
make install INSTALLDIR=/path/to/install/directory
```

Wherever you install it, make sure to add /path/to/install/directory/taucmdr/bin to your PATH environment variable.
e.g. somewhere in your `.bash_profile`

```
export PATH=$PATH:/path/to/install/directory/taucmdr/bin
```

You are now done installing Tau Commander and can start trying it out.


