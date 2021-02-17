## `pre-commit` checking

When `git commit` is attempted, the `.git/hooks/pre-commit` script will be run
(if it exists), and must pass (return status 0) for the commit to proceed.

If `RUN` in this directory is copied or linked to that location, it will in
turn invoke each of the numbered scripts in this directory, and will only
permit the commit to proceed if all of them "pass".

(Check scripts must be executable and have names that start with a digit and end
with an alphanumeric are considered, so backups ending in '~', the `RUN`
script, and this README are not considered.)
