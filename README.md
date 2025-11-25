<img width="900" height="481" alt="image" src="https://github.com/user-attachments/assets/0e728ce3-1a97-4032-a015-d12591810998" />

2. Le projet de la solution est « Diayma » eet est composée d’un seul projet :
• Diayma → Projet ASP.NET Core Web Application (.NET Core App 2.0 dans ce cas précis, voir question 3)
Aucun projet supplémentaire (pas de projet Models, Tests, Infrastructure séparé). Tout est organisé dans un unique projet avec les dossiers classiques MVC (Controllers, Views, Models, Components, wwwroot, etc.).

<img width="900" height="481" alt="image" src="https://github.com/user-attachments/assets/21a2b734-5caa-4c7d-a00e-4fbb037b762a" />

3. Quelle est la version SDK .NET utilisée par ces projets ?
La version utilisée pour ces projets est la version 2.0
<img width="880" height="120" alt="image" src="https://github.com/user-attachments/assets/aa756c87-b75a-4a94-a3a7-138e58c6c9f6" />

4. Installez le SDK
Installons le SDK
<img width="901" height="213" alt="image" src="https://github.com/user-attachments/assets/2f2860ad-146e-4727-8917-d42b0abb248c" />

5. Créons notre propre dépôt GitHub pour y stocker le code
<img width="914" height="448" alt="image" src="https://github.com/user-attachments/assets/da53c4a4-7aba-4d3f-86b4-4330df6d120b" />

7. Explorez l’application. Signalez 2 bugs trouvés ?
La langue espagnole ne fonctionne pas et le contenu du panier est incorrect : le total du panier devrait être calculé à partir de la somme de la colonne Sous-total (quantité × prix), mais le système additionne seulement les valeurs de la colonne Prix (prix unitaire), ce qui fausse le total.
<img width="900" height="503" alt="image" src="https://github.com/user-attachments/assets/1b1f4e2f-71b2-41e8-8a97-046d3670a4e4" />


8. Placez un point d’arrêt sur les lignes suivantes du code
a) CartSummaryViewComponent.cs, ligne 10

<img width="899" height="251" alt="image" src="https://github.com/user-attachments/assets/164aa9d5-94ca-4bb1-a1ee-1f57cf06903f" />
<img width="904" height="177" alt="image" src="https://github.com/user-attachments/assets/a7d8e558-e272-417e-92f2-6266975e5778" />

b) ProductController.cs, ligne 15 
<img width="901" height="480" alt="image" src="https://github.com/user-attachments/assets/a32c0cdb-a450-4900-a130-ef12761d9bfa" />

c) OrderController.cs, ligne 17 
<img width="906" height="484" alt="image" src="https://github.com/user-attachments/assets/c64480c8-3583-41b6-9d33-32f43c97d005" />

d) CartController.cs, ligne 15
<img width="906" height="185" alt="image" src="https://github.com/user-attachments/assets/ff82e73c-12d6-4ff7-8027-3ca503e5ca5f" />

e) Startup.cs, ligne 20
<img width="900" height="485" alt="image" src="https://github.com/user-attachments/assets/a8f624d6-0d94-4636-845e-76bef110e84e" />




