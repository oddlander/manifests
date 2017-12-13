Trimble Repo Manifest For Yocto
=============================================
This repository provides Repo manifests to setup the Yocto build system for
supported Trimble boards as well as manufacutrers (Xilinx & Freescale) eval boards.

Getting Started
---------------
**1.  Install Repo.**

Download the Repo script:

    $ curl https://storage.googleapis.com/git-repo-downloads/repo > repo

Make it executable:

    $ chmod a+x repo

Move it on to your system path:

    $ sudo mv repo /usr/local/bin/

If it is correctly installed, you should see a Usage message when invoked
with the help flag.

    $ repo --help


**2.  Initialize a Repo client.**

Create an empty directory to hold your working files:

    $ mkdir trmb-yocto-bsp
    $ cd trmb-yocto-bsp

To test out the master branch type:

    $ repo init -u ssh://git@github.com/oddlander/trmb-yocto

A successful initialization will end with a message stating that Repo is
initialized in your working directory. Your directory should now contain a
.repo directory.

**3.  Fetch all the repositories:**

    $ repo sync

At the end of the commands you (hopefully) have every metadata you need to start working...
The source code is checked out at trmb-yocto-bsp/sources.
***


**4. To start a simple yocto image build:**

    $: MACHINE=<a_specific_board(1)> source setup-environment <name of build directory(2)>
    $: bitbake core-image-minimal

(1) besides the Freescale/Xilinx boards, there are a couple of Trimble boards:
imx51-imc 
imx51-ccb 
imx51-ipcr3 
zynq-guru 
zynq-ccb 

(2) You can use any directory to host your build.
eg:
build-imx51-imc
***

**5. Next time...**

Next time you're working with this board/machine you have to reinitialize the above created build enviroment

    $: source setup-environment <name of build directory(3)>

(3) tip: use tab-completion



