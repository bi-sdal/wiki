# Information about the servers

# Servers

Servers found using `sudo lxc-ls`.

IP addresses found using `sudo lxc-info --name rstudio-server`

- `analysis-server`: `192.168.122.`
- `analysis_ubu_server`: `192.168.122.`
- `awlxc`: `192.168.122.`
- `centos6`: `192.168.122.`
- `jupyterhub-server`: `192.168.122.8`
- `postgresql-server`: `192.168.122.3`
- `rstudio-server`: `192.168.122.10`
- `shiny-server`: `192.168.122.`
- `ubu_r-server`: `192.168.122.`

# Connecting to servers

## `lightfoot`

You have to first be connected to `lightfoot` in order to connect to the other servers.
To connect to `lightfoot` you need to create a `ssh` tunnel:

`ssh pid@lightfoot.vbi.vt.edu`

Once you are connected, your terminal prompt should look something like this: `[chend@lightfoot ~]$ `

## the rest

once you are connected to `lightfoot` you can then make another `ssh` command to one of the servers listed above.

For example, if you want to connect to the `rstudio-server`, you'd want to `ssh 192.168.122.10`.

## Connections to applications running on servers

### Connections to applications using the same port number

Server applications run on various ports.
For example, when you `ssh` into a machine, you are actually connected to port 22 (by default).

Programs like `rstudio` and `jupyter notebook` run on separate ports.
`rstudio` runs on port `8787` and `jupyter notebook` runs on port `8888`.
*You've probably typed those numbers before, that's the reason why.*

To make a `ssh` connection to a port, you need to use a special paramter (aka flag) when making the connection.
For example, if you want to make a connection to port `8888`, you'd type `ssh -L 8888:localhost:8888 192.168.122.10`.
What this will do is connect your machine's own port `8888` to the remote machine's port `8888`.

### Connections to applications using different port number

This is why applications all run on separate ports, so they don't have port conflicts.
It's like how every program runs in its own separate window.
You can't have 2 programs running in the same window.
Ports are just like these windows.

There will be times when the port on the server you want to connect to conflicts with your local machine's port.
Let's say instead of installing rstudio on my own laptop, I opted to install the server version.
Then port `8888` on my laptop will be taken by the rstudio install on my laptop.
If I want to connect to a server rstudio, then there will be a conflict.
We then have to modify how we want the port to connect on our laptop.

The program still runs on the same port on the server, we just need to change the port on our local machine.
We alter the command to `ssh -L 1234:localhost:8888 192.168.122.10`.
This will take port `8888` on the server, and map it to port `1234` on your local machine.
