<h1 align="center">A Garden Irrigation System for Home Assistant</h1>


<h2>Background</h2>

This package is a completely self contained* system for Home Assistant which as presented here will control five different irrigation zones over two cylces per day. However, I have tried to write it in such a way that there is as little code replication as possible which means that if you want a different number of zones then you more or less have to just add more (or remove) some  ```input_boolean / number / datetime / select```s in```garden_globals.yaml``` and the rest of the code largely takes care of itself. There are a couple of automations that will also need to be replicated but I think (hope) tat these should be self explanatory.

The system as I have it implemented is based around Sonoffs controlling the valves but that should be irrelevant.

The weather calculation sections are experimental and I have never actually relied on them. 

__*Note -__ A few extra features here such as Amazon Dash button control and notifications depend on other parts of my configuration so you will have to either remove those sections or adapt them to suit you.

__Disclaimer__ - This was the first thing I wrote for HA (apart from the obligatory 'light-on-when-it-is-dark-automation' that everyone does) so I *know* that there are things I could have done better / more elegently. I might one day get round to improving the code but it worked flawlessly all through the summer of 2018 and I don't want to break it!

*Any feedback including constructive criticism is very welcome and I'm particuarly interested if you have any ideas for improving the weather calcualtions.*

<h1>Here is how it looks in Lovelace</h1> 


__The Master control Switch OFF hides all other UI elements__

<img src="https://github.com/kloggy/Home-Assistant/blob/master/packages/garden/Screenshots/MasterControlSwitch.png">

__The Morning Cycle showing the Schedule__

<img src="https://github.com/kloggy/Home-Assistant/blob/master/packages/garden/Screenshots/MorningCycleWithSchedule.png">

__The Morning Cycle showing the Weather Adjustments

<img src="https://github.com/kloggy/Home-Assistant/blob/master/packages/garden/Screenshots/MorningCycleWithWeatherAdjustments.png">

__Showing the Irrigation History

<img src="https://github.com/kloggy/Home-Assistant/blob/master/packages/garden/Screenshots/IrrigationHistory.png">
