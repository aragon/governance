## Preamble

    AGP: 24
    Title: Deprecation of 0.5 Rinkeby DAOs
    Author: Brett Sun
    Type: Product / Communication
    Status: Final, v1.0
    Created: 2018-09-27
    Last updated: 2018-10-16
    Requires:

## Abstract

Updates to aragonOS (`aragonOS@4`) are backwards-incompatible (e.g. non-upgradeable) with the current base contracts and proxy contracts deployed on Rinkeby, affecting any DAOs created via the 0.5 [democracy kit](https://rinkeby.etherscan.io/address/0x344bc497128f1e373639fa0621a12331f65bdc7a) or [multisig kit](https://rinkeby.etherscan.io/address/0x876556bbea9e66e8580adfe1f960dc87c3652bfd).

A decision has been made to deprecate these old DAOs, and communicate to users the extent of this deprecation as well as how to recreate their DAOs on Rinkeby.

## Specification

### Goals

- Effectively communicate to the user base that this deprecation is happening, and allow them to respond
- Make the switch over to the new contracts as painless as possible

## Description

`aragonOS@4` introduces a number of breaking changes from `aragonOS@3`. We'll be deploying these new, backwards-incompatible contracts on both Rinkeby and Mainnet.

With the upcoming release of Aragon Core v0.6, enough breaking changes have been introduced such that old organizations will be properly loaded anymore. Most important are the contract changes:

- Old organizations won't be able to upgrade to new versions of any contracts (either internal to aragonOS, like the Kernel or ACL, or any Apps), without there being internal state inconsistencies
- Old organizations won't have access to the recovery vault functionality
- Old organizations will have a number of inconsistencies in declared constants

As part of the migration, a new root ENS registry, as well as Aragon Package Manager, will be deployed. A new root ENS registry will allow users to recreate DAOs with their old ENS names (although there is the issue with squatting these now known names).

### Roadmap

**Oct. 16:**

- Deploy contracts based on `aragonOS@4` to Rinkeby, with new ENS and Aragon Package Manager instances
- Provide a git tag, release, and branch for the deprecated version
- Add [deprecation warning to the current Aragon Core 0.5 frontend](https://github.com/aragon/aragon/issues/364) and additional information in the new Aragon Core if a [DAO could not be found](https://github.com/aragon/aragon/issues/271)
- Blog post, social media posts, outreach, etc.

**Oct. 29:**

- Upgrade Aragon Core, and move Aragon Core v0.5 to a new URL (e.g. old-app.aragonpm.eth)
- Disable onboarding for the deprecated Aragon Core v0.5

## Uncertainties

If any users are currently relying on their 0.5 Rinkeby DAOs. We will be listening closely to social media as well as any outreach from users, and help them with this migration.

## Contributions

Thanks to all [5 participants](https://github.com/aragon/governance/issues/33) who contributed to the discussion, as well the attention of those in the all devs call when this was brought up for review.

## References

1. [https://github.com/aragon/governance/issues/33](https://github.com/aragon/governance/issues/33)

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
