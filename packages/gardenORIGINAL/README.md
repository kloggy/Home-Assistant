<h1 align="center">A Garden Irrigation System for Home Assistant</h1>


<h2>Background</h2>

This package is a completely self-contained* system for Home Assistant which as presented here will control five different irrigation zones over two cylces per day. However, I have tried to write it in such a way that there is as little code replication as possible which means that if you want a different number of zones then you more or less have to just add more (or remove) some  ```input_boolean / number / datetime / select```s in```garden_globals.yaml``` and the rest of the code largely takes care of itself. There are a couple of automations that will also need to be replicated but I think (hope) that these should be self-explanatory.

The system as I have it implemented is based around Sonoffs flashed with Tasmota controlling the valves but that should be irrelevant.

The weather calculation sections are experimental and I have never actually relied on them. 

__*Note -__ A few extra features here such as Amazon Dash button control and notifications depend on other parts of my configuration so you will have to either remove those sections or adapt them to suit you.

__Disclaimer__ - This was the first thing I wrote for HA (apart from the obligatory 'light-on-when-it-is-dark-automation' that everyone does) so I *know* that there are things I could have done better / more elegantly. I might one day get around to improving the code but it worked flawlessly all through the summer of 2018 and I don't want to break it!

*Any feedback including constructive criticism is very welcome and I'm particularly interested if you have any ideas for improving the weather calculations.*

__Weather sensors:__ I use SmartWeather and DarkSky weather sensors to provide the data for duration adjustments.

Smart Weather is a custom component - https://github.com/briis/smartweather

--------------

<h6>Thanks to @krash, @itajackass and @woody4165 for suggestions and help in making it better.</h6>

--------------

## Changes ##
*1 September 2019* - A complete re-upload of my files as it appears that there may have been some errors/inconsistencies which crept in due to me using GitHub only as a way to make my files public rather than as any kind of master repository or version control.

Also my new Lovelace Garden view which I think is an improvement.

*16 August 2019* - Many small changes. Mostly tidying up code and renaming to standardise some items especially automations which shouldn't make any difference but do help when debugging. Also some slight reworking of the weather adjustment code which should be an improvement :-)

If you already use this package please take some care before blindly copying this across I think it might have to be all or nothing if it isn't going to break. If you want to find my 'improvements' they should be easily implemented in your version.

*10 July 2019* - Small change to immediately update the Adjusted Zone Durations whenever the temperature or rain thresholds are changed.

*5 April 2019* - Corrected the logic for updating next run time.

*31 March 2019* - I have added a script to ```garden_irrigation.yaml``` that sets ```pulsetime[1, 2, 3, 4]``` on the Sonoff to act as a failsafe in the event that HA loses any communication with  the switch.


<h1>Here is how it looks in Lovelace</h1> 

__The Master Control Switch 'OFF' hides all other UI elements__

<img src="https://github.com/kloggy/Home-Assistant/blob/master/packages/garden/Screenshots/MasterControlSwitch.png">

__The Morning Cycle showing the Schedule__

<img src="https://github.com/kloggy/Home-Assistant/blob/master/packages/garden/Screenshots/MorningCycleWithSchedule.png">

__The Morning Cycle showing the Weather Adjustments__

<img src="https://github.com/kloggy/Home-Assistant/blob/master/packages/garden/Screenshots/MorningCycleWithWeatherAdjustments.png">

__Showing the Irrigation History__

<img src="https://github.com/kloggy/Home-Assistant/blob/master/packages/garden/Screenshots/IrrigationHistory.png">
