---
title:      Encoder
slug:       encoder-control-element
layout:     reference_manual
category:   reference-manual
description: How to set up encoder-type control elements.
---

## Encoder Button

### button_number
- shortname: bnu
- **How:** `self:button_number()` or `self:button_number(number)`
    - number: signed integer
- **What:** This function when given no parameter, returns the # number of the control element. These numbers are from the top left, read left to right, top to bottom `0` to `15` OR in the case of the PBF4 from `0` to `11`. 
  When this function is given a parameter, it will set the # number of the control element to the `number` given.
- **Example:**

### button_value
- shortname: bva
- **How:** `self:button_value()` or `self:button_value(value)`
  - value: integer, ranging 0...127
- **What:** This function returns the value associated to the button. By default, this value is `127` when the button is pressed down and `0` when released.
  When this function is given a parameter, it will set the value associated with the button state according to the parameter given.
  When using other types of button modes, described later in this chapter, the button values are evenly spread across the steps: eg. spilt 3 was would be values `0` `63` `127` split 4-way would be `0` `47` `95` and `127`.
- **Example:** Inputting the code `self:button_value(127)` will make all button press and  button release event return the value `127`.

### button_min
- shortname: bmi
- **How:** `self:button_min()` or `self:button_min(value)`
    - value: integer, ranging 0...127
- **What:** This function returns the minimum value of the button state. This is `0` by default.
  When given a parameter, this function changes the minimum value of the button state according to the `value` given as parameter.
- **Example:** The code `self:button_min(20)` will set the value of the button to `20` when released.

### button_max
- shortname: bma
- **How:** `self:button_max()` or `self:button_max(value)`
    - value: integer, ranging 0...127
- **What:** This function returns the maximum value of the button state. This is `127` by default.
  When given a parameter, this function changes the maximum value of the button state according to the `value` given as parameter.
- **Example:** The code `self:button_max(110)` will set the value of the button to `110` when pressed down. This can be useful to set easy to use values for a switch, like `self:button_max(1)` will make it so that there are only two values this button can send out `0` and `1`.

### button_mode
- shortname: bmo
- **How:** `self:button_mode()` or `self:button_mode(mode)`
    - mode: integer, ranging 0...127
- **What:** This function returns the value of the button mode. This is `0` by default. Button mode means how many 'steps' the button has between its maximum and minimum value. For example when the function is used to set this value like this: `self:button_mode(mode)` the resolution parameter will govern the number of steps.
- **Example:** The code `self:button_mode(2)` will make the button a 3-step switch. The three states will be `0` , `63` and `127`.

### button_elapsed_time
- shortname: bel
- **How:** `self:button_elapsed_time()`
- **What:** This function returns the time elapsed since the last trigger in frames.
- **Example:**

### button_state
- shortname: bst
- **How:** `self:button_state()`
- **What:** This function will return the "state" of the control element. In case of a button this is either "pressed down" `0`  OR "released" `127`. These values independent from the maximum and minimum values of the control element.
- **Example:**

## Encoder Rotation

### encoder_number
- shortname: enu
- **How:** `self:encoder_number()` or `self:encoder_number(number)`
    - number: signed integer
- **What:** This function, when given no parameter, returns the # number of the control element. These numbers are from the top left, read left to right, top to bottom `0` to `15`. 
  When this function is given a parameter, it will set the # number of the control element to the `number` given.
- **Example:**


### encoder_value
- shortname: eva
- **How:** `self:encoder_value() `or `self:encoder_value(value)`
    - value: integer, ranging 0...127
- **What:**  This function returns the value of the encoder state. By default, this value is `0` when the encoder is turned and tops out at `127`.
  When this function is given a parameter, it will set the value associated with the encoder state according to the parameter given and will output that `value` on each trigger.
- **Example:** 


### encoder_min
- shortname: emi
- **How:** `self:encoder_min()` or `self:encoder_min(value)`
    - value: integer, ranging 0...127
- **What:** This function returns the minimum value configured to the encoder minimum state. This is `0` by default.
  When given a parameter, this function changes the minimum value of the encoder state according to the `value` given as parameter.
- **Example:** The code `self:encoder_min(20)` will set the starting value of the encoder to `20` when rotated.


### encoder_max
- shortname: ema
- **How:** `self:encoder_max()` or `self:encoder_max(value)`
    - value: integer, ranging 0...127
- **What:** This function returns the maximum value configured to the encoder maximum state. This is `127` by default.
  When given a parameter, this function changes the maximum value of the encoder state according to the `value` given as parameter.
- **Example:** The code `self:encoder_max(110)` will set the end value of the encoder to `110` when turned.


### encoder_mode
- shortname: emo
- **How:** `self:encoder_mode()` or `self:encoder_mode(mode)`
    - resolution: integer, ranging 0...1
- **What:** This function returns the value of the encoder mode. This is `0`  or "absolute mode" by default.
  When function is given `1` as a value, it will change the encoder to "relative mode". In this mode turning the encoder 'backwards' or counterclockwise will always result in the value `63` and turning it 'forwards' or clockwise will always result in the value `64` .
- **Example:** The code `self:encoder_mode(1)` will change the encoder into relative mode. 


### encoder_velocity
- shortname: ev0
- **How:** `self:encoder_velocity()` or `self:encoder_velocity(velocity)`
  - velocity: integer, ranging 0...100
- **What:** This function returns the value of the encoder velocity parameter. This is `100` by default. When the function is given a value for the `velocity` parameter, it will set  the encoder velocity to that value. Velocity increases the steps the encoder value increases on each tick, depending on the speed of rotation. Setting the `velocity` parameter to `0` turns off encoder velocity completely.
- **Example:**  The code `self:encoder_velocity(0)` will turn off the velocity increase function of the encoder. In this case turning the encoder by one tick, will increase the value of the encoder by 1. 


### encoder_elapsed_time
- shortname: eel
- **How:** `self:encoder_elapsed_time()`
- **What:** This function returns the time elapsed since the last trigger in frames.
- **Example:** 
### encoder_state
- shortname: est
- **How:** `self:encoder_state()`
- **What:** This function will return the "state" of the control element.
- **Example:** 