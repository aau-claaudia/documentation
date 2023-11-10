# Jupyter Notebook

## Ensure Jupyter Notebook is installed

If you are unsure wether or not you have Jupyter Notebook installed on your system, you can try running the command `which jupyter`. This command outputs the filepath to which the `jupyter`-command refers. If you see a filepath, you can assume `jupyter` is installed on your instance. If the command returns `jupyter not found`, it means that `jupyter` is not bound to an executable on your system, and is most likely not installed.

## Installing Jupyter

### Using Conda

Please note, that you can also find an image called *Miniconda Ubuntu 22.04* in the list of source-images, when you create your instance. This comes with a version of conda preinstalled. Refer back to the section [Launch Instance]('../../getting_started/launch_instance.md') to learn about this list. Otherwise you should follow [the official instructions for installing Conda/Miniconda](https://docs.conda.io/projects/miniconda/en/latest/#quick-command-line-install).

```
conda install -c conda-forge jupyter
```
### Using Pip

Update the apt package index:
```
sudo apt update
```
Then install Pip:
```
sudo apt install python3-pip python3-dev
```
Jupyter Notebook can now be installed with pip install

```
pip3 install jupyter
```

Finally set jupyter to the path where pip installed it:
```
export PATH="$PATH:\$HOME/.local/bin/"

```

## Launch Jupyter Notebook

By adding a few details to our initial SSH-command, you can launch a Jupyter Notebook on the server and access it in the web browser of your local computer.
``` 
ssh -i ~/.ssh/my_ssh_key -L 8888:localhost:8888 <user>@<instance_ip>
```

This establishes port-forwarding from your instance to the localhost of your computer. If you did not do this when you logged in to your instance, simply log out and log back in with these details added.

Launch the Jupyter Notebook from your intance with:
```
jupyter notebook --port=8888
```
This will generate a substantial number of lines. Find the line that has a link that looks something like this:
```
http://localhost:8888/tree?token=b9fc44a51db685da273a2cd2kl25ac299f346ce8445bfa262382c
```
Now copy this link in to your web browser of choice. 

This should land you inside the notebook and everything should feel familiar.
