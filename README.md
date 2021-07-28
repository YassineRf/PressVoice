# PressVoice

## Pré-requis

Afin d'utiliser correctement PressVoice et ses intents, seules deux conditions doivent être remplies :

  * iOS Deployment Target minimum version : 13.0
  * PressKit est nécessaire
  * Le ```Development language``` de votre app doit être le francais

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
 * Supprimez ces fichiers
 * Drag & drop les .swift et le .plist se trouvant dans le dossier ```Sources``` du repo, dans le dossier de votre extension
 * ```Add to targets``` votre extension
 <img width="719" alt="Capture d’écran 2021-07-23 à 17 57 15" src="https://user-images.githubusercontent.com/72382446/126809255-77cbddce-c89a-417a-b8b8-e74876042773.png">
 
 * Si le message "Would you like to configure an Objective-C bridging header ?" apparait, cliquez sur ```Don't Create```
 * Le .plist de votre extension ne doit pas avoir de target séléctionné
 * Changez le ```Bundle display name``` de l' ```Info.plist``` de votre extension, selon le nom de votre extension

 Apercu du dossier de votre extension :
 
 <img width="1185" alt="Capture d’écran 2021-07-23 à 17 55 04" src="https://user-images.githubusercontent.com/72382446/126808856-1d436671-8417-455e-a6b4-c5e3126b75ac.png">
 
 * Drag & drop le PressVoice.xcframework dans votre dossier ```Framework``` se trouvant à la racine de votre projet (si le dossier n'existe pas, créez-le)
 * ```Add to targets``` le .xcframework à votre extension et à votre app
 * Selectionnez le fichier ```Intents.intentdefinition``` et changez les targets de votre app ainsi que de votre extension en ```No Generated Classes```

<img width="254" alt="Capture d’écran 2021-07-26 à 12 55 19" src="https://user-images.githubusercontent.com/72382446/126978072-494d1186-95be-4c31-8a77-a31c07019812.png">

### Remarques

* Vérifiez bien que le .xcframework est bien en ```Embed & Sign``` à votre app et votre extension
* Vous remarquerez que les intents supportés par votre app se trouvent dans ```Info.plist``` de votre extension > ```NSExtension``` > ```NSExtensionAttributes``` > ```IntentsSupported```

## Utilisation

### UIKit

 * Import ```PressVoiceFramework```
 * Faite heriter votre ViewController de ```PVController```
 * Utilisez la public func ```getAddToSiriButton``` et ajoutez-y les paramètres que vous souhaitez 

Example :

<img width="1110" alt="Capture d’écran 2021-07-28 à 10 56 21" src="https://user-images.githubusercontent.com/72382446/127294365-184ed36a-4b39-49b1-96f1-5be981a5f2b4.png">

### SwiftUI

 * Import ```PressVoiceFramework```
 * Utilisez la view ```SiriButtonView```, ajoutez-y les paramètres que vous souhaitez et ajoutez une frame de 100 par 100 à votre view

Example :

<img width="1110" alt="Capture d’écran 2021-07-28 à 10 59 25" src="https://user-images.githubusercontent.com/72382446/127294827-0580d321-fecb-4cc0-9488-6897749dfe9a.png">
