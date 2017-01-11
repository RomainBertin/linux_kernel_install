# Linux kernel install

Little script for quickly create a debuggable linux kernel. 

##Dependencies 

- cpio 
- qemu (for qemu-system-x86_64)
- gdb (for debugging purpose)


##Installation process

Execute the script with the output directory in parameter, this one must be writable. 

```bash
chmod +x installer.sh 
./installer.sh /tmp/installDir
```

##To know

By default the script is configured to install linux 3.13.6. 

You will need to update this data for installing another version. 