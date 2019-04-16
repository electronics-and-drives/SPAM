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
