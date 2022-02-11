# Protocol Info

## Tokens

* **Token decimals:**
  * Acala (ACA): 12
  * LDOT: 12
  * Acala Dollar (aUSD): 12
* **Base unit:** “Plank"
* **Balance type:**
* **Total Fixed Supply of ACA:** 1,000,000,000

## Account

### Address Format

Acala uses the [SS58 (Substrate) address format](https://github.com/paritytech/substrate/wiki/External-Address-Format-\(SS58\)). Relevant SS58 prefixes are:

* **Acala**: 10 ([ss58 registry details](https://github.com/paritytech/substrate/blob/df4a58833a650cf37fc97764bf6c9314435e3cb2/ss58-registry.json#L103-L111))
* **Karura**: 8 ([ss58 registry details](https://github.com/paritytech/substrate/blob/df4a58833a650cf37fc97764bf6c9314435e3cb2/ss58-registry.json#L85-L92))
* **Mandala**: 42

### Existential Deposit

Acala uses an _existential deposit_ (ED) to prevent dust accounts from bloating state. If an account drops below the ED, it will be removed from this account and be donated to the Treasury.

ED of native token ACA is configured in the runtime. Non-native tokens (DOT, aUSD, BTC etc) can be queried via SDK. The amount of ED can only be decreased, not increased, therefore it often starts with a higher number.

`transfer` and `deposit` in `pallet_balances` and `orml_tokens` will check the ED of the receiver account. A transaction may fail due to not meeting ED requirements, a typical one would be a user is swapping token A for token B, where token A balance no longer meets ED requirements. A front-end DApp shall perform checks and prompt user for such incidents.

Read more on ED [here](../../get-started/acala-account/#existential-deposit).

## Protocol Fees

* **Mint aUSD with DOT & lDOT:**
  * **Liquidation penalty:** 12%
  * **Stability Fee:** 3%

## Transaction Fees

Acala uses weight-based fees, unlike gas, are predictable and charged pre-dispatch. See the [transaction fee](https://wiki.acala.network/karura/get-started/transaction-fees) page for more info.

## Types

Type definitions allow the SDK to know how to serialize / deserialize blocks, transactions and events.

Acala's type definition bundle can be found [here](https://unpkg.com/browse/@acala-network/type-definitions@latest/json/typesBundle.json).

## JS SDK

Acala.js: [https://github.com/AcalaNetwork/acala.js](https://github.com/AcalaNetwork/acala.js)

Documentation: [https://github.com/AcalaNetwork/acala.js/wiki](https://github.com/AcalaNetwork/acala.js/wiki)

Please also refer to the [documentation of polkadot.js](https://polkadot.js.org/docs/api/).