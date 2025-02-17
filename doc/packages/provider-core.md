# @nearjs/provider-rpc

## Installation

```shell
npm i @nearjs/provider-rpc --save
```

```shell
yarn add @nearjs/provider-rpc
```

## Usage

```typescript
import {
  RPCProviderConfig,
  RPCProvider,
  StandardNodeUrls,
  BroadcastTx,
} from '@nearjs/provider-rpc';

const config = new RPCProviderConfig(StandardNodeUrls.TESTNET);

const provider = new RPCProvider(config);

(async () => {
  const request = new BroadcastTx(undefined);

  const result = await provider.sendRPCRequest(request);

  console.log(result);
})();
```

## Dynamic annotations

The provider class support dynamic type annotations meaning that return type of RPC request is defined on the flight by the `sendRPCRequest` input argument:

For example, if you send BroadcastTX request, the result field will be typed as string

![Showcase of BroadcastTX result](../resources/broadcast-tx-annotation.png)

If you send ViewAccount request, the result field will be typed as a ViewAccountResult object

![Showcase of ViewAccount result](../resources/viewaccount-annotation.png)



