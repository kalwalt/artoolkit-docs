#Using NFT on ARToolKit for Unity

##Introduction
ARToolKit for Unity supports natural feature tracking (NFT), which will be familiar to users of ARToolKit for mobile and desktop platforms. ARToolKit's NFT uses the natural features of flat, 2D, textured surfaces. You can find collected information on ARToolKit's NFT capabilities on the page [ARToolKit NFT][nft].

##How to use an existing NFT dataset in Unity
NFT mode is enabled by adding an "ARMarker" script to the scene and choosing "NFT" as the marker type. This makes available an additional field where you can enter the name of the dataset. The actual NFT data which are generated by the genTexData utility should placed into the folder "Assets/StreamingAssets" of your Unity project.

The SDK includes an example dataset (file names: gibraltar.iset, gibraltar.fset, gibraltar.fset2). The example NFT dataset can be enabled by entering the basename of the datafiles (in this case: gibraltar) into the "dataset" field.

![NFT options panel.][nft_options]

##Generating new NFT datasets
An NFT dataset must be generated for each surface you wish to track. This is done using the genTexData command-line tool. The ARToolKit NFT for Unity Windows installer / Mac OS X .zip file include genTexData in the bin/ directory. See [Training ARToolKit NFT to a new surface][train_nft] and [ARToolKit NFT Utilities: genTexData][gentexdata] for usage.

*The NFT dataset format changed with ARToolKit Professional v5.0 (incorporated into ARToolKit for Unity v5.0) so any datasets created with previous versions of the tools will need to be regenerated if being used with ARToolKit for Unity v5.0 and later.*

##Deployment Notes
If you are not using NFT markers, be sure to remove any NFT datasets from the StreamingAssets folder before final build to avoid unwanted extra disk usage.

[nft]:/ARToolKit_NFT "wikilink"
[nft_options]:/File:ARToolKit_for_Unity_-_NFT_options.png "wikilink"
[train_nft]:/Training_ARToolKit_NFT_to_a_new_surface "wikilink"
[gentexdata]:/ARToolKit_NFT_Utilities:_genTexData "wikilink"

[Category:ARToolKit for Unity](/Category:ARToolKit_for_Unity "wikilink")