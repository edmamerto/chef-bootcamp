## Run chef-client periodically

> you may also want to run chef-client periodically. One reason is to help ensure that your servers are free from configuration drift.

Ways to run a chef-client periodically
> On Linux nodes, you might use a daemon, cron job, or service.
> On Linux, the chef-client cookbook sets up chef-client to run as a service

Obtaining `chef-client` cookbook
> to obtain the cookbook you can use knife supermarket command. However, the chef-client cookbook has dependencies on other cookbooks
> HOWEVER knife supermarket does not resolve these dependencies for you.

What is Berkshelf
> is a tool that helps you resolve cookbook dependencies. Berkshelf can retrieve the cookbooks that your cookbook depends on and can upload your cookbooks to your Chef server. Berkshelf comes with Chef Workstation. Befkshelf comes with Chef Workstation

in your working dir create Berkfsfile
```
$ touch Berksfile
```
```
source 'https://supermarket.chef.io'
cookbook 'chef-client'
```

download the chef-client cookbook and its dependencies.
```
$ berks install
```
Berkshelf downloads the chef-client cookbook and its dependent cookbooks to the ~/.berkshelf/cookbooks directory.
```
$ ls ~/.berkshelf/cookbooks
```
upload the chef-client cookbook and its dependencies to Chef server.
```
berks upload
```
## Create a role

> Now that the chef-client cookbook is on your Chef server, you need to update your node's run-list to use it. You also need to specify how often to run chef-client. In this part, you'll use a role to define both.
