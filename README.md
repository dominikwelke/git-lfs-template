## EEGManyLabs OSF replacement repository template
we use git lfs to store potential larger files in your repository in an efficient way.
it is not currently possible to upload large files (>25mb) to github using the webbrowser, so in order to work with this repository, **you need git-lfs installed** on your system and a minimum level of work on the commandline/terminal. no worries, we will try to guide you through it as smoothly as possible!

### step 0: install git lfs
checkout https://git-lfs.com/ for how to do this.

### step 1: copy this template as a base for your project
use the zip download (green "Code" button on the top right of this screen) if you are less tech savvy.

you can rename the (unzipped) folder in your filesystem, to avoid confusion.
have the new name include your Replication ID.

### step 2: prepare your git folder to point to your account
open your github in a web browser, and create a new empty repository that will host the data.

copy the url of this new repository. this will look something like: 
https://github.com/[YourUsername]/[YourNewRepositoryName]

in a terminal / commandline window, navigate into the downloaded+renamed folder and run the following :
```
git init
git remote add origin https://github.com/[YourUsername]/[YourNewRepositoryName]
git add . -f
git commit -m "initialize lfs repository"
git push --set-upstream origin main
```

you now linked your template folder to the blank repository on your account and set everything up. 
anything you upload will now go there.

### step 3: add your files, make your changes
open the folder and add all your files (use your preferred filebrowser).

don't forget to also update this README file (see below for some info to keep)!

### step 4: commit and push your changes to the github server
in a terminal / commandline window, navigate into the datafolder and run the following (adapting commit message + tag label if needed):

```
git add .
git commit -m "v1.0.0 - code and pilot data [adapt for an appropriate commit message]"
git push
git tag v1.0.0
git push origin v1.0.0
```

this will upload all the files you added or changed to your github server, and create a release with the version tag you specified.
strictly speaking, the tag is optional but we set up the repository so that tags will trigger a "release" and create a zip-file that allows downloading the entire data in one go.
otherwise, people will need to download files individually by hand, or programmatically using the commandline. 

### step 5: done! 
distribute the link to your tagged release in publications etc.

if you need to add more data or update/remove something, simply repeat steps 3 and 4.

## !!KEEP THIS INFORMATION IN THE README.md FILE!!
due to the technical implementation using git lfs, retrieving files via the github website is a bit cumbersome.

### how to download all the data from a webbrowser
for this reason, we build "release assets" allowing you to download a single zip file with all data files in the repository.

you simply have to navigate to the latest release via the "Releases" link on the right pane and download the file called "vX.X.X.zip"

### how to download the data programmatically using git and git-lfs
if you know your git, that should be straightforward to you. 
clone the repository, open a commandline, change into the folder and run:

```
git lfs fetch
git lfs checkout [or git lfs dedup on macos]
```
this will download the data and replace the pointer files with the actual content
