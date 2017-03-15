# Sony Xperia M4 Aqua AOSP #

### Installing Repo ###

```bash
# Make a directory where Repo will be stored and add it to the path
$ mkdir ~/bin
$ PATH=~/bin:$PATH

# Download Repo itself
$ curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo

# Make Repo executable
$ chmod a+x ~/bin/repo
```

### Initializing Repo ###

```bash
# Create a directory for the source files
# This can be located anywhere (as long as the fs is case-sensitive)
$ mkdir android
$ cd android

# Install Repo in the created directory
# Use a real name/email combination, if you intend to submit patches
$ repo init -u https://github.com/SonyM4/platform_manifest -b android-7.1.1
```

### Downloading the source tree ###

The downloaded data is around 20 GB, and for a successful build you need 100 GB free hard disk space.
Depending on your Internet connection, it can take quite a long time to download the source code.
When the download has finished you have the basic AOSP source code on your computer.

```bash
# Let Repo take care of all the hard work
$ repo sync
```

## Building ##

Now you are ready to build AOSP images that can be flashed to a device.
To do this, you have to point out your specific device and then start building the images.

```bash
# Enter the following commands:
$ source build/envsetup.sh && lunch
# When prompted, pick the number corresponding to your device in the list displayed and press enter.
# To start the build, type:
$ make –j <insert the cpu thread number of your computer>
```
