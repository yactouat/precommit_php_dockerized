# precommit hook for a dockerized PHP app' template

## what is this ?

This template contains minimal code to run tests with PHPUnit using a precommit hook. It assumes that you are writing a Composer library (but you can change that).

## prerequisites

- Linux
- have PHP in your path
- have Docker installed

## how to use

- clone the template repo
- look for `project_name` occurrences in the project and remplace it with the name of your project
- update relevant values in the `composer.json`
- `docker compose up`
- in `hooks/pre-commit`, replace the container name by your PHP container name in the `exec` command, also replace `project_name` if it's not already done
- `composer install`
- `git add . && git commit -m "initial commit"` => see the magic of a local test pipeline happening !
