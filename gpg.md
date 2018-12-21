# GPG

## Check for existing GPG

~~~
gpg --list-secret-keys --keyid-format LONG
~~~

## Create GPG key

~~~
gpg --full-generate-key
~~~

Follow the instructions (sorry, not a tutorial).

## Using GPG keys

List the available keys with

~~~
gpg --list-secret-keys --keyid-format LONG
~~~

Select a key by identifier.  You can find the identifier by the line labeled 'sec' and it is the batch of numbers following the encryption and followed by the date.

Now create a gpg key in ascii armor format with

~~~
gpg --armor --export THEIDENTIFIERYOUFOUND
~~~

Copy that and use for GPG

Much more advanced usage at [Arch Linux Wiki](https://wiki.archlinux.org/index.php/GnuPG)
