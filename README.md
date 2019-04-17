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
$ git clone https://github.com/rbzentrum/SPAM.git ~/.cadence/spam
```
into a directory of your choosing, for example ```~/.cadence/spam/```.

Make sure environment variables ```SPAMHOMEPATH``` and ```SPAMPROJPATH``` are set either with
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

## Adding Repositories

The repository definition for github is given in ```repo.ils```, 
just add others or private repositories in the same way to that list.
Alternatively you can call ```spmDefineRepo``` at runtime:
```scheme
(spmDefineRepo 
    t_name
    t_metaUrl
    u_urlGenerator
) => r_repo
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
