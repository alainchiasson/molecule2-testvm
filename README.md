Molecule test VM
=================

This is a quick and dirty vagrant file that deploys everything required to
run the [TOX test](http://molecule.readthedocs.io/en/v2/testing.html#full-testing)
for Molecule v 2.0 without polluting my local system.

I have made it to pull my own repo - this can be changed.

Just run :

```
vagrant up
```

It will install all dependant packages, pull in all python requirements
and run the TOX tests.

Todo
-----

[] Parameterise git to pull and branch to run tests
[] add some script
[] see if I can move this to a docker container instead of vagrant
