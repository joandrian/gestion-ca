Voici le contenu complet et soigné pour votre fichier `README.md`. Il reflète toutes les fonctionnalités finales (Authentification, Livraison, Bénéfice, PWA).

```markdown
# 📱 ViewCA

**ViewCA** est une application web progressive (PWA) légère, sécurisée et performante conçue pour les épiceries et commerces de proximité à Madagascar.

Elle permet de gérer le stock, de calculer automatiquement le Chiffre d'Affaires (CA) et d'analyser la rentabilité (Bénéfices) en tenant compte des livraisons et de la démarque (pertes).

La devise utilisée est l'Ariary (MGA).

---

## ✨ Fonctionnalités

*   🔐 **Sécurité** : Accès protégé par un code PIN à 4 chiffres.
*   📦 **Gestion de Stock Intelligent** : Le CA est calculé automatiquement par déduction `(Stock J-1 + Livraison - Stock J - Pertes)`.
*   🚚 **Gestion des Livraisons** : Intégration des arrivées de marchandises dans le calcul du stock.
*   ⚠️ **Gestion de la Démarque** : Déclaration précise des pertes (Casse, Péremption, Vol) pour ne pas fausser les ventes.
*   💰 **Analyse de Rentabilité** : Saisie du prix d'achat et du prix de vente pour calculer le **Bénéfice Net** par produit.
*   📊 **Dashboard Visuel** : Graphiques dynamiques (Top CA, Top Bénéfices, Ratio Rentabilité) sans librairie externe.
*   💾 **Offline-First** : Fonctionne sans internet (PWA) et sauvegarde les données localement (LocalStorage).
*   🛠️ **Catalogue CRUD** : Création, modification et suppression des produits.

---

## 🛠️ Technologies Utilisées

*   **HTML5** & **CSS3** : Structure et design "Mobile-first".
*   **Vanilla JavaScript (ES6+)** : Logique métier, gestion d'état et rendu des graphiques (Canvas API).
*   **Service Workers** : Mise en cache pour le mode hors ligne.
*   **LocalStorage** : Persistance des données sur l'appareil.

---

## 📂 Arborescence du projet

Le projet est structuré pour être simple et autonome.

```text
gestion-ca/
│
├── index.html        # Application complète (Logique, Vue, Style)
├── manifest.json     # Configuration PWA (Icônes, Nom, Thème)
├── sw.js             # Service Worker (Gestion du cache)
└── README.md         # Ce fichier
```

---

## 🚀 Installation et Utilisation

### 1. Lancer en local (Test)

1.  Téléchargez ou clonez le dépôt.
2.  Ouvrez simplement le fichier `index.html` dans votre navigateur.
3.  Au premier lancement, définissez votre **code PIN**.

### 2. Déployer sur GitHub Pages

1.  Poussez le code vers votre dépôt GitHub.
2.  Allez dans **Settings** > **Pages**.
3.  Sélectionnez la branche `main` (ou `master`) et le dossier `/ (root)`.
4.  Votre app sera disponible à l'adresse : `https://votre-username.github.io/gestion-ca/`

### 3. Installer sur Mobile (PWA)

Une fois déployée :
*   **Android** : Ouvrez le lien dans Chrome -> "Installer l'application" (icône menu).
*   **iOS** : Ouvrez le lien dans Safari -> "Partager" -> "Sur l'écran d'accueil".

---

## 📐 Logique Métier & Formules

L'automatisation est le cœur de ViewCA. L'utilisateur ne saisit pas les ventes, il saisit l'état du stock et les événements.

### 1. Calcul des Ventes
L'application calcule le nombre d'articles vendus en corrigeant la variation de stock par les entrées et sorties anormales.

```text
Ventes = (Stock Hier + Livraison du jour) - Stock Actuel - Pertes
```

### 2. Calcul du Chiffre d'Affaires (CA)
```text
CA = Ventes × Prix de Vente Unitaire
```

### 3. Calcul du Bénéfice Net
ViewCA permet de distinguer le chiffre d'affaires de la rentabilité réelle.

```text
Marge Unitaire = Prix de Vente - Prix d'Achat
Bénéfice Net = Ventes × (Prix de Vente - Prix d'Achat)
```

---

## 📸 Captures d'écran (Description)

*   **Inventaire** : Liste des produits avec saisie rapide via pavé numérique. Indicateurs visuels pour les livraisons (Vert) et les pertes (Rouge).
*   **Dashboard** :
    *   3 KPIs : CA Ventes, Bénéfice Net (Orange), Démarque.
    *   Graphique "Top Bénéfices" : Identifie quels produits sont les plus rentables, pas seulement ceux qui se vendent le plus.
*   **Catalogue** : Gestion des produits avec prix d'achat et prix de vente.

---

## 🔄 Mode Hors Ligne

Grâce au **Service Worker**, une fois l'application chargée une fois, elle fonctionne entièrement sans connexion internet. Les données sont stockées dans la mémoire du téléphone (LocalStorage) et ne sont pas partagées entre différents appareils.

---

## 🚧 Roadmap (Évolutions futures)

*   [ ] Synchronisation Cloud (Supabase) pour multi-supports (Téléphone + PC).
*   [ ] Authentification multi-utilisateurs (Email/Mot de passe).
*   [ ] Historique des ventes sur 30 jours.
*   [ ] Export des données en CSV/Excel.
*   [ ] Scan Code-Barres.

---

## 📝 Licence

Ce projet est Open Source. Vous êtes libre de l'utiliser et de le modifier.

---

**Développé avec ❤️ pour simplifier la gestion des commerces à Madagascar.**
```