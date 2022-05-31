# connect-four
Connect Four Web Application

Game application that uses HTML, CSS, and vanilla JavaScript and can be ran using Live Server Extension on Visual Studio Code, or other local host implementations. 

The game is played manually by two players, one is designated red chips, and the other black chips. The game starts off by selecting a random number to determine who will begin the game and then the players are able to choose where they want to place the chips by selecting the "Drop" buttons underneath the board, at each column. The game alternates player after each player has selected where they want to drop their chip. The game ends when either player has four consecutive chips of the same color in a row. The player who was won is prompted with a message above the board.

The main function internally of the applicaiton is that the board is a N * M two-dimensional matrix and begins at (0,0) and is designated accordingly. Each player also is designated a corresponding two-dimensional array that will hold the coordinates of the chips that each player chose. The game then continually checks for a winning sequence of chips, given a new coordinate after a player selects a position, and performs to appropriate action. The application is set up to check for sequences horizontally, vertically, and diagonally, but in a single direction becasue the array is sorted using the sort method from the array object. The checking algorithms work by keeping a "consecutive" variable tracker that will increment once an element in the array is determined to be next in a sequence based on coordinates, for example, (0,0) -> (0,1) would indicate that two chips are next to each other, horizontally, and a sequence such as (0,0) -> (0,1) -> (0,2) -> (0,3) would be a winning sequence, horizontally.

The JavaScript aspect of the project is a little more involved with the data structures used by the application, and namely, each player's array. The game, and all of the corresponding aspects, are also able to be dynamically sized as a result. The concept with the front-end is that the board is a seperate <div> element and the chips themselves, are of "position: absolute" with the board being of "position: relative", so to dynamically add the chips with their own distinct color, the location of the chip image is determined based on the width and the height of the board, and the chip width and height as a result. Each position of the chip is then determined based on which column and row is available and a constant factor to determine the x and y position of the chips.
