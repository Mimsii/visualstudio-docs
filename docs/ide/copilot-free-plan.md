---
title: 'GitHub Copilot Free in Visual Studio'
description: Use GitHub Copilot Completions, Chat, and Edits for free in Visual Studio.
ms.date: 12/18/2024
ms.topic: overview 
author: anandmeg
ms.author: meghaanand
ms.manager: mijacobs
ms.subservice: ai-tools
ms.collection: ce-skilling-ai-copilot
monikerRange: '>= vs-2022'
---
# Use GitHub Copilot for free in Visual Studio

GitHub Copilot Free enables you to experience AI-powered coding assistance in your IDE by providing limited access to select Copilot features. With [Copilot Free](https://devblogs.microsoft.com/visualstudio/github-copilot-free-is-here-in-visual-studio/), you can now access all AI-integrated features in Visual Studio, including [Completions](visual-studio-github-copilot-extension.md), Edits, and [Chat](visual-studio-github-copilot-chat.md).

## Prerequisites

To get started with Copilot Free in Visual Studio, you need:
+ Visual Studio 2022 [version 17.8](/visualstudio/releases/2022/release-history) or later
+ [GitHub Copilot](visual-studio-github-copilot-install-and-states.md) in Visual Studio

## Get started with Copilot Free in Visual Studio

**Set up Copilot Free using Visual Studio**

- In Visual Studio, select the **GitHub Copilot** badge in the upper-right corner of the IDE. 
- Select **Get Copilot Subscription** or **Add GitHub account to Visual Studio**.
- If you have an existing GitHub account, sign in when prompted. If not, follow the steps to create a new GitHub account. 
- Select **Sign up for Free** to complete the setup. Once finished, you’ll be redirected back to Visual Studio. 

**Set up Copilot Free using GitHub.com**

- In the upper-right corner of any GitHub page, select your profile photo, and then select **Your Copilot**. 
- Select **Start using Copilot Free** to activate Copilot Free and open a conversation thread.
- Select **Use Copilot in other IDEs**, select **Visual Studio** and follow the instructions provided for Visual Studio. 

## Copilot Free usage limits in Visual Studio

Copilot Free provides a limited number of code completions and chat responses for free per month. Changes in Copilot functionality may indicate you've reached your monthly usage limit.
You can check the current status of your Copilot Free account on the [GitHub account settings page](https://github.com/settings/copilot).

When you hit the usage limits, your Copilot experience in Visual Studio may be impacted as follows:

:::row::: 
    :::column span="1"::: 
       **Usage limit for Completions is reached**
    :::column-end::: 
    :::column span="2"::: 
       User receives IntelliCode suggestions instead of Copilot completions. The Copilot badge stays green, indicating **active** status. 
    :::column-end::: 
:::row-end:::
:::row::: 
    :::column span="1"::: 
       **Usage limit for Chat is reached**
    :::column-end::: 
    :::column span="2"::: 
       User no longer receives chat responses when sending prompts. The Copilot badge stays green, indicating **active** status. 
    :::column-end::: 
:::row-end:::
:::row::: 
:::row-end:::

When you reach usage limits for Copilot Free, you can wait for them to reset at the end of the monthly cycle or upgrade to Copilot Pro to continue using Copilot.

## Frequently asked questions

#### Who can access Copilot Free?

Copilot Free is not available if you have an EMU account, access to a Copilot seat through an organization, an existing Copilot Pro subscription or trial, or free access to Copilot Pro as a student, teacher, or open-source maintainer.
For the latest information, see [About GitHub Copilot Free](https://aka.ms/ghdocscopilotfreepage).

#### Can I turn off completions to save them for later?

Yes. You can enable or disable completions at any time.
To enable or disable, select **Settings** > **Options** from **GitHub Copilot** badge in the upper-right corner of your IDE, and then select or unselect **Enable Copilot Completions**. 

#### Can I block suggestions matching public code with Copilot Free?

Yes. You can configure these settings from the [GitHub Copilot Settings](https://github.com/settings/copilot) page.

#### What Copilot features are included in Copilot Free?

Copilot Free includes the following features: Copilot Completions, Edits, and Chat.
Learn more at [About GitHub Copilot Free](https://aka.ms/ghdocscopilotfreepage).

#### What are the Copilot Free limits for Completions and Chat?

See [About GitHub Copilot Free](https://aka.ms/ghdocscopilotfreepage) for information.

## Related content

- [Install and manage GitHub Copilot in Visual Studio](visual-studio-github-copilot-install-and-states.md)
- [GitHub Copilot experience for Visual Studio](visual-studio-github-copilot-extension.md)
- [GitHub Copilot Chat experience for Visual Studio](visual-studio-github-copilot-chat.md)
- [About GitHub Copilot Free](https://aka.ms/ghdocscopilotfreepage)