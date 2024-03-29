# Prettress SM

Prettress SM stands for PRETTy progRESS Sprite Maker. This tool, written in
python, enables you to make sprite icons built step-by-step. Namely a progress
bar, a volume icon or a battery icon.

To use it, you need a layout image, which will be the base of your sprite and an
image of the progressive part of your sprite when "it is full". You can specify
either the number of steps you want for your sprite, or a threshold (number of
pixels to delete at each step) and the script will do the job.

You can also add "state" images. Each state image will be merged with each step
of the generated sprite. This can be useful to add state information to a
battery icon for instance (charging/discharging).

## Usage

    prettress-sm [OPTION]... [OUTPUT-FILENAME-PATTERN]

### Options

* **-l, --layout**=*LAYOUT-IMAGE*
    * An image file
* **-p, --progress**=*PROGRESSION-IMAGE*
    * An image file
* **-i, --steps**=*NB-STEPS*
    * The minimum that makes sense is 2 (or 1 if you use states)
* **-t, --threshold**=*NB-PIXELS* 
    * The minimum that makes sens is 1
* **-s, --state**=*STATE-IMAGE,...*
    * You can specify multiple comma-separated filenames
* **-b, --black-is**=*COLOR*
    * Recolor black pixels (#000000) with the given color
* **-w, --white-is**=*COLOR*
    * Recolor white pixels (#ffffff) with the given color
* **-k, --skip-steps**=*STEP,...*
    * Do not create images for the given comma-separated steps list
* **-f, --force**
    * Overwrite files if already exists
* **-V, --verbose**
    * Write more information to stdout
* **-q, --quiet**
    * Do not write anything to stdout
* **-Q, --fail-silently**
    * Do not write anything to stderr
* **--dry-run**
    * Echo filenames that would be created
* **-v, --version**
    * Print version information

### Output filename pattern

The following placeholder can be use :

* **%l :** Layout filename without extension ;
* **%i :** Step number (starting with 0 (empty) to NB-STEPS - 1 (full)) ;
* **%s :** State filename without extension ;
* **%x :** File extension of the layout image

The default filename pattern is : `%l-%i-%s.%x`
