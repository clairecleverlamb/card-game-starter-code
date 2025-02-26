# 🃏 Card Flip Game  

## 🚀 Overview  
This is a simple **Card Flip Game** where players draw cards from one deck and move them to another by clicking a button. The game visually updates the decks as cards are transferred.  

## 🎮 Features  
- **Two decks of cards**: One starts full, the other starts empty.  
- **Random card selection**: A card is picked from Deck 1 and moved to Deck 2.  
- **Visual transitions**:  
  - Deck 1 shrinks while Deck 2 grows.  
  - Shadows move dynamically as the game progresses.  
  - The last card flip adds an outline to the empty deck.  
- **Interactive UI**: Click a button to flip cards and watch the decks change in real-time.  

## 🛠️ Technologies Used  
- **HTML, CSS**: Structure and styling.  
- **JavaScript**: Game logic and interactions.  

---

## 🎲 How It Works  
1. Deck 1 starts with **52 cards**.  
2. Clicking the **Flip Card** button randomly selects a card from Deck 1 and moves it to Deck 2.  
3. Deck 2 starts empty and fills up as cards are flipped.  
4. When **half the cards (26) are flipped**, the shadow moves from Deck 1 to Deck 2.  
5. When **all cards are moved**, Deck 1 becomes an empty outline.  

---

## 🛠️ Installation & Setup  
1. Clone the repository:  
   ```sh
   git clone https://github.com/yourusername/card-game.git
   cd card-game
   ```  
2. Open `index.html` in your browser.  
3. Click the **Flip Card** button and enjoy!  

---

## 🌜 Code Breakdown  

### **🔹 Deck Initialization**  
```js
const init = () => {
    deck1 = ["dA", "dQ", "dK", "dJ", ..., "s03", "s02"];
}
init();
```
✔️ Fills `deck1` with **52 cards** while `deck2` starts empty.  

### **🔹 Card Flipping Logic**  
```js
const handleClick = () => {
    if (deck1.length > 0) {
        let randomIdx = Math.floor(Math.random() * deck1.length);
        let cardPicked = deck1.splice(randomIdx, 1)[0];
        deck2.push(cardPicked);
        render(cardPicked);
    }
}
```
✔️ Selects a random card, moves it from `deck1` to `deck2`, and updates the UI.  

### **🔹 Rendering UI Updates**  
```js
const render = (cardPicked) => {
    if (deck2.length === 1) deck2El.classList.remove("outline");
    if (deck2.length > 1) deck2El.classList.remove(cardToRemove);
    cardToRemove = cardPicked;
    deck2El.classList.add(cardPicked);
    if (deck2.length === 26) {
        deck2El.classList.add("shadow");
        deck1El.classList.remove("shadow");
    }
    if (deck1.length === 0) {
        deck1El.classList.add("outline");
        deck1El.classList.remove("back-blue");
    }
}
```
✔️ Updates visual elements dynamically based on the number of flipped cards.  

---

## 🚀 Future Enhancements  
🔹 **Animated card flips** for a more dynamic experience.  
🔹 **Sound effects** when cards are flipped.  
🔹 **Multiple game modes**, such as a timed challenge.  
🔹 **Mobile-friendly design** for better accessibility.  

---

## 🎲 Play & Have Fun!  
Flip the deck, watch the magic, and enjoy the game! 🚀🎉  

