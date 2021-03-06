---
layout: tutorial
tutorial_type: Lesson Plan
authors:
- Joe Savage
- Ross Gardiner
---

# Encryption

## Overview

Our society depends utterly on our ability to securely send messages — like financial transactions, business emails and medical records — so that they cannot be intercepted and read by criminals or other 'bad actors'.

*Cryptography* is the complex and subtle science of scrambling a message's contents so that it can be read only by its intended recipient.

In this activity, students will learn about simple forms of cryptography and use them to exchange messages.

{% include image.html source='http://imgs.xkcd.com/comics/cryptography.png' alt='xkcd 153' caption='(from [xkcd](https://xkcd.com/153/))' %}

### What you need

* Teams of two, paired into teams of four
* One micro:bit per person
* The `Mu` Python editor

### Resources

* [BBC micro:bit MicroPython documentation](http://microbit-micropython.readthedocs.io/en/latest/)
* Suggested book: [The Cracking Code Book, Simon Singh](https://www.harpercollins.co.uk/9780007176045/the-cracking-code-book)
* [Online Python editor](https://www.microbit.co.uk/app/#create:xyelfe) (NB: the online editor does not currently work with the Bluetooth radio - Mu must be used in the meantime)
* [Offline Python editor (Mu)](http://codewith.mu/)

### Learning Objectives

Students will finish this activity understanding:

* what cryptography is and does
* why cryptography is important
* how the most basic forms of cryptography — the Caesar cipher and other simple substitution ciphers — work
* how the most basic forms of cryptography can be broken

## Starter Activity

In the [starter activity](/tutorial/crypto-student-starter), students will discover what happens when we fail to encrypt messages.

If students have not used Mu before, show them how to launch it.

Each student should have a partner. Once everyone has read the introduction and flashed the script to their micro:bit, you should ask them to start pressing the 'A' button. This will cause the micro:bit to send the student's name over Bluetooth. The micro:bits will display any messages they receive. This illustrates how you cannot control who recieves your wireless messages.

## Main Activity

In the [main activity](/tutorial/crypto-student-main), students will learn about substitution ciphers by making and breaking basic shift cipher messaging protocols. Students should be placed in teams of two, implementing their own cipher and attempting to break the code of another group.
