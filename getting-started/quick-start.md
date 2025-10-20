# Quick Start

Welcome to Gatekeeper!

Gatekeeper is a discord bot which handles applications for entry. When using Gatekeeper, upon joining users will have to click an **Apply** button and fill out an application. After they submitted the application, you and users you authorize will be allowed to approve or deny the application.

## Adding Gatekeeper

<a href="https://discord.com/oauth2/authorize?client_id=1269133368382193757&permissions=8&integration_type=0&scope=bot"><img width=200 src="/img/add-to-discord-button.png"></a>

Click the button above to add Gatekeeper to your discord server.

## Setup

After adding Gatekeeper to your server you'll need to setup the bot. This requires running a few commands to get things going.

### Roles and Channels

First, we'll setup roles and channels. There are three roles and two channels to setup. The **Member** role, **Approver** role and **Manager** role as well as the **Approval** channel and the **Application** channel.


| Type | Name | Description |
| ---- | ---- | ----------- |
| Role | Member | The role which Gatekeeper gives when an application is approved |
| Role | Approver | This role is allowed to approve or deny applications submitted to Gatekeeper |
| Role | Manager | This role is allowed to manage gatekeeper as well as approve or deny applications |
| Channel | Approval | The channel where all applications are set for review, they can be approved or denied here |
| Channel | Application | The channel which houses the embed with the apply button to allow users to apply to the guild |
