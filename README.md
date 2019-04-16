# SKILL Package Manager (SPAM)

SPAM is a package management system for Cadence SKILL.

## Dependencies

Following *nix utilities must be installed:
+ wget
+ unzip

SPAM has only been tested under Cadence Design Framework:
+ virtuoso version 6.1.7-64b 01/24/2018
+ SKILL 35.00

## Getting Started

Download spam
```bash
$ git clone https://github.com/rbzentrum/SPAM.git
```
into a directory of your choosing, ```~/.cadence/spam/``` being recomended.

Make sure ```SPAMHOMEPATH``` and ```SPAMPROJPATH``` are set either with
```bash
$ export SPAMHOMEPATH=~/.cadence/spam
$ export SPAMPROJPATH=/path/to/project
```
or in your ```.cdsinit```
```scheme
(setShellEnvVar "SPAMHOMEPATH" "~/.cadence/spam")
(setShellEnvVar "SPAMPROJPATH" "/path/to/project")
```
and load ```spam.ils```.
```scheme
(load "spam.ils")
```

## Function Reference

### spamSearch
```scheme
(spamSearch
    t_query
) => t | nil
```
Searches for packages with the names given by the string 't_query'.

### spamInstall
```scheme
(spamInstall
    t_name 
    [ t_name ]
    ...
) => t | nil 
```
Installs the packages given by the strings 't_name'.
If the installation was successful, t is returned.

### spamRemove
```scheme
(spamRemove
    t_name
    [ t_name ]
    ...
) => t | nil
```
Removes the packages with the names given by the strings 't_name'.

### spamUpdate
```scheme
(spamUpdate
    [t_name]
    ...
) => t | nil
```
Updates a given list of packages (t_name).
If no packages are specified the meta database will be updated.

### spamInfo
```scheme
(spamInfo
    t_name
) => t | nil
```
Prints information about the given package with name 't_name'.

### spamUse
```scheme
(spamUse
    t_name
    [ t_name ]
    ...
) => t | nil
```
Includes the given packages in the given order into the current toplevel.
