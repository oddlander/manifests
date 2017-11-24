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

To test out the release branch type:

    $ repo init -u https://github.com/oddlander/trmb-yocto -b master

A successful initialization will end with a message stating that Repo is
initialized in your working directory. Your directory should now contain a
.repo directory.

**3.  Fetch all the repositories:**

    $ repo sync

At the end of the commands you (hopefully) have every metadata you need to start working...
***


**4. To start a simple yocto image build:

    $: MACHINE=<a_specific_trimble_board(1)> source ./setup-environment <name of build directory(2)>
    $: bitbake core-image-minimal

You can use any directory to host your build.

The source code is checked out at trmb-yocto-bsp/sources.

(1) trimble boards:
trmb_imx51_imc 
trmb_imx51_ccb 
trmb_imx51_ipcr3 
trmb_zynq_guru 
trmb_zynq_ccb 

(2) eg:
build_imc
