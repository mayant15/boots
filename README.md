# boots

boots - The workspace bootstrapping program

Use along with the [predefined containers](https://github.com/mayant15/devcontainers/) to get pristine workspaces
powered by Docker!

**Why?** Because I didn't want to install all these language tools and frameworks to my machine.

## Usage

Extract/clone the repo to somewhere on your PATH so that you can run the `boots` Bash script. Run `boots help` for all available commands.

### Basic Example

From the root of your code directory run `boots start` to launch a new container with the given Docker image. This
creates a bind mount from current host directory to `~/code` in the container.
```sh
boots start <image>
```

Once you have a container running you can look at all running containers with
```sh
boots ps
```

To connect a new terminal to a running container grab it's ID from `boots ps` and run
```sh
boots connect <container-id>
```

### Configuration

You can have a file called `.bootsrc` in your code repo to avoid passing arguments to CLI. It's a shell script which
is sourced and can define the following variables
```sh
BOOTS_DOCKER_IMAGE= # Docker image used by boots start
BOOTS_SHELL=        # Shell to start in the container, default is /bin/zsh
```

