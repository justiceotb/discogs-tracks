# DISCOGS COLLECTION TRACKS
Turn a Discogs collection into a spreadsheet of tracks.

## Prerequisites

### Creating a Discogs token
* Log into Discogs.
* Click the user avatar on top right of screen.
* Settings.
* Developers.
* Generate new token.

Save this token, but be careful not to share it with anyone - this is an API token to your account. For some more info see [Discogs User-token Authentication](https://github.com/joalla/discogs_client/blob/master/docs/source/authentication.md#user-token-authentication).

### Setting up your Python environment

* Install Python 3
* Create a Python virtual environment
```
PS C:\discogs-tracks> python -m venv .venv
PS C:\discogs-tracks> .\.venv\Scripts\Activate.ps1 
```
or
```
C:\discogs-tracks> python -m venv .venv
C:\discogs-tracks> .\.venv\Scripts\Activate.bat
```
* Install the Python requiremnts into the virtual environment
```
> python -m pip install -r requirements.txt
```

## Using
```
> python all-songs.py -h
usage: all-songs.py [-h] --token TOKEN [--file FILENAME]

Create an Excel spreadsheet or tracks from a Discogs collection

options:
  -h, --help       show this help message and exit
  --token TOKEN    Your Discgos API token
  --file FILENAME  The spreadsheet name, including .xlsx. Default is tracks.xlsx
```

### Example 
```
> python all-songs.py --token abc123xyz890 --file all-my-songs.xlsx
```

## Output
A spreadsheet with the following colums will be generated:
| Column | Description |
|--------|-------------|
| Album ID | The internal Discogs reference for this release
| Album | The album title
| Year | The year it was released
| Artists | The album artist
| Track Number | The track number
| Track | The track title
| Track Artists | The track artist (if different to the album arttist)
| Styles | The music styles, as recorded in Discogs
| Format | The release format
| Notes | Any notes that you have made to the collection entry