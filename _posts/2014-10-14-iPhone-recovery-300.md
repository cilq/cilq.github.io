---
published: false
---

## iPhone recovery 300

_A few weeks ago my girlfriend had some trouble updating her iPhone, so I came to help. Of course I could only lose._

It all started with the update to iOS 8 failing because of insufficient storage space. After removing some pictures and music from the device the update would start at least. The update failed somehow and apparently left some garbage behind, because afterwards there was not enough space left to repeat the update.

During my iPhone days I was quiet used to recovering my phone from backups when I was jailbreaking the device. Wiping it would then trigger iTunes to request a clean setup or a restore from a specified backup. Naturally, I recommended her to do the same with her phone to complete the update. Everything went fine up until the point when the iPhone contacted iTunes after the wipe and did a backup - overwriting the previous one without asking, of course.

So there we were - iOS installed on the device, but all application data was lost. Of course Time machine or iCloud backups weren't set up and thats how the "fun" stuff started.

### Step 1 - Restoring the backup
Using DiskDrill I scanned the complete hard drive, but would not find useable files to undelete. The full block scan however revealed a lot of so called "db3" files. Having some experience with iOS and OSX development, I immediately associated sqlite3 with that - and I was right. Half an hour later, I had about 2 gb of sqlite3 files. As it turns out, not every developer uses the sqlite3 storage backend and for those apps, I wasn't able to rescue any preferences.

### Step 2 - Filtering the relevant files
To find out which files are potential backup candidates, you have to know the structure of the applications sqlite3 database. For that I questioned my girlfriend for applications she really needed to be restored and some details about them in order to guess some keywords. I also asked her to create a new backup and create a snapshot of it just to be save. I than grepped through all of those backup files for "SQL??"
> grep command

and already found some of them.
fake entry -> backup -> grep

### Step 3 - Recovery magic
backup replace -> restore -> happy

### Step 4 - Summary
BACKUP your Backups!!
no encryption?
