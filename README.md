# auto-follow
auto follow Threads

Instructions

Étape 1 : Ouvrir la Console du Navigateur
Pour exécuter le script, vous devez d'abord ouvrir la console du navigateur sur la page où vous souhaitez l'utiliser. Voici comment :

Allez sur la page web où vous voulez exécuter le script.
Faites un clic droit n'importe où sur la page et sélectionnez Inspecter (ou utilisez le raccourci clavier Ctrl+Shift+I sur Windows/Linux, Cmd+Option+I sur Mac).
Dans la fenêtre d'inspection qui s'ouvre, cliquez sur l'onglet Console.
Étape 2 : Copier et Coller le Script
Copiez le script JavaScript fourni.
Revenez à la console du navigateur que vous avez ouverte à l'étape 1.
Collez le script dans la console.
Étape 3 : Exécuter le Script
Appuyez sur Entrée pour exécuter le script.
Le script va commencer à cliquer automatiquement sur les boutons "Suivre".
Une fois terminé, le script affichera dans la console le nombre de boutons sur lesquels il a cliqué.


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
