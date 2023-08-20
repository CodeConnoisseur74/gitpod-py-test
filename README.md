Readme.md

# **BLACKJACK PY**

![Live Project Mockup](/readme-images/amiresponsive.png)
[Link to Live Project](https://pyblackjack-e3fb5b12d78b.herokuapp.com/)

## Table of Contents

- [**BLACKJACK PY**](#blackjack-py)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [UX](#ux)
    - [User Stories](#user-stories)
    - [Wireframes](#wireframes)
  - [Features](#features)
    - [Blackjack Algorithm](#blackjack-algorithm)
    - [Features Left to Implement](#features-left-to-implement)
  - [Technologies Used](#technologies-used)
    - [Languages Used](#languages-used)
    - [Frameworks, Libraries \& Programs Used](#frameworks-libraries--programs-used)
  - [Testing](#testing)
  - [Deployment](#deployment)
    - [Heroku](#heroku)
    - [Forking the GitHub Repository](#forking-the-github-repository)
    - [Cloning the GitHub Repository](#cloning-the-github-repository)
    - [Code](#code)
  - [Credits](#credits)

## Introduction

Blackjack Py is a command-line clasic card game, also refered to as 21. The object of the game is to get as close to the score of 21 without going over (known as "bust" or "busted"). A dealer (Traditionally in a Casino setting) will deal out 2 cards to themselves and t cards to the player. Cards 2 - 10 are worth their face value. For example, a 2 of hearts is worth 2 points. Kings, Queens and Jacks are worth 10 poits each.

 The player has three choices: Hit: The dealer will deal out another card to the player, Stand: The Dealer will not deal out any cards to the player and will turn over their hidden card (Dealer shows 1 card to the player and one face down) to reveal how many points their 2 cards are worth, and Double Down: The player will choose to double their initial bet. If the player ends up with more than 21 points, the player looses and vice versa.

 Money in the form of chips is usually used for the player to place bets. The player can choose how many chips (or money) they will bet on during that particular game (also known as a hand). If the player looses (explained above) the amount of money the player has bet on that hand is lost. If The player wins, the player wins double the amount of the bet.

 Multiple hands are played until the player either chooses to end and cash in the chips for money, or looses all of the money.

## UX

### User Stories

| ID  | As a...                                        | I Want To Be Able To...                                                               | So That I Can...                                                                                                                                                                                                                           |
| --- | ---------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 01  | Game Enthusiast                                | a simple card game                                                                    | Simple instructions at beginning of game. I have the ability to strategically place my ships as I can with the board game. Game also gives me contant score updates and feedback on invalid coordinates, as well as if I have won or lost. |
| 02  | Older middle-aged vintage computers enthusiast | Classic CLI game for nostalgia.                                                       | I can relive my childhood by running a good old fashioined command-line game.Easy to run and can play whilst doing other tasks on my computer.                                                                                             |
| 03  | Young student learning python                  | I can play games like my parents did back in the day and have fun studying at school. | I can run this on single board computer projects for school and hobby.                                                                                                                                                                     |

### Wireframes

- No wireframes were required for this project.

## Features

- The player is met with a start menu, allowing the choice to start the game or quit the game:

![](/readme-images/test-start-menu.png)

- The player has the choice to quit the game after every hand played:

![](/readme-images/test-quit.png)

- The player will be met with the game rules, money limit and a question of how much they would like to bet, to initiate game play:

![](/readme-images/test-rules.png)

-During the game: the player has seperate menu with the choices of Hit, Stand and Double Down:

-The game play will show the cards of the player, the cards of the dealer using "#" to illustrate the hidden dealer card, the current score of the player.

![](/readme-images/test-game-play.png)

[ASCII CHR() CODE CHART for QTP UFT Selenium Playwright and Cypress](https://testguild.com/qtp-ascii-chr-code-chart/)

-The cards were drawn by using the ASCII CHR() code chart. The cards are assembled in rows
in a dict (array). the for loop enumerates the rows and prints them lines of the cards. A conditional statement in the display cards function determines if the card is facing down (BACKSIDE) or up.

![](/readme-images/test-display-cards.png)

### Blackjack Algorithm

Certainly, here's an explanation of the algorithm for the Blackjack game you've implemented:

1. **Initialization:**
   - The game starts with a welcome message that explains the rules of Blackjack and presents a menu with options to start a new game or quit.

2. **Main Menu:**
   - The player is presented with a main menu where they can choose to play Blackjack or quit the game.
   - If the player chooses to play, the `play_blackjack()` function is called.

3. **Play Blackjack:**
   - The game begins by initializing the player's starting money.
   - The game loop starts, where the player plays rounds of Blackjack until they quit or run out of money.
   - Inside the loop:
     - The player is asked to place a bet for the current round. The bet is validated to ensure it's within the allowed range.
     - The deck of cards is created and shuffled.
     - Two cards are dealt to both the player and the dealer.
     - The player's turn begins:
       - The player's hand is displayed, and they are prompted to choose from available actions: Hit, Stand, or Double Down (if eligible).
       - The chosen action is processed. If the player chooses to hit, a new card is added to their hand.
       - If the player's hand exceeds 21 points (busts), their turn ends.
     - The dealer's turn begins:
       - If the player didn't bust, the dealer draws cards until their hand value reaches 17 or higher.
       - If the dealer's hand exceeds 21 points, they bust.
     - The final hands of the player and the dealer are displayed, and the winner of the round is determined:
       - If the player's hand exceeds 21 points, the dealer wins.
       - If the dealer's hand exceeds 21 points, the player wins.
       - If neither busts, the higher hand wins. If the hands are tied, the bet is returned.
     - The player's money is updated based on the outcome of the round.
     - The player is presented with options to play a new game or quit.

4. **End of Round Options:**
   - After each round, the player is presented with options to play a new game or quit.
   - If the player chooses to play a new game, the loop continues, and a new round begins.
   - If the player chooses to quit, the game exits with a thank you message.

5. **Card Values:**
   - Card values are calculated by summing up the values of the cards in the hand.
   - Number cards have their face value, face cards are worth 10, and Aces are worth 1 or 11, whichever is more beneficial.

6. **User Input Validation:**
   - User inputs, such as bets and actions, are validated to ensure they are within the allowed range and correspond to valid actions.

7. **Graphics:**
   - The game's visual appeal is enhanced by using ASCII art for the Blackjack logo and card representations.

8. **Exiting the Game:**
   - The game can be exited at various points, either by choosing to quit from the main menu or after each round.

This algorithm outlines the flow and logic of your Blackjack game, from the main menu to playing rounds, making bets, handling player and dealer actions, determining winners, and providing options to continue or quit.

### Features Left to Implement

- Describe some features that we would like to implement in the future

*Add color to the game through Colorama included with python and some ASCII art.

*Expand on the gameplay messages to expand the game.

*Use PyGame for a complete 2D GUI expereince.

*Eventually devolp further as an Android app.

## Technologies Used

*[VSCode](https://en.wikipedia.org/wiki/Visual_Studio_Code)

![VSCode](/readme-images/vscodelogo.png)

*[Pycharm](https://en.wikipedia.org/wiki/JetBrainse)

![PyCharm](/readme-images/PyCharmlogo.png)

*[Heroku](https://en.wikipedia.org/wiki/Heroku)

![Heroku](/readme-images/herokulogo.png)

### Languages Used

*[Python](https://en.wikipedia.org/wiki/Python_(programming_language))

![Python](/readme-images/python-logo-only.png)

### Frameworks, Libraries & Programs Used

*[Random](https://docs.python.org/3/library/random.html)

*[Black Formatter](https://black.readthedocs.io/en/stable/)

*[Flake8](https://flake8.pycqa.org/en/latest/)

*[CI Python Linter](https://pep8ci.herokuapp.com/)

## Testing

CI Linter, Flake8 and Black Formatter was used to test and find errors. Only syntax errors were found. Renaming of functions and variables according to PEP8 documentation was carried out and refactored using PyCharm before confirming and copying over to VSCode in Gitpod.

The only errors encountered were formatting errors and errors thrown by the linter:

E203, E266, E501, W503

This was fixed by adding both a .flake8 flie and pyproject.toml to the root of the project.

## Deployment

### Heroku

This program was deployed to Heroku, following the below steps:

    Push most up-to-date code to Github

    Create a list of requirements by typing the following into the terminal: pip3 freeze > requirements.txt

    Push the requirements to Github

    Logon to Heroku

    Select create new app

    Add app name

    Add app region

    Select 'Create app'

    Open up the Settings tab, on the top ribbon

    In 'Config Vars' select 'Reveal Config Vars'

    Add 'PORT' as a key and '8000' as a value

    In 'Buildpacks' select 'Add buildpack' and choose python. Then, repeat for nodejs (order is important; python first followed by nodejs)

    Navigate to 'Deploy' on the top ribbon

    In 'Deployment method', select 'Github', once clicked it should say 'connected'

    Enter a repository in Github to connect to and click 'Search'

    Once repository has been found, click 'Connect' to link new app to Github repository

    In 'Automatic deploys', select the 'Enable Automatic Deploy' option

    To view your command line on the Heroku platform, once a new code has been pushed to Github, log on to Heroku

    Select the required app that appears on your home screen

    Select 'Open app' on the right hand side of the screen

    The app should appear in a new tab on the web browser

    The link to my Heroku app is: https://pyblackjack-e3fb5b12d78b.herokuapp.com/

### Forking the GitHub Repository

The following steps can be used to fork the GitHub repository:

- On GitHub navigate to the main page of the repository.
- The 'Fork' button can be found on the top righthand side of the screen.
- Click the button to create a copy of the original repository.

### Cloning the GitHub Repository

The following steps can be used to clone the GitHub repository:

- On GitHub navigate to the main page of the repository.
- Above the list of files select 'Code'.
- Three options are provided, HTTPS, SSH and GitHub CLI. Select the appropriate option and click the 'Copy' button next to the URL.
- Open Git Bash.
- Change the working directory to the location for the cloned directory.
- Type git clone and paste the copied URL.
- Press 'Enter' to create the clone.

### Code

*[Blackjack functional Programming](https://github.com/plemaster01/pygameBlackjack/blob/main/pygame_blackjack.py)

*[Real Python](https://realpython.com/lessons/random-data-generation-python/)

## Credits

- Credit and articles etc that we have copied code from

*[ASCII CHR() CODE CHART for QTP UFT Selenium Playwright and Cypress](https://testguild.com/qtp-ascii-chr-code-chart/)

*[Blackjack functional Programming](https://github.com/plemaster01/pygameBlackjack/blob/main/pygame_blackjack.py)

*[Real Python](https://realpython.com/lessons/random-data-generation-python/)

