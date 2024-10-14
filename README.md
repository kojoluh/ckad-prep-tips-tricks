# CKAD-tips-and-prep-points

## Vim Setup

Persist Vim settings in .vimrc
The following settings will already be configured in your real exam environment in ~/.vimrc. But it can never hurt to be able to type these down
We look at important Vim settings if you like to work with YAML during the K8s exams.

Settings
First create or open (if already exists) file .vimrc :

vim ~/.vimrc
Now enter (in insert-mode activated with i) the following lines:

set expandtab
set tabstop=2
set shiftwidth=2
Save and close the file by pressing Esc followed by :x and Enter.

## Backup
Always make or create a backup of your work. especially the yaml files.
```
# create a pod
k run tip1 --image=nginx --dry-run-client -oyaml > tip1.yaml
# copy the yaml to backup
cp tip1.yaml tip1.yaml.backup

```

## Search and Replace in Vim
Use '/' to search and 'n' to go to the next match.
Use 'shift+C' to replace the word under the cursor.
Use 'shift+R' to replace all matches in the file.

Eg. change the container name in a pod or a deployment yaml file.
```
k create deployment tip2 --image=nginx --dry-run=client -oyaml > tip2.yaml
```

```
# search and replace
sed -i 's/tip1/tip2/g' tip1.yaml
```

## Append Text at the and of a line
Use 'shift+A' to move the cursor to the end of a line and 'i' to insert text at the cursor position.

E.g Add tip3 to the end of the container name in tip3.yaml

vim tip3.yaml

use / to search for the container name
use shift+A to move the cursor to the end of the line
use i to insert the text (tip3) at the cursor position

```
# append text at the end of a line
sed -i 's/$/nginx/' tip3.yaml
```


#
