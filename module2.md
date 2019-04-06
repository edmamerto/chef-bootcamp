## Configure a Chef Server
> In this module we will setup a Chef Server 

Verify your chef workstation is installed
```
$ chef --version
```
Create a working directory
```
mkdir ~/learn-chef
cd ~/learn-chef
```
## Sign up for Hosted Chef

What is Knife?
> knife is the command-line tool that provides an interface between your workstation and the Chef server
> knife enables you to upload your cookbooks to the Chef server and work with nodes, the servers that you manage.

What are required files by `knife` to authenticate with Chef server?

- An RSA private key

> Every request to the Chef server is authenticated through an RSA public key pair. The Chef server holds the public part; you hold the private part.

- a `knife` configuration file

> The configuration file is typically named knife.rb. It contains information such as the Chef server's URL, the location of your RSA private key, and the default location of your cookbooks.

Where are these files located?

> Both of these files are typically located in a directory named .chef. By default, every time knife runs, it looks in the current working directory for the .chef directory. If the .chef directory does not exist, knife searches up the directory tree for a .chef directory. This process is similar to how tools such as Git work.

Generate your knife configuration file
```
~/learn-chef/.chef/knife.rb
```

Generate your validation key
```
~/learn-chef/.chef/<username>.pem
```

git ignore `.chef`

Validate your connection
```
$ knife ssl check
```



