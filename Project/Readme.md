### Bash script to extract all the midi tracks into one abc file with an empty line
### between tracks to match the DutchFolkTunes dataset's format

find private_melodylines -iname '*.mid*' -print0 | sort -zn | xargs -0 ls | while IFS= read -r line
do
   ../Abcmidi-20191209/midi2abc "$line"
   echo
done >private_abc/all.abc
