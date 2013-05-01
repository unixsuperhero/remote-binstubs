heroku-binstubs
===============

Smaller, localized version of http://github.com/unixsuperhero/app-binstubs

# Path ENV

I prefer to keep a separate directory for my binstubs.  Something like ./stubs.  Which is nice if you add it to your path:

    export PATH=./stubs:$PATH

# Usage

After the stubs have been generated, you can use the following commands, assuming you have a remote called staging:

* staging logs
 * $&gt; heroku logs -t -a $(app_name staging)
* staging console
 * $&gt; heroku run rails console -a $(app_name staging)
* staging deploy
 * multiple commands: git push, rake db:migrate, heroku restart
