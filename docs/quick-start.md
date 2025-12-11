# Quick Start

## Adding Gatekeeper

<a href="https://discord.com/oauth2/authorize?client_id=1269133368382193757"><img width=200 src="/assets/add-to-discord-button.png"></a>

Click the button above to add Gatekeeper to your discord server.

## Setup

After adding Gatekeeper to your server you'll need to setup the bot. This requires running a few commands to get things going.

!!! warning "Permissions Required"
    This guide assumes you are the **Guild Owner**. If you are not the guild owner, you must have them set the **manager** role to a role that you have to continue setup. This is a security precaution to ensure admins cannot enable or modify Gatekeeper without authorization.

### Prerequisites

Before getting into the thick of things, you need to ensure you have some things set to go.

1. A role which is given to members to few all content of the guild. This would be the "main role" of your guild, something granted to all members which allows them to access the discord. You'll need to setup a main role and apply the appropriate permissions before using Gatekeeper. This is not something I cover in the Quick Start guide here.
2. A channel where users can apply, where everyone **except** your main role has access, at least read-only access. This channel will be the first and only thing users see when they first join as they won't have the main role yet.
3. A channel where approvers, managers and guild owners can approve applications. This should be locked down to those three roles only. The approve/manager permissions can be assigned to existing roles, no need to create specific roles just for this (unless you want to).

### Roles and Channels

First, we'll setup roles and channels. There are three roles and two channels to setup. The **Member** role, **Approver** role and **Manager** role as well as the **Approval** channel and the **Application** channel.


| Type | Name | Description |
| ---- | ---- | ----------- |
| Role | Member | The role which Gatekeeper gives when an application is approved |
| Role | Approver | (Optional) This role is allowed to approve or deny applications submitted to Gatekeeper |
| Role | Manager | (Optional) This role is allowed to manage gatekeeper as well as approve or deny applications |
| Channel | Approval | The channel where all applications are set for review, they can be approved or denied here |
| Channel | Application | The channel which houses the embed with the apply button to allow users to apply to the guild |

1. First let's setup our member role, do to that run the `/setup member-role` command and specify a role which users will receive.
2. Next, let's add our approvers, you now run `/setup approver-role` and specify a role for which users can approve applications. This is optional, this role is not required if you as the guild owner are going to be the only one approving applications.
3. Finally, let's add a manager role, run `/setup manager-role` and specify a role for managers. This is optional and not required if you as the guild owner are going to be the one one managing Gatekeeper.

Now that we have our roles setup, we can setup our channels. Both channels are mandatory!

1. Run `/application channel` and provide a channel, this sets the channel that will hold your application button. Users should be dropped into this channel first to be able to click the button.
2. Next run `/application approval-channel` and provide a channel, this is the channel that applications will go into once submitted. From this channel you can approve/deny as needed.

Great, we're almost finished with roles and channels. Now we need to send our application embed. To do so, you can run `/application send`, this will send the embed to the application channel for users to apply from.

### Questions

!> **WARNING:** Before proceeding with adding questions, please note that at this time you can only have **4 questions per guild**. This may get increased in the future.

Now that we have our roles set, channels set and embed sent we can setup our questions. All of these commands reside under `/question` the commands are as follows:

- `/question add` adds a new question
- `/question delete` deletes a question
- `/question edit` edits details of an existing question
- `/question list` lists all configured questions and their details
- `/question reorder` moves a question up or down in the application (position 1 through 4)

Obviously to start we need to add a question so let's start that command. This may get increased in the future but I've found that 4 is the sweet spot for the modal that appears for the application. 

There are two things required when adding a question the `Type` and the `Text`. Optionally, you can specify a `Placeholder`, `Minimum Length`, `Maxmium Length` and if it is `Required` or not.

?> **NOTE:** All questions are required by default. You have to set `Required` to **False** if you don't want to make it required.

Lets breakdown what each option is and what it does.

- `Type` for this you have two options; `Short Text` or `Paragraph`.
    - `Short Text` is a single line entry field
    - `Paragraph` is a multi-line entry field
- `Text` this is the question itself so for example it could be `Why do you want to join?` or `Who referred you?`.
- `Placeholder` (Optional) the placeholder will be in the answer field by default, you can provide additional context here.
- `Minimum Length` (Optional) this is the minimum number of characters a response can have
- `Maximum Length` (Optional) this is the maximum number of characters a response can have
- `Required` (Optional) this makes a question required or not, by default all questions are required

?> **NOTE:** `Text` and `Placeholder` can only be 45 and 100 characters long respectively. This is a **discord limitation** not a gatekeeper limitation.

After you have added your 4 questions, run `/question list` to ensure they are all set properly. Once you have done that you're all set to go!

## Usage

After you have all of your settings set, you shouldn't have to change them again unless you want to. Maybe you want to remove a question or adjust one, maybe you want to change a role, you can do that at anytime by running the respective command.

Now all you have to do is sit back and wait for applications!