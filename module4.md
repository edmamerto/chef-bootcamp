## Bootstrap your node 
What does `chef-client` do?
> It is the command that applies the policy defined by your cookbooks to a node 

What does it mean to `bootstrap`?
> The process that installs chef-client on a node and the initial check-in to the Chef server.

Bootstrap your node using key based authentication
```
$ knife bootstrap ADDRESS --ssh-user USER --sudo --identity-file IDENTITY_FILE --node-name node1-ubuntu --run-list 'recipe[learn_chef_apache2]'
```
example
> - FQDN => public ip 
> - USER => ubuntu or root
> - PEM_FILE => yourpem.pem
> - NODE_NAME => whatever
```
$ knife bootstrap FQDN --ssh-user USER --sudo --identity-file ~/.ssh/PEM_FILE --node-name NODE_NAME --run-list 'recipe[learn_chef_apache2]'
```

Confirm result
```
$ knife node list
$ knife node show <node-name>
```
```
$ curl <host address>
```
