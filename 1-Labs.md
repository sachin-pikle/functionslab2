# Functions Labs

In each of the following labs you'll explore a different aspect of Oracle
Functions from creating, to deploying, to troubleshooting, to invoking.  In all
cases you'll be using the `fn` CLI extensively so you may find these references
helpful:

* [fn Commands
  Cheatsheet](https://github.com/sachin-pikle/functionslab/wiki/Functions-Commands-Cheatsheet)

* [fn CLI docs](https://github.com/fnproject/docs/blob/master/cli/README.md)

## Your First Function

Now that `fn` CLI is installed and your development envirionment is configured,
we can dig into the creation and running of functions.  In this lab you'll
create, deploy, and run a Node.js function.  If you aren't a Node.js programmer
don't panic! All the code is provided and is pretty easy to understand.  The
focus of this tutorial is on becoming familiar with the basics of Fn, not
Node.js programming.

So let's [create and deploy your first function](3-First-Function.md).

## Your First Python Function

https://github.com/abhirockzz/oracle-functions-hello-worlds/blob/master/python-hello-world.md

## Java Functions

Fn provides an FDK (Function Development Kit) for each of the core supported
programming languages.  But the Java FDK is the most advanced with support for
Maven builds, automatic function argument type conversions, and comprehenive
support for function testing with JUnit.

The [Introduction to Java Functions](4-Java-Functions.md) lab covers all these
topics and more.

## Troubleshooting

If you've been following the instructions in the tutorials carefully you
shouldn't have run into any unexpected failures--hopefully!!  But in real life
when you're writing code things go wrong--builds fail, exceptions are thrown,
etc.  Fortunately the
[Troubleshooting](5-Troubleshooting.md) tutorial
introduces techniques you can use to track down the source of a failure.

## Getting started with OCI Events

In this example we will take a look at another serverless offering - OCI Events service. We will listen to object store bucket create/update/delete events and send an email notification when someone creates/updates/deletes buckets. With simple event rules you can keep an eye on OCI resource changes without having to write, deploy, run and maintain your own polling mechanism on a server yourself.
[Send email notifications using OCI Events ](https://docs.cloud.oracle.com/iaas/Content/Events/Concepts/eventsgetstarted.htm)


## Trigger a function using OCI Events

In this example we will take a look at a serverless way to trigger your function using OCI Events.
[Trigger a function using OCI Object Store Object Events](https://blogs.oracle.com/developers/oracle-functions-invoking-functions-automatically-with-cloud-events)

## Access other OCI services from a function

Next, let's see an example of how to use Functions Resource Principals to access downstream OCI services. Each function is a resource, can be added to a dynamic group and policies can be configured to grant the group access to specific downstream OCI services. For more information about this topic please see https://docs.cloud.oracle.com/iaas/Content/Functions/Tasks/functionsaccessingociresources.htm

Let's start with a single function that list objects from an OCI Object Store bucket. [Getting Started with Oracle Functions and Object Storage](https://blogs.oracle.com/cloud-infrastructure/getting-started-with-oracle-functions-and-object-storage)

Now, let's extend this example with functions that perform get and put operations on an OCI Object Store bucket.
[Java Functions to perform list/get/put operations on OCI Object Store](https://github.com/abhirockzz/oracle-functions-oci-object-store).

## Accessing ATP database from a Java function

https://blogs.oracle.com/developers/oracle-functions-connecting-to-an-atp-database




## Containers as Functions

One of the coolest features of Fn is that while it's easy to write functions in
various programming languages, you can also deploy Docker images as functions.
This opens up entire world's of opportunity as you can package existing code,
utilities, or use a programming language not yet supported by Fn.  Try the
[Containers as Functions](6-Container-as-Function.md)
tutorial to see how easy it is.

## Functions Clients

Functions can be invoked over HTTP using their "invoke endpoint".  You can
either invoke the endpoint directly or use the OCI SDK to both manage and invoke
functions.  We'll explore invoking a function via the
[`oci-curl` utility](7-Functions-Clients.md) as well as invocation using the
[OCI SDK for Functions](https://blogs.oracle.com/developers/oracle-functions-invoking-functions-with-the-oci-sdk).

## Functions CI/CD

In this lab we'll see how we can build and deploy functions using [Developer
Cloud Service](9-Functions-CICD.md).
