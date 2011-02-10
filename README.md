# VM Helpers

This is a set of helper script to make using Nimbus with non-cumulus staging
methods easier. The idea is that you use them alongside your standard Nimbus
Cloud Client tools. 

## Install

The easiest way to install the helpers is to simply get the pre-bundled Nimbus Cloud Client, which includes the helpers. Install this as you would any other Cloud Client installation. This is available at:

https://github.com/downloads/hep-gc/vm-helpers/nimbus-cloud-client-017-plus-extras.tar.gz

## Manual Install

To install the helpers to your prexisting Cloud client install, copy the vm-* scripts from this source directory to the bin directory of your cloud client install, and mark the workspace.sh command in lib as executable. (`chmod +x workspace.sh`).

## Manually Bundling the Helpers and Cloud Client

To bundle Cloud Client with these VM helpers, simply run the bundle script in the extras directory like:
    $ ./extras/bundle

This will create a tarball with cloud client and the helpers bundled together.
