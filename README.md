# G2WwiseProject
**Requires Wwise 2019.2.15.7667** and https://github.com/glacier-modding/G2WwiseDataTool

## Included in this project:
* Known audio buses used in HITMAN 3 (more will be added in the future once we figure out their names).
* Example audio objects + events + soundbank (you should make your own soundbank for mod compatibility).
* Switches and States (more will also be added)

## Information
* When you add events into the SoundBank in the SoundBank Manager you will need to untick the "Media" field for each event. This is because the media gets put into the WWEV files which G2WwiseDataTool generates instead of being in the SoundBank itself.

## Plugins
Here is a list of Wwise plugins that HITMAN 3 is using (taken from Init.bnk):
- Wwise Parametric EQ
- Wwise Delay
- Wwise Compressor
- Wwise Peak Limiter
- McDSP FutzBox
- Wwise RoomVerb
- Wwise Flanger
- Wwise Guitar Distortion
- Wwise Convolution Reverb
- Wwise Meter
- Wwise Recorder
- Wwise Stereo Delay
- Wwise Pitch Shifter
- Wwise Harmonizer
- Wwise Gain
- System
- No Output
- Mastering Suite
- Wwise Audio Input
- Wwise Motion

## Automation
If you want G2WwiseDataTool to run automatically when you generate SoundBanks you can setup a Project Post-Generation Step.

Go to SoundBank Manager -> User Settings... -> Tick "Override Project Post-Generation Step".

Double click on "Global closing step" and add the following to it:\
**Description:** Run G2WwiseDataTool\
**Commands:** PathToG2WwiseDataTool -i "$(HeaderFilePath)\Windows\SoundbanksInfo.xml" -o "PathToOutput"

Optionally add **-s** if you want the tool to generate events, switches and soundbank txt files with assembly paths in them

Make sure to replace PathToG2WwiseDataTool, PathToOutput and Windows (if you are on a different platform)