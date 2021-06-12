# English Modding Guide

<ins>[[< Previous Page]](./main.md)</ins> <ins>[[Next Page >]](./use-2.md)</ins>

## How to install and configure UnityModManager for ADOFAI

### Installing UnityModManager

1. `UnityModManager` installation link: https://www.nexusmods.com/site/mods/21
   - Click the link and register if you do not have account.
   - After logging in, click `Manual` button next to `Download:` text.
   - Click `Slow Download`.
2. Unzip the downloaded `UnityModManager.zip`.
   - **Do not** unzip the file inside ADOFAI's directory!
3. If needed, [edit](#File-Editing) the `UnityModManagerConfig.xml` file based on [your game's version](#How-to-check-your-games-version) and execute the `UnityModManager.exe` file.
4. Configure `UnityModManager`.
   - Click the `Install` tab.
   - Click the dropdown next to the `Game` text, and select `A Dance of Fire and Ice`.
   - Click the button next to the `Folder` text, and select the folder (preferably the Steam folder) that contains the .exe file of ADOFAI. After selecting the folder, you can click OK.
   - Choose `Assembly` in the `Installation Method` group.
   - After clicking the `Install` button, please check if notepad pops up after executing the game. If notepad pops up, it means something went wrong while editing `UnityModManagerConfig.xml`. If you can't see what's wrong and need help, you can always join the [ADOFAI Modding Community Discord](https://discord.gg/AGFXhCfyE5) and ask for help.
   - If you are having a hard time understanding, you can follow the same steps using image below. The correct sequence is Red → Blue → Green if you can't read small numbers well.
     ![](../resources/use-1/image1.png)

---

<!-- Additional Info -->

### Additional Information

#### How to check your game's version

For older versions of ADOFAI, press `Esc` on main screen and go to `Settings`.
![](../resources/use-1/image2.png)

For the latest version of ADOFAI, press `Esc` on main screen.
![](../resources/use-1/image3.png)

#### File Editing

**Case 1:**
(Last checked 25/2/2021) There is a case you should edit the `UnityModManagerConfig.xml` file because of code differences between the current(`1.11.3 r70~`) and past(`v1.11.1 r68`) versions.

[Click here to check your game's version.](#How-to-check-your-games-version)

```xml
<GameInfo Name="A Dance of Fire and Ice">

...

</GameInfo>
```

Find the lines with above contents, and edit the `StartingPoint` and `UIStartingPoint` inside.

With version `r68` and below, use the below settings.

```xml
<StartingPoint>[Assembly-CSharp.dll]ADOBase.SetupLevelEventsInfo:Before</StartingPoint>
<UIStartingPoint>[Assembly-CSharp.dll]ADOBase.SetupLevelEventsInfo:After</UIStartingPoint>
```

After version `r69`, use the below settings. (You do not need to edit your file at all if you just downloaded UnityModManager.)

```xml
<StartingPoint>[Assembly-CSharp.dll]ADOStartup.Startup:Before</StartingPoint>
<UIStartingPoint>[Assembly-CSharp.dll]ADOStartup.Startup:After</UIStartingPoint>
```

This is preview of your settings. Note that `your settings value..` is not the actual value; it should be one of the values above.

```xml
<GameInfo Name="A Dance of Fire and Ice">
    <Folder>ADOFAI</Folder>
    <ModsDirectory>Mods</ModsDirectory>
    <ModInfo>Info.json</ModInfo>
    <GameExe>A Dance of Fire and Ice.exe</GameExe>
    <EntryPoint>[UnityEngine.UIModule.dll]UnityEngine.Canvas.cctor:Before</EntryPoint>
    <StartingPoint>your settings value..</StartingPoint>
    <UIStartingPoint>your settings value..</UIStartingPoint>
    <MinimalManagerVersion>0.22.14</MinimalManagerVersion>
    <Comment>Required minimum game version 1.11.3</Comment>
</GameInfo>
```

If you don't know how this XML format works, **try not to put settings value in the comments.**

[Alternatively, you can download a pre-edited version of the file.](https://drive.google.com/file/d/1BZ6XJwMnb9KsKtLcuQ5JctRs81nw_60V/view?usp=sharing)

**Case 2:**
If the game is not added in UnityModManager, you have to add it by yourself.

Just copy other game's data and replace the value with your needs.

---

## [Click here to go the next page.](./use-2.md)