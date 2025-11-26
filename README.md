Réponses aux Tâches
1. Récupérez dans Visual Studio et exécutez le code fourni lien Github. Fermez la fenêtre d’avertissements ⚠ affichée.
(Non détaillé dans ce README, mais le code a été cloné et exécuté avec succès. La fenêtre d'avertissement a été fermée comme indiqué.)

2. Quels sont les projets de la solution ?
Le projet de la solution est « Diayma » et est composé d’un seul projet :

Diayma → Projet ASP.NET Core Web Application (.NET Core App 2.0 dans ce cas précis, voir question 3).
Aucun projet supplémentaire (pas de projet Models, Tests, Infrastructure séparé). Tout est organisé dans un unique projet avec les dossiers classiques MVC (Controllers, Views, Models, Components, wwwroot, etc.).

Explorateur de solutions

<img width="900" height="481" alt="image" src="https://github.com/user-attachments/assets/21a2b734-5caa-4c7d-a00e-4fbb037b762a" />

3. Quelle est la version SDK .NET utilisée par ces projets ?
La version utilisée pour ces projets est la version 2.0.
Version SDK:
<img width="880" height="120" alt="image" src="https://github.com/user-attachments/assets/aa756c87-b75a-4a94-a3a7-138e58c6c9f6" />

4. Installez le SDK
Installons le SDK
<img width="901" height="213" alt="image" src="https://github.com/user-attachments/assets/2f2860ad-146e-4727-8917-d42b0abb248c" />

5. Créez votre propre dépôt GitHub pour y stocker le code
Un nouveau dépôt GitHub a été créé pour stocker le code : [ https://github.com/YacineG03/YG_Diayma2025.git ]
Dépôt GitHub
<img width="914" height="448" alt="image" src="https://github.com/user-attachments/assets/da53c4a4-7aba-4d3f-86b4-4330df6d120b" />

6. Explorez l’application. Signalez 2 bugs trouvés ?
La langue espagnole ne fonctionne pas et le contenu du panier est incorrect : le total du panier devrait être calculé à partir de la somme de la colonne Sous-total (quantité × prix), mais le système additionne seulement les valeurs de la colonne Prix (prix unitaire), ce qui fausse le total.
Bug Panier:
<img width="900" height="503" alt="image" src="https://github.com/user-attachments/assets/1b1f4e2f-71b2-41e8-8a97-046d3670a4e4" />


7. Placez un point d’arrêt sur les lignes suivantes du code
Les breakpoints ont été placés comme suit :
a) CartSummaryViewComponent.cs, ligne 10
Breakpoint a

<img width="899" height="251" alt="image" src="https://github.com/user-attachments/assets/164aa9d5-94ca-4bb1-a1ee-1f57cf06903f" />
<img width="904" height="177" alt="image" src="https://github.com/user-attachments/assets/a7d8e558-e272-417e-92f2-6266975e5778" />

b) ProductController.cs, ligne 15 
Breakpoint b
<img width="901" height="480" alt="image" src="https://github.com/user-attachments/assets/a32c0cdb-a450-4900-a130-ef12761d9bfa" />

c) OrderController.cs, ligne 17 
Breakpoint c
<img width="906" height="484" alt="image" src="https://github.com/user-attachments/assets/c64480c8-3583-41b6-9d33-32f43c97d005" />

d) CartController.cs, ligne 15
Breakpoint d
<img width="906" height="185" alt="image" src="https://github.com/user-attachments/assets/ff82e73c-12d6-4ff7-8027-3ca503e5ca5f" />

e) Startup.cs, ligne 20
<img width="900" height="485" alt="image" src="https://github.com/user-attachments/assets/a8f624d6-0d94-4636-845e-76bef110e84e" />

5. (Deuxième) Quels sont les namespaces, classes et méthodes visités avant l’affichage des produits sur l’écran d’accueil de votre navigateur ?
J’ai lancé l’application en mode débogage (F5) et je suis allé sur http://localhost:60000.
Voici le flux complet observé, dans l’ordre exact où les breakpoints ont été touchés :

Avec F11
Fichier : Startup.cs
Namespace : Diayma
Classe : Startup
Méthode : Startup(IConfiguration configuration) (constructeur)
Ligne : 20
Action : Configuration = configuration;
→ Stocke la configuration (appsettings.json, variables d’environnement…) dans le champ privé.

Flux 1
<img width="901" height="486" alt="image" src="https://github.com/user-attachments/assets/4e38e12e-c5ef-4872-a590-4c2087d76793" />


Avec F11
Fichier : Startup.cs
Namespace : Diayma
Classe : Startup
Méthode : ConfigureServices(IServiceCollection services)
Ligne : autour de 25–35 (selon ton code)
→ Enregistrement des services dans le conteneur DI (DbContext, repositories, etc.).

Flux 2
<img width="898" height="478" alt="image" src="https://github.com/user-attachments/assets/154672a1-0b1c-4013-bc6c-bd0cb80b7458" />

Avec F11
Fichier : Startup.cs
Namespace : Diayma
Classe : Startup
Méthode : Configure(IApplicationBuilder app, IHostingEnvironment env)
→ Configuration du pipeline middleware (UseStaticFiles, UseMvc, etc.).

Flux 3
<img width="897" height="480" alt="image" src="https://github.com/user-attachments/assets/f5725747-ba15-46c8-b108-e0e4f143e0b2" />


Avec F10
Fichier : CartSummaryViewComponent.cs
Namespace : Diayma.Components
Classe : CartSummaryViewComponent
Méthode : Invoke() ou InvokeAsync()
Ligne : 12
→ Récupère le panier depuis la session et renvoie la vue partielle du résumé panier (affiché dans le header).
Fichier : ProductController.cs
Namespace : Diayma.Controllers
Classe : ProductController
Méthode : ProductController()
Ligne : 15
→ Récupère la liste des produits depuis le repository et renvoie la vue avec les produits.
<img width="899" height="480" alt="image" src="https://github.com/user-attachments/assets/7560cc5c-7c65-4097-b963-e5aa3f1d926b" />

Mode utilisé :

F10 (Pas à pas principal) la plupart du temps
F11 (Pas à pas détaillé) uniquement quand je voulais entrer dans une méthode spécifique (ex. GetCart()).

6. Déployez votre solution sous forme d’exécutable Windows.
La solution a été déployée via dotnet publish -c Release -r win-x64 --self-contained false.
L'exécutable est disponible dans bin/Release/netcoreapp2.0/win-x64/publish/Diayma.exe.
<img width="903" height="490" alt="image" src="https://github.com/user-attachments/assets/4826314b-bd47-4dd1-b81f-da8336350824" />

8. Fournir un lien drive Google, Onedrive etc. à l’exécutable ci-dessus.
Lien Google Drive vers l' exécutable [https://drive.google.com/drive/folders/1BFsidZZg3XhQzB_eilafrhMN95DMw6xY?usp=sharing]
