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


## Open JupyterLab
- Once you run the container you will see link similar to the one below in the output of the terminal:
    - `http://127.0.0.1:8888/lab?token=75bc9868c98805cd5a823a502eaad20d6a238bcdc1cefb95`
    - Your will have a different token.
    - Open the link in your browser and you will see JupyerLab:
    -  ![screenshot of jupyterlab](./jupyterlab.png)
    -  Double click the `work` icon at the left pane and you will see the files and directories in your host.




> Note: If you only want to run GCC directly in a linux machine then you may want to use the GCC image, e.g.: `docker container run --rm -it -v "$(pwd)":/usr/src gcc`, this will open a linux machine with gcc installed, here you can use commands like `g++ -std=c++20 myfile.cpp -o executable_of_myfile`.
