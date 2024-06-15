# pigpio-debugger

a CLI tool that allows for writing to pigpio pins.

## Installation

```sh
npm i -g pigpio-debugger
```

## Usage

### Single write

```txt
Usage: pigpio-debugger single --pin <gpio number> (--digital/--servo/--analog) --value <value>

Options:
  -p, --pin <pin>      GPIO number
  -d, --digital        Digital write
  -s, --servo          Servo write
  -a, --analog         PWM/analog write
  -r, --range <range>  PWM range
  -f, --frequency      PWM frequency
  -i, --info           Get info about a GPIO device.
  -w, --wait <value>   Value to wait (in ms)
  -v, --value <value>  Value to write
  -m, --mock           Doesn't actually use pigpio; simply mocks values and logs it.
```

### Multi write

```txt
Usage: pigpio-debugger multi <value>t<gpio number><mode>[t(ime)=ms]

t stands for to

mode:
        d for digital,
        s for servo,
        a for analog/pwm,
        f for frequency

Examples:
        to set the servo pulse width to 1500 on GPIO 6 and wait 1s
                pigpio-debugger multi 1500t6s[t=1000]
        to write the digital value "1" on GPIO 5
                pigpio-debugger multi 1t5d
        to start and stop servos 3,4,5 for 2s
                pigpio-debugger multi 1700t3s 1700t4s 1700t5s[t=2000] 1500t3s 1500t4s 1500t5s[t=2000]

Options:
  -m, --mock  Doesn't actually use pigpio; simply mocks values and logs it.
```

## Contributing

If you want to contribute allowing reading GPIO pins, feel free to!
