# Change Password #
The WebIOPi server uses an encrypted file that contains both login and password. To generate this file, simply run the **webiopi-passwd** command with sudo and follow instructions :

```
$ sudo webiopi-passwd
WebIOPi passwd file generator
Enter Login: webiopi
Enter Password: 
Confirm password: 

Hash: e70c940a189251e9cd4515b3a1a6c6f02aa05c744a456ce360fe14bf2c5c0353
Saved to /etc/webiopi/passwd
```

Then restart the default server :
```
$ sudo /etc/init.d/webiopi restart
```

# Remove Protection #
To remove login/password protection, you can ever remove /etc/webiopi/passwd or empty it, then restart the webiopi server.

# webiopi-passwd syntax #
```
$ webiopi-passwd -h
WebIOPi passwd file generator
Usage: webiopi-passwd [--help|file]
Compute and display hash used by WebIOPi for Authentication
Login and Password are prompted
	--help	Display this help
	-h
	file	Save hash to file
```
By default, the hash is saved in /etc/webiopi/passwd. Specifying a file allows to save the hash in another file, to use it with custom servers.