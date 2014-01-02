local manifest and instructions for building omni on a d2 device, using the necessary CAF items. (Omni can be built in a much easier fashion without CAF, but there's a loss of functionality if CAF isn't used.)

This was built on ubuntu 13.10, but these instructions should be the same on any linux distro as long as you have all the proper dependencies.

This is subject to heavy change, so expect updates, and I'd recommend checking back here. (expect changes in the manifest as well). This is a simple build of omni with no added tweaks.   

This guide assumes you are in your omnirom root directory (so wherever omnirom was repo sync'd). This guide also assumes you haven't changed anything yet.  
=============================================================================================================================================
Steps:

1. Using the manifest in this repository, change the device-specific repository (from d2spr to whichever d2 device you have. The rest of the repositories in that manifest should stay the same..I think.) (Just in case you didn't know, place the local manifest in .repo/local_manifests/ , and if the local_manifests directory doesn't exist, create it.) 

2. Use my device repositories as a guide to help you set up yours. (My device might be different from yours since mine is cdma, but you should check if yours is gsm or cdma) (Make sure to set up both d2-common and your specific d2 device repository, using mine as a guide. There should only be a few changes that are actually different between mine and yours, if any) I'd recommend not cloning my device repository because I may not update this github fork very fast. I'd recommend just changing your device repository directly with the same changes I made in my github. (I made a commit called "mass commit to set up build omni" in both the device-specific repo and the d2-common repo. If you click on that, it will show you all the changes necessary to set up build in one convenient page)

3. Before starting the build, after running . build/envsetup.sh, run "repopick 2687 3269 3271 3452 3739 3749 3890 4342 4344" without the quotes. (This command picks stuff from omni's gerrit that haven't been merged yet. This is subject to change as omni merges stuff, so expect this to change, maybe even right after this readme is uploaded to github.) You will have to run this repopick command every time you repo sync because repo sync will overwrite the repopick changes. 
