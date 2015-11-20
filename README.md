# Project Valhalla Images
Vagrant and docker images for compiling and testing [Project Valhalla](http://openjdk.java.net/projects/valhalla/)

After using `vagrant up` you can execute the following statements to download and compile the valhalla 
source tree in the current directory: 

*(from the Valhalla page)*

    hg clone http://hg.openjdk.java.net/valhalla/valhalla valhalla
    cd valhalla
    chmod u+x get_source.sh
    ./get_source.sh
    bash configure
    make images

The last command might take a while. On my computer it seemed stuck at 

    ...
    Generating java.security
    Note: Some input files use unchecked or unsafe operations.
    Note: Recompile with -Xlint:unchecked for details.
    Warning: generation and use of skeletons and static stubs for JRMP
    is deprecated. Skeletons are unnecessary, and static stubs have
    been superseded by dynamically generated stubs. Users are
    encouraged to migrate away from using rmic to generate skeletons and static
    stubs. See the documentation for java.rmi.server.UnicastRemoteObject.
    
But it just took a few minutes to continue.

You can run `./build/linux-x86_64-normal-server-release/jdk/bin/java -version` to verify all went well.

## Supported versions

The Vagrantfile has been tested on

- Microsoft Windows [Version 10.0.10240]
- Vagrant 1.7.4
- VirtualBox 5.0.10 r104061
