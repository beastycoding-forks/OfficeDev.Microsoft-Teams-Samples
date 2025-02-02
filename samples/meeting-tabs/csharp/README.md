---
page_type: sample
description: This sample shows app stage view, Mute/Unmute Teams meeting audio call in meeting Side panel tab.
products:
- office-teams
- office
- office-365
languages:
- csharp
extensions:
 contentType: samples
 createdDate: "24-01-2023 10:00:01"
urlFragment: officedev-microsoft-teams-samples-meeting-tabs-csharp

---

## Meeting Tabs Sample

This sample shows app stage view, Mute/Unmute Teams meeting audio call in meeting Side panel tab.

## Included Features
* Meeting Stage
* Meeting SidePanel
* RSC Permissions
* Teams Theme Handler

**Interaction with bot**
![MeetingTabsGif](Images/MeetingTabsGif.gif)

**Interaction with Teams Themes**
![TeamsTheme](Images/TeamsThemes.gif)

## Try it yourself - experience the App in your Microsoft Teams client
Please find below demo manifest which is deployed on Microsoft Azure and you can try it yourself by uploading the app manifest (.zip file link below) to your teams and/or as a personal app. (Sideloading must be enabled for your tenant, [see steps here](https://docs.microsoft.com/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant#enable-custom-teams-apps-and-turn-on-custom-app-uploading)).

**Meeting-Tabs:** [Manifest](/samples/meeting-tabs/csharp/demo-manifest/meeting-tabs.zip)

## Prerequisites

- [.NET Core SDK](https://dotnet.microsoft.com/download) version 6.0

  determine dotnet version
  ```bash
  dotnet --version
  ```
- [dev tunnel](https://learn.microsoft.com/en-us/azure/developer/dev-tunnels/get-started?tabs=windows) or [ngrok](https://ngrok.com/) latest version or equivalent tunnelling solution
- [Teams](https://teams.microsoft.com) Microsoft Teams is installed and you have an account

## Setup

> Note these instructions are for running the sample on your local machine.

1. Run ngrok - point to port 3978

   ```bash
   ngrok http 3978 --host-header="localhost:3978"
   ```  

   Alternatively, you can also use the `dev tunnels`. Please follow [Create and host a dev tunnel](https://learn.microsoft.com/en-us/azure/developer/dev-tunnels/get-started?tabs=windows) and host the tunnel with anonymous user access command as shown below:

   ```bash
   devtunnel host -p 3978 --allow-anonymous
   ```

2. Setup

   **Register your application with Azure AD:**

    - Register a new application in the [Azure Active Directory – App Registrations](https://go.microsoft.com/fwlink/?linkid=2083908) portal.

    - Select **New Registration** and on the *register an application page*, set following values:
           * Set **name** to your app name.
           * Choose the **supported account types** (any account type will work)
           * Leave **Redirect URI** empty.
           * Choose **Register**.

    - On the overview page, copy and save the **Application (client) ID, Directory (tenant) ID**. You’ll need those later when updating your Teams application manifest and in the appsettings.json.

    - Ensure that you've [enabled the Teams Channel](https://docs.microsoft.com/en-us/azure/bot-service/channel-connect-teams?view=azure-bot-service-4.0)

3. Clone the repository

    ```bash
    git clone https://github.com/OfficeDev/Microsoft-Teams-Samples.git
    ```
    
4. Run the app from a terminal or from Visual Studio, choose option A or B.

    A) From a terminal, navigate to `samples/meeting-tabs/csharp`

    ```bash
    # run the app
    dotnet run
    ```
    B) Or from Visual Studio

    - Launch Visual Studio
    - File -> Open -> Project/Solution
    - Navigate to `samples/meeting-tabs/csharp` folder
    - Select `AppInMeeting.sln` file
    - Press `F5` to run the project

5. In a terminal, navigate to `samples/meeting-tabs/csharp/ClientApp`

    - Inside ClientApp folder execute the below command.

        ```bash
        # npm install
        ```
 6. __*This step is specific to Teams.*__

- **Edit** the `manifest.json` contained in the  `AppManifest` folder to replace your Microsoft App Id (that was created when you registered your bot earlier) *everywhere* you see the place holder string `<<YOUR-MICROSOFT-APP-ID>>` (depending on the scenario the Microsoft App Id may occur multiple times in the `manifest.json`)

- **Edit** the `manifest.json` for `<<DOMAIN-NAME>>` with base Url domain. E.g. if you are using ngrok it would be `https://1234.ngrok-free.app` then your domain-name will be `1234.ngrok-free.app` and if you are using dev tunnels then your domain will be like: `12345.devtunnels.ms`.

- **Zip** up the contents of the `AppManifest` folder to create a `manifest.zip` (Make sure that zip file does not contains any subfolder otherwise you will get error while uploading your .zip package)

- **Upload** the `manifest.zip` to Teams (In Teams Apps/Manage your apps click "Upload an app". Browse to and Open the .zip file. At the next dialog, click the Add button.)

- Add the app to team/groupChat scope (Supported scopes). 

## Running the sample

You can interact with Teams Tab meeting sidepanel.

1. **Install app**
![InstallApp](Images/InstallApp.png)

2. **Type a meeting name**
![AddMeetingTabs](Images/AddMeetingTabs.png)

3. **Select meeting name**
![selectMeetingName](Images/selectMeetingName.png)

4. **Add meeting tab**
![AddMeeting](Images/AddMeeting.png)

5. **Join meeting**
![JoinMeeting](Images/JoinMeeting.png)

6. **Select your app**
![appAddMeeting](Images/appAddMeeting.png)

7. **Add meeting tab**
![appAddMeetingTabs](Images/appAddMeetingTabs.png)

8. **Home page**
![HomePage](Images/HomePage.png)

9. **Click share To stage view**
![clickShareStageView](Images/clickShareStageView.png)

10. **Share To stage view**
![NextTenant](Images/NextTenant.png)

11. **Toggle To Mute**
Toggle button to mute state its looks like below.
![audioCall](Images/audioCall.png)

12. **Toggle To Unmute**
Toggle button to Unmute state it will unmute client audio.
![audioCallTrue](Images/audioCallTrue.png)

13. **App theme when dark**
![Dark](Images/dark-with-timer.PNG)

14. **App theme when light**
![Light](Images/light-with-timer.PNG)

15. **App theme when contrast**
![Contrast](Images/contrast-with-timer.PNG)

## Further reading

- [Toggle incoming audio](https://docs.microsoft.com/en-us/microsoftteams/platform/apps-in-teams-meetings/api-references?tabs=dotnet#toggle-incoming-audio)
- [Get incoming audio speaker](https://docs.microsoft.com/en-us/microsoftteams/platform/apps-in-teams-meetings/api-references?tabs=dotnet#get-incoming-audio-speaker)
- [Generate meeting side panel](https://learn.microsoft.com/en-us/microsoftteams/platform/sbs-meetings-sidepanel?tabs=vs)
- [Handle theme change](https://learn.microsoft.com/en-us/microsoftteams/platform/tabs/how-to/access-teams-context?tabs=Json-v2%2Cteamsjs-v2%2Cdefault#handle-theme-change)


<img src="https://pnptelemetry.azurewebsites.net/microsoft-teams-samples/samples/meeting-tabs-csharp" />