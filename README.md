# Minitest #1 Linux - AP Hogeschool Elektronica-ICT
Small bash script we had to make for a test

<h1>The script</h1>
<p>First clear the terminal/console with a command and show a menu where the user can choose between 3 options.</p>
a) Create a file<br>
b) Check if a file exists<br>
c) Remove a file<br><br>

``` shell
#!/bin/bash

clear

echo "a) bestand aanmaken"
echo "b) bestand checken"
echo "c) bestand wissen"

read -p "Geef de letter in van u keuze> " keuze
```

<br>

<h2>Part "a"</h2>
<p>If the user chooses option "a"</p>
<p>User provides the name of the file they would like to create and a number. The number provided by the user represents how many files are being created. Example user inputs 4, 4 files are create as following: file0.txt file1.txt ... file3.txt</p><br>

``` shell
teller=0

if [ $keuze = "a" ]; then
	clear
	read -p "Naam> " naamfile
	read -p "Getal> " getalfile
	while [ $teller -lt $getalfile ]
	do
		touch $naamfile-$teller.txt
		teller=$((teller+1))	
	done
	ls
	echo "$teller Bestand(en) aangemaakt"
fi
```

<br>

<h2>Part "b"</h2>
<p>If the user chooses option "b"</p>
<p>User provides the full path of the directory they would like to check a file in. A command coded in the script shows what files and directories there are in the provided path. User inputs the filename and gets the output if it exists or not.</p><br>

``` shell
if [ $keuze = "b" ]; then
	clear
	read -p "In welke directory moeten bestanden gecheckt worden?> " checkdir
	ls $checkdir
	read -p "Bestandsnaam> " checkfile
	cd $checkdir
	if [ -e $checkfile ]; then
		echo "Bestand bestaat"
	else	
		echo "Bestand bestaat niet"
	fi
fi
```

<br>

<h2>Part "c"</h2>
<p>If the user chooses option "c"</p>
<p>User provides the full path of the directory they would like to remove a file from. A command coded in the script shows what files and directories there are in the provided path. User inputs the filename and the script removes the file and show a message that the file was removed.</p><br>

``` shell
if [ $keuze = "c" ]; then
	clear
	read -p "In welke directory moet een bestand verwijderd worden?> " removedir
	ls $removedir	
	read -p "Bestandsnaam> " removefile
	cd $removedir
	rm $removefile
	echo "Bestand gewist"
fi
```
