# Greetings

## Hello there 

:wave:
Hey there, I'm Alexandro castro, brazilian :brazil: , but now living in Portugal :portugal:

I Love Open Source, FrontEnd and Mobile Development Project

:man_technologist: All of my projects are available at https://github.com/alexcastrodev

:memo: I regularly write articles on https://alexandrocastro.dev.br

:page_facing_up: Know about my experiences https://www.linkedin.com/in/alexandro-c-oliveira/


<br>
<hr/>
<br>

# Quick Start

If you want to use `npm`, you can use this command.

```bash
npm i castroclock
```

Maybe you want to use `yarn`.

```bash
yarn add castroclock
```



## How to use

This `package` does not have any dependencies. Therefore, you are free to design what you want.

## imports

Import this module

```javascript
import CastroClock from 'castroclock-js'
```

## Typescript support 

To have a typescript support, you should import

```javascript
import { CastroClockType } from 'castroclock/types'
```


## Examples

Project code:

https://github.com/AlexcastroDev/chronometer-react

Preview:
https://chronometer.vercel.app/


## Tests

All calls and exceptions are covered by Jest

## Documentation

### start

This method returns instance of Timer, and start chronometer

Exemple: 
```javascript
CastroClock.start()
```

### pause

This method returns instance of Timer, and pause chronometer

```javascript
CastroClock.pause()
```

### continue

This method is a void, and resume chronometer

```javascript
CastroClock.continue()
```


### lap

This method returns an array of stops (object), that contains: `start_at (unix)`, `ends_at (unix)` and a string called `period` that returns `00:00:04`

If `start` and `wait` 4 seconds

```javascript
CastroClock.lap()
```

### reset

This method returns instance of Timer, and reset chronometer status

```javascript
const logger = () => {
    console.log("I'm here")
}
CastroClock.onChange(logger)
```

### onChange

This method recieve a `() => void` that is called when [one of them] `pause`, `reset`, `lap`, `continue` are called.

```javascript
CastroClock.reset()
```

### currentTime
This getter returns an object, that contains: `hours (Number)`, `minutes (Number)`, `seconds (Number)`

### currentTimeString
This getter returns a string that returns `00:00:04` 

If `start` and `wait` 4 seconds

### periodTime

Period time: When you call `CastroClock.start()` untill Call this getter.

This getter returns an object, that contains: `hours (Number)`, `minutes (Number)`, `seconds (Number)`

### periodTimeString

This getter returns a string that returns `00:30:00` 

If you `start`, wait about 30 minutes and call this getter or your `lap`s time is about 30 minutes and call this getter.


### Timer
This getter returns a Proxy Handler

```
_instance: {
        startInstance: Number | null,
        stopInstance: Number | null,
    },
    stopwatch: {
        startTime: Number | null,
        stopTime: Number | null,
    },
    stops: [
        {
            start_at: Number | null,
            ends_at: Number | null,
            period: string | null,
        }
    ],
    onChange: Function
```