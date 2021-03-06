APONTAMENTOS DEVOPS
===================

Index
---




GIT - DISTRIBUTED VERSION-CONTROL SYSTEM
---------------------------------------


### O QUE É UM VERSION-CONTROL SYSTEM(VCS)?

- Controlo de versão é um sistema que grava mudanças de um ou vários ficheiros ao longo do tempo para poder recuperar versões especificas mais tarde.
- Pode ser usado para quase qualquer tipo de ficheiro (e.g. ficheiros de texto)
- Serve para poder recuperar uma versão antiga de um ficheiro em caso de falha ou de alguma alteração não pretendida.

### O QUE É UM CENTRAL VERSION-CONTROL SYSTEM (CVCS)?
- Foram desenvolvidos porque os desenvolvedores precisavam de colaborar 
- Todas as versões dos ficheiros são mantidas num único servidor que é acedido pelos clientes.
- Durante muitos anos foi o standard.
- Torna fácil controlar o que é feito num projeto.
- Sofre de problemas de fiabilidade já que se esse único servidor falhar, todo o projeto é perdido
### O QUE É UM DISTRIBUTED VERSION-CONTROL SYSTEM (DVCS)?
- Contém toda a visualização do historial do projeto 
- Todo os historial do projeto é guardado tanto no servidor central como várias copias espelho estão guardadas nos computadores clientes (e.g nos computadores dos desenvolvedores). São feitos vários clones que servem de backup a todos os outros clientes e servidor.
- Permite que repositórios remotos e que se trabalhe em vários branches que de outro modo não seria possivel
### QUE É O GIT?
- Foi desenvolvido pela comunidade Linux, liderada por Linus Torvalds pela necessidade de desenvolver um Distributed version-control system open source.
- GIT guarda “snapshots” de ficheiros (ao contrário de outros VCS que só guardam alterações), ou seja, quando um ficheiro é alterado o GIT guarda esse ficheiro com um commit, excepto se não existirem alterações.
- As snapshots são guardadas localmente e depois atualizadas no servidor. Desta forma é possível trabalhar sem internet já que as alterações são guardadas localmente.
- Git tem integridade checksum. Guarda tudo na base de dados por hashvalue.
- O GIT só adiciona dados, não apaga. É possível reverter commits, sendo assim mais fácil de experimentar coisas sem medo de perder o estado anterior do ficheiro. 	

### QUAIS SÃO OS ESTADOS DO GIT?

- Estados GIT:
- Modified: O ficheiro foi modificado mas não está commited na base de dados
- Staged: O ficheiro modificado está marcado para na sua versão atual para para entrar no próximo commit. (git add <filename>)
- Committed: A informação está guardada na base de dados. 
- Isto leva-nos às 3 areas de um projeto:
- Working directory: Um branch é uma versão do projeto. 
- Staging área
- Diretório GIT (Repositório)

### WHAT ARE THE MAIN COMMANDS USED IN GIT? 

Source: PP DevOps02
- To initialize git use git init on the intended folder for the VCS to track
- Make sure that you are on the right directory. Use DIR to find the current directory and cd <directory> to change to the intended directory .
- To add a specific file to the staging area use git add <filename>
- To add all files to the staging area when committing use -a flag. When doing this there is no need to use git add <filename> command.
- Ex: git commit -a -m ’added new benchmarks’
- To delete a file from git, remove it from the staging area and commit. Use the git rm to remove the file from working directory and untrack it. The next time a commit is done it will be gone and no longer tracked.
- Ex: git rm SETUP
- If the file to be removed was already added to the staging area then remove must be forced with the flag -f.
- To keep the file in the working tree (locally) but remove it from the staging area – keep the file on the hard drive but not have git track it. This is useful if the file is not in gitignore:
- Ex: Git rm –cached README
- To show the commits listed by reverse chronological order:
- Git log

 
### HOW TO WORK WITH REMOTES?

Sources: PP DevOps02
- Remotes are needed in order to collaborate in a git project and to manage repositories, pushing and pulling data to and from these repositories. Remote repositories are versions of the project that are hosted on the internet or networked somewhere. 
### HOW TO SHOW REMOTES?
- To see which remote servers are configured:
- Git remote 
- Flag -v displays more information.
### HOW TO ADD REMOTE REPOSITORIES?
- Git clone command adds implicitly the origin remote. 
- How to add a new remote git repository explicitly?
- Git remote add <shortname> <url> (after add, shortname of the remote and the url). To display the information, git remote -v.
- e.g. git remote add photos https://github.com/paulboone/ticgit

### HOW TO FETCH?

- Git fetch will pull the data from that remote project that is not yet on the local repository. This command does not merge or modify the current local work. 
- Git fetch <remote> (name of the remote)
### HOW TO PULL?
- To pull and merge, use the pull command. Git pull <remote>
### HOW TO PUSH?
- To push the project upstream:
- Git push <remote> <branch>
- e.g. git push origin master will push the local master branch to the origin server. Git push -u origin master to keep the connection between local and remote.
### HOW TO INSPECT A REMOTE?
- To know more about a particular remote:
- Git remote show <remote>
- E.g. git remote show origin
### HOW TO TAG?
- Git can annotate specific point in the timeline of the repository and mark release points:
- Git tag (It automatically tags)

**How to annotate tags?**

- To create annotated tags  (better use -a flag when running this command to include all files)
- Git tag -a v1.4 -m “my version 1.4”
- To show the annotated tags:
- Git show v1.4
- Tags are not pushed with the git push command. They need to explicitly be pushed in the push command. To do this:
- git push origin <tagname>	
- e.g. git push origin v1.5

### WHAT IS GITIGNORE AND HOW TO USE IT? 

### WHAT ARE GIT BRANCHES?
Sources : devops02b.pdf
- Git saves data as a series of snapshots. When making a commit, git stores a commit pointer that stores a pointer to the snapshot of the staged content. This contains the author’s name, email, the typed message and the commits that precede the current.
- With every committed change come the previous commit’s pointer associated. A branch of git is a movable pointer to one of these commits
- The default branch is git is called master.
 
### HOW TO CREATE A NEW BRANCH?
- Git branch testing (testing is the name of the branch)

### HOW DOES GIT KNOW WHAT’S THE CURRENT BRANCH?
- Git keeps a special pointer called HEAD. This is a pointer to the local branch currently in work. The git branch command only crates a new branch. It does not change  from the current branch to the newly created branch.

### HOW TO CHANGE TO AN EXISTING BRANCH?
- Git checkout testing (testing is the name of the branch)
- E.g. git checkout master (changes to the master branch)
- Git checkout change the HEAD pointer to the intended branch. It reverts the files in the working directory back to the snapshot that the master branch is pointing to (the last commit of the master branch). 
- Any changes made on the files will now be on the current branch selected on the checkout and new commits will be built from this new branch.
- Theses 2 branches (master and testing) will be separate. We can checkout to one branch or the other back and forth and these will be separate. When ready, these can also be merged back together.
### How to work with branches?
- E.g. Create a new branch to fix an issue: git branch issue3. Change from master branch to the new branch: git checkout issue3. Work on the new branch to solve the issue. Commit the new snapshot with the issue fixe: git commit -a -m “fixed issue 3”. A new issue arrives and we need to switch back to master: git checkout master. Create and and change to a new branch to fix the new issue: git checkout -b hotfix; git commit -a -m “fixed new issue”. Merge it back to master branch: git checkout master; git merge hotfix
- How to merge branches?
- Select the branch to merge onto: git checkout master (switched to master)
- To merge a branch into another: git merge otherbranch. This will merge otherbranch into the current branch (in this case, master).
- How to delete branched? 
- Git branch -d <branch name>
 
- Conflicts can happen when merging two branches. This occurs when the same part of a file was modified in different ways in both branches. When this happens, gits pauses the merge so the conflict can be solved. To see what files are unable to merge, run the command git status. Files that are unable to be merged are marked as un-merged.
 
-  To solve the conflict, manually change the file by selecting what versions is to keep. This can be done by copying the intended version to the file with the unwanted version part. Then, run git add command to add it to the staging area. This marks the conflict as resolved in git. Then commit the file.
- How to see the available branches?
- Git branch command – besides creating and deleting new branches  also can show the current branches if run without arguments. The branch with an * behind is the currently selected branch.
- Git branch
- To see the last commit on each branch:
- Git branch -v 
- Merged and no merged options can filter this list to branches that have been merged or not
- Git branch -v -- merged
- Git branch -v  -- no-merged
- If a branch on this list appears without a * in front it’s because that branch has already been merged onto another and can be deleted without any consequence or lost information (because it is already merged into another existing branch).
- If you work on your local master branch and someone else pushes their changes to the remote origin master branch in the repository then the history will move forward differently. To synchronize work run git fetch origin. This command will fetch new data from the origin server and update the local repository, moving the origin/master pointer to the new more updated snapshot.
- To push a branch it is necessary to explicitly push the intended branch. That way private branches can be kept and only share some. 
- To push a branch onto origin:
- Git push origin serverflix
- By fetching a new remote-tracking branch it does not bring the local copies of the files. Can’t modify the pointer. To merge this into the currently working branch, run git merge.
- E.g git checkout -b serverflix origin/serverfix. The branch serverfix set up to track remote branch serverfix from origin. Switched to a new branch ‘serverfix’. This gives a local branch to work that starts where origin/serverfix is.
- More to learn about git tools -> https://try.github.io

------------------------------------------------------------------------------------------

Maven
-----

Gradle
------



Virtualization / Vagrant
------------------------

Docker / Containers
------------------

### What are containers?
Containers are environments that isolate memory, filesystem and network resources. They are used as an alternative to virtual machines because these are lighter. These can be set up in a single host and share the operating system of the host. Docker is a solution allows to create containers.

- **Docker image**: A Docker image is a template used to create a docker container. You can create or take an existing image and use it to instanciate a container.

- **Docker container**: A Docker container is the runnable instance of an image. You can create, stop, delete containers. You can also configure the network of a container or attach storage and
also create new images based on a running container. When a container is removed,
all changes made to it are lost.

### How to install Docker? 

You can install and use Docker in several ways (for all, access
https://www.docker.com):

**Docker Desktop** - For running Docker in MacOS and Windows machines. See
https://www.docker.com/products/docker-desktop. This requires Hyper-v on
Windows

**Docker Toolbox** - For some Windows systems that do not support Hyper-v (i.e.,
Home editions) or have Hyper-v disabled. Docker Toolbox will run Docker server
inside a Virtual Box VM. See https://docs.docker.com/toolbox/overview/

**Docker Engine for Linux** - Install Docker on a machine with Linux or on a VM with
Linux. See https://hub.docker.com/search?q=&type=edition&offering=
community&operating_system=linux


### Docker commands:

**Docker information:**

Command: `docker info`

**List local docker images:**

Command: `docker images`

**Get an image from Docker Hub:**

Command Template: `docker pull [image]`

Command Example: `docker pull httpd:2.4`

**Start a docker container:**

Command Template: `docker run [image]`

Command Example: `docker run –d httpd`

**List running containers:**

Command: `docker ps`

**Run a command on the container:**

Command Template: `docker exec -it [container ID] [command]`

Command Example: `docker exec -it 8e32ef0aa1d5 bash`

**Stop a running container:**

Command Template: `docker stop [container ID]`

Command Example: `docker stop 8e32ef0aa1d5`

**Remove a container:**

Command Template: `docker rm [container ID]`

Command Example: `docker rm 8e32ef0aa1d5`

**Remove an image:**

Command Template:`docker rmi [image]`

Command Example: `docker rmi hello-world`


### How to run a container? 

A complete (and common) way of using docker run:

`sudo docker run --name [container name] -i -t [image] [command] [arguments]`
  
- -i and –t setups an interactive session (attaches stdin and stdout to a terminal)
- [container name] is the name of the container that we can use instead of the ID
- [image] is the image of the container
- [command] is a command to be run on the container once it is started
- [arguments] is a list of command arguments
  

Example:

`docker run --name my-ubuntu-container -i -t ubuntu /bin/bash`
- Starts an a shell (/bin/bash) on a container named my-hello-world-container, using
the hello-world image

- To stop the container:
`docker stop my-ubuntu-container`

### Container lifecycle

Containers can be set into different states using:

`docker pause/unpause/start/restart/stop/run/kill [container id]`

Containers are transient in nature. Changes made to a running container are not saved to the image. When you kill a container, all changes are lost. You can create a new image from a running container.

Remember that any change made to the container is lost when the container is killed.
However, you can create a new image from a running container:

`docker commit [container ID] [image name]`

For example:
`docker commit 8e32ef0aa1d5 my_image`

You can also push images to docker hub:
`docker login`

`docker push [image]:[tag]`

- [image] is the image name
- [tag] is a tag of the image

### How to configure DockerFiles?

The configuration of Docker images can be automated using Dockerfiles.

Using Dockerfiles, you can:
- Define a base image (for example, from docker hub)
- Copy/remove/edit configuration files into the image
- Install new tools/applications into the running container
- Essentially run any command on the container after it is started

To create an image from a Dockerfile:

`docker build`

`docker build –f [path-to-dockerfile] –t [tag]`

 
![image](images/dockerCommands.png)
source: https://docs.docker.com/engine/reference/builder/


### What is Docker Compose?

Docker compose allows to define and run multi-container applications. To do that you can specify images and configuration in a simple YAML file **docker-compose.yml**. To get the  container running use the command: 

 `docker-compose up`

 Docker-compose up builds the image from Dockerfiles, pulls images from registries, creates and starts containers, configures a bridge netwword for the containes and handles logs.
 
 This allows to create multiple isolated environments and scale to multiple containers and to a single host or a cluster.

![image](images/dockerComposeYml.png)
![image](images/dockerComposeYml2.png)

Compose file support many configuration options.

Volumes are the preferd mechanism for persisting dat in Docker. They are used to persist database files, share configuration and souce code between host and container. More on volumes. https://docs.docker.com/storage/volumes/


### Compose command references:

**Docker-compose up builds the image from Dockerfiles, pulls images from registries, creates and starts containers, configures a bridge netwword for the containes and handles logs.**

 `Docker-compose up` 

**Build the images:**

 `docker-compose build `

**Start/Stop containers: **

 `docker-compose start/stop <service> `

**List the containes:**

 `docker-compose ps `

**Execute a command inside a service/container (the following example will get an
interactive prompt in the container named nagios):**

 `docker-compose exec nagios sh `

**See the logs generated by the containers:**

 `docker-compose logs <service> `

**Remove stopped service containers:**

 `docker-compose rm <service> `

**List images:** 

 `docker-compose images `

 
 Compose command reference:

 https://docs.docker.com/compose/reference/overview/


 An example of a docker compose that sets up 2 containers provided by Alexandre Bragança:
 https://bitbucket.org/atb/docker-compose-spring-tut-demo/

 This example is a container that will run Tomat and the spring tutorial application
and will run H2. To run this "compostion", execute in the root folder that contains the yml file:

`docker-compose up`

To "enter" in a container, for instance web, type (i.e., the folder that contains the
yml file):

`docker-compose exec web bash`

You can run any linux command inside. Type `exit` to exit.

----------------------------------------------------------------------------------------------

UTILS

