# secret-contract-verifier
this repo helps verify contracts deployed to secret network

http://secret-contracts.com/ exists today but can only build against one version of the [optimizer](https://hub.docker.com/r/enigmampc/secret-contract-optimizer) at a time and require the uploader to know which version of the optimizer the contract was compiled with. The source and optimizer version can be specified when uploading code.

This repo will attempt to automatically verify code where the source and optimizer is specified. For example:
```
secretcli tx compute store contract.wasm.gz \
  --source 'https://github.com/scrtlabs/snip20-reference-impl' \
  --builder 'enigmampc/secret-contract-optimizer:1.0.6'
  ```
or
  ```
const storeTx = await secretjs.tx.compute.storeCode({
    sender: myAddress,
    wasmByteCode: wasmFile,
    source: "https://github.com/scrtlabs/snip20-reference-impl/tree/v1.4.0",
    builder: "enigmampc/secret-contract-optimizer:1.0.6"
});
```
