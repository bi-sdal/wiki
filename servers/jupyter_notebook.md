# Python Server

## How to connect to it (manually)

1. `ssh` into [`lightfoot`](https://github.com/bi-sdal/wiki/blob/master/servers/README.md)
2. `ssh` into the `jupyterhub-server`: `ssh 192.168.122.8`
3.  You should be usin the [Anaconda]() distribution of Python,
  - type `which python`
  - if it says `~/anaconda3/bin/python` you're good to go!
  - if it says `/usr/bin/python`, you need to [install it](https://github.com/bi-sdal/wiki/blob/master/installation/python_anaconda.md)
    - log out and log back in after installation

## Launching a `jupyter notebook`

- First make a connection into the `jupyter notebook`
- navigate to your project folder
- `jupyter notebook`
- You should get output something along the lines of this:

```
$ jupyter notebook
[I 14:53:20.734 NotebookApp] Writing notebook server cookie secret to /run/user/21280/jupyter/notebook_cookie_secret
[I 14:53:20.860 NotebookApp] Serving notebooks from local directory: /home/chend/temp
[I 14:53:20.860 NotebookApp] 0 active kernels 
[I 14:53:20.860 NotebookApp] The IPython Notebook is running at: http://localhost:8888/
[I 14:53:20.860 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
```

note the adress in the above statement, here it says: `http://localhost:8888/`.
The `8888` here is important since it is the port that you will need to connect to.

- You will need to make a connection from your local computer to lightfoot to the jupyter server.

Your terminal should look something like this:

```
[dchen@longclaw ~]$ ssh -L 8888:localhost:8888 chend@lightfoot.vbi.vt.edu
chend@lightfoot.vbi.vt.edu's password: 
Last login: Fri Jan 20 15:07:55 2017 from 172.30.11.152
[chend@lightfoot ~]$ ssh -L 8888:localhost:8888 192.168.122.8
Last login: Fri Jan 20 14:08:20 2017 from gateway
[chend@jupyterhub-server ~]$ 
```

- Go to your browser and in the URL bar type: `localhost:8888`
