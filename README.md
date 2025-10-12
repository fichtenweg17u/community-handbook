# community-guidelines
Welcome to Fichtenweg 17 U, the lower floor of our student-dorm! This is the repository and web host for our dorm-community guidelines. Feel free to take a look around!

## How do I work with this codebase?

The development environment for this project is a DevContainer. In short this means, that the entire environment is defined in configuration files and startup scripts, and is executed in a docker container. For details about the technology see the documentation page [here](https://code.visualstudio.com/docs/devcontainers/containers).

There are three main benefits about this:

-   Setting up the environment is as easy as spinning up the container, and all dependencies will be installed automatically.
-   The container will behave equally on every system, whether it's Windows, MacOS or Linux. More specifically: The container itself runs Linux (usually Debian based), so the applications will feel right at home on Linux servers or even more so in a docker hosting environment.
-   If you are done with the project, just delete the container, and no traces will be left on your system.

### Installing VS Code and Docker

Enough about selling DevContainers, lets get to specifics on how to open this repository. You will need to install the following three tools:

-   [Docker Desktop](https://www.docker.com/products/docker-desktop/): Default installation will do. Make sure it is configured for Linux containers, but that is the default. Just launch it once and make sure you click through the setup until you see the dashboard. After that you won't need to touch it again.
-   [Visual Studio Code](https://code.visualstudio.com): Also just the default installation is fine. The only extension you need is:
    -   [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers): This connects VS Code to docker, and lets you view and manage the created containers from inside VS Code. On MacOS you might get prompted if you want to allow communication from VS Code to other apps -> That is necessary for this extension to control docker.

All of these tools are also available in pretty much all packet managers, [Homebrew](https://brew.sh) for example even recognizes and installs VS Code extensions.

### Spinning up the container

Once you have all of that installed, checkout the git repository, open the folder in VS Code and either wait for the popup prompting you to reopen it in a container, or click on the remote symbol "><" in the lower left corner and select "reopen in container" manually. That is also where you can exit the remote connection btw.

The initial spin-up might take a little, since it will download the Debian container base and run all the startup scripts. If you want to see the progress in more detail, just click on the progress panel in the lower right corner. When everything is booted up, you should see the TEX extensions running, so there should be a new "TEX" tab in the bar on the left side.

Attention though: While the TEX extension is installed, the latex environment is not. For that you need to execute the initialization script: Open a terminal (`CTRL + SHIFT + P` to open command palette, then execute `Terminal: Create new Terminal`) and run
```
./post-create.sh
```

This COULD be run by default on startup, but the download and installation of the texlive environment takes pretty long and I prefer to see the progress ^^.

### Working with LaTeX

Now you can just enter the .tex files and start typing as you like. On every save the pdf document should be recompiled into `/dorm_community_handbook/main.pdf`. To view the pdf side-by-side with the source enter a .tex file, press `CTRL + SHIFT + P` to open command palette and run `LaTeX Workshop: View LaTeX PDF file`. 

A little Tipp: To jump in the preview-pdf to where your cursor is in the latex source file, press `CTRL + ALT + J`, and to jump with the cursor to a specific point in the pdf just `CTRL + CLICK` where you want to go.

Happy writing! :)