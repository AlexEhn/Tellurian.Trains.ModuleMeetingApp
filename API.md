# Clock API
The API is intended for supporting many clock instances running in parallel. 
At the moment only oneinstance is supported and it is named *Default*.
Using any other instance name will return *NotFound*.

Any action that modify the clocks state required an *API-key*. 
All calls that requires an API-key returns *Unauthorized* if no or incorrect API-key is provided.
The API-key is configured in the servers settings.

The API is English-only. Clients has the responsibility to translate to other languages.

The {*server*} placeholder in the url:s represents a name or ip-address with an optional port number,
for examle *192.168.0.182:5001* or *telluriantrainsclocksappserver.azurewebsites.net*

## Get time and status
    https://{server}/api/clock/Time/Default
```json
{
    "name": "TellurianClock",
    "weekday": "Wednesday",
    "time": "06:02",
    "duration": 15,
    "isRunning": false,
    "isRealtime": false,
    "isCompleted": false,
    "message": "",
    "speed": 5.5,
    "isUnavailable": false,
    "realEndTime": "13:14",
    "fastEndTime": "21:00",
    "isPaused": false,
    "pauseReason": "Dinner",
    "expectedResumeTimeAfterPause": "13:00",
    "stoppedByUser": "",
    "stoppingReason": "SelectStopReason"
}
```
- **weekday** - { None | Monday | Thuesday | Wednesday | Thursday | Friday | Saturday | Sunday }
- **duration** - is total game duration in hours. May have fraction of hours; 15.5 means 15 1/2 hour.
- **pauseReason** - { None | Breakfast | Lunch | Dinner | Meeting | Closing | Other }
- **stopReason** - see **Stop Clock** below.
## Start clock
    https://{server}/api/clock/Start/Default?apiKey={anApiKey}

## Stop clock
    https://{server}/api/clock/Stop/Default?apiKey={anApiKey}&user={userOrStationName}&reason={aReason}
- **User- or station name**
should be url-encoded if it contains non-ASCII characterns (like **���**). 
Returns *BadRequest* if not provided.
- **Reason** should be one of the strings below. Returns *BadRequest* if other value is provided.
    - **StationControl** - problems with operating a station.
    - **SwitchProblem** - problems woth one or several switches.
    - **TrackProblem** - Problem with track , for example module joints.
    - **BoosterError** - Booster not working or shortcuts that hinders operation.
    - **LocoNetError** - Problems with LocoNet cabling and/or signals.
    - **CablingError** - Other cabling error.
    - **CentralError** - Problems with the digital central(s).
    - **Delays** - Sever delays in operation requires stopping clock to catch up.
    - **DriverShortage** - Duties become unassigned after their start time.
