# NPM and Express

## Roadmap

## NPM and NPM Init

In a previous lesson we learned how to create a (very) basic web server using nothing but Node. Now, we're going to bring in a couple of Node _modules_, which you'll remember are basically JavaScript libraries that add functionality to our application.

The most popular module for adding web server functionality to Node apps is **Express.js**. We're going to bring that in but before we can do that we need to learn a bit about the **Node Package Manager** or NPM.

NPM is an online repository with _hundreds of thousands_ of node modules. We can bring them into our application as needed in seconds via a simple command line utility.

You already have NPM on your system, it installed alongside Node (Linux users may have to install it separately with apt-get, but this guide is written with Windows environments in mind.)

### NPM Init

Modules installed via NPM live in a directory called **node_modules**. Because this directory can get very large, the Node Modules folder it usually ignored by version control systems such as git.

Node Modules that are required for your application to run are referred to as _dependencies_. A reference to these dependencies is kept in a file called **package.json**. The modules referenced there can be installed easily via the **npm install** command.

This is a great system that allows node applications to be highly sharable and version-control friendly. Before we can use this system, we'll need to get our application set up for it with the **npm init** command.

Make sure you're in your MyBlog directory and run the following command in your terminal:

```
npm init
```

This will initialize package.json in your system. The utility will prompt you with a bunch of questions. Just accepts the defaults for now, only add your name as the author of the app.

You should now see a file called **package.json** in your directory. Go ahead and open it up and look around but don't change anything.

## Adding Express

We can now add Express to our application. In your terminal, run the following command:

```
npm install express --save
```

This command is pretty self explanatory. It will cause npm to find the express module and add it to your application as a dependency. The _--save_ option is actually unnecessary in modern version of npm as new modules are saved as dependencies by default but it is listed in a lot of online tutorials and so is included here to avoid confusion.

After you run the command you should see a new folder in your application: **node_modules**.

Go ahead and open up node*modules and look around. You'll notice that there are a \_lot* of files in there. Each of these folders contains a small application that is a _dependency_ of Express, which is in turn a dependency of our application (or at least it will be very soon.)

If you look in your package.json you will see that it has changed, as well. Express is now listed as a dependency.

There is another file that has been added. **package-lock.json**. Package-lock.json keeps a more exact dependency tree for your application and locks the version needed for each of these dependencies. _It does not replace package.json_. Keep both in your application.

## Initialize Git

Go ahead and go to your Github page and add a new respository for MyBlog, making it private or public as you prefer. Then, come back and initialize Git in your MyBlog directory. This will allow you to recover if there is a problem while building this app.

But wait! Look at the number of changes! This is because of our node_modules folder.

Create a .gitignore file and add node_modules to it. Once that is working go ahead and make a commit and push it to your new repository.

## Using Express
