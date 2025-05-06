# PyEasyThymio

This is a package to allow anyone to code Thymio-II robot using simple Python scripts in a sequential manner. We also included a librry to write a state machine class to control Thymio following the notes in [this course](https://data-driven-world.github.io/2023/notes/category/week-8-design-of-state-machines).

## Instalation

Use the package manager to install pyeasythymio.

```shell
python -m pip install pyeasythymio --upgrade
```

## Requirements

First, you need to make sure that you have [Thymio Suite](https://www.thymio.org/download-thymio-suite/) downloaded. Before you run any Python script with `pyeasythymio` library, open and run the Thymio Suite. You can leave it at the background while writing your code in Python. At the bottom left of Thymio Suite, make sure you can see "Discovery service enabled". This allows your computer to find and connect to the Thymio-II robot.

## Usage

### Simple Python Script

Create a Python script, say `hello_thymio.py` and import the class `EasyThymio`.

```python
from pyeasythymio import EasyThymio
```

We can then create an `EasyThymio` object. Before that, make sure that your Thymio robot is connected. You can use Thymio Suite to check whether Thymio robot is detected in your computer.

```python
robot = EasyThymio()
```

Once the connection is established, you can use the API to control the robot and read the sensors. See [Documentation](#documentation) below for more detail on the current implemented API.

For example, if you want to move the robots forward, you can set the left and right wheels to 50.

```python
robot.wheels(50, 50)
robot.sleep(5)
```

The code above moves the robot forward for 5 seconds. To read the input from the buttons, you can read the property.

```python
if robot.button_center == 1:
    print("Button is pressed")
```

Finally, to disconnect the robot, call `stop()`.

```python
robot.stop()
```

### State Machine

Will be updated soon.

## Documentation

### Wheels
- `wheels(left, right)`:

### Delay
- `sleep(duration)`:

### Buttons
- `button_backward`
- `button_center`
- `button_forward`
- `button_left`
- `button_right`

### Sensors
- `prox_horizontal`
- `prox_ground`
- `prox_ground_ambiant`
- `prox_ground_delta`
- `prox_ground_reflected`
- `acc`
- `temperature`

### LEDs
- `leds_circle(br0, br1, br2, br3, br4, br5, br6, br7)`:
- `leds_top(red, green, blue)`
- `leds_bottom_right(red, green, blue)`
- `leds_bottom_left(red, green, blue)`:
- `leds_buttons(br0, br1, br2, br3)`:
- `leds_leds_prox_h(br0, br1, br2, br3, br4, br5, br6, br7)`:
- `leds_leds_prox_v(br0, br1)`:
- `leds_rc(br)`:

### Sounds
- `leds_sound(br)`:
- `leds_temperature(r, g)`:
- `sound_system(sound_id)`:
- `sound_duration(sound_id, duration)`:
- `sound_record(sound_id)`:
- `sound_play(sound_id)`:
- `sound_replay(sound_id)`:






