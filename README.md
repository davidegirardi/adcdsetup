# Setup for the ADCD distribution

If you are running an emulated mainframe with zD&T or zPDT, these are the jobs for you!

Watch the great videos from [Henri Kuiper](https://www.youtube.com/channel/UCNqJto8aivX0_mZWRZnkzwQ "Henri Kuiper's Youtube channel") to get a hold about what this stuff does.

There are some extra scripts in here. They just extend Henri's workflow to automate even more.

## SETUP.JOBS
This directory contains all the setup scripts. Create a `IBMUSER.SETUP.JOBS` PDS on your mainframe and upload all the members there.

Here's an overview:

* `@CONFIG` is the main configuration file. Pretty much the only one to edit.
* `J00ADCDP` generate a random password for all the default ADCD users, except `IBMUSER`.
* `J01DASDI` DASD initialization.
* `J02UCAT` create a user catalog.
* `J03HLQ` create an alias for the main HLQ and links it to the user catalog.
* `J04RACF` protection of the main HLQ and group.
* `J05SMS` instructions about the configuration of SMS. This is not a script.
* `J06STST` test the SMS configuration.
* `J07UGID` configure RACF for the automatic UID/GID generation for OMVS.
* `J08ADGRP` create a default group in OMVS for our users.
* `J09AUTOM` configure automount for OMVS homes. This is an OMVS script.
* `J10ADUSR` create a user.
* `J11RMUSR` delete a user.
* `GENPASS` generates a random password for a user. Dependency of `J10ADUSR`.
* `@JOBCARD` skeleton job card.

## TODO
See `SETUP.JOBS/TODO`.

