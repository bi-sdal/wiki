# Python Server

## How to connect to it (manually)

1. `ssh` into [`lightfoot`]()
2. `ssh` into the `jupyterhub-server`: `ssh 192.168.122.8`


## Launching a `jupyter notebook`

1. First make a connection into the `jupyter notebook`
2. navigate to your project folder
3. `jupyter notebook`
4. You should get output something along the lines of this:

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

5. 
