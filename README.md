# memory-game-2


This code is for a memory card game in JavaScript, similar to the memory game 1, but with another feature: it uses two sets of images in the cardArray to create pairs of matching cards. Here's an explanation of the code:

cardArray:

cardArray is an array containing objects representing the cards in the game.
Each object has a name property (e.g., 'pokemon1') and an img property pointing to the image file associated with that card.
There are two sets of objects in cardArray, which means there are pairs of cards with the same name but different images.
Random Shuffling:

cardArray.sort(() => 0.5 - Math.random()) shuffles the cardArray randomly, ensuring that the cards are in a random order each time the game starts.
HTML Elements:

grid: Represents the grid (game board) where the cards will be displayed.
resultDisplay: Used to display the player's score.
Variables:

cardsChosen: An array to store the names of cards that the player has chosen.
cardsChosenId: An array to store the IDs of the cards that the player has chosen.
cardsWon: An array to keep track of pairs of matching cards.
createBoard() Function:

This function creates the game board by dynamically generating and populating it with card images.
It uses a loop to create an <img> element for each card in cardArray, sets attributes like src and data-id, and adds a click event listener to each card to call the flipCard function when clicked.
checkForMatch() Function:

This function checks if the two chosen cards match.
If the player clicks the same card twice, it alerts them and resets both cards.
If the player finds a matching pair, it alerts them and replaces both cards with white images (images/white.png). It also removes the click event listeners for those cards and adds the pair to cardsWon.
If the player selects two different cards that do not match, it alerts them and resets both cards to the blank state.
flipCard() Function:

This function is called when a player clicks on a card.
It retrieves the data-id attribute of the clicked card, adds the card's name to cardsChosen, and its ID to cardsChosenId.
It changes the src attribute of the clicked card to reveal its image.
If the player has chosen two cards, it calls checkForMatch after a brief delay (500 milliseconds).
Game Initialization:

The createBoard function is called to create the initial game board.
Winning Condition:

The game checks if the player has won by comparing the length of cardsWon to half the length of cardArray (since there are two sets of cards for each pair).
The game is designed to be played by matching pairs of cards with the same name, and it keeps track of the player's score by counting the number of matched pairs. The player wins when all pairs have been found.