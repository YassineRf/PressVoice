# PressVoice

## Pré-requis

Afin d'utiliser correctement PressVoice et ses intents, seules deux conditions doivent être remplies :
  
    * PressKit est nécessaire
    * development language de votre app doit être le francais

Si vous souhaitez changer le development language de votre app de english à francais, suivez ces étapes :
  - Depuis Xcode, ```Project``` > ```Info``` > ```Localizations``` > cliquez sur le petit + > ```French (fr)```
  - Clique-droit sur le project, ```Show in finder```, clique droit sur le .xcodeproj, ```Afficher le contenu du paquet```
  - Ouvrez le project.pbxproj avec un editeur de texte
  - Recherchez la ligne ```developmentRegion = en;``` et changez ```en``` en ```fr```, CTRL+S et quittez l'éditeur
  - Depuis Xcode, ```Info.plist``` > changez le ```DEVELOPMENT_LANGUAGE``` en ```France```

## Installation

L'installation de PressVoice et de l'extension Siri se feront manuellement en suivant toute les étapes cités ci-dessous, veillez à les suivre attentivement.

 * Depuis Xcode, ```Project``` > ```Add a target``` > ```Intents Extension```, remplissez les champs et ```Finish```
 * Une nouvelle target apparaitra, ainsi qu'un nouveau dossier contenant un .plist ainsi qu'un IntentHandler.swift
 * Supprimez votre ```IntentHandler.swift```
 * Drag & drop les .swift se trouvant dans le dossier ```Sources``` du repo, dans le dossier de votre extension
 * ```Add to targets``` votre extension
 <img width="719" alt="Capture d’écran 2021-07-23 à 17 57 15" src="https://user-images.githubusercontent.com/72382446/126809255-77cbddce-c89a-417a-b8b8-e74876042773.png">
 <img width="1185" alt="Capture d’écran 2021-07-23 à 17 55 04" src="https://user-images.githubusercontent.com/72382446/126808856-1d436671-8417-455e-a6b4-c5e3126b75ac.png">
 
 * Selectionnez le fichier ```Intents.intentdefinition``` et changez les targets de votre app ainsi que votre extension en ```No Generated Classes```
 <img width="254" alt="Capture d’écran 2021-07-23 à 19 51 56" src="https://user-images.githubusercontent.com/72382446/126821834-215ca7ea-d55a-4ea1-9e7c-2982d0c72bea.png">
 
 * Drag & drop le xcframework à la racine du repo, dans votre dossier ```Framework``` se trouvant à la racine de votre projet (s'il n'existe pas, créez le)
 * À la différence des sources, ```Add to targets``` le .xcframework à votre extension mais aussi à votre app
 * Vérifiez bien que le .xcframework est bien en ```Embed & Sign``` à la fois pour votre app et votre extension




