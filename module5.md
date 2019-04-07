## Update your node's configuration
Key points
> - You ran `knife bootstrap` to associate your node with the Chef server and do an initial check-in. Bootstrapping is a one-time process.
> - The `knife ssh` command enables you to update your node's configuration when your cookbook changes.

Add template code to your HTML
```
<html>
  <body>
    <h1>hello from <%= node['fqdn'] %></h1>
  </body>
</html>
```

Update your cookbook's version metadata
```
version '0.2.0'
```

Upload your cookbook to the Che server
```
$ knife cookbook upload learn_chef_apache2
```

Run the cookbook on your node
```
$ chef-client
```
OR Update your node using key-based authentication
```
$ knife ssh 'name:node1-ubuntu' 'sudo chef-client' --ssh-user USER --ssh-identity-file IDENTITY_FILE --attribute ipaddress
```
```
$ knife ssh 'name:node1-ubuntu' 'sudo chef-client' --ssh-user vagrant --ssh-identity-file ~/.ssh/private_key --attribute ipaddress
```

Verify the result
```
$ curl <host_address>
```

What is a node object
> An object on the Chef server that contains attributes that describe a node.
