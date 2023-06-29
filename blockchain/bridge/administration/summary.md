# Ethereum Bridge administrator guide

## Introduction

This guide is for mainnet only.

There are two roles in the bridge:

* Super Admin, which is capable of adding relays, removing watchers and changing number of required votes (a.k.a. things that potential attacker would really like to do)
* Admin, which is capable of adding watchers, removing relays, changing fees and stopping/starting the bridge

Super Admin MUST be a secure multisig wallet, requiring sign-off from multiple parties. Admin should be a multisig wallet with a low threshold.

The recommendation is to use the same people for super admin and admin accounts, but with different thresholds (for ex. 4/5 for Super Admin and 1/5 for Admin).

## Initial setup

See [Initial setup](./initial-setup.md) docs. This is likely already done by the dev team.

## Basic admin tasks

* [Add new operator](./add-operator.md)
* [Remove operator](./remove-operator.md)