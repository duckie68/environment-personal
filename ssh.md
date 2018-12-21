# SSH

## Check for existing SSH key

~~~
ls -al ~/.ssh
~~~

## Generate New SSH Key

~~~
ssh-keygen -t rsa -b 4096 -C "name@email.com"
~~~

Accept defaults

## Ensure Agent is Running

~~~
eval "$(ssh-agent -s)"
~~~

If not, 

~~~
sudo systemctl start sshd.service
~~~

add key

~~~
ssh-add ~/.ssh/id_rsa
~~~

## Using Keys

Copy / Paste method

~~~
xclip -sel clip < ~/.ssh/id_rsa.pub
~~~

Automagic method

~~~
ssh-copy-id remote-server.org
~~~
