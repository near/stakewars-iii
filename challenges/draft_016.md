
# Stake Wars: Episode III. Challenge 016
***STATUS: DRAFT***

* Published on: 2022-08-24
* Updated on: 2022-08-24
* Submitted by: Meta Pool supported by Notifi Network
* Rewards: 10 Delegated NEAR Points (DNP)
  
Connect a node validator for sending notifications through [Notifi](https://notifi.network/).

Notifi Network is a notifications provider for web3. In this challenge, you will test yourself on using the Notifi API to communicate when your staking is going lower than seat price.


## kuutamod support:

kuutamod team is available for solving doubts about setting up kuutamod.

For support join [kuutamo-chat on Matrix.](https://matrix.to/#/#kuutamo-chat:kuutamo.chat) 

## Steps to complete:
* In #integration-requests channel, ask to integrate a new validator on Near for Stake Wars! 
* A support ticket will be created with you in it.
* You'll be asked for your valid testnet wallet, validator name, and email/sms where you want test messages sent.
* Once approved, a moderator will send you credentials for your account. This is the sid/secret you’ll use in the SDK to authenticate from the validator. Keep these credentials safe and never shared.
* Use the SDK sample here to broadcast messages to a particular topic. The topic name will be provided to you when you get your sid/secret pair.
https://github.com/notifi-network/notifi-sdk-ts/tree/main/packages/notifi-node
* Use NotifiClient.sendBroadcastMessage to send your message via the provided topic name. For this challenge, you can leave targetTemplates as undefined, as we will use the default ones. Required variables are “subject” and “message”.


## Acceptance criteria

An Email and/or SMS is sent when staking is below seat price.

## Submission Form

Screenshot of your Email or SMS.

[Submit the form](https://docs.google.com/forms/d/e/1FAIpQLScp9JEtpk1Fe2P9XMaS9Gl6kl9gcGVEp3A5vPdEgxkHx3ABjg/viewform) with your distribution transactions.

## Disclaimer

This is a code provided by community, there is not knowledge of auditments or warranty on its use. Do your own review of code to ensure security and stability. Use it at your own risk.
