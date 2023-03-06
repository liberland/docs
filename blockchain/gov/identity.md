# Approving identity of a Citizen

## Get requested identity:

1. Visit Polkadot.js Apps: https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/chainstate
2. In **selected state query** select **identity** and **identityOf(AccountId32)**.
3. Put address of the account in **AccountId32** field.
4. Hit `+` icon.

You should see something similar to this:

```
{
  judgements: []
  deposit: 12,000,000,000
  info: {
    additional: [
      [
        {
          Raw: eligible_on
        }
        {
          Raw: 0xd74805
        }
      ]
      [
        {
          Raw: citizen
        }
        {
          Raw: 1
        }
      ]
    ]
    display: {
      Raw: asd
    }
    legal: None
    web: None
    riot: None
    email: None
    pgpFingerprint: null
    image: None
    twitter: None
  }
}
```

In this data, you're mostly interested in:
* the value of `eligible_on` (in the example it's `0xd74805`) 
* the value of `citizen` (in the example it's `1`)
* FIXME: do we verify other stuff like display, legal and email?

## Converting `eligible_on` to date

1. Copy the value of `eligible_on` you've got
2. Visit https://www.save-editor.com/tools/wse_hex.html#hex
3. Put the value in **HEX Hexadecimal number** field
4. Make sure **LITTLE ENDIAN** option is checked.
5. Click **HEX to DEC**

The number you've got is a block number. To convert it to the expected date:

1. Check current latest block number: https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/explorer
2. Substract current block number from the number you've got from hex converter.
3. Multiply the value by 6, divide by 86400.
4. The value you've got is a number of days from now - if the number is negative, it means it's in the past.
5. The value is the the date of 13th birthday - verify this with ID.
    * note that it's impossible to have `eligible_on` older than the start of blockchain, so verification passes as long as the result you've got is after the actual 13th birthday. 

## Verify identity

Verification passes if:
* `citizen` is present and set to `1`
* `eligible_on` is present and set to 13th birthday or to the birth of blockchain

## Provide judgement

1. Visit Polkadot.js Apps: https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/addresses
2. Add the citizen to your contact list
3. Click the name of the contact - a side bar on the right should open with details
4. In the side bar, click **Add identity judgment** - if you don't see it, the identity is incomplete - it needs to have some non-additional field set.
5. Make sure the **registrat index** is **0**.
6. Select **judgement**: **KnownGood**
7. Click **Judge**