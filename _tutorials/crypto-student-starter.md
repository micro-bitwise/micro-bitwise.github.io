---
layout: tutorial
tutorial_type: Starter Activity
authors:
- Joe Savage
- Ross Gardiner
---

# Encryption

When you log into a website - like Facebook, or your email account - have you ever wondered how the website can tell that it is really you? Your computer must be sending a message to the website with your password. But what if other people were able to read those messages? That would be bad! They could steal your password, and then they could pretend to be you!

![Uh oh!](/assets/contrib/images/crypto/facebook-login.png)

Hmm, maybe that would be a bad thing.

Now think about buying something from a shop with a credit card. How does the shop tell the bank to move the money from your account to their account? What if someone else could intercept those messages and change them? That would be bad too - then they could change the prices, or move the money to their account instead!

All of these problems are solved by *encryption*. An encrypted message is scrambled so that nobody - except the sender and the receiver - can read it. Even if someone else intercepts the message, they won't be able to read it. If they try to change it, it will be obvious to the receiver. The science of encryption is called *cryptography*, and has existed for thousands of years.

![A scrambled message](/assets/contrib/images/crypto/scrambled-message.png)

## Chaos!

First, we're going to see what happens when we send messages with no encryption. Your micro:bit can send and receive wireless messages using something called 'Bluetooth'. It's a little bit like WiFi, but Bluetooth is designed for small, nearby objects that want to talk to one another.

Open the [micro:bit Python editor](https://www.microbit.co.uk/app/#create:xyelfe) (if you are using the desktop app Mu instead, open that). We're going to write some very simple Python code that will repeatedly send and receive messages using Bluetooth.
