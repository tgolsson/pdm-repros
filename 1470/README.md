This is a repro to show the need for including version in the lockfile.

Note that `pdm lock` was ran on version 0.1.0 of the local package,
but `pdm sync -G ci` fails because the actual local package is now
0.2.0 and that isn't in the lockfile. `pdm install -G ci --check`
passes the check and then fails to install.

This breaks pre-commit checks like validating lockfile integrity,
because the lockfile can't be detected out of date in that case.
