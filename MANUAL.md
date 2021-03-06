# Administrators manual
This manual describes what the clock administrator has to know and what to tell the other participants. 
The manual is valid for both cloud- and local version. 
To running clock locally, see separate documentation [Installation](https://github.com/tellurianinteractive/Tellurian.Trains.ModuleMeetingApp/blob/master/INSTALLATION.md).

## Setting up a new clock
The *Demo clock* is always the starting point for setting up a new clock.
The *Cloud version* of the clock application is found [here](https://telluriantrainsclocksappserver.azurewebsites.net/).
How to access a locally running clock server is described in [Installation](https://github.com/tellurianinteractive/Tellurian.Trains.ModuleMeetingApp/blob/master/INSTALLATION.md).

First you have to be an administrator of the *Demo clock*:
1. Go to the **Registration** page and enter your name and the *Demo clocks* password, which always is '*password*' and cannot be changed.
1. Be sure that you also select the *Demo* clock.
1. Klick **Save**. 

Then you create your own clock instance:

4. Go to the **Clock administration** page.
1. Change *clock name* to a descriptive name for your purpose.
1. Its also recommended that you change the clocks *password*.
1. Change the other settings of choice.
1. Klick **Apply**.

Now your registstration is updated with your new *clock name* and *clock password*, 
so it automatically becomes the selected clock for you.

Once you have registerd a clock, its *name* is reserved. 
If somebody else tries to register a clock with the same name to steal it, such registration is ignored.

## Let other users access the clock
Other users can access your newly created clock in these steps:
1. Open a web browser window.
1. Enter the URL for the *clock application*. 
It could be the [*cloud version*](https://telluriantrainsclocksappserver.azurewebsites.net/) or a local version. 
To access the clock locally, see separate documentation [Installation](https://github.com/tellurianinteractive/Tellurian.Trains.ModuleMeetingApp/blob/master/INSTALLATION.md).
1. Go to the **Registration** page and select the appripriate clock name in the dropdown list.
1. Optionally enter your name or your stations name. This gives the user the right to stop and start the clock for some reason.
1. Click **Save**.
1. Go to the **Clock** page.
1. Click on **Show more** and verify that it is the correct clock name your are displaying.

## Stopping and starting clock during game
Sometimes something happens that requirest the clock to be stopped. 
All users that register their (or their stations) name can stop the clock if they select a reason for it.
The clock will display who stopped the clock and why. Reason shows in the choosen language.

When the problem is fixed. only the user that requested the stop or the administrator can resume game time.


## Managing pauses
The clock can be configuret to automatically stop at a specific real time displaying a reason for stopping. 
This is practical for example when a game continues after lunch.
In the **Clock administration** page do the following:
1. Enter a real time to pause.
2. Select a reason for pause.
3. Enter the estimatied real time when you extect to resume the game.
4. Optionally select if the clock shold show real time during pause. This does not affect the game time, but everyone sees when to resume.
4. Click **Apply**.

> ***EXAMPLE* Lunch break**:
>  Pause time is 12:00 when the lunch start.
> The reason is 'lunch'
> The estimated time to resume is 13:00.

When you enter an estimated time to resume, the expected real end time of the game will include the pause. 

NOTE: Only the administrator can resume the game time after a pause.
