# DDM Explorer

Jamf DDM Explorer is an app that was built to help Jamf Pro administrators learn and understand how Apple’s powerful Declarative Device Management framework works. Additionally, you can build and test declarations on your own Jamf-enrolled devices **(COMING SOON)**.

### Explore and Learn

With DDM Explorer, you can explore every detail of Apple’s DDM components (including Activation, Asset, Configuration, Status and Management). All DDM framework data is retrieved directly from Apple’s GitHub and DDM Explorer allows you to explore non-release/beta branches when available.

### Build and Test

Using the built-in declaration creator, build and save your DDM components directly within the app. In an upcoming release of DDM Explorer, you will be able to connect the app to Jamf Pro and test your declarations on enrolled devices.

Please note that this app is currently in beta and elements may changed, added or removed at any point as Jamf 


## Table of Contents
- [What is DDM?](#What-is-DDM?)
- [Declaration Components](#Declaration-Components)
- [Explore & Build Declarations with DDM Explorer](#Explore-&-Build-Declarations-with-DDM-Explorer)
- [Combine Components & Send Declaration to a Device (COMING SOON)](#Combine-Components-&-Send-Declaration-to-a-Device)
- [Download (macOS & iPadOS)](#Download)


## What is DDM?
Declarative Device Management (DDM) is a modern framework introduced by Apple to simplify and improve the way organizations manage Apple devices. It uses a declarative model to apply and maintain configurations, settings, and policies on devices more efficiently than traditional management approaches.

### How Does It Work?
* Traditional Management: Relies on commands sent from a server to enforce settings. Devices frequently contact the server to check for updates, leading to higher latency and server dependency.
* DDM Approach: Devices are provided with declarations (descriptions of desired state or behavior) from a server. Devices interpret and apply these declarations locally, reducing server dependency and enabling faster responses to changes.

## Declaration Components
Declarations are composed of multiple components and can be used to build complex workflows. The following are DDM components that can be build in DDM Explorer:

| Component    | Description  | Example  |
| ------------- | ------------- | ------------- |
| Activation      | Activates specific configurations or other items based on device or user conditions. | A device activates a "Work Mode" configuration when the user logs in with a corporate account. Using the **Predicate** key, you can reference Status items (ex: OS version, device type, battery, etc.) to design your deployment requirements. |
| Asset     | Represents reusable resources like wallpapers, certificates, app configurations and much more. | Define items such as corporate email accounts, wallpaper images or Wi-Fi profiles to deploy to all employee devices. |
| Configuration | Defines settings or policies applied to devices. | Enforce configurations such as password requirements, disk management settings, software updates, background tasks, Safari extensions, to name a few. |
| Management | Oversees and coordinates all the declarations and ensures devices receive the correct policies. | Assign different profiles based on user roles. |
| Status | Tracks and reports the current state of the device back to the management system. | Report whether the device is compliant with the password policy. Status elements can be added to the Activation Predicate key. |


## Explore & Build Declarations with DDM Explorer
To start building declaration components, click on an item in the sidebar or home view. Browse the keys and subkeys and use the declaration builder to create your JSON structure. When finsished, click Save at the bottom-right.

Note that you must include a unique identifier in the Identifier field. You must reference this identifier in other declaration components when you construct and send declarations to devices. In the following example, the Activation references a saved configuration called `com.jamf.passcode`.

```json
{
  "type" : "com.apple.activation.simple",
  "id" : "com.jamf.activation.predicate.mac",
  "payload" : {
    "StandardConfigurations" : [
      "com.jamf.passcode"
    ],
    "Predicate" : "(@status(device.model.family) == 'Mac')"
  }
}
```

## Combine Components & Send Declaration to a Device
After creating constituent components, combine them into a declaration and send them to a test device by cllicking Send Declaration on the home view or at the bottom-right of an Activation, Asset, Configuration, Management or Status view.

Select all desired values from the drop-down menus and note the following:
* An **Activation** and **Configuration** are required
* Confirm the Declaration Channel matches the **Allowed Scope** of your components
* Make sure Jamf Pro is configured in **Settings** and that your test device's Jamf Pro Management ID is entered correctly

<img width="1624" alt="DDM Explorer" src="https://github.com/user-attachments/assets/ca33eb1b-fc8b-4856-8bc7-f658dfb0a39c" />

## Download
Download DDM Explorer on the Apple App Store. Available for Mac and iPad.

[![app_store svg](https://github.com/user-attachments/assets/eec5de86-703d-444d-9785-027e315e8ddf)](https://apps.apple.com/app/ddm-explorer/id6677001018)





