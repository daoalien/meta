# dns-metadata-service

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![License][license-shield]][license-url]
[![Travis][travis-shield]][travis-url]

## API


### Request
- __network:__ Name of the chain to query for. (mainnet | rinkeby | ropsten | goerli ...)
- __contactAddress:__ accepts contractAddress of the NFT which represented by the tokenId
- __NFT v1 - tokenId:__ accepts labelhash of DNS name in both hex and int format
- __NFT v2 - tokenId:__ accepts namehash of DNS name in both hex and int format

```
/{networkName}/{contractAddress}/{tokenId}
```

Request (example)

https://metadata.dns.domains/mainnet/0x57f1887a8BF19b14fC0dF6Fd9B2acc9Af147eA85/42219085255511335250589442208301538195142221433306354426240614732612795430543/

### Response (example)

```json
{
  "name": "nick.dao",
  "description": "nick.dao, an DNS name.",
  "attributes": [
    {
      "trait_type": "Created Date",
      "display_type": "date",
      "value": 1580803395000
    },
    {
      "trait_type": "Registration Date",
      "display_type": "date",
      "value": 1580803395000
    },
    {
      "trait_type": "Expiration Date",
      "display_type": "date",
      "value": 1698131707000
    }
  ],
  "name_length": 4,
  "short_name": null,
  "length": 0,
  "url": "https://app.dns.domains/name/nick.dao",
  "version": 0,
  "background_image": "https://metadata.dns.domains/mainnet/avatar/nick.dao",
  "image_url": "https://metadata.dns.domains/mainnet/0x57f1887a8BF19b14fC0dF6Fd9B2acc9Af147eA85/0x5d5727cb0fb76e4944eafb88ec9a3cf0b3c9025a4b2f947729137c5d7f84f68f/image"
}

```

More info and list of all endpoints: https://metadata.dns.domains/docs


## How to setup

```
git clone https://github.com/Dao-Universeorg/dns-metadata-service.git
cd dns-metadata-service
cp .env.org .env // Fill in Vars
yarn
yarn dev
```


## How to deploy

```
yarn deploy
```


## How to test

Regular unit test;
```
yarn test
```

Unit test + coverage;
```
yarn test:cov
```


## Environment Variables

| Name | Description | Default value | Options |
| ---- | ----------- | ------------- | ------- |
| HOST | Host (ip/domain) address of the running service | localhost | - | No |
| ENV | Project scope | local | local/prod |
| INAMEWRAPPER | InterfaceId of NameWrapper Contract | 0xe89c48dc | - |
| ADDRESS_ETH_REGISTRAR | Ethereum address of DNSBaseRegistrar Contract | 0x7bD1d65640e9Ee51b06a8Ee55b2Ea601704F76E5 | - |
| ADDRESS_NAME_WRAPPER | Ethereum address of NameWrapper Contract | 0x396bBd3D9Ff5910f1d192b04F79Ae8f4cD593648 | - |


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/Dao-Universeorg/dns-metadata-service.svg?style=for-the-badge
[contributors-url]: https://github.com/Dao-Universeorg/dns-metadata-service/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/Dao-Universeorg/dns-metadata-service.svg?style=for-the-badge
[forks-url]: https://github.com/mdtanrikulu/Dao-Universeorg/dns-metadata-service/members
[stars-shield]: https://img.shields.io/github/stars/Dao-Universeorg/dns-metadata-service.svg?style=for-the-badge
[stars-url]: https://github.com/Dao-Universeorg/dns-metadata-service/stargazers
[issues-shield]: https://img.shields.io/github/issues/Dao-Universeorg/dns-metadata-service.svg?style=for-the-badge
[issues-url]: https://github.com/Dao-Universeorg/dns-metadata-service/issues
[license-shield]: https://img.shields.io/github/license/Dao-Universeorg/dns-metadata-service.svg?style=for-the-badge
[license-url]: https://github.com/Dao-Universeorg/dns-metadata-service/blob/master/LICDNSE
[travis-shield]: https://img.shields.io/travis/com/Dao-Universeorg/dns-metadata-service/master?style=for-the-badge
[travis-url]: https://travis-ci.com/github/Dao-Universeorg/dns-metadata-service
