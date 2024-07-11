## Tuesday

### [New clowes.blog post](https://clowes.blog/2024/07/09/i-love-the.html)

> I love the wonderful terminology of American music in the 1940’s. [[Crooner]], [[Bobby soxer]], doo-wop, hep cat, zoot suit, rag cutter, jitterbug, be-bop, boogie-woogie, hepcat, juke joint, swooner, moldy fig, killer-diller.

***

New notes today:
- [[Crooner]]
- [[Bobby soxer]]
- [[Nina Simone]]

***

I need to find out the [HTML colour code](https://htmlcolorcodes.com) of what's on my screen surprisingly often.

My current work flow is taking a screenshot and then going to a website and getting the code from there. But I've been meaning to get an app that cut out the middle-person for quite a while. I've finally installed one: [ColorSlurp](https://colorslurp.com).
## Wednesday

### Removing GPS location data from photos

One of the downsides of publishing my notes to the web is that I need to be careful of privacy. The main privacy risk I have is GPS location data in my photos. I don't mind keeping location info for photos when I'm out and about. It's pretty obvious the area where I live. But I'd ideally not like the location of my actual house out there. So I need to find a way to remove GPS EXIF data from photos taken at my house.

You can do it in the Preview app manually. And there are apps for it. But that's not ideal. And I love a shell script. So I've written one that removes the GPS EXIF data using [exiftool](https://formulae.brew.sh/formula/exiftool) and then moves it to my Obsidian `files` folder.

```#!/bin/zsh

# Source and target directories
SOURCE_DIR="/Users/elliotclowes/Dropbox/Auto/Image - Remove GPS info and move to Obsidian files"
TARGET_DIR="/Users/elliotclowes/Dropbox/Notes/files"

# Check if exiftool is installed
if ! command -v exiftool &> /dev/null
then
    echo "exiftool could not be found. Please install exiftool using 'brew install exiftool'."
    exit 1
fi

# Check if the source directory exists
if [ ! -d "$SOURCE_DIR" ]; then
    echo "Source directory $SOURCE_DIR does not exist."
    exit 1
fi

# Check if the target directory exists, create it if it doesn't
if [ ! -d "$TARGET_DIR" ]; then
    echo "Target directory $TARGET_DIR does not exist. Creating it now..."
    mkdir -p "$TARGET_DIR"
fi

# Iterate over each photo in the source directory
for photo in "$SOURCE_DIR"/*; do
    if [ -f "$photo" ]; then
        echo "Removing GPS EXIF data from $photo..."
        exiftool -gps:all= "$photo"
        echo "Moving $photo to $TARGET_DIR..."
        mv "$photo" "$TARGET_DIR"
        echo "Done."
    else
        echo "File $photo does not exist or is not a regular file."
    fi
done

echo "All files processed."
```

***

## Thursday

### Oliver Burkeman book

Oliver Burkeman has a new book out: “ MEDITATIONS FOR MORTALS: Four Weeks to Embrace Your Limitations and Make Time for What Counts”.

Here’s a description: 

> Meditations for Mortals is intended as a ‘retreat of the mind’: four weeks of digestible daily chapters – though of course you don’t have to read it that way – offering perspective shifts and practical tools for confronting reality and taking action on what matters most to you, while navigating an increasingly volatile and anxiety-inducing world. (Some chapters are based on greatest hits from The Imperfectionist; there’s also a ton of new material.) The structure is designed to let the outlook I call ‘imperfectionism’ really sink into your bones, where it can make a concrete and lasting difference.

After I read his last book, XXXX, I[ created an 8 week plan](https://blot.blog/2024/04/27/4000-weeks-embracing-limits-for-a-fuller-life/) you could follow to implement its ideas. Its sounds like his new book does something similar. 

*** 

Lesson of the morning: always set notification reminders for appointments. I didn’t notice I had a 9AM dentist appointment today and I’ve come into work at London 😬