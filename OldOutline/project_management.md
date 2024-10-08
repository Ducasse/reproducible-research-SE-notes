## Project Management


### Private repositories. What?

@private_repos

Firstly, private repository does not entail, by any means, non collaborative repository.
They work exactly the same as public repositories except commits are only available to select collaborators.

In the early stages, your project may be geared towards a very specific goal and you may not want to display the incremental developments to the public but simply collaborate privately with some people.
From this perspective, private repositories can be seen as hidden development branches of the project.

!!note You can always turn a public repository into a private one and vice versa
!!note Free private repositories for academics
!!todo Remark on Travis for private repos
!!todo Warning that when the repo goes public, all previous commits will be accessible to anyone, so be politically correct.

### Setting


As a first step, you could create a public repository that may simply be used as a showcase for the project, for the world to know you are working on something and be the place where you provide stable releases.

!!note Write a good README

In parallel, you can develop the project in a private repository.
To make releases available once ready, you must add the public repository to the remotes of your private repository.

### In practice


Create the public and private repositories on GitHub.

On GitHub, create a public repository and copy its URL.
Create an empty \(No Readme, .gitignore, Licence\) private repository and clone it on your computer
```language=bash
$ git clone https://github.com/user_name/private_repo.git
```


Add the public repository to the remotes of your private repository
```language=bash
$ git remote add [public_remote_name] https://github.com/user_name/public_repo.git
```


Check you have two different remotes
```language=bash
$ git remote
origin
public_remote_name
```


Pull the content of the public repository to the private one
```language=bash
$ git pull [public_remote_name] master
```


Start tracking the files you just pulled
```language=bash
$ git add -A
```

!!note "-A" for tracking all files tracked file

Commit the updated state of the private repository
```language=bash
$ git commit -a -m "Initial synchronization of public and private repositories"
```

!!note "-a" for gathering every \(tracked\) file in the same commit, "-m" for assigning a message to this commit

Push i.e. save these changes in the history of the private repository
```language=bash
$ git push origin master
```


First stage is complete, public and private repositories are synchronized and both share the same initial history.
Your private project can now begin.

Tell GIT not to track and version specific files/folders

For some reasons you may not want specific folders, files or file types to be revealed to the public world.
One main reason is that some files are pointless to share \(e.g. .aux or .log\), another reason could be that they are heavy files or because you work with sensitive data that must be kept locally.

For this purpose, you can tell GIT not to track a list of different files/folders.

Create a .gitignore file
```language=bash
$ touch .gitignore
```


Then edit it with your favorite text editor say Vim
```language=bash
$ vim .gitignore
```


As an example, to avoid tracking the "confidential/" folder and all Python notebooks add the following lines to the .gitignore file
**"
confidential/
*.ipynb
**"

!!note You can find [more examples](­https://www.atlassian.com/git/tutorials/saving-changes/gitignore) about .gitignore files.
!!note You could have used the "Add .gitignore" button at the creation of the repo on GitHub, to automatically exclude common useless files relative a language, e.g. ".log", ".aux" ... with LaTex.

Good practice

For the sake of sanity, it is highly recommended to create a development branch in the private repository
```language=bash
$ git checkout -b dev
```


so that the "master" branch in the private repository plays the role of buffer between the "dev" branch of the same repository and the "master" branch of the public repository.