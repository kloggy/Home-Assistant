<h1 align="center">A Guest Mode Package for Home Assistant</h1>


<h2>Background</h2>

This package is (mostly) self-contained and allows for an ad-hoc guest mode as well as two or more regular schedules.

You will obviously need manage how you deal with Occupancy in general because everyone's requirements are different but to use this you will need to include the following somewhere in your configuration to indicate that Guest Mode is active:


```
#===================
#=== Binary Sensors
#===================
binary_sensor:
  - platform: template
    sensors:

      #======================================================
      #=== Guest Mode - set on when a guest timer is running
      #======================================================
      guest_mode:
        friendly_name: Guest mode
        value_template: >
          {{ is_state('timer.guest_mode_once_duration', 'active') or
             is_state('timer.guest_mode_schedule_1_duration', 'active') or      
             is_state('timer.guest_mode_schedule_2_duration', 'active') }}      
        icon_template: >
          {% if is_state('binary_sensor.guest_mode', 'on') %}      
            mdi:account-multiple
          {% else %}
            mdi:account-multiple-minus
          {% endif %}
```

<h2>Here is how it looks in Lovelace</h2> 

__Guest Mode 'OFF'__

<img src="https://github.com/kloggy/Home-Assistant/blob/master/packages/occupancy/screenshots/GuestModeOff.png">


__Guest Mode 'ON'__

<img src="https://github.com/kloggy/Home-Assistant/blob/master/packages/occupancy/screenshots/GuestModeOn.png">


__Guest Mode 'ON' expanded__

<img src="https://github.com/kloggy/Home-Assistant/blob/master/packages/occupancy/screenshots/GuestModeOnExpanded.png">


__Guest Mode 'ON' fully expanded__

<img src="https://github.com/kloggy/Home-Assistant/blob/master/packages/occupancy/screenshots/GuestModeOnFullyExpanded.png">


__Guest Mode 'ON' two schedules fully expanded__

<img src="https://github.com/kloggy/Home-Assistant/blob/master/packages/occupancy/screenshots/GuestModeOnTwoSchedulesFullyExpanded.png">


__Guest Mode popup__

<img src="https://github.com/kloggy/Home-Assistant/blob/master/packages/occupancy/screenshots/GuestModePopup.png">
