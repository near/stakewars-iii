
# Stake Wars: Episode III. Challenge 015
### Status: **DRAFT**
* Published on: 2022-08-16
* Updated on: 2022-08-16
* Submitted by: Meta Pool supported by Kuutamo
* Rewards: XXX Delegated NEAR Points (DNP)
  
Setup a kuutamo High Availability (HA) NEAR Validator running on `shardnet`

The kuutamo (HA) NEAR Validator node distribution combines a Linux operating system (NixOS) preconfigured for security and performance for this use case, kuutamod, consuld and neard.

kuutamod is a distributed supervisor for neard that implements failover. To avoid having two active validators running simultaneously, kuutamod uses consul by acquiring a distributed lock.

For support join [kuutamo-chat on Matrix](https://matrix.to/#/#kuutamo-chat:kuutamo.chat) 

## Tasks:

 1. Deploy kuutamod on a localnet following [this guide](https://github.com/kuutamolabs/kuutamod/blob/main/docs/run-localnet.md). Write a blog post documenting your experience.
 2. Deploy a HA pool using kuutamo with a name appended with `_kuutamo` on shardnet (i.e. `mypoolname_kuutamo.factory.shardnet.near`). Write a blog post documenting your experience. This part of the challenge requires machines with NixOS 22.05. There is a quickstart AWS walkthrough [here](https://github.com/kuutamolabs/kuutamod/blob/main/docs/shardnet-on-aws-lab.md) which starts by explaining how to get the NixOS AMI image, or you can try setting up NixOS youself using [this install guide](https://nixos.org/manual/nixos/stable/index.html#ch-installation) on your own machines and following [this doc](https://github.com/kuutamolabs/kuutamod/blob/main/docs/run-main-test-shard.md).

## Deliverables

 - Blog for localnet deployment
 - Blog for shardnet deployment. On each kuutamo node, once your system is operational, run the commands below and include screenshots in blog.
```console
$ nixos-version
$ journalctl -u kuutamod.service | grep 'state changed'
$ systemctl status kuutamod
```

## Submission Form
TBD

## Disclaimer

This is a code provided by community, there is not knowledge of auditments or warranty on its use. Do your own review of code to ensure security and stability. Use it at your own risk.

## Useful links:

[kuutamo NEAR Validator GitHub/Docs](https://github.com/kuutamolabs/kuutamod)

[Installing NixOS](https://nixos.org/manual/nixos/stable/index.html#ch-installation)

[An opinionated guide for developers getting things done using the Nix ecosystem](https://nix.dev/)

[Nix to Debian phrasebook](https://nixos.wiki/wiki/Nix_to_Debian_phrasebook)
