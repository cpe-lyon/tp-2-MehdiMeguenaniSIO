Mehdi Meguenani 3ICS

# Exercice 1. Variables d’environnement 

1. Photo 
2. La variable d'environement qui permet a cd de nous renvoyer vers le répertoire est $HOME 
3. La variable LANG détermine la langue utilisé par le système afin de communiquer avec l'utilisateur. La variable PWD permet de lister le répertoire qui est utilisé. La variable OLDPWD permet enregistre le répertoire précédent et donc d'y accèder a l'aide de cd-. La commande shell interprète les commande de l'utilisateur 
4. Photo 
5. La commande bash permet de créer un nouveau shell , la variable $MY_VAR n'existe pas car c'est une variable local que l'on a créer dans un autres session
6. En la transformant en variable d'environement la variable est disponible a partir de tous les shell ou interpréteur.
7. Photo. 
8. Il faut ecire echo "Bonjour a vous, $NOM" (Photo)
9. En faisant usnet on supprime totalement la varianble, elle n'existe plus. Si la varaible est vide elle existe toujours mais ne renverra rien.
10. (PHOTO)

# Exercice 2. Contrôle de mot de passe

```
#!/bin/bash
PASSWORD=test123
read -p 'Saisissez un mot de passe : ' -s pass
if [ $pass = $PASSWORD ]; then
        echo "C'est le bon mot de passe"
else
        echo "Se n'est pas le bon mot de passe"
fi

```


# Exercice 3. Expressions rationnelles

``` 
#!/bin/bash

function is_number()
{
re='^[+-]?[0-9]+([.][0-9]+)?$'
if ! [[ $1 =~ $re ]] ; then
        return 1
else
        return 0
fi
}

is_number $1

echo "$?"
```
# Exercice 4. Contrôle d’utilisateur

```

#!/bin/bash
function test(){
        if  [ -z $1 ]: then
                echo "Utilisation : $0, nom utilisateur"
        else
                grep -F "$1" /etc/passwd > test1
                        if [ $? != 0 ]; then
                               echo "L'utilisateur n'exsite pas " 
                        else 
                                echo "L'utilisateur existe "
                        fi
       fi
}

test $1 

```

# Exercice 5. Factorielle




