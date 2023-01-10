# Protocol Info

## Tokens

* **Token decimals:**
  * Karura (KAR): 12
  * LKSM: 12
  * Karura Dollar (kUSD): 12
* **Base unit:** “Plank"
* **Balance type:**
* **Total Fixed Supply of KAR:** 100,000,000

## Account

### Address Format

Karura uses the [SS58 (Substrate) address format](https://github.com/paritytech/substrate/wiki/External-Address-Format-\(SS58\)). Relevant SS58 prefixes are:

* **Acala**: 10 ([ss58 registry details](https://github.com/paritytech/substrate/blob/df4a58833a650cf37fc97764bf6c9314435e3cb2/ss58-registry.json#L103-L111))
* **Karura**: 8 ([ss58 registry details](https://github.com/paritytech/substrate/blob/df4a58833a650cf37fc97764bf6c9314435e3cb2/ss58-registry.json#L85-L92))
* **Mandala**: 42

### Existential Deposit

Karura uses an _existential deposit_ (ED) to prevent dust accounts from bloating state. If an account drops below the ED, it will be removed from this account and be donated to the Treasury.

ED of native token KAR is configured in the runtime. Non-native tokens (KSM, kUSD, BTC etc) can be queried via SDK. The amount of ED can only be decreased, not increased, therefore it often starts with a higher number.

`transfer` and `deposit` in `pallet_balances` and `orml_tokens` will check the ED of the receiver account. A transaction may fail due to not meeting ED requirements, a typical one would be a user is swapping token A for token B, where token A balance no longer meets ED requirements. A front-end DApp shall perform checks and prompt user for such incidents.

Read more on ED [here](../../../get-started/get-started/karura-account/#existential-deposit).

## Protocol Fees

* **Mint kUSD with KSM & lKSM:**
  * **Liquidation penalty:** 12%
  * **Stability Fee:** 3%

## Transaction Fees

Karura uses weight-based fees, unlike gas, are predictable and charged pre-dispatch. See the [transaction fee](../../../get-started/get-started/transaction-fees.md) page for more info.

## Types

Type definitions allow the SDK to know how to serialize / deserialize blocks, transactions and events.

Acala's type definition bundle can be found [here](https://unpkg.com/browse/@acala-network/type-definitions@latest/json/typesBundle.json).

## MultiLocation

You can use these MultiLocation to add Karura token assets to other parachains foreign token list.

Asset Name: Acala Dollar \
Asset Symbol: AUSD\
Decimals: 12\
existentialDeposit: 0.01

`{"parents": 1, "interior": {"X2": [{"Parachain": 2000}, { "GeneralKey": 0x0081} ]}}`

Asset Name: Liquid KSM\
Asset Symbol: LKSM\
Decimals: 12\
existentialDeposit: 0.0005

`{"parents": 1, "interior": {"X2": [{"Parachain": 2000}, {"GeneralKey": 0x0083} ]}}`&#x20;

Asset Name: Karura Native Token\
Asset Symbol: KAR\
Decimals: 12\
existentialDeposit: 0.1

`{"parents": 1, "interior": {"X2": [{"Parachain": 2000}, { "GeneralKey": 0x0080} ]}}`

### Autogenerated MultiLocations

{% embed url="https://replit.com/@GregoryLuneau/Karura-MultiLocations?lite=true" %}
Click Run to generate the current full list of MultiLocations
{% endembed %}

## JS SDK

Acala.js: [https://github.com/AcalaNetwork/acala.js](https://github.com/AcalaNetwork/acala.js)

Documentation: [https://github.com/AcalaNetwork/acala.js/wiki](https://github.com/AcalaNetwork/acala.js/wiki)

Please also refer to the [documentation of polkadot.js](https://polkadot.js.org/docs/api/).

## Telemetry

[https://telemetry.polkadot.io/#list/Karura](https://telemetry.polkadot.io/#list/Karura)

## Polkadot apps

[https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fkarura-rpc.dwellir.com#/explorer](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fkarura-rpc.dwellir.com#/explorer)

## Explorer

[https://karura.subscan.io/](https://karura.subscan.io/)