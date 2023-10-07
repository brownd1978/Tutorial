# Steps to take your first time


1. If you have not already done so, [make your working space on the app and data disks:](https://mu2ewiki.fnal.gov/wiki/LoginTutorial#Mu2e_Disks)
1. ```cd /srv/mu2e/app/users/$USER```
1. ```mkdir Tutorial```
1. ```cd Tutorial```
1. ```mkdir -p /srv/mu2e/data/users/$USER/Tutorial```
1. ```ln -s  /srv/mu2e/data/users/$USER/Tutorial out```
1. ```git clone https://github.com/Mu2e/Tutorial```
1. Optional: checkout a tag:  ```git checkout -b vx_y_z_branch vx_y_z```
1. ```muse backing TutorialBacking v01_00_00```
1. ```ls -l``` .  The output should look like:

```
lrwxrwxrwx 1 kutschke mu2e 65 Oct  6 22:23 backing -> /cvmfs/mu2e.opensciencegrid.org/Musings/TutorialBacking/v01_00_00
lrwxrwxrwx 1 kutschke mu2e 38 Oct  6 22:22 out -> /srv/mu2e/data/users/kutschke/Tutorial
drwxr-xr-x 1 kutschke mu2e 12 Oct  6 22:22 Tutorial
```

## Explanation

Here are some comments on steps that may need some explanation.

1. Steps 1 through 4 are just making your working space.  You may choose aname different from Tutorial if you wish but you should work in your space on the /srv disks.
1. You should not put output files on the app disks. So steps 5 and 6 make space for output files on the data disk. For convenience it puts the symbolic link named out in the local directory.
1. Step 8: You will be told if you should work with the head of the repository of checkout a specific branch
1. Step 9. [Muse](https://mu2ewiki.fnal.gov/wiki/Muse) is the Mu2e Software environment.  When you need to choose a version different than v01_00_00 we will edit this file to let you know. So type the command as is.

### Muse ###

The code that you build in the tutorial creates a plugin that will be loaded by the main Mu2e Software, called [Offline](https://github.com/Mu2e/Offline).
Some parts of the Tutorial will also need information from 3 other Mu2e repositories,
[Production](https://github.com/Mu2e/Production),
[TrkAna](https://github.com/Mu2e/TrkAna),
and [REve](https://github.com/Mu2e/REve).
You will learn about these at the appropriate time.
The ```muse backing``` command configures your environment so that Muse knows where to find the include files, libraries and run-time auxillary files from
all of the 4 repositories.
If you recursive follow all of the backing symbolic links, you will discover the all of the include files, libraries and auxillary files.
The details of how it all works is beyond the scope of this part of the tutorial.