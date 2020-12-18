# Minitest #1 Linux - AP Hogeschool Elektronica-ICT
Small bash script we had to make for a test
<h1>What did we have to make?</h1>

<h1>The script</h1>
```
#!/bin/bash

clear

echo "a) bestand aanmaken"
echo "b) bestand checken"
echo "c) bestand wissen"

read -p "Geef de letter in van u keuze> " keuze
```

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
	
if [ $keuze = "c" ]; then
	clear
	read -p "In welke directory moet een bestand verwijderd worden?> " removedir
	ls $removedir	
	read -p "Bestandsnaam> " removefile
	cd $removedir
	rm $removefile
	echo "Bestand gewist"
fi
</code>
