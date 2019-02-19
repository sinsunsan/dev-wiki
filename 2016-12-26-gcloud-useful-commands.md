---
published: true
title: Useful commands to start with gcloud utility
---

gcloud is a command line utility very useful to manage you projects on Google cloud.

I am a beginner with google cloud and found the UI quite confusing. A bit less than AWS thought. I do not know why cloud giant (AWS, Google...) cannot hire good designer to craft a simple and efficient UI. Perhaps because the target user are developers and for them the most important is that is works!

They should  take example on [Digital Ocean](digitalocean.com), that I love and trust a lot. Why? Because it is very elegantly designed.

Anyway when trying to forget all the useless information that is displayed in the UI. And thanks to the tutorials ([like the hello  world in node.js](https://cloud.google.com/nodejs/)), I have understood a bit more how the hell it work.

An important utility to manage project is **gcloud**. So we are going to identify some useful commands to dig a bit more in what it can do.

The full gcloud doc is available [here](https://cloud.google.com/sdk/gcloud).

### Authenticate with your google account

[https://cloud.google.com/sdk/gcloud/reference/auth/login](https://cloud.google.com/sdk/gcloud/reference/auth/login)    

`gcloud auth login`     

Open a browser tab displaying an oauth consent screen and  ask you to connect to you google account.
If you are  not logged yet. It is the first step to do, to have authorization to manage your projects.

### List your projects on google cloud    

[https://cloud.google.com/sdk/gcloud/reference/projects/list](https://cloud.google.com/sdk/gcloud/reference/projects/list)     

`gcloud projects list`    

Display a list of your projects
The name if the human name  and project_id is an unique project id derived from the human name.

```shell
$ gcloud projects list
PROJECT_ID                NAME         PROJECT_NUMBER
api-project-194095586610  API Project  194095586610
bookshelf-153721          bookshelf    723276592807
```

### Get information about your gcloud environment

[https://cloud.google.com/sdk/gcloud/reference/info](https://cloud.google.com/sdk/gcloud/reference/info)

`gcloud info`   

Display :

* Installed components
* Default project
* Important files (logs...) that you can access
* ....

Well you have got a problem with your local install, typing this command could be a good start.


### Open an app in the browser

[https://cloud.google.com/sdk/gcloud/reference/app/browse](https://cloud.google.com/sdk/gcloud/reference/app/browse)

`gcloud app browse`

When inside the app directory, typing this command try to load the online version

### Deploy an app

[https://cloud.google.com/sdk/gcloud/reference/app/deploy](https://cloud.google.com/sdk/gcloud/reference/app/deploy)

`gcloud app deploy`

When in the local app code directory upload the files following the guidance of a specific YAML file.

If like me at your first attempt you have the following message

`ERROR: (gcloud.app.deploy) You do not have permission to access app [bookshelf] (or it may not exist): Operation not allowed`

You should try a debug mode as explained [here](http://stackoverflow.com/questions/39594478/do-not-have-permission-to-access-app-while-deploying-google-service-account).

`$ gcloud app deploy --log-http --verbosity=debug`
