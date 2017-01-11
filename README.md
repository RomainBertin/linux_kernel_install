# Linux kernel install

Little script for quickly create a debuggable linux kernel. 

##Dependencies 

- cpio 
- qemu (for qemu-system-x86_64)
- tar
- make
- gzip
- gdb (for debugging purpose)


##Installation process

Execute the script with the output directory in parameter, this one must be writable. 
At the end of the script, run.sh should be present in the output directory. 

```bash
chmod +x installer.sh 
./installer.sh /tmp/installDir
```

##Launching the linux kernel

By default run.sh execute qemu in debugging mode with -S s. You can remove this parameter to disable this mode. 

## Remote debugging with gdb 

As mentioned above, -S s should be present in the qemu command for be able to debug the kernel. 
YOU HAVE TO LAUNCH THESE COMMAND BEFORE EXECUTING run.sh 

```bash 
$ gdb 
> set architecture i386:x86-64
> file /tmp/installDir/vmlinux
> target remote :1234
> load /tmp/installDir/vmlinux
```

In another shell

```bash 
run.sh
```

More about kernel debugging at http://elinux.org/Debugging_The_Linux_Kernel_Using_Gdb

##By default

The installation script is configured to install linux 3.13.6. 
You will need to update this data for installing another version. 
