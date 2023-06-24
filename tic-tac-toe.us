var currentPlayer = 'X';
var gameState = [
	[null, null, null],
	[null, null, null],
	[null, null, null]
];
function handleCellClick(event) {
	// Get the row and column of the clicked cell
	var row = event.target.parentNode.rowIndex;
	var col = event.target.cellIndex;

	// Ignore clicks on cells that have already been played
	if (gameState[row][col] !== null) {
		return;
	}

	// Update the state of the game
	gameState[row][col] = currentPlayer;

	// Update the display of the clicked cell
	event.target.textContent = currentPlayer;

	// Check if the game is over
	var winner = checkForWinner();
	if (winner !== null) {
		document.getElementById('message').textContent = winner + ' wins!';
		return;
	}

	// Switch to the other player
	currentPlayer = (currentPlayer === 'X') ? 'O' : 'X';
}
function checkForWinner() {
	// Check rows
	for (var row = 0; row < 3; row++) {
		if (gameState[row][0] !== null && gameState[row][0] === gameState[row][1] && gameState[row][0] === gameState[row][2]) {
			return gameState[row][0];
		}
	}

	// Check columns
	for (var col = 0; col < 3; col++) {
		if (gameState[0][col] !== null && gameState[0][col] === gameState[1][col] && gameState[0][col] === gameState[2][col]) {
			return gameState[0][col];
		}
	}

	// Check diagonals
	if (gameState[0][0] !== null && gameState[0][0] === gameState[1][1] && gameState[0][0] === gameState[2][2]) {
		return gameState[0][0];
	}
	if (gameState[0][2] !== null && gameState[0][2] === gameState[1][1] && gameState[0][2] === gameState[2][0]) {
		return gameState[0][2];
	}

	// If there is no winner, return null
	return null;
}
document.getElementById('cell00').addEventListener('click', handleCellClick);
document.getElementById('cell01').addEventListener('click', handleCellClick);
document.getElementById('cell02').addEventListener('click', handleCellClick);
document.getElementById('cell10').addEventListener('click', handleCellClick);
document.getElementById('cell11').addEventListener('click', handleCellClick);
document.getElementById('cell12').addEventListener('click', handleCellClick);
document.getElementById('cell20').addEventListener('click', handleCellClick);
document.getElementById('cell21').addEventListener('click', handleCellClick);
document.getElementById('cell22').addEventListener('click', handleCellClick);
