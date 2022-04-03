# Create a Docker image to run JupyterLab with C++

## Build the image
- Install docker in your system
- Build the Dockerfile in this repository with the following command:
  - `docker build . -t xcpp`
    - `xcpp` will be the name of the image but you can use the name of your choice.
    -  If the docker file is NOT in your current directory then change the dot for its full path.

## Run the container
- `docker run --rm -p 8888:8888 -v "$(pwd)":/home/jovyan/work xcpp`
  - Note the command will bind your current directory (pwd) to the container, this is useful to save your files in your host or if you want to pass existing files in your host to the container.


## Open JupyerLab
- Once you run the container you will see link similar to the one below in the output of the terminal:
    - `http://127.0.0.1:8888/lab?token=75bc9868c98805cd5a823a502eaad20d6a238bcdc1cefb95`
    - Your will have a different token.
    - Open the link in your browser and you will see JupyerLab.
