# Saudações

## Bem vindo(a)

:wave:
Olá pessoal, Eu sou Alexandro castro, Brasileiro :brazil: , agora morando em tuga :portugal:

Eu amo sistemas livres, desenvolvimento de projetos frontend e mobile.

:man_technologist: Todos meus projetos estão aqui https://github.com/alexcastrodev

:memo: Se quiser ver meus artigos, vídeos, etc... https://alexandrocastro.dev.br

:page_facing_up: E um pouco de minhas experiências https://www.linkedin.com/in/alexandro-c-oliveira/


<br>
<hr/>
<br>

# Instalação

Se você for usar `npm`, use este comando.

```javascript
npm i castroclock
```

e se for usar `yarn`.

```javascript
yarn add castroclock
```


## Como usar

Este `pacote` não tem nenhuma dependência externa. Então fique livre para desenhar qualquer tela que quiser.

## Importação

Só importar o módulo e começar a usar

```javascript
import CastroClock from 'castroclock-js'
```

## Typescript suportado

Se você for usar typescript, você pode pegar todos os tipos aqui

```javascript
import { CastroClockType } from 'castroclock/types'
```


## Exemplos

Projeto usando este pacote:

https://github.com/AlexcastroDev/chronometer-react

Em produção:
https://chronometer.vercel.app/


## Testes unitários

Todas funções tem testes unitários, testes de sucesso, e testes de excessões.

## Documentação

### start

Este método retorna a instância do Timer, e inicia o cronômetro.

Exemple: 
```javascript
CastroClock.start()
```

### pause

Este método retorna a instância do Timer, e pausa o cronômetro.

```javascript
CastroClock.pause()
```

### continue

Este médodo não retorna nada, mas continua a contagem de tempo

```javascript
CastroClock.continue()
```


### lap

Este método retorna uma coleção de objetos que são as voltas, dentro dele tem: `start_at (unix)`, `ends_at (unix)` e uma string `period` que retorna `00:00:04`

Caso essa volta dure 4 segundos

```javascript
CastroClock.lap()
```

### reset

Este método retorna a instância do Timer, e reseta os dados.

```javascript
const logger = () => {
    console.log("I'm here")
}
CastroClock.onChange(logger)
```

### onChange

Essa função recebe uma função normal ou anônima `() => void` que é chamada quando você chama uma dessas funções `pause`, `reset`, `lap`, `continue`

```javascript
CastroClock.reset()
```

### currentTime

Este getter retorna um objeto que contém: `hours (Number)`, `minutes (Number)`, `seconds (Number)`

### currentTimeString

Este getter retorna uma string `00:00:04` 

Caso chame start e chame após 4 segundos

### periodTime

Period time: É o período que você inicia o cronômetro, e chama esse getter

e retorna um objeto que contém: `hours (Number)`, `minutes (Number)`, `seconds (Number)`

### periodTimeString

É o período que você inicia o cronômetro, e chama esse getter, só que formatado.

Se você iniciar, esperar 30 minutos e chamar esse getter, você vai ter 30 minutos aqui, e mesmo que tenha voltas, o tempo total será a soma de todas voltas + tempo atual.

Ao contrário de `currentTimeString`, que só retorna o tempo que está rodando, sem considerar o início da chamada.


### Timer
É onde a mágica acontece, ele é um `getter` que retorna um Proxy Handler
Você não precisa se preocupar com ele, você pode acessar os dados de dentro se quiser.

por exemplo:


```javascript
    console.log(CastroClock.timer.stops)
```

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