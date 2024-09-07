step-by-step guide to integrating Git LFS for handling large binary files:

### 1. Install Git LFS
If you don’t have Git LFS installed, follow these steps:
- *MacOS*: Use Homebrew to install Git LFS:
  bash
  brew install git-lfs
  
- *Linux*: Use package managers like apt or yum:
  bash
  sudo apt install git-lfs
  
- *Windows*: Download and install Git LFS from the official website: [Git LFS](https://git-lfs.github.com/).

Once installed, initialize Git LFS for your repository:
bash/terminal
git lfs install


### 2. Track Large Files
Choose the file extensions or specific files to track with Git LFS. For example, if you're dealing with .bin files:
bash
git lfs track "*.pdf"


This command tells Git LFS to track all .pdf files in your repository.

### 3. Add Files to Repository
Now add the large binary file to the repository using Git commands:
bash
git add .
git commit -m "Add large binary file tracked by LFS"


### 4. Push Files to Remote Repository
Once the files are committed locally, push them to the remote repository. Ensure that the remote repository is initialized or exists:
bash
(First time Push into repo use command below)
$ git push --set-upstream origin lfs
(file will upload as below)
Uploading LFS objects:  50% (1/2), 118 MB | 380 KB/s
         (or if branch present in repo use below command)
git push origin lfs


### 5. Clone the Repository on Another Machine
On another machine, clone the repository to verify that the binary files are downloaded correctly:
bash
git clone <repository_url>
(<repository_url>  Available in Git under Code as HTTP)


When you clone the repository, Git LFS will ensure that the binary files are pulled down as expected.

### 6. Verify Git LFS is Working
You can verify which files are tracked by Git LFS by running:
bash
git lfs ls-files


That’s it! You've integrated Git LFS into your project for managing large binary files efficiently.