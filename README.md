# mst_autoattend

![banner](https://i.imgur.com/xtq5Muz.png)

This python application will automatically join [Microsoft Teams](https://www.microsoft.com/en-in/microsoft-365/microsoft-teams/group-chat-software) meetings appearing in your [Teams calendar](https://teams.microsoft.com/_#/calendarv2). On the first run, you have to enter the credentials which are saved and then used later in the subsequent runs (can be reset using `--reset` while running the application).

## Features:

The salient features of the application are:

- add a random delay (10s - 180s) between joining and leaving meeting
- automatically join a meeting if available
- turn off your camera and microphone
- it periodically looks for new meetings and joins them
- gives option of having browser open in case the user wants to attend the meeting in person

NOTE: If the organiser does not end the meeting i.e. attendees are made to leave the meeting, the script will automatically leave the meeting after the number of participants present in the meeting falls below the minimum participants allowed set by the user, but will rejoin the meeting if the join button is still visible on the calendar tab.

## Installation

The script requires the following before installation:

- [>Python3.6](https://www.python.org/downloads/)
- [Google Chrome browser](https://www.google.com/intl/en_in/chrome/)

To install the script use `pip install mst_autoattend`

NOTE: For windows please [install pip](https://phoenixnap.com/kb/install-pip-windows) and then install the program using pip.

## Usage:

Run the script using `mst_autoattend` in your terminal. On the first run, the script would ask for basic configuration which is stored and used in the subsequent runs.

NOTE: To reset config, run with `mst_autoattend --reset`

### Config

The following configuration is asked when you run the script for the first time:

- `Please enter your MS Teams username: ` - enter your microsoft teams username
- `Please enter your MS Teams password: ` - enter your microsoft teams password
- `Please enter minimum participants to exit the meeting: ` - the minimum number of participants required to stay in the meeting
- `Do you want to interact in the meeting while it is going on? (y/n): ` - "y" will open a chrome browser with the script when it is running, "n" will run it in the terminal only

NOTE: The configuration is saved in your home directory and the credentials are not sent to any remote server or the author.

## Example Scenarios

### Scenario 1 (you wake up before the meeting)

- You have a meeting at 9 A.M, you may run the script anytime before 9 A.M. and the script will automatically join the meeting when the join button is available.
- The script will then automatically join the next meeting scheduled at e.g.:- 10 A.M. AFTER the organiser ends the meeting.
- If the organiser does not end the meeting i.e the organiser leaves the meeting instead of ending the meeting and tells the attendee to leave the meeting, the script will leave the meeting after the strength of the meeting falls down to 10 or any minimum value set by user.

### Scenario 2 (you don't want wake up before the meeting)

- You have a meeting at 8 A.M, you may run the script before sleeping at night and keep your laptop on.
- The script will then automatically join the meeting once the join link becomes available at 9 AM.
- Voila! You've been saved. If you had set interactive mode to "y", you'll be able to see the meeting going on and join when you wake up.

## Contributing

For requesting new features or [report bugs](https://polite.technology/reportabug.html), please raise a ticket in the issues tab.

### Local Setup

Please follow the steps to setup locally for development purposes.

- Clone the repository.
- [Install Python 3.6 or higher](https://www.python.org/downloads/)

#### Using Pipenv

- [Install Pipenv](https://pipenv-fork.readthedocs.io/en/latest/install.html)
- run `pipenv shell --three` to create a new virtual environment
- run `pipenv install` to install the required dependencies

#### Using pip

- run `pip install -r requirements.txt` to install dependencies

## Credits

This is forked from [MS-Teams-Auto-Joiner](https://github.com/atharva-lipare/MS-Teams-Auto-Joiner).