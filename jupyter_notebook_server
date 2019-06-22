## Make your own Jupyter Notebook server

#### Requirements
- ngrok
- jupyter notbook

#### Download ngrok
In general, if the server has a static public IP, we can easily access the server using `ssh user@IP_address`. However, most of PCs are in the WLAN, which cannot give every device a public IP address. So we need perform `NAT traversal` to access the PC via internet.

ngrok is a reverse proxy tool, which is used to expose your WLAN IP to the internet.

#### Regist and install
Vist [ngrok](https://ngrok.com), regist an account and download the client.

Install the APP after the installation. Note that you need to get your token from https://dashboard.ngrok.com/auth.

#### Initial ngrok on your server.
Connect ngrok account:
`ngrok authtoken your_token`.

Expose a web server on port 80 of your local machine to the internet:
`ngrok http 80`

Details see the [ngrok docs](https://ngrok.com/docs)

#### Config Jupyter Notebook
Check to see if you have a notebook configuration file, `jupyter_notebook_config.py`. The default location for this file is your Jupyter folder located in your home directory:`Windows: C:\Users\USERNAME\.jupyter\jupyter_notebook_config.py`

If you don’t already have a Jupyter folder, or if your Jupyter folder doesn’t contain a notebook configuration file, run the following command:
`jupyter notebook --generate-config`

Set your password:  
`jupyter notebook password`

The minimum set of configuration options that you should uncomment and edit in jupyter_notebook_config.py is the following:
```
# Set ip to '*' to bind on all interfaces (ips) for the public server
c.NotebookApp.ip = '*'
c.NotebookApp.open_browser = False

# It is a good idea to set a known, fixed port for server access
c.NotebookApp.port = 9999
```

Details see [Jupyter Notebook docs](https://jupyter-notebook.readthedocs.io/en/stable/public_server.html)

##### HAPPY CODING!
