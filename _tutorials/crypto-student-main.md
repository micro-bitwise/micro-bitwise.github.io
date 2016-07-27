---
layout: tutorial
tutorial_type: Main Activity
authors:
- Joe Savage
- Ross Gardiner
---

# Encryption

With an understanding of what cryptography is and why it's important, the question remains: *how* exactly does encryption hide messages? To examine this question — and some solutions — more closely, let's write a program that allows two micro:bits to talk to one another: Micro:bit Messenger.

## Hello, World

Let's take another look at the script from the starter activity:

```
from microbit import *

import radio

radio.on()

while True:
    if button_a.was_pressed():
        radio.send("Mr Eric Praline") # Change this to your name!

    new_message = radio.receive()
    if new_message:
        display.scroll(new_message)
```

Though primitive in nature, this could be considered a very simple free-for-all messaging program. Scripts of this kind simply consist of a series of commands that the computer should execute, from top to bottom. In this case, the code does the following:

1. Import some handy conveniences to allow the script to easily manipulate various features of the micro:bit.
2. Turn on the micro:bit's radio to allow it to communicate over Bluetooth, a technology for wirelessly sending messages over short distances.
3. Do the following forever:
	1. If the 'A' button was pressed, send a message over the radio with your name.
	2. Check for any messages from the radio, displaying anything that is found.

There are a few obvious problems with this though. Firstly, messaging applications [*usually*](https://en.wikipedia.org/wiki/Yo_(app)) let you write your own message rather than sending one for you. And secondly, we probably want to introduce some idea of different chats rather than a single free-for-all.

<!-- TODO: Add alphabet selection -->

The radio in the micro:bit doesn't allow you to send messages directly to one person — anyone can listen in on your conversation. Instead, groups of messages can be differentiated by a channel. Sending messages over multiple channels is similar to the transmission of multiple radio stations. Different stations broadcast on different frequencies at the same time, but your car radio — though it *could* listen to all the stations simultaneously — is set up to only listen to one channel at a time. After all, nobody wants to listen to One Direction, The Beatles, and Metallica all at the same time.

Within a particular channel, there are further ways to distinguish between messages such as sending with and filtering by a particular number called an 'address' (much like a postal address). We can configure the radio to listen and send only on a particular set of related communications — e.g. address 50 on channel 3 — by adding the follow command after enabling the radio:

```
radio.config(channel=7, address=50)
```

You can try this with your partner. Add the above line to the script we used previously — choosing a channel between 0 and 100 and an address between 0 and 4,294,967,295 — and watch how the conversation suddenly seems so quiet. Despite appearances, however, this conversation is far from private! Every message is still being broadcast for all to see, it's just that most devices are keeping themselves to themselves and not eavesdropping. So how can we go about resolving this issue of privacy?

## Cryptography!

Thankfully, our old friend cryptography is here to save the day. If we scramble our messages such that only the intended recipients are able to unscramble them, our secrets are safe. Anyone listening in may intercept the scrambled message, but they won't know what to make of it. But how should we actually go about muddling up our messages in this way?

One simple solution, which has been used since at least 50 BC, is the *shift* or *Caesar cipher*. This replaces each letter in the *plaintext* (the raw message we want to transmit), with a different letter some fixed number of positions away in the alphabet, wrapping back around to the ends of the alphabet when necessary. If we choose to shift three spaces down the alphabet, for example, all `A`s become `D`s, `B`s become `E`s, `X`s become `A`s, etc.

{% include image.html source='/assets/contrib/images/crypto/caesar-cipher-right-shift-3.png' alt='A Caeser cipher shifting three positions to the right' caption='Each letter is replaced by another three letters down in the alphabet' %}

Under this scheme, the plaintext “The quick brown fox jumps over the lazy dog” is transformed into the *ciphertext* (the result of cipher encryption) as follows:

```
Plaintext:  The quick brown fox jumps over the lazy dog.
Ciphertext  Wkh txlfn eurzq ira mxpsv ryhu wkh odcb grj.
```

This ciphertext is then broadcasted, and any valid receiver of the message — with whom this code of shifting three places to the right has already been established — then needs only to shift each letter back three places. `A` becomes `X`, `D` becomes `A`, `E` become `B`, etc. This seems like a clear improvement on transmitting plaintext, so let's integrate this idea into our messaging program.




---

<!-- TODO: -->
<!-- - Actually implement the thing -->
<!-- - The language is too closely related to English (e.g. punctuation, letter frequency, etc.), hence cryptanalysis is easy. Try it out by using X script to log messages from another group and then break their encryption! -->
<!-- - Lead into the issue that we needed initial secret communication in the first place, which isn't always possible over the Internet -->

