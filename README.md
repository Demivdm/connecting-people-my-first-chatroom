> _Fork_ deze leertaak en ga aan de slag. Onderstaande outline ga je gedurende deze taak in jouw eigen GitHub omgeving uitwerken. De instructie vind je in: [docs/INSTRUCTIONS.md](docs/INSTRUCTIONS.md)

# My first chatroom in PlantSwap huisstijl

![WhatsApp_Video_2023-05-22_at_18_02_39_AdobeExpress](https://github.com/Demivdm/connecting-people-my-first-chatroom/assets/112861166/9a217291-ba32-4533-a7ef-7bc4b48019d8)

## Inhoudsopgave

- [Beschrijving](#beschrijving)
- [Tools](#tools)
- [Kenmerken](#kenmerken)
- [Extra functionaliteiten](#extra-functionaliteiten)
- [Bronnen](#bronnen)
- [Licentie](#licentie)

## Beschrijving

Dit is een realtime chatroom die ik heb gemaakt voor de "My first chatroom" deeltaak. De chatroom is gemaakt in de huisstijl van PlantSwap. Door de chatroom te maken heb ik een beetje kunnen oefenen met socket.

## Tools

🧦Socket.io

🚂Express

🥜Node.js

🖥️HTML

🖌️CSS

## Extra functionaliteiten

Voor de extra functionaliteiten heb ik toegevoegd dat de kleur van het bericht van de gebruiker anders is dan de kleur van het bericht van de ontvanger. De gebruiker ziet zijn eigen berichten rechts uitgelijnd in het oranje. De gebruiker ziet de berichten van andere gebruikers links uitgelijnd in het groen. Ik heb dit op de volgende manier gedaan; 

Eerst heb ik op de server side een emit uitgevoerd. Een emit is een custom verzoek naar de (socket) server. In deze emit stop ik de message en een user id. In uid zit een id wat socket voor het bericht aanmaakt. 

```js io.emit('message', {uid: socket.id, message: message})```

Vervolgens heb ik client side een functie gemaakt om te herkennen van wie het bericht is. 

```js
function addMessage(uid, message) {
// er is een uid voor het bericht en de ioServer.id is voor de gebruiker.
  let messageClass = ''
 ```
Als er een uid is(wat er altijd is) voer dan de volgende code uit:

 ```js  if(uid){ ```
 
 Alle kinderen van de variabele "messages" krijgen een li eraan toegevoegd.
 
 ```js
 const messageConst = messages.appendChild(Object.assign(document.createElement('li'), {textContent: message }))
 ```
Als de message id overeenkomt met de ioServer id dan is het bericht van de gebruiker zelf dan wordt een class met de uitlijning aan het variabele messageConst toegevoegd.
    
 ```js
    if (uid == ioServer.id) {
      messageConst.classList.add('eigen-bericht')
    }
    messages.scrollTop = messages.scrollHeight
  }
}
```

## Bronnen
[Justus](https://github.com/ju5tu5)
[Tolga](https://github.com/Tolga1999)
[Krijn](https://github.com/krijnhoetmer)

## Licentie

This project is licensed under the terms of the [MIT license](./LICENSE).
