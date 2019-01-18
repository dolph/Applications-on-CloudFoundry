# Deploy your applications on CloudFoundry and Diego

IBM Bluemix is where enterprise developers build, run, scale, and manage applications. Ready to start creating your own apps on Bluemix? This tutorial walks you through the steps for hosting you application. We will go through the basic steps to launch Java, Node and PHP applications. You can pick the language you are comfortable with to go through the steps. After that, we will consume the services provided by Bluemix.

## Scenarios
### [Create and deploy Java application on Cloud Foundry](doc/java.md)
* [1.Create And Modify your java application](doc/java.md#1)
  * [1.1 Import the app into your Eclipse workspace](doc/java.md#1.1)
  * [1.2 Modify the code](doc/java.md#1.2)
  * [1.3 Create and bind a DB service to the application](doc/java.md#1.3)
  * [1.4 Run JUnit tests](doc/java.md#1.4)
* [2.Deploy your Java Application](doc/java.md#2)
  * [2.1 Deploy as a .war app](doc/java.md#2.1)
  * [2.2 Deploy as docker image using Diego](doc/java.md#2.2)
  * [2.3 Add Zipkin to docker image](doc/java.md#2.2)

### [Create and deploy Node application on Cloud Foundry](doc/node.md)
* [1.Create And Modify your Node application](doc/node.md#1)
  * [1.1 Try out the code](doc/node.md#1.1)
  * [1.2 Create and bind a DB service to the application](doc/node.md#1.2)
  * [1.3 Two ways to modify the code to access DB](doc/node.md#1.3)
  * [1.4 Run the code](doc/node.md#1.4)
* [2.Deploy your Node Application](doc/node.md#2)
  * [2.1 Deploy as an app](doc/node.md#2.1)
  * [2.2 Deploy as docker image using Diego](doc/node.md#2.2)
  * [2.3 Add Zipkin to docker](doc/node.md#2.2)

## Included components
IBM Bluemix
Cloud Foundry

## Prerequisites
[Create an IBM Bluemix account](https://cloud.ibm.com/).
After that, please download the [Bluemix CLI.](https://cloud.ibm.com/docs/cli/index.html)
Make sure you run <kbd class="ph userinput">bx login</kbd> command and create the org and space for the demo.

## Glossary and status messages
Let's review some terms and status messages you're likely to encounter as you use Bluemix.

### Glossary

Familiarize yourself with the following important terms, which you'll often see in documentation and status messages when you work with Bluemix.

* Droplet— A bundle ready to run in the cloud, including everything needed (for instance, a bundle with JVM, Liberty profile server, and your app) except an operating system.
* Buildpack— An executable that takes the code or packaged server that you push, and bundles it up into a droplet.
* Manifest— An optional file, named manifest.yml, that you can add to your project. The manifest file configures various parameters that affect the deployed server — including memory size, buildpack to use during deployment, services that are required, the disk space consumed, and so on. For simple Java web apps, you don't need a manifest; the system automatically detects and uses the Liberty profile buildpack and applies a default configuration.
* Staging— The process handled by the buildpack, bundling what you uploaded with system components and dependencies into a valid droplet
* Droplet Execution Agent (DEA)— The system piece that's responsible for reconstituting the droplet and running your app in the cloud

### Status messages

When you issue the cf push CLI command or deploy via the IBM Tools for Eclipse, you see a series of status messages. If you examine them carefully, you'll see the following sequential phases:

* Your push successfully uploaded the WAR or packaged server to the staging area.
* If an existing instance of your app is already running, it's stopped before staging begins.
* The buildpack starts the staging process, which can include:
* Downloading and installing various system components
* Downloading and installing compilers (the JVM, for example)
* Putting your app into place
* Setting up the environment
* Bundling everything up to create the droplet
* To speed up these steps, staging makes heavy use of cache, so you might also see some reuse-from-cache messages in the mix. The DEA tries to start your app from the droplet, running under supervision of a container

## Reference
