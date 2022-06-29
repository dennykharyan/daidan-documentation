[Daidan Projects Documentation](https://github.com/dennykharyan/daidan-documentation "Daidan Projects Documentation")


# Global Configuration
<table>
    <tr><td>IP Address</td><td>192.168.1.56</td></tr>
    <tr><td>Operation System</td><td>Cent-OS</td></tr>
    <tr><td>Web Server</td><td>Nginx</td></tr>
    <tr><td>Connection</td><td>SSH</td></tr>
    <tr><td>Port</td><td>22</td></tr>
    <tr><td>Login</td><td>root</td></tr>
    <tr><td>Password</td><td>daidan2018</td></tr>
    <tr><td>Firewall</td><td>none</td></tr>
</table>

You can connect directly to the server using [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) either in local network or trought VPN connection. For the VPN connection detail you can ask to the Administrator. Here is the example of PuTTY configuration:

![alt text](/img/putty-configuration.png "putty configuration")

# The Project Root Directory
The project root directory is in 
```
/usr/share/nginx/
```
![alt text](/img/project-root.png "project root")

At the moment there is only two active directory that currently used, 
```
/usr/share/nginx/daidangroup
```
and
```
/usr/share/nginx/daidangroup-finacc
```

Each directory stored in [daidangroup](https://github.com/itdaidangrup/daidangroup) and [daidangroup-finacc](https://github.com/itdaidangrup/daidangroup-finacc). You can login with `it@daidangrup.com` github account to see what's in it.

## Creating New Directory
Typically we sync the project directory with github so we can easly pull from the repository. For example we will create new peoject directory in project root directory using 

```
git clone https://github.com/itdaidangrup/daidan.git
```

Git will create new folder exactly same with repository name.

## Creating New Configuration File
When all file successfully cloned to local repository, then you should make a configuration file so the web server can managed to access the directory. The config file is placed in 

```
/etc/nginx/conf.d/
```

The config file should formated .conf as default. To create new configuration file use

```
nano /etc/nginx/conf.d/daidan.com.conf
```

Here is the example of basic configuration file
![alt text](/img/conf-d-example.PNG "Config file example")

1. Port Listening

As you can see, the configuration file contain information for where the project stored and what port should user use to access the application. Because we using PHP as programming language, we should still listen to port 80 as written on line 3. In the next line you can add which port the user can access the application, in this example we using port 8006. You dont need to setup the firewall in this documentation, because all this projects only be able to access throught VPN connection so we decided not to use firewall. 

2. Project Root Path

On line 7 as you can see we tell the server which folder that contain the application, in this case the public root project is in `/usr/share/nginx/daidangroup/public`. Make sure that you can access the directory by see the owner of the folder.

3. Acceptable File Format

On The next line we defined what kind of acceptable file format. If the new project is using another programming language you can set the entry point with this way. You can read the documentation of which programming language you used.

# Database
Currently the database is stored in different engine and different IP Address. You can see the computer on 192.168.1.53 address to see how the database should look like.
<table>
    <tr><trd>Engine</trd><td>SQL SERVER 2008 R2</td></tr>
    <tr><trd>IP Address</trd><td>192.168.1.53</td></tr>
    <tr><trd>Port</trd><td>1433</td></tr>
    <tr><trd>Username</trd><td>daidan</td></tr>
    <tr><trd>Password</trd><td>daidangrup</td></tr>
    <tr><trd>Database Name</trd><td>daidangrupdb</td></tr>
</table>

Here is the capture of the database from my local machine at this time.
![alt text](/img/databases.PNG "Database")

Currently we use same database for every project, so if you change something in a table, it might bee affect to all projects. You need to understand both project structure first before make any change in any table.

# Efiling Directory
## How The Efiling Work
We using FTP Server to transfer all file that needed in both projects and the root directory is in
![alt text](/img/ftp-root.png "FTP Root Directory")
## Accessing The Efiling Directory

# /usr/share/nginx/daidangroup