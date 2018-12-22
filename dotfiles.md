## Starting procedure

I begin by setting up a bare git repo on the first machine, and an alias for
git that will use this.

~~~
git init --bare $HOME/.cfg
alias dotfile='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
dotfile config --local status.showUntrackedFiles no
echo "alias dotfile='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'" >> $HOME/.bashrc
~~~

Next I use the alias **dotfile** as I would use git, but specificly for
dotfiles.

~~~
dotfile status
dotfile add .bashrc
dotfile commit -m "Added bashrc"
dotfile push origin master
~~~

Of course, I must push to my dotfile repo.  The first time with

~~~
dotfile remote add origin git@github.com:duckie68/dotfiles.git
dotfile push -u origin master
~~~

On my other machines I would first add my alias of dotfile.

~~~
alias dotfile='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
~~~

Then some book keeping to avoid recursion

~~~
echo ".cfg" >> .gitignore
~~~

Then perform the first clone

~~~
git clone --bare git@github.com:duckie68/dotfiles.git $HOME/.cfg
~~~

Then make sure the shell is re-sourced, or just define the alias for that
instance.  Next, checkout the actual content

~~~
dotfile checkout
~~~

This may fail because files will be overwritten.  Run this ditty to back up the
files, though I could just trash them.

~~~
mkdir -p .config-backup && \
dotfile checkout 2>&1 | egrep "\s+\." | awk {'print $1'} | \
xargs -I{} mv {} .config-backup/{}
~~~

do the checkout again.  Set this flag;

~~~
dotfile config --local status.showUntrackedFiles no
~~~

...and all should work :D
