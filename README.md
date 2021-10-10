# bolt11
A lightweight and naïve library for decoding lightning network payment requests as defined in [BOLT #11](https://github.com/lightningnetwork/lightning-rfc/blob/master/11-payment-encoding.md).

It doesn't recover payee from signature, doesn't check signature, doesn't parse fallback addresses and doesn't do any encoding -- therefore dependencies are very minimal (no libsecp256k1 here).

Code derived from [bolt11](https://npmjs.com/package/bolt11), which has the full functionality but it's a pain to run in browsers.

## Installation

```
yarn add light-bolt11-decoder
```

## Example

```
> require('light-bolt11-decoder').decode('lnbc120n1pskxyl3pp5uwfjlx3mx9w2gnqx2ckjgzs3gyrflhwqt8rys6u3pd4mcxdqt99qdq20paxxcthv5xqyjw5qcqzyssp56grhkv8ztlf6s9swde8kguzwx84vnru7cyc6s7yw227kafa86afqrzjq0zn80anhfz2vp4qve4svppq7h8y2tsja03wq68re7a55ga2ks95zz4utvqqnpsqqyqqqqlgqqqqqqgq9q9qxsqyssq9qp2zvahzalxeegdshejjxsytwqhau3s6pwupyl5hpc6854xc6qsh3a2xyz9hhrhhtky9m8jss6jq9t2syagruw3y5dqnjye7uwnkfcppyj8v3')
{
  paymentRequest: 'lnbc120n1pskxyl3pp5uwfjlx3mx9w2gnqx2ckjgzs3gyrflhwqt8rys6u3pd4mcxdqt99qdq20paxxcthv5xqyjw5qcqzyssp56grhkv8ztlf6s9swde8kguzwx84vnru7cyc6s7yw227kafa86afqrzjq0zn80anhfz2vp4qve4svppq7h8y2tsja03wq68re7a55ga2ks95zz4utvqqnpsqqyqqqqlgqqqqqqgq9q9qxsqyssq9qp2zvahzalxeegdshejjxsytwqhau3s6pwupyl5hpc6854xc6qsh3a2xyz9hhrhhtky9m8jss6jq9t2syagruw3y5dqnjye7uwnkfcppyj8v3',
  prefix: 'lnbc120n',
  network: {
    bech32: 'bc',
    pubKeyHash: 0,
    scriptHash: 5,
    validWitnessVersions: [ 0 ]
  },
  millisatoshis: '12000',
  timestamp: 1633883121,
  payment_hash: 'e3932f9a3b315ca44c06562d240a1141069fddc059c6486b910b6bbc19a0594a',
  description: 'xzcawe',
  expire_time: 604800,
  min_final_cltv_expiry: 144,
  payment_secret: 'd2077b30e25fd3a8160e6e4f64704e31eac98f9ec131a8788e52bd6ea7a7d752',
  routing_info: [
    {
      pubkey: '03c533bfb3ba44a606a0666b060420f5ce452e12ebe2e068e3cfbb4a23aab40b41',
      short_channel_id: '0abc5b0009860001',
      fee_base_msat: 1000,
      fee_proportional_millionths: 1,
      cltv_expiry_delta: 40
    }
  ],
  feature_bits: {
    word_length: 6,
    option_data_loss_protect: { required: false, supported: false },
    initial_routing_sync: { required: false, supported: false },
    option_upfront_shutdown_script: { required: false, supported: false },
    gossip_queries: { required: false, supported: false },
    var_onion_optin: { required: false, supported: true },
    gossip_queries_ex: { required: false, supported: false },
    option_static_remotekey: { required: false, supported: false },
    payment_secret: { required: true, supported: false },
    basic_mpp: { required: false, supported: true },
    option_support_large_channel: { required: false, supported: false },
    extra_bits: { start_bit: 20, bits: [Array], has_required: false }
  },
  timeExpireDate: 1634487921
}
```

## LICENSE [MIT](LICENSE)
