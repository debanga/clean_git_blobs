# Remove Unwanted Blobs from Git Commit History

## How to clean blobs (and previous commits) of large files that you accidentally commited to git?

### Removing unwanted git blobs

#### Step 1: List the blobs
Source: https://gist.github.com/debanga/6d5ffae603ec437ad80ed3c9c268c57b

```
1. $ sudo chmod +x git_list_blobs.sh

2. $ ./git_list_blobs.sh
```

#### Step 2: Select the blob (and previous commits) you want to remove

E.g.

Say, blob list looks like this and you want to remove all blobs of `DataManager.cpp`
...
100644 blob 2e293f4f101d2683722b9d6a748785fdbd423cba   37190    Source/DataManager.cpp
100644 blob 8d6aafe62034647427c5a97a6c13bdea851a7461   36643    Source/DataManager.cpp
100644 blob 05801aeada4bf3f52a71c43d47a6dff390affb51   30308    Source/MainWindow.cpp
100644 blob 6d5ebc0b617489578dbb8ad3e6dd4663c5f830bb   29550    FtReader/ATIDAQ/xmlrole.c
...


#### Step 2: Remove the blobs

Source: https://gist.github.com/debanga/1c537d38af9d4f48565db2720e3a4ae7

Also, please refer to https://ownyourbits.com/2017/01/18/completely-remove-a-file-from-a-git-repository-with-git-forget-blob/ for precautions.

```
1. $ sudo wget https://raw.githubusercontent.com/nachoparker/git-forget-blob/master/git-forget-blob.sh -O ./git-forget-blob

2. $ sudo chmod +x git-forget-blob

3. Now, commit and push the repo.

4. $ ./git-forget-blob.sh Source/DataManager.cpp  # <blob_name> from Step 1

5. $ git remote add origin git clone https://uname:pw@bitbucket.org/xxx/xxx.git

6. $ git push --set-upstream origin master # Use --force if needed

```
