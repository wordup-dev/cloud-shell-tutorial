# Wordup Tutorial

<walkthrough-tutorial-duration duration="5"></walkthrough-tutorial-duration>

## Let's get started!

This guide will show you how to build your own WordPress plugin or theme with the wordup-cli. 

* You will setup a new wordup project to develop a WordPress plugin/theme 
* Export your project as a zip-file
* Live preview your development


## What is wordup

Wordup is an open-source development toolkit for setting up and managing your local WordPress Theme/Plugin development.

The wordup-cli is a command line interface written in nodejs. 

It is available as a package on [npm](https://www.npmjs.com/package/wordup-cli) 

<walkthrough-devshell-precreate></walkthrough-devshell-precreate>

## Setting up an new project

### Open Cloud Shell

<walkthrough-open-cloud-shell-button />

### Init your first project

We are using wordup-cli as a local devDependency for your newly created project. 

To do that we will run the wordup-cli commands via `npx`.

`npx` belongs to npm and executes a command even if it's not installed on your system. 

To start your first project run:

```bash
npx wordup-cli init
```

Please follow the instructions and use the following settings:

* As a project name use: **WordPress Testplugin**
* Create a WordPress plugin
* Make sure to *scaffold* your project src code. 

<walkthrough-footnote>On your local machine you could install wordup-cli as a global node package.</walkthrough-footnote>

## Your new project

You now have a new wordup project up and running. Please `cd` to your newly created project:

```bash
cd wordpress-testplugin
```

### Start coding

Take a look at the newly created project folder in the editor:

<walkthrough-spotlight-pointer spotlightId="devshell-web-editor-button"
                               text="Open Editor">
</walkthrough-spotlight-pointer>

All files located in the /src folder belong to the WordPress plugin/theme you want to create.

Files outside of this folder belong to your project in general. For example:

<walkthrough-editor-open-file filePath="./testproject/package.json">Open package.json</walkthrough-editor-open-file>

In the package.json file you can see the wordup project settings. 

### Preview on localhost

Because we are executing all our commands in Cloud Shell, 
we are not able to preview the created WordPress website directly on localhost in the browser.

But it should be running under http://localhost:8000

You can verify that, by running the following command:

```bash
npx wordup list
```

## Export your project

After some coding, you want to distribute your WordPress plugin/theme.

You can do that by running in your project folder:  

```bash
npx wordup export 
```

Wordup will export your /src folder to a zip file, based on `.distignore` and your wordup settings. 

You have also the posibilty to export your whole project. For more information see [Export docs](https://github.com/wordup-dev/wordup-cli#wordup-export-type)

## Show in Web preview 

Google Cloud Shell has a web preview.

Wordup is able to use this feature, so that you can preview your project online. 

But first we need to stop and delete the current WordPress installation.

```bash
npx wordup stop --delete
```

### Install with custom siteurl

Now we will install our project with a custom siteurl:

<walkthrough-spotlight-pointer spotlightId="devshell-web-preview-button"
                               text="Open your web preview on port 8080">
</walkthrough-spotlight-pointer> 

You browser should open a new website which shows an error message. 

Please copy the url and run the following command:

```bash
npx wordup install -p 8080 --siteurl=https://copied-url/
```

*This command will install a wordup dev server on port 8080 with your custom preview url*

After executing this command you should reload your preview url and see a running WordPress installation.

Login as an admin, so that you can see that your created WordPress plugin is also available.

## Conclusion
<walkthrough-conclusion-trophy />

### Congratulations

You have finished the wordup-cli tutorial. 

For more information visit wordup on [GitHub](https://github.com/wordup-dev/wordup-cli) 

Please follow us also on [Twitter](https://twitter.com/wordup_dev)

### Happy Coding!!!