# Install git if not installed


# Clone msticpy-training repo

Change directory to the folder where you want to clone the [msticpy-training repo](https://github.com/microsoft/msticpy-training)

```bash
cd root_src_folder
git clone https://github.com/microsoft/msticpy-training.git

```

# Build the docker image

```bash
cd msticpy-training/workshops/Oct2022
docker build --pull --rm -f Dockerfile.txt -t firecon:latest "."
```

# Run the container
```bash
docker run -it --rm -v %CD%:/nbexec -w /nbexec -e MSTICPYCONFIG="%CD%/msticpyconfig.yaml" firecon:latest bash
```

```bash
docker run -it --rm -v $PWD:/nbexec -w /nbexec -e MSTICPYCONFIG="$PWD/msticpyconfig.yaml" firecon:latest bash
```