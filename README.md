# code-analysis

This is an experimental repo to conduct study over code submissions and run against various code-completions ML models mainly (Salesforce/CodeT5 or GPT-Clippy). 

#### Jupyter
 
The main jupyterhub is placed [here](https://github.com/yj7o5/code-analysis/blob/main/Dockerfile.jupyterhub). This is for starting the main jupyter-hub server that spawns new signle-user jupyter images when ever a new logs in or gets setup.

This contains a set of docker files to aid in spinning up the jupyterhub server. The main docker file [here](https://github.com/yj7o5/code-analysis/blob/main/docker/uh-notebook/Dockerfile) bases off of the nvidia-cuda v11.x (ubuntu distro) to provide with all the GPU and CUDA resources to be used by child images either using pytorch or tensorflows. 

The singleuser image [here](https://github.com/yj7o5/code-analysis/blob/main/singleuser/Dockerfile) bases off of the `docker/uh-notebook/Dockerfile` that contains all the nvidia/gpu resources.

The docker-compose file starts the jupyterhub database, and the juputerhub server itself. It also sets the various volumes and various other parameters defined in the .env file in the root of the repository. 
