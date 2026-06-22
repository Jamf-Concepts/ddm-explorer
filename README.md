## DDM Explorer

<p align="center">
  <a href="https://apps.apple.com/app/ddm-explorer/id6754861743">
    <img src="https://github.com/user-attachments/assets/eec5de86-703d-444d-9785-027e315e8ddf" alt="Download on the App Store" width="180" />
  </a>
  <br/>
  <em>Available for Mac and iPad</em>
</p>

<img width="1279" height="802" alt="Explorer Home view" src="https://github.com/user-attachments/assets/6e1ed34e-f08e-41e4-9d53-e6f7297b8461" />

Jamf DDM Explorer is an app built to help IT administrators learn and understand Apple's Declarative Device Management framework, allowing users to browse published declaration types compatible for both currently-shipping operating systems, as well as pre-release beta declarations published in available GitHub branches. Use this app for same-day declaration building as soon as documentation is released for available beta operating system versions.

  <img width="1279" height="802" alt="Declaration Explorer view" src="https://github.com/user-attachments/assets/9e2203eb-ac2d-40bd-9261-35c90323e2f9" />

Browse and build payloads in a brand-new Declaration Explorer editor for deployment as custom declarations to test devices, and deploy with your device management system for testing. All declaration objects are sourced directly from Apple's GitHub, allowing for loading pre-release branch documentation, when available.

<img width="1279" height="802" alt="Status Explorer view" src="https://github.com/user-attachments/assets/41a95c94-cac7-4f9b-b666-7965171d76a0" />

Once declarations are deployed and activated, use the Status Explorer view to view your test device's current declarative status reports, including available status subscriptions. Status documentation is also built in-line with the Status Explorer viewer for reference.

Note: Features such as reading a test device's status reports require an integration with Jamf Pro.

### Explore and Learn

Use the Declaration Explorer view to browse available declarations and learn how they can be configured. DDM Explorer translates yaml data files into an easy-to-read browser, displaying information such as supported OS platform and version compatibility, enrollment types, and available scoping channels (System or User) for each given declaration type. 

Additionally, each declaration's key structure is visually displayed to show the hierarchy of required keys and formatting, combined with additional details and descriptions pulled directly from Apple's documentation.

Use the Status Explorer view to inspect device status information from your test device in Jamf Pro that was sent via declarative status subscriptions. View and inspect what type of data is possible to receive from managed devices using DDM status messages in the status browser, then compare that to live status data that's retrieved via the Jamf Pro API.

When testing new and updated declarations against beta operating systems, it can be helpful to view and export this status data to include when filing Feedback with Apple or reporting issues with Jamf.


### Build and Test

The Declaration Explorer viewer is also a declaration editor, allowing you to add keys and values to a declaration, while letting the editor build the required JSON formatting. Easily add additional keys and array items within the editor, with inline guidance showing which keys are required in specific configurations. 

As edits take place, view the Declaration Payload window and the JSON output displayed in real time to see the structure of the declaration object, then copy the payload data to deploy as a Custom Declaration to deploy and test with in Jamf Pro.

**(COMING SOON)** Use Jamf Platform API integration to deploy declarations to test devices. 

Please note that this app is provided as-is and elements may be changed, added, or removed at any point. 


### Configure DDM Explorer for your environment

You can choose which available GitHub documentation branch to explore and configure available Jamf API integrations in the Settings viewer. Apple's `release` branch is the default source, and beta documentation branches can be selected instead, when available.

#### Integrate with the Jamf Pro API

The Status Explorer allows you to view the full status reports of the latest data reported to Jamf Pro from a specific test device. Use the Settings viewer to configure this integration, using either Username & Password credentials or an API Client & Secret for authentication.

Required permissions for this API access are:
- `Read Computers`
- `Read Mobile Devices`

Enter your full server URL, such as `https://YOURSERVER.jamfcloud.com`.
Enter your test device's Jamf Pro Management ID value, (i.e. `c2682b69-4073-499f-a024-bf583d26a78c`).

#### Deploy test declarations with a Custom Declarations component in blueprints

Once a declaration payload is built, the JSON contents can be copied and deployed as a custom declaration in blueprints. See Jamf documentation for more information: [Creating a Custom Declaration Blueprint](https://learn.jamf.com/r/1wMrPGpTfIhzefOZY1loHg/zmGXeA6z6wrw3zw2G5mLhw)


## Download
Download DDM Explorer on the [App Store](https://apps.apple.com/app/ddm-explorer/id6677001018). Available for Mac and iPad.
