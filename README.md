# auto-follow
auto follow Threads


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
