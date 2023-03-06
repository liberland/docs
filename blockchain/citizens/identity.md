# Setting identity for citizenship

## Block number calculations

To be eligible for citizenship rights, you must be 13 years old. To set this in blockchain, you must calculate the block number at which you've reached or will reach 13 years old. The process is as follows:

* Check current latest block number: https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/explorer
* Calculate number of seconds between now and your 13th birthday
* If you're 13+, the eligibility block number is: `current_block_number - number_of_seconds/6` - use `0` if you got a negative number
* If you're younger, the eligibility block number is: `current_block_number + number_of_seconds/6`

## Block number encoding

You must encode the decimal block number you've got in previous step to Hex that blockchain will understand:

1. Visit https://www.save-editor.com/tools/wse_hex.html#hex
2. Put the block number from previous step in **DEC Decimal number** field
3. Make sure **LITTLE ENDIAN** option is checked.
4. Click **DEC to HEX**

Copy the **HEX** value somewhere, it will be needed in next step

## Setting identity

1. Visit Polkadot.js Apps: https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ftestchain.liberland.org#/extrinsics
2. In the **submit the following extrinsic** field select **identity** and **setIdentity(info)**
3. In the display field:
    * Select **Raw**
    * Enter your display name in **Raw: Bytes** field
4. In the additional field:
    * add item:
        * First field is **Raw** with **Raw: Bytes** set to `citizen`
        * Second field is **Raw** with **Raw: Bytes** set to `1`.
    * add item:
        * First field is **Raw** with **Raw: Bytes** set to `eligible_on`
        * Second field is **Raw** with **Raw: Bytes** set to the **HEX** from previous step **prefixed with `0x`**.
5. Submit transaction
