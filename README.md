# Process Cycle

This is a collection of scripts that automates the software process cycle.

### node.js Setup

    $ processcycle node

Downloads the nvm and installs the stable release.

### Initial Setup

    $ processcycle init

This option will retrieve the source code, install required software and do the needed configurations.
After this steps, run the node module should be enougth to get a working project:

    $ npm start

### Source Code Test

    $ processcycle test

This option will **update the source code** and **validate it** by runnning its tests. 
*If source code is invalid*, output of the failing steps should be prompted to the user.

### Source Code Deploy

    $ processcycle deploy

It runs **$ processcycle test**. *If source code is valid*, the script will compress the 
source code folder, genereta a hash for the compressed folder file, log that hash into a
file, then remove the compressed file and merge the source code deployed.

### Check Source Code Deploys

    $ processcycle check $1

If **$1** is empty, this option will check the last deployed source code by running **$ processcycle deploy**'s
subroutines, without the merge operation. The hash generated should be equal to the hash logged. If **$1** was 
given, then **$1** deploys will be checked.

To check all deploys:

    $ processcycle checkall
