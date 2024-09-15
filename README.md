
Le CTF se trouve à cette adresse : 
https://www.andapirate.com/wtf

## Challenge 1:

On a donc accès à une page nous demandant un code secret pour accéder à la suite du challenge et un indice nous conseillant d'utiliser notre inspecteur f12 (ouvrir les outils de développement)

Personnellement je suis allé dans la partie "Eléments" puis j'ai eu accès à ces 3 parties : 

![[Pasted image 20240915173332.png]]

Ici nous allons nous intéresser à la partie `head`, je clique donc dessus pour avoir plus de détails sur sa composition puis en lisant les métadonnées (`<meta>`) j'en trouve une nommé "Preuve WTF" avec comme content le code à entrer. 

**Flag :** `wtf0924`


## Challenge 2:

On arrive sur un challenge nommé public folder avec comme indice "motdepasse.txt". J'en conclus qu'il faut faire du fuzzing. 
Ayant un indice je décide d'essayer l'url "https://www.andapirate.com/wtf/motdepasse.txt" qui ne mène à rien mais quand j'essaie "https://www.andapirate.com/motdepasse.txt" j'obtient le mot de passe cherché.

**Flag:** `merci123`


## Challenge 3:

J'arrive sur un challenge nommé "Le md5", qui est une fonction de hachage cryptographique. J'ai en indice "username". 
Je suis donc allé sur ce site: https://www.md5.fr/ et j'ai hashé mon username discord (tout en minuscule) puis j'ai entré le résultat sur l'input du challenge. 

**Flag :** `TonPseudo` + https://www.md5.fr/


## Challenge 4:

Le challenge numéro 4 se nomme "binaire 1", le binaire est un système n'utilisant que des 0 et des 1. Nous avons en indice "`101101 | 110101 (or)`".
En binaire l'opération "or" fonctionne de cette manière :
On met les deux valeurs l'une au dessus de l'autre et le résultat sera 1 si l'un des deux bits vaut 1, sinon le résultat est de zéro. 
Vous pouvez sinon utiliser [ce site](https://miniwebtool.com/bitwise-calculator/?data_type=2&number1=101101&number2=110101&operator=OR) qui vous donnera directement le résultat. 

**Flag :** `111101`


## Challenge 5:

On peux voir qu'on est toujours sur du binaire, ce challenge se nomme "binaire 2" et on a comme indice "`01101110 LEFT SHIFT`". 
Le left shift indique une opération de décalage à gauche. Ce décalage consiste à déplacer tout les bits vers la gauche et à ajouter un 0 à droite.  
Vous pouvez utiliser [ce site](https://circuitdigest.com/calculators/bit-shift-calculator) pour le faire d'une façon automatisée.

**Flag :** `11011100`


## Challenge 6: 

On arrive sur un challenge nommé "discord lookup" avec comme indice : `202524094225317897 + 2` et une aide qui nous dis " [AndaOS Tools OBLIGATOIRE >](https://www.andapirate.com/tools)". Vous pouvez cliquer sur le lien pour vous y rendre. 
Dans la catégorie WhoIs puis DiscordId on peux rentrer l'id donc 202524094225317899 car on fais +2 à l'id de base. On voit des informations sur ce compte et on sait que c'est le compte qu'on recherchais car on voit une référence à anda dans sa bio. 
Dans le result json qu'on obtient on peux voir une variable nommée "WWWTF". C'est notre flag.

**Flag :** `f02368945726d5fc2a14eb576f7276c0`


## Challenge 7:

Le challenge 7 est nommé OSint 1" et nous avons comme indice : "ASN de andapirate.com". Il faut encore utilisé les AndaOS Tools et cette fois nous allons aller dans Whois > Http, ici on va rentrer "andapirate.com" puis sur la deuxième ligne du json qu'on nous return on aura l'asn recherché.

**Flag :** `AS16509`



Voilà le ctf anda pirate est terminé, j'espère que j'aurais pus vous aider et que vous avez compris mes démarches. <3

