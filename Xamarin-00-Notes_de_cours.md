# Xamarin
## Introduction
La migration vers MAUI apparait assez lourde.

Les templates sont dans le dossier Ressources/layout.  
On ne modifie pas directement le manifest, on passera par clic droit / propriété / manifest.  
La classe R qui est une classe auto-générée dans Android Vanilla et contenant l'ensemble des élements contenus dans le dossier ressources. Dans Xamarin, on aura ainsi une classe Ressource en Xamarin.

Dans l'idée le projet natif est redirigé vers le projet Xamarin.

Gestion du style de l'application dans app.xaml

iOs : appDelegate est l'équivalent de MainActivity qui va instancier un app FormXamarin. Le reste se fait dans Xamarin.

LinearLayout en Xamarin : Stack Layout

En XAML, la balise content page représente la page. Plusieurs namespaces existent.

Styles dans la partie App Xaml : targettype permettra de l'appliquer à une élément (button etc...)
Pour lui donner un nom ce sera x:Key
On aura ensuite des Setters permettant de surcharger certains sites.
Pour l'utiliser : dans les paramètres <button style="{Dynamic ressource Button_title}"

Methode Clicked : 
sender : reference vers le bouton qui vient d etre clique

Le second sera un objet evenement qui pourra différer selon 
S'il s'agit d'un textChange, on peut récupérer la variable.

Par défaut l'orientation est verticale.

les images source = image ou lien

Dependency Service :
Côté Xamarin Form ,créer une interface ToastInterface pour définir la ou les méthodes qu'on souhaite appeler cote android.
Ici une methode showToast qui attend le message en argument
Dans la partie native, on créer une classe Toast qui implémente l'interface
Ajouter une partie Assembly au dessus du namespace
Utilisation avec DepencyService.Get<ToastInterface>.ShowToast(message)
