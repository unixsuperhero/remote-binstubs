heroku-binstubs
===============

Smaller, localized version of http://github.com/unixsuperhero/app-binstubs.

Shorten both git and heroku commands by targeting a specific remote repository.

# Path ENV

I prefer to keep a separate directory for my binstubs.  Something like ./stubs.  Which is nice if you add it to your path:

    export PATH=./stubs:$PATH

# Usage

After the stubs have been generated, you can use the following commands, assuming you have a remote called staging:

## Config Commands
* staging ignore
    * echo "stubs/" >>.gitignore

## Heroku Commands
* staging app
    * echoes the heroku app-name
* staging logs
    * $&gt; heroku logs -t -a $(app_name staging)
* staging console
    * $&gt; heroku run rails console -a $(app_name staging)
* staging deploy
    * multiple commands: git push, rake db:migrate, heroku restart
* staging repush
    * for pushing to a QA server. deploy changes for testing without:
        * merging into master
        * destroying other test features
        * being rejected (when your branch doesn't have other test features merged in)
    * multiple commands: co temp-branch; pull --rebase staging master; gp staging master
* staging migrate
* staging restart
* staging psql

## Git Commands
### git fetch
* staging fetch
    * $&gt; git fetch staging

### git push
* staging push
    * $&gt; git push staging head
* staging push -f
    * $&gt; git push -f staging head
* staging push master
    * $&gt; git push staging master

### git pull --rebase
* staging rebase
    * git pull --rebase staging master
