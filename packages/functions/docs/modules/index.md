# Module: index

## Table of contents

### Interfaces

- [Geo](../interfaces/index.Geo.md)
- [Request](../interfaces/index.Request.md)

### Functions

- [geolocation](index.md#geolocation)
- [getEnv](index.md#getenv)
- [ipAddress](index.md#ipaddress)
- [waitUntil](index.md#waituntil)

## Functions

### geolocation

▸ **geolocation**(`request`): [`Geo`](../interfaces/index.Geo.md)

Returns the location information for the incoming request.

**`Example`**

```js
import { geolocation } from '@vercel/functions';

export function GET(request) {
  const details = geolocation(request);
  return Response.json(payload);
}
```

#### Parameters

| Name      | Type                                        | Description                                                     |
| :-------- | :------------------------------------------ | :-------------------------------------------------------------- |
| `request` | [`Request`](../interfaces/index.Request.md) | The incoming request object which provides the geolocation data |

#### Returns

[`Geo`](../interfaces/index.Geo.md)

The location information of the request, in this way:

```json
{
 "city": "New York",
 "country": "United States",
 "flag": "🇺🇸"
 "countryRegion": "NY",
 "region": "dev1",
 "latitude": "40.7128",
 "longitude": "-74.0060"
}
```

#### Defined in

[packages/functions/src/headers.ts:158](https://github.com/vercel/vercel/blob/main/packages/functions/src/headers.ts#L158)

---

### getEnv

▸ **getEnv**(`env?`): `Object`

Get System Environment Variables exposed by Vercel.

**`See`**

https://vercel.com/docs/projects/environment-variables/system-environment-variables#system-environment-variables

#### Parameters

| Name  | Type     | Default value |
| :---- | :------- | :------------ |
| `env` | `Object` | `process.env` |

#### Returns

`Object`

| Name                              | Type                    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| :-------------------------------- | :---------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `CI`                              | `undefined` \| `string` | An indicator that the code is running in a Continuous Integration environment. **`Example`** `ts "1" `                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| `VERCEL`                          | `undefined` \| `string` | An indicator to show that System Environment Variables have been exposed to your project's Deployments. **`Example`** `ts "1" `                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `VERCEL_AUTOMATION_BYPASS_SECRET` | `undefined` \| `string` | The Protection Bypass for Automation value, if the secret has been generated in the project's Deployment Protection settings.                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `VERCEL_BRANCH_URL`               | `undefined` \| `string` | The domain name of the generated Git branch URL. The value does not include the protocol scheme https://. **`Example`** `ts "*-git-*.vercel.app" `                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `VERCEL_DEPLOYMENT_ID`            | `undefined` \| `string` | The unique identifier for the deployment, which can be used to implement Skew Protection. **`Example`** `ts "dpl_7Gw5ZMBpQA8h9GF832KGp7nwbuh3" `                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `VERCEL_ENV`                      | `undefined` \| `string` | The Environment that the app is deployed and running on. **`Example`** `ts "production" `                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `VERCEL_GIT_COMMIT_AUTHOR_LOGIN`  | `undefined` \| `string` | The username attached to the author of the commit that the project was deployed by. **`Example`** `ts "johndoe" `                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `VERCEL_GIT_COMMIT_AUTHOR_NAME`   | `undefined` \| `string` | The name attached to the author of the commit that the project was deployed by. **`Example`** `ts "John Doe" `                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `VERCEL_GIT_COMMIT_MESSAGE`       | `undefined` \| `string` | The message attached to the commit the deployment was triggered by. **`Example`** `ts "Update about page" `                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `VERCEL_GIT_COMMIT_REF`           | `undefined` \| `string` | The git branch of the commit the deployment was triggered by. **`Example`** `ts "improve-about-page" `                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| `VERCEL_GIT_COMMIT_SHA`           | `undefined` \| `string` | The git SHA of the commit the deployment was triggered by. **`Example`** `ts "fa1eade47b73733d6312d5abfad33ce9e4068081" `                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `VERCEL_GIT_PREVIOUS_SHA`         | `undefined` \| `string` | The git SHA of the last successful deployment for the project and branch. NOTE: This Variable is only exposed when an Ignored Build Step is provided. **`Example`** `ts "fa1eade47b73733d6312d5abfad33ce9e4068080" `                                                                                                                                                                                                                                                                                                                                                                                |
| `VERCEL_GIT_PROVIDER`             | `undefined` \| `string` | The Git Provider the deployment is triggered from. **`Example`** `ts "github" `                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `VERCEL_GIT_PULL_REQUEST_ID`      | `undefined` \| `string` | The pull request id the deployment was triggered by. If a deployment is created on a branch before a pull request is made, this value will be an empty string. **`Example`** `ts "23" `                                                                                                                                                                                                                                                                                                                                                                                                             |
| `VERCEL_GIT_REPO_ID`              | `undefined` \| `string` | The ID of the repository the deployment is triggered from. **`Example`** `ts "117716146" `                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| `VERCEL_GIT_REPO_OWNER`           | `undefined` \| `string` | The account that owns the repository the deployment is triggered from. **`Example`** `ts "acme" `                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `VERCEL_GIT_REPO_SLUG`            | `undefined` \| `string` | The origin repository the deployment is triggered from. **`Example`** `ts "my-site" `                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `VERCEL_PROJECT_PRODUCTION_URL`   | `undefined` \| `string` | A production domain name of the project. This is useful to reliably generate links that point to production such as OG-image URLs. The value does not include the protocol scheme https://. **`Example`** `ts "myproject.vercel.app" `                                                                                                                                                                                                                                                                                                                                                              |
| `VERCEL_REGION`                   | `undefined` \| `string` | The ID of the Region where the app is running. Possible values: - arn1 (Stockholm, Sweden) - bom1 (Mumbai, India) - cdg1 (Paris, France) - cle1 (Cleveland, USA) - cpt1 (Cape Town, South Africa) - dub1 (Dublin, Ireland) - fra1 (Frankfurt, Germany) - gru1 (São Paulo, Brazil) - hkg1 (Hong Kong) - hnd1 (Tokyo, Japan) - iad1 (Washington, D.C., USA) - icn1 (Seoul, South Korea) - kix1 (Osaka, Japan) - lhr1 (London, United Kingdom) - pdx1 (Portland, USA) - sfo1 (San Francisco, USA) - sin1 (Singapore) - syd1 (Sydney, Australia) - dev1 (Development Region) **`Example`** `ts "iad1" ` |
| `VERCEL_SKEW_PROTECTION_ENABLED`  | `undefined` \| `string` | When Skew Protection is enabled in Project Settings, this value is set to 1. **`Example`** `ts "1" `                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `VERCEL_URL`                      | `undefined` \| `string` | The domain name of the generated deployment URL. The value does not include the protocol scheme https://. NOTE: This Variable cannot be used in conjunction with Standard Deployment Protection. **`Example`** `ts "*.vercel.app" `                                                                                                                                                                                                                                                                                                                                                                 |

#### Defined in

[packages/functions/src/get-env.ts:6](https://github.com/vercel/vercel/blob/main/packages/functions/src/get-env.ts#L6)

---

### ipAddress

▸ **ipAddress**(`request`): `string` \| `undefined`

Returns the IP address of the request from the headers.

**`Example`**

```js
import { ipAddress } from '@vercel/functions';

export function GET(request) {
  const ip = ipAddress(request)
  return new Response('Your ip is' ${ip});
}
```

#### Parameters

| Name      | Type                                        | Description                                       |
| :-------- | :------------------------------------------ | :------------------------------------------------ |
| `request` | [`Request`](../interfaces/index.Request.md) | The incoming request object which provides the IP |

#### Returns

`string` \| `undefined`

The IP address of the request.

#### Defined in

[packages/functions/src/headers.ts:111](https://github.com/vercel/vercel/blob/main/packages/functions/src/headers.ts#L111)

---

### waitUntil

▸ **waitUntil**(`promise`): `undefined` \| `void`

Extends the lifetime of the request handler for the lifetime of the given Promise

**`See`**

https://developer.mozilla.org/en-US/docs/Web/API/ExtendableEvent/waitUntil

**`Example`**

```js
import { waitUntil } from '@vercel/functions';

export function GET(request) {
  waitUntil(fetch('https://vercel.com'));
  return new Response('OK');
}
```

#### Parameters

| Name      | Type                                                                                                              | Description              |
| :-------- | :---------------------------------------------------------------------------------------------------------------- | :----------------------- |
| `promise` | [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)<`unknown`\> | The promise to wait for. |

#### Returns

`undefined` \| `void`

#### Defined in

[packages/functions/src/wait-until.ts:19](https://github.com/vercel/vercel/blob/main/packages/functions/src/wait-until.ts#L19)
