# opengamedata-api-gamestates

Repository for the OpenGameData Player ID + State Saving API. These allow users of `opengamedata-unity` and `opengamedata-js-log` to obtain randomly-generated IDs to display for users, which can then be used to save and restore game states.

## Getting Started

### Hello World of Flask

Steps to run:

1. Check out latest `opengamedata-server`.
2. Run `pip install -r requirements.txt` to ensure you've got flask.
3. Run `flask run`.
4. Open localhost:5000 or localhost:5000/hello to see some really basic text output from the Flask server.

If Flask doesn't run, it's possible you'd need to first export FLASK_APP as an environment variable, set to "wsgi" (so in Bash, export FLASK_APP=wsgi).
However, the script is named wsgi.py specifically because Flask is supposed to auto-detect it. So if this issue ever did come up, please ping Luke so he can look into it.

## APIs

Below is a listing of the current API calls available, in function format to indicate what the request parameters.
For each API, there is also an api path, with path parameters in angle bracket (<, >) format.
Lastly, at this point in time, the `<server_path>` is `https://fieldday-web.wcer.wisc.edu/opengamedata.wsgi`

### GameState API

#### Save and retrieve game states

`<server_path>/player/<player_id>/game/<game_id>/state:`  
`GET(int count = 1, int offset = 0)`  

- Returns a list of game states, length == count, starting from the nth most-recent state, where n == offset, or a null value and an error message.

`POST(str state)`

- Attemps to save the state. Returns a null value and a success/error message.

### Hello API

#### Verify the API is alive

`<server_path>/hello`  
`GET()`

- returns no value, and a success message  

`POST()`

- returns no value, and a success message

`PUT()`

- returns no value, and a success message
