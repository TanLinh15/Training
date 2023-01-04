# *~~ Managing Shared Libraries ~~*

- Linux supports two different flavors of libraries. One is static libraries (also called stati-cally linked libraries ) that are copied into an application when it is compiled. The other fl a-vor is shared libraries (also called dynamic libraries ) where the library functions are copied into memory and bound to the application when the program is launched. This is called loading a library . 

- On Linux, like application packages, library files have naming conventions. A shared library file employs the following filename format:

```
lib LIBRARYNAME .so. VERSION
```

> Keep in mind that just as with packages, these are naming guidelines (similar to pirate codes) and not laws.

## Locating Library Files (Định vị tệp thư viện)
When a program is using a shared function, the system will search for the function’s library file in a specific order; looking in directories stored within the
1. LD_LIBRARY_PATH environment variable
2. Program’s PATH environment variable
3. /etc/ld.so.conf.d/ folder
4. /etc/ld.so.conf file
5. /lib*/ and /usr/lib*/ folders
> Be aware that the order of #3 and #4 may be flip-flopped on your system. This is because the /etc/ld.so.conf fi le loads confi guration files from the /etc/ld.so.conf.d/ folder. An example of this fi le from a CentOS distro is shown (along with fi les residing in
the /etc/ld.so.conf.d directory) in Listing 2.34. 


Listing 2.34: Displaying the /etc/ld.so.conf file contents on CentOS
```
$ cat /etc/ld.so.conf
```

```
$ ls -1 /etc/ld.so.conf.d/
```

Listing 2.35: Looking at the /etc/ld.so.conf.d/ file contents on CentOS
```
$ cat /etc/ld.so.conf.d/mariadb-x86_64.conf
```
```
$ ls /usr/lib64/mysql
```
