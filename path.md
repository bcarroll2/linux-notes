### The PATH environment variable

Path is an environment variable that outputs a string of colon separated absolute paths to executable programs. An example PATH looks something like:

```
/usr/local/sbin:/usr/local/bin:/usr/bin:/usr/bin/site_perl:/usr/bin/vendor_perl:/usr/bin/core_perl:/usr/bin/site_perl:/usr/bin/vendor_perl:/usr/bin/core_perl
```

When a user types a command into their shell, if that command is not built into the shell or the user does not provide an absolute path, the shell will use the PATH variable to search for executable programs. The shell will split the PATH variable by the colon delimiter, and attempt to use each path to resolve the location of the program.

You can add directories or absolute paths to the PATH variable for either the current session:

```
PATH=$PATH:/usr/sbin
``` 

or (more commonly) for all sessions:

```
export PATH=$PATH:/usr/sbin
```

By prepending the current value of PATH (with $PATH) you won't overwrite the default variable, but instead add to it.

Source: http://www.linfo.org/path_env_var.html
