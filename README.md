# Session iOS

[Download Session on the App Store](https://getsession.org/iphone)

## Summary

Session integrates directly with [Oxen Service Nodes](https://docs.oxen.io/about-the-oxen-blockchain/oxen-service-nodes), which are a set of distributed, decentralized and Sybil resistant nodes. Service Nodes act as servers which store messages, and a set of nodes which allow for onion routing functionality obfuscating users' IP addresses. For a full understanding of how Session works, read the [Session Whitepaper](https://getsession.org/whitepaper).

<img src="https://i.imgur.com/Ioub5bx.png" width="320" />

## Want to contribute? Found a bug or have a feature request?

Please search for any [existing issues](https://github.com/session-foundation/session-ios/issues) that describe your bugs in order to avoid duplicate submissions. Submissions can be made by making a pull request to our dev branch. If you don't know where to start contributing, try reading the Github issues page for ideas.

## Build instructions

Build instructions can be found in [BUILDING.md](BUILDING.md).

## Translations

Want to help us translate Session into your language? You can do so at https://getsession.org/translate !

## Verifying signatures

**Step 1:**

Add Jason's GPG key. Jason Rhinelander, a member of the [Session Technology Foundation](https://session.foundation/) and is the current signer for all Session iOS releases. His GPG key can be found on his GitHub and other sources.

```sh
wget https://github.com/jagerman.gpg
gpg --import jagerman.gpg
```

**Step 2:**

Get the signed hashes for this release. `SESSION_VERSION` needs to be updated for the release you want to verify.

```sh
export SESSION_VERSION=2.9.1
wget https://github.com/session-foundation/session-ios/releases/download/$SESSION_VERSION/signature.asc
```

**Step 3:**

Verify the signature of the hashes of the files.

```sh
gpg --verify signature.asc 2>&1 |grep "Good signature from"
```

The command above should print "`Good signature from "Jason Rhinelander...`". If it does, the hashes are valid but we still have to make the sure the signed hashes match the downloaded files.

**Step 4:**

Make sure the two commands below return the same hash for the file you are checking. If they do, file is valid.

```
sha256sum session-$SESSION_VERSION.ipa
grep .ipa signature.asc
```

## License

Copyright 2011 Whisper Systems

Copyright 2013-2017 Open Whisper Systems

Copyright 2019-2021 The Oxen Project

Licensed under the GPLv3: http://www.gnu.org/licenses/gpl-3.0.html
