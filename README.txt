local_manifest
==============
IGNORE THESE INSTRUCTIONS FOR THE TIME BEING. I'M ALMOST FINISHED WITH A BETTER WAY TO DO THIS (INCLUDING A BETTER MANIFEST), AND ESPECIALLY FIXING STEP 3 IN THE PROPER MANNER. I SHOULD HAVE THE NEW INSTRUCTIONS UPLOADED SOON.

local manifest and instructions for building omni on a d2 device, using the necessary CAF items. (Omni can be built in a much easier fashion without CAF, but there's a loss of functionality if CAF isn't used.)

This is subject to heavy change, so expect updates, and I'd recommend checking back here. (expect changes in the manifest as well). This is a simple build of omni with no added tweaks.   

This guide assumes you are in your omnirom root directory (so wherever omnirom was repo sync'd). This guide also assumes you haven't changed anything yet.  

1. Using the manifest in this repository, change the device-specific repository (from d2spr to whichever d2 device you have. The rest of the repositories in that manifest should stay the same..I think.) (Just in case you didn't know, place the local manifest in .repo/local_manifests/ , and if the local_manifests directory doesn't exist, create it.) 

2. After you have synced your omnirom repository, go to system/core/rootdir and open init.rc . Find the line that says, import.slim.rc and replace the word slim with omni. So it should say "import init.omni.rc" (without the quotes). 

3. Go to frameworks/av/services/audioflinger and open Tracks.cpp . On line 86, replace "audio_is_compress_voip_format(format)) ?" with "audio_is_supported_compressed(format)) ?" (without the quotes) (I have submitted this to omni's gerrit, this step may change depending on the result of that) EDIT: Looks like this change only applies to us because we are using slim's system/core. Once I can use all of omni's repositories to build even with CAF, this step won't be necessary.

4. Use my device repositories as a guide to help you set up yours. (My device might be different from yours since mine is cdma, but you should check if yours is gsm or cdma) (Make sure to set up both d2-common and your specific d2 device repository, using mine as a guide. There should only be a few changes that are actually different between mine and yours, if any) I'd recommend not cloning my repository because I may not update this github fork very fast. I'd recommend just changing your device repository directly with the same changes I made in my github. (I made a commit called "mass commit to set up build omni" in both the device-specific repo and the d2-common repo. If you click on that, it will show you all the changes necessary to set up build in one convenient page) 

5. Before starting the build, after running . build/envsetup.sh, run "repopick 2687 3269 3271 3452 3890" without the quotes. (This command picks stuff from omni's gerrit that haven't been merged yet. This is subject to change as omni merges stuff, so expect this to change, maybe even right after this readme is uploaded to github.) You will have to run this repopick command every time you repo sync because repo sync will overwrite the repopick changes. 
