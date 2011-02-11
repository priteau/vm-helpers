# VM Helpers

This is a set of helper script to make using Nimbus with non-cumulus staging
methods easier. The idea is that you use them alongside your standard Nimbus
Cloud Client tools. 

## Install

The easiest way to install the helpers is to simply get the pre-bundled Nimbus Cloud Client, which includes the helpers. Install this as you would any other Cloud Client installation. This is available at:

https://github.com/downloads/hep-gc/vm-helpers/nimbus-cloud-client-017-plus-extras.tar.gz

## Usage

This package includes three scripts which you might use. Here is an example how
you might use them. It assumes you've added the cloud client bin directory to
your path.

    $ vm-run -c cloud.example.com -i http://vmrepo.example.com -m 1024
    Workspace created: id 222
    eth0
          Association: private
           IP address: 192.168.107.1
             Hostname: examplevm01
              Gateway: 192.168.1.217
    
           Start time: Thu Feb 10 15:53:01 PST 2011
             Duration: 500 minutes.
        Shutdown time: Fri Feb 11 00:13:01 PST 2011
     Termination time: Fri Feb 11 00:15:01 PST 2011

    Wrote EPR to "./nimbus.1297381979.epr"

    Waiting for updates.
    "http://cloud.example.com/sl54base_i386.img.gz" state change: Unstaged --> Unpropagated
    "http://cloud.example.com/sl54base_i386.img.gz" state change: Unpropagated --> Propagated
    "http://cloud.example.com/sl54base_i386.img.gz" state change: Propagated --> Running
    "http://cloud.example.com/sl54base_i386.img.gz" reached target state: Running

    $ vm-list cloud.example.com
    Querying for ALL instances.
    
    [*] - Workspace #222. 192.168.107.1 [ examplevm01 ]
          State: Running
          Duration: 500 minutes.
          Start time: Thu Feb 10 15:53:01 PST 2011
          Shutdown time: Fri Feb 11 00:13:01 PST 2011
          Termination time: Fri Feb 11 00:15:01 PST 2011
          No matching handle found in history directory.

    $ vm-kill cloud.example.com 222
    Sleeping 8 seconds to wait for shutdown
   
    Destroying workspace 222 @ "https://cloud.example.com:8443/wsrf/services/WorkspaceService"... destroyed.

## Manual Install

To install the helpers to your prexisting Cloud client install, copy the vm-* scripts from this source directory to the bin directory of your cloud client install, and mark the workspace.sh command in lib as executable. (`chmod +x workspace.sh`).

## Manually Bundling the Helpers and Cloud Client

To bundle Cloud Client with these VM helpers, simply run the bundle script in the extras directory like:
    $ ./extras/bundle

This will create a tarball with cloud client and the helpers bundled together.
