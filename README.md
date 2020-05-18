## `pre-commit` checking

When `git commit` is attempted, the `.git/hooks/pre-commit` script will be run
(if it exists), and must pass (return status 0) for the commit to proceed.

If `RUN` in this directory is copied or linked to that location, it will in
turn invoke each of the numbered scripts in this directory, and will only
permit the commit to proceed if all of them "pass".

(Check scripts must be executable and have names that start with a digit and end
with an alphanumeric are considered, so backups ending in '~', the `RUN`
script, and this README are not considered.)

## Contributing to the parent project

Add this repo as a submodule; this only needs to be done once.

Each time you clone the parent repo, activate this by going:

    ln -fs ../../.git.precommit.d/RUN .git/hooks/pre-commit

This will prevent the subsequent introduction of syntax errors and whitespace
anomalies. Please ensure you have `/bin/bash` installed.

The check files here are common to nearly all projects.

The `100-run-tests` check script implements the common convention of having a
`t` directory that contains unit tests. These are specific to each project and
usually focus on logic and correctness, and ideally there should be a test
script for each function or method, plus one for each package or module to
verify constants and global initialisers.
