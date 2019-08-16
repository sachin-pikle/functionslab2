# Environment Setup

For convenience, each lab participant will be provided with an Oracle Cloud
Infrastructure virtual machine configured with all the tools you'll need for
this workshop.

Your workshop instructor will provide you with the following:

1. Participant Number--your unique id that will be incorporated into your user
   id and your virtual machine name.  We'll also use it in the labs.
2. User Id/Password--to enable you to log into the OCI Console and to deploy
   functions
3. Tenancy Name--that you will use to log into the OCI account.
4. Auth Token--used as your password when logging into OCIR
5. IP Address--of your hosted development environment machine
6. VNC Password--to allow you to log into your hosted development machine
7. URL of the preview release of the OCI SDK which includes Functions support.

> As you make your way through this lab, look out for this icon.
![user input](images/userinput.png) Whenever you see it, it's time for you to
perform an action.

## Pre-requisites

Before we get started you'll need to log into the OCI account you've been
provided to change your password from the temporary initial password.  Although
we're going to be working in the Phoenix region, you'll need to login into
Ashburn to reset your password.

![user input](images/userinput.png) Log into the OCI console in Ashburn
specifying the **cloudnative-devrel** tenancy.  

https://console.us-ashburn-1.oraclecloud.com

![Login Tenancy](images/login.png)

![user input](images/userinput.png) Provide your username along with the initial password you were provided.

![Login User](images/login-user.png)

![user input](images/userinput.png) Provide a new password satisfying the
requirements and record it for use during the workshop.

![Login New Password](images/login-new-password.png)

![user input](images/userinput.png) Once you've successfully changed
your password and logged in, log out.  Later on we'll be logging into the
Phoenix region console.

![Select Region](images/logout.png)

## Configuring your Environment

Now that your user account is accessible, let's log into the provided VM where
you'll be ready to start no configuration.

To access your cloud-based development environment you'll need a VNC client
on your laptop.  You can use whatever you have previously installed or you can
use the VNC Viewer for Chrome that is extremely easy to install.

https://chrome.google.com/webstore/detail/vnc%C2%AE-viewer-for-google-ch/iabmpiboiopbgfabjmgeedhcmjenhbla/related

> NOTE: If you're curious about how to setup your own machine to build functions
> and deploy them to Oracle Functions you can follow the instructions in the
> [Quick Start
> Guide](https://www.oracle.com/webfolder/technetwork/tutorials/infographics/oci_faas_gettingstarted_quickview/functions_quickview_top/functions_quickview/index.html#)

![user input](images/userinput.png) Log into your VM using the provided IP
Address and password.  The VNC port is *5903* so the server address you'll need
to provide will look like `n.n.n.n:5903`

Enter the provided VNC password to complete your login.

![vnc login](images/vnc-login.png)


Open a terminal and type the following command to ensure you are using the
`workshop` context that points to Oracle Functions:

![user input](images/userinput.png)
>```sh
>fn ls contexts
>```

Your output should look something like the following:

```shell
CURRENT NAME      PROVIDER  API URL                                         REGISTRY
        default   default
*       workshop  oracle    https://functions.us-phoenix-1.oraclecloud.com  phx.ocir.io/cloudnative-devrel/workshop-NNN
```

Now to make sure you can be authenticated correctly and communicate with 
Oracle Functions let's run a command to list all of the existing applications.
It doesn't matter what the results--just that you do get result to confirm
connectivity.

![user input](images/userinput.png)
>```sh
>fn ls apps
>```

You may see a list of applications something like this:

```shell
NAME        ID
labapp-NNN  ocid1.fnapp.oc1.us-phoenix-1.aaaaaaaaag4h7xotdzz27sp7z23ci6z4jqj4raq43ui6ouae5k2kl7irx34a
```

## Login to OCIR

In each of the labs you'll be building functions and packaging them as
Docker container images which you'll push to the OCIR Docker container registry.
But before you can push container images you'll have to login.  The login command
has this structure `docker login <region-code>.ocir.io`.  In a terminal type
the following to login to OCIR in the Phoenix region:

![user input](images/userinput.png)
>```sh
>docker login phx.ocir.io
>```

When prompted, enter your OCIR identity using this format
`<tenancy-name>/<username>`.  For example `cloudnative-devrel/workshopNNN`.

The password is the **auth token** you were provided with, **NOT** the password
for your OCI account.

If all goes well you should see a success message:

```sh
Login Succeeded
```

## Clone the Workshop Repo

Before we actually get started let's clone the git repo for this workshop so
that you have all of the necessary materials.  Open a terminal and in your
home directory (i.e., /home/demo) type:

![user input](images/userinput.png)
>```sh
>git clone https://github.com/sachin-pikle/functionslab2.git
>```

In the `functionslab` folder you'll find the sources for this workshop along
with materials for some of the labs you'll be doing.

## All Set!

Now that you're logged into your development machine, cloned the repo, and are
able to communicate with Oracle Functions it's time to get started!

NEXT: [*Function Labs*](1-Labs.md), UP: [*INDEX*](README.md)

