# Trivio Game

## About this project
Trivio is an educational trivia game designed for school-aged children (approximately 10–14 years old). The game includes three subject categories — Math, Social Science, and Science — and it supports multiple difficulty levels. Trivio is written in Python and uses the pygame library. Game data is stored in JSON files. The project was developed using Visual Studio Code and PyCharm.

## Requirements
- Python 3.11.3
- pygame 2.5.2
- cx-Freeze 6.15 (optional, for building an executable)

Recommended development environments:
- Visual Studio Code 1.83.2
- PyCharm 2023.3

## Setup

1. Install Python 3.11.3:
   - Download from the official site: https://www.python.org/downloads/
   - Verify installation:
     ```bash
     python3 --version
     ```

2. Install pygame:
   ```bash
   python3 -m pip install pygame
   ```
   or
   ```bash
   python -m pip install pygame
   ```

3. (Optional) Install cx-Freeze if you want to build an executable:
   ```bash
   python3 -m pip install cx-Freeze
   ```

4. Download the Trivio project (ZIP or clone the repository) and extract it if necessary.

## Running the game (from source)
Use this method if you want to run directly from the code.

1. Open the project folder in Visual Studio Code or PyCharm.
2. Ensure the Python interpreter is set to Python 3.11.x and pygame is installed in that environment.
3. In the project root, run:
   ```bash
   python main.py
   ```
   or (if your system uses python3)
   ```bash
   python3 main.py
   ```

## Building an executable (using cx_Freeze)
This describes how to compile the project into a standalone executable.

1. Ensure `cx-Freeze` is installed:
   ```bash
   python3 -m pip install cx-Freeze
   ```

2. Confirm `setup.py` is present in the project root. Then run:
   ```bash
   python setup.py build
   ```

3. After the build completes, change into the `build` directory to find the executable folder:
   ```bash
   cd build
   ls
   # (you will see a folder like exe.win32-3.11 or similar)
   cd exe.<SOME_TEXT>
   ```

4. Move the `images` folder into the `lib` folder inside the executable directory so the executable can find assets:
   - macOS / Linux:
     ```bash
     mv images lib
     ```
   - Windows (PowerShell or cmd):
     ```powershell
     move images lib
     ```

5. Run the executable:
   - macOS / Linux:
     ```bash
     ./main
     ```
   - Windows:
     ```
     main.exe
     ```

Note: Some platforms may require additional packaging of assets or adjustments to the `setup.py` script.

## User Guide

### Player
1. Start the game. The welcome screen will appear and background music will play.
2. Click "Start" to begin, "X" to quit, or "Options" to change the music volume.
3. After clicking "Start" you will see the Login page. You can log in as an existing user or create a new user account.
4. The Debugger and Instructor modes are accessible from buttons on the login screen.
5. After logging in (or creating an account), choose "New Game" or "Saved Game". If no saved game exists, "Saved Game" will show an error.
6. Select a category (Social Science, Science, or Math) and choose a difficulty level to begin playing.
7. During gameplay, the current level is shown at the top center, and the question appears below. Answer the questions to progress.
8. At the end of the game you will see a win or lose screen summarizing your score, category, level, remaining boss HP, and counts of correct/incorrect answers.

### Debugger and Instructor
- Debugger:
  1. From the login page, click the Debugger button.
  2. Enter the debugger password to access the debug menu where you can select a category and view the question bank for testing and validation.

- Instructor:
  1. From the login page, click the Instructor button.
  2. Enter the instructor password to access the instructor dashboard where you can search for a student username and view their last-played timestamp and saved game information.

## Passwords and Sample User Accounts

- Instructor Mode password: `instruct`
- Debugger Mode password: `debug`

Sample user accounts included for testing:
- nateyu / hello
- sophiayuan / 123
- stephoh / oh
- michaelkim / 0987
- harjapgrewal / harjapgrewal

(These accounts are provided for testing/demo purposes only. Remove or change them before deploying or sharing the game publicly.)

## Additional Notes
- One team member reported that the packaged executable `./main` does not run correctly on macOS. If you encounter issues with the executable, run the game from the development environment (python main.py) instead.
- If you need help adjusting `setup.py` for cx_Freeze or packaging assets correctly for different platforms, I can help update that script.

## License
(Include license information here if needed.)