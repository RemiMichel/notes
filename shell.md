# Shell

## Split | Concat d'une variable selon chaine de caractères
Voici une des façons que j'ai retenues pour splitter une variable dans un script.  
Le principe est de setter la variable global $IFS et de la remettre pour concaténer.
```shell
IP=192.168.100.56
# Swap des IFS
OLD_IFS=$IFS
IFS='.'
# Split de la chaine selon l'IFS
read -a ip_digits <<< "$IP"
# Set l'ancienne valeur
IFS=$OLD_IFS
# Concaténation
SUBNET="${ip_digits[0]}.${ip_digits[1]}"
END_IP="${ip_digits[2]}.${ip_digits[3]}"
# Print
echo $SUBNET
# 192.168
echo $END_IP
# 100.56
```
## Récupérer l'IP de la machine
```shell
IP=$(hostname -I)
```
## Exporter une variable d'environnement
```shell
export VARIABLE=<SOMETHING>
```