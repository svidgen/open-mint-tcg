# @open-mint-tcg/conformance-tests

An `npx` command used to test whether Open Mint TCG clients and servers are operating according to the specification.

## Mining Client

The Mining Client is responsible for generating valid cards, validating cards, and correctly assessing the legality of a card.

1. Client can generate valid cards.
2. Client does *not* generate invalid cards.
3. Client correctly categorizes valid/invalid cards.

***RFC needed.***

## Game Engine Server

A stateful server that can be accessed via HTTP(s) to simulate gameplay. The server will be expected to receive game events (player actions, dice rolls, etc.) and report the correct game state. The server should also be capable of validating cards.

The server may also be required to rule on whether an individual player has the rights to play a card at an event "registered" to the server.

***RFC needed.***

## Registry Server

TBD whether this is a designed component.

***RFC needed.***
