---
sidebar_position: 1
---

import CollapsibleAnswer from '@site/src/components/CollapsibleAnswer';
import DeepDive from '@site/src/components/DeepDive';
import ImageCard from '@site/src/components/ImageCard';
import ChatBaseBubble from '@site/src/components/ChatBaseBubble';
import VideoItem from '@site/src/components/VideoItem';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem'

# Installation and Setup

:::caution Versions
We are using the following versions of Unity editor, `mono`, `dotnet`, and C# Visual Studio Code extension:

- [Unity Hub 3.5.0](https://unity.com/download)
- [Unity 2022.3.5f1](https://unity.com/releases/editor/whats-new/2022.3.5)
- [Mono 6.12.0 ](https://www.mono-project.com/download/stable/)
- [.NET 7.0](https://dotnet.microsoft.com/en-us/download)
- [VSCode Extension C# v1.26.0](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)

You are free to use other code editors or IDE such as Neovim, Visual Studio or Monodevelop. Please enable intellisense regardless of which IDE/code editor you are using.
:::

Please install all of the above tools before proceeding.

### Basic Setup

:::note
**Download the starter asset** from your **course handout**, under "Class Calendar" heading, _Week 1 Lab Session_ row. This is a **starter** asset for this week that you can import to your project and complete the lab. It contains all required images, sound files, etc so we can save time without having to search for all these assets.
:::

### Create New Project

Using UnityHub, create a new 2D project:

<ImageCard path={require("./images/installation/2023-07-25-16-39-08.png").default} widthPercentage="70%"/>

Then, **import** the asset you downloaded:
<ImageCard path={require("./images/installation/2023-07-25-16-40-37.png").default} widthPercentage="70%"/>

You should see a list of assets on the Project tab in the Unity editor.

### Setting up VSCode

Check that `dotnet` and `mono` are installed properly:

<ImageCard path={require("./images/installation/cli-check-mono-dotnet.png").default} widthPercentage="70%"/>
<br/>
If you're using VSCode, ensure that you install the C# VSCode extension:

<ImageCard path={require("./images/installation/csharp-extension.png").default} widthPercentage="70%"/>

<br/>
Then add the following to your VSCode`settings.json`:

```json title="[other path]/Code/Usersettings.json"
{
  // ... other settings
  "omnisharp.projectLoadTimeout": 60,
  "omnisharp.monoPath": "/Library/Frameworks/Mono.framework/Versions/Current",
  "omnisharp.dotnetPath": "/usr/local/share/dotnet/dotnet",
  "omnisharp.useModernNet": false,
  "omnisharp.useGlobalMono": "always",
  // for format on save (automatically)
  "editor.formatOnSave": true,
  "[csharp]": {
    "editor.defaultFormatter": "ms-dotnettools.csharp"
  }
}
```

You might want to ignore irrelevant files while opening your project with VSCode. Add the following setting in your project workspace:

```json title=".vscode/settings.json"
    // Configure glob patterns for excluding files and folders.
    "files.exclude": {
        "**/.git": true,
        "**/.DS_Store": true,
        "**/*.meta": true,
        "**/*.*.meta": true,
        "**/*.unity": true,
        "**/*.unityproj": true,
        "**/*.mat": true,
        "**/*.fbx": true,
        "**/*.FBX": true,
        "**/*.tga": true,
        "**/*.cubemap": true,
        "**/*.prefab": true,
        "**/Library": true,
        "**/ProjectSettings": true,
        "**/Temp": true
    }
```

You also need to install Visual Studio Code Editor under Window >> Package Manager in Unity:

<ImageCard path={require("./images/installation/package-manager-install-vscode-editor-support.png").default} widthPercentage="70%"/>

And then link VSCode in External Tools tab under Unity's Preferences:

<ImageCard path={require("./images/installation/externaltools-resetarg-regenprojectfiles.png").default} widthPercentage="70%"/>
<br/>

:::tip
The official support for Unity in VSCode has been dropped, so it might be a bit wonky sometimes (VSCode can't find `mono`, etc). Try completely quitting VSCode (<span className="orange-bold">not just closing it</span>) and reopening the files.
:::

## Housekeeping

To work better, we need to set up the UI in a more comfortable way. We need at least the following **windows**:

1.  **Inspector** (to have an overview of all elements in a GameObject), set on the right hand side,
2.  Game Hierarchy (to have an overview of all GameObjects in the scene), set on the left hand side
3.  Scene Editor (to add GameObjects and place them), set on the middle of the screen
4.  Then usually we also have the following windows (kept as tabs):
    1.  Project (to show all the files),
    2.  Console (to see printed output)
    3.  Game Screen (to test your game)

Then, go to **Scenes** folder and rename your scene in a way that it makes more sense than “_SampleScene_”. Create **two more folders** called “**Scripts**”, and “**Prefabs**” under "**Assets**". We will learn about them soon.

Here's a suggested layout:

<ImageCard path={require("./images/installation/2023-07-27-08-14-48.png").default} widthPercentage="100%"/>