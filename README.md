[Daidan Projects Documentation](https://github.com/dennykharyan/daidan-documentation "Daidan Projects Documentation")


# global configuration
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
------
![alt text](/img/putty-configuration.png "putty configuration")

# project root directory
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

each directory stored in [daidangroup](https://github.com/itdaidangrup/daidangroup) and [daidangroup-finacc](https://github.com/itdaidangrup/daidangroup-finacc). You can login with `it@daidangrup.com` github account to see what's in it.

## creating new directory
Typically we sync the project directory with github so we can easly pull from the repository. For example we will create new peoject directory in project root directory using 

```
git clone https://github.com/itdaidangrup/daidan.git
```

Git will create new folder exactly same with repository name. When all file successfully cloned to local repository, then you should make a configuration file so the web server can managed to access the directory. The config file is placed in 

```
/etc/nginx/conf.d/
```

The config file should formated .conf as default. To create new configuration file use

```
nano /etc/nginx/conf.d/daidan.com.conf
```

Here is the example of basic configuration file
![alt text](/img/conf-d-example.PNG "Config file example")
# database
# efiling directory
# /usr/share/nginx/daidangroup