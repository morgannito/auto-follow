# auto-follow Threads

# Guide d'Utilisation du Script de Suivi Automatique

Ce README explique comment exécuter un script JavaScript personnalisé pour suivre automatiquement des utilisateurs sur une page web spécifique.

## Prérequis

- Un navigateur web moderne (par exemple, Chrome, Firefox, Edge).
- Accès à la page web où vous souhaitez exécuter le script.

## Instructions

### Étape 1 : Ouvrir la Console du Navigateur

Pour exécuter le script, vous devez d'abord ouvrir la console du navigateur sur la page où vous souhaitez l'utiliser. Voici comment :

1. Allez sur la page web où vous voulez exécuter le script.
2. Faites un clic droit n'importe où sur la page et sélectionnez `Inspecter` (ou utilisez le raccourci clavier `Ctrl+Shift+I` sur Windows/Linux, `Cmd+Option+I` sur Mac).
3. Dans la fenêtre d'inspection qui s'ouvre, cliquez sur l'onglet `Console`.

### Étape 2 : Copier et Coller le Script

1. Copiez le script JavaScript fourni.
2. Revenez à la console du navigateur que vous avez ouverte à l'étape 1.
3. Collez le script dans la console.

### Étape 3 : Exécuter le Script

1. Appuyez sur `Entrée` pour exécuter le script.
2. Le script va commencer à cliquer automatiquement sur les boutons "Suivre".
3. Une fois terminé, le script affichera dans la console le nombre de boutons sur lesquels il a cliqué.

## Avertissement

- Utilisez ce script avec prudence et à vos propres risques.
- Le script est destiné à des fins éducatives et ne doit pas être utilisé pour des activités qui enfreignent les conditions d'utilisation de la plateforme web.
- L'exécution de scripts automatisés peut parfois conduire à des comportements inattendus sur les sites web et peut potentiellement violer les termes de service.

## Support

Pour toute question ou problème concernant l'utilisation de ce script, veuillez contacter le développeur.



```
// Fonction pour simuler un clic sur un élément
function simulateClick(element) {
    const event = new MouseEvent('click', {
        bubbles: true,
        cancelable: true,
        view: window
    });
    element.dispatchEvent(event);
}

// Fonction pour trouver et cliquer sur tous les boutons "Suivre", avec un compteur
function followAll() {
    // Trouver tous les divs qui ont le texte "Suivre"
    const allDivs = Array.from(document.querySelectorAll('div'));
    const followButtons = allDivs.filter(div => {
        return div.textContent === 'Suivre' && div.parentElement.getAttribute('role') === 'button';
    });

    let counter = 0; // Initialiser le compteur

    followButtons.forEach(button => {
        // Simuler un clic sur chaque bouton
        simulateClick(button.parentElement);
        counter++; // Augmenter le compteur pour chaque clic
    });

    console.log(`${counter} boutons 'Suivre' ont été cliqués.`);
}

// Exécutez la fonction
followAll();

```
