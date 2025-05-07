# ZcashExplorer

This is a fork of https://github.com/nighthawk-apps/zcash-explorer, intended to
help develop support for block explorers in
[Zebra](https://github.com/ZcashFoundation/zebra).

## Local Dev Setup

### Build and run `zcashd`

``` shell
sudo pacman --noconfirm -S make git autoconf libtool unzip python automake pkgconf patch wget binutils gcc
cd
git clone https://github.com/zcash/zcash.git
cd zcash
./zcutil/clean.sh
./zcutil/build.sh -j$(nproc)
mkdir -p ~/.zcash
touch ~/.zcash/zcash.conf
```

Put the following to your `~/.zcash/zcash.conf`:

```
rpcport=8232
rpcbind=127.0.0.1
rpcuser=nighthawkapps
rpcpassword=ffwf
txindex=1
experimentalfeatures=1
insightexplorer=1
testnet=1
```

Run `./src/zcashd` and wait until it syncs.

### Build and run the explorer

``` shell
sudo pacman --noconfirm -S make elixir gcc git npm inotify-tools
cd
git clone https://github.com/ZcashFoundation/zcash-explorer
cd zcash-explorer
mix deps.get
cd assets
npm install
cd ..
```

Run `iex -S mix phx.server`.

Visit http://localhost:4000.

## Documentation: 

https://nighthawkapps.gitbook.io/zcash-explorer/

## Disclosure Policy
Do not disclose any bug or vulnerability on public forums, message boards, mailing lists, etc. prior to responsibly disclosing to Nighthawk Apps and giving sufficient time for the issue to be fixed and deployed. Do not execute on or exploit any vulnerability.

### Reporting a Bug or Vulnerability
When reporting a bug or vulnerability, please provide the following to nighthawkwallet@protonmail.com

A short summary of the potential impact of the issue (if known).
Details explaining how to reproduce the issue or how an exploit may be formed.
Your name (optional). If provided, we will provide credit for disclosure. Otherwise, you will be treated anonymously and your privacy will be respected.
Your email or other means of contacting you.
A PGP key/fingerprint for us to provide encrypted responses to your disclosure. If this is not provided, we cannot guarantee that you will receive a response prior to a fix being made and deployed.

## Encrypting the Disclosure
We highly encourage all disclosures to be encrypted to prevent interception and exploitation by third-parties prior to a fix being developed and deployed.  Please encrypt using the PGP public key with fingerprint: `8c07e1261c5d9330287f4ec35aff0fd018b01972`

## Contact Zingoista Devs
u1w47nzy4z5g9zvm4h2s4ztpl8vrdmlclqz5sz02742zs5j3tz232u4safvv9kplg7g06wpk5fx0k0rx3r9gg4qk6nkg4c0ey57l0dyxtatqf8403xat7vyge7mmen7zwjcgvryg22khtg3327s6mqqkxnpwlnrt27kxhwg37qys2kpn2d2jl2zkk44l7j7hq9az82594u3qaescr3c9v

### License
Apache License 2.0
