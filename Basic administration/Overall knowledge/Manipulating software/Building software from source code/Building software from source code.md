As an illustration, here’s how you build a version of **tcpdump** from the source code.

The first chore is to identify the code. Software maintainers sometimes keep an index of releases on the project’s website that are downloadable as tarballs. For open source projects, you’re most likely to find the code in a Git repository.

Clone the repository in the **/tmp** directory, create a branch of the tagged version you want to build, then unpack, configure, build, and install it:

```bash
$ cd /tmp  

$ git clone https://github.com/the-tcpdump-group/tcpdump.git  
<status messages as repository is cloned>  

$ cd tcpdump  

$ git checkout tags/tcpdump-4.7.4 -b tcpdump-4.7.4  
Switched to a new branch 'tcpdump-4.7.4'  

$ ./configure  
checking build system type... x86_64-unknown-linux-gnu  
checking host system type... x86_64-unknown-linux-gnu  
checking for gcc... gcc  
checking whether the C compiler works... yes  
...  
$ make  
<several pages of compilation output>  

$ sudo make install  
<files are moved in to place>
```

This **configure/make/make install** sequence is common to most software written in C and works on all UNIX and Linux systems. It’s always a good idea to check the package’s **INSTALL** or **README** file for specifics.

>[!note]
>You’ll often need to tweak the build configuration, so use **./configure --help** to see the options available for each particular package. Another useful configure option is **--prefix**=*directory*, which lets you compile the software for installation somewhere other than **/usr/local**, which is usually the default.