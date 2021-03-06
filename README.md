
# Synthstrom Deluge maintenance utils

## Fix missing samples
### Platforms
- Mac OSX, Linux, Windows 
### Want to fix your samples in Songs, Kits and Synths after moving around folders on your SD card? 
- Analyzes your XML Files and looks for missing samples. 
- Fixes your XML Files and generates full report. 
- A backup folder is created for overwritten files: _MISSING_SAMPLES_FIXER_ARCHIVE
- Supported audio file extensions: .wav, .aif, .aiff
- Samples with a '~' in their name are skipped: http://forums.synthstrom.com/discussion/1234/strange-sample-names-in-xml-files
  
### Run as NPM app
- Clone this repository
- cd missingsamplefixer
- npm install
- electron .
### Build app
- npm run pack

## samplefixer.sh

### Platforms
- Mac OSX, (Linux, Windows Shell)

### Want a tidy sample library? 
- Get rid of "UNSUPPORTED" messages in the Synthstrom Deluge file browser
- Place this script in the root directory of the SD Card
- Consider a backup before running any write commands
- Supported audio file extensions: .wav, .aif, .aiff

### Use cases
- Analyze all data 
`sh samplefixer.sh convert_clean`

- Fix all data
`sh samplefixer.sh convert_clean_write`

### Options

Default path is the Deluge SAMPLES folder. You may pass a directory as an optional parameter. Pass it as relative path, e.g. `sh samplefixer.sh clean RESAMPLE/`, to narrow the search space. 

- **convert [PATH]**
List WAV files below 44kHz. Inspect for fishy data formats as well.

- **clean [PATH]**
List non-audio files and WAV samples Synthstrom Deluge might not be able to load.

- **convert_write [PATH]**
Convert WAV files lower than 44kHz to 44kHz/16bit. No backup! Attention, disk usage might increase a lot.

- **clean_write [PATH]**
Delete non audio files and WAV samples Synthstrom Deluge might not be able to load. No backup!



## archive_unused_recordings.rb

### Platforms
- Mac OSX, (Linux, Windows Shell)

Script to remove unused samples on the Deluge SD Card
currently only removes recordings
`ruby archive_unused_recordings.rb`
- recommended: create a backup of the SD Card first
- place this script in the root dir of the SD card
- all delete candidates are moved to the folder '_ARCHIVED', paths are preserved 


