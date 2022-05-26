# ManageImageFiles
This is a PS script to move and sort image files based on the Taken Date attrribute in the metadata.

The original file is at https://blog.jongallant.com/2021/03/organize-photos-powershell/

Here’s what it does.

+ Loops through each file in the source directory looking for a date to use
    + If file has EXIF Data Taken, then it uses that
    + If it doesn’t, then it finds all properties that have “date” or “created” in them and uses the oldest date.
 + If the source file and destination file have the exact same path, then it skips that file.
 + If the destination directory already has a file with the same name, then it renames the file.
 + Moves the file from the source directory to the destination directory.

The script requires PS V7 or greater. Using PS v5.1 gives a ParseExact error on the date extracted from TakenDate

Usage:

./MoveImages.ps1 <SourceDirectory> <DestinationDirectory>

    
