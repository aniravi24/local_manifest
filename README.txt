local manifest and instructions for building omni on a d2 device.

This was built on ubuntu 13.10, but these instructions should be the same on any linux distro as long as you have all the proper dependencies.

This is subject to heavy change, so expect updates, and I'd recommend checking back here. (expect changes in the manifest as well). This is a simple build of omni with no added tweaks.

This guide assumes you are in your omnirom root directory (so wherever omnirom was repo sync'd). This guide also assumes you haven't changed anything yet.
===================================================================================

Steps:

1. Using the manifest in this repository, change the device-specific repository (from d2spr to whichever d2 device you have. The rest of the repositories in that manifest should stay the same..I think.) (Just in case you didn't know, place the local manifest in .repo/local_manifests/ , and if the local_manifests directory doesn't exist, create it.)

2. Use my device repositories as a guide to set up yours. I decided that I'm just going to have my repositories branched into two separate branches. My manifest already has my android-4.4 branch, which is basically cm but has only the necessary changes to build omni. (I'll be constantly syncing this with cm) You're welcome to just use the d2-common from my repository as it is in my manifest or you can do what you want :P The personal branch is just some of my own stuff. (My device might be different from yours since mine is cdma, but you should check if yours is gsm or cdma) (Make sure to set up both d2-common and your specific d2 device repository, using mine as a guide. There should only be a few changes that are actually different between mine and yours, if any) (I made a commit called "mass commit to set up build omni" in both the device-specific repo and the d2-common repo. If you click on that, it will show you all the changes necessary to set up build in one convenient page, BUT make sure to look at the newer commits because things change.)

4. Before starting the build, after running . build/envsetup.sh, run "repopick 3197 4748 4749 4750 4753 4984 5037 5073 5074 5075 5076 5078 5080 5081 5082 5083" without the quotes. Also, go into the directory hardware/qcom/media-caf and run "git fetch https://gerrit.omnirom.org/android_hardware_qcom_media-caf refs/changes/77/5177/1 && git cherry-pick FETCH_HEAD" (without the quotes) (These commands picks stuff from omni's gerrit that haven't been merged yet. This is subject to change as omni merges stuff, so expect this to change, maybe even right after this readme is uploaded to github.) You will have to run both of these commands every time you repo sync because repo sync will overwrite the changes. (The alternative to the second command is to change the default manifest itself.. which I'd rather not do.)
