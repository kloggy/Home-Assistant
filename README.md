# Home-Assistant

This might one day have my whole config but at the moment I have only posted my garden irrigation system which is (almost completely) a self contained package.

See here for more information - https://community.home-assistant.io/t/my-garden-irrigation/99686

## Changes ##
*5 April 2019* - Corrected the logic for updating next run time.

-----------------

*31 March 2019* - I have added a script to ```garden_irrigation.yaml``` that sets ```pulsetime[1, 2, 3, 4]``` on the Sonoff to act as a failsafe in the event that HA loses any communication with  the switch.

Thanks to @itajackass for finding the Sonoff command.

