# MSE FOR STUDIO - SETTINGS & CONFIGURATION

## 1. MSE Profile Settings
Mse using the mse config in studio/pcr
The existing **On-Air profile** must use the same profile configuration/name as the one configured in the application and Studio/PCR.
make name of profile and channel are identical
Required profiles:

* **On-Air Profile**
* **Preview Profile**

### Preview Profile

Create a new MSE profile called:

**PREVIEW**

The PREVIEW profile requires the following channels.

### Channel 1 - Same Channel Name as On-Air

Add a channel using the **same channel name as the On-Air profile**.

Example:

If the On-Air profile uses:

**VIZ2**

then the PREVIEW profile must also contain:

**VIZ2**

Configuration:

* Channel Name: `VIZ2`
* Engine: Viz Preview Engine
* Port: `6100`
* Renderer Mode: **PROGRAM**

> The channel name must match the channel used by the On-Air profile.

---

### Channel 2 - LIVEBOXPREVIEW

Add another channel called:

**LIVEBOXPREVIEW**

Configuration:

* Channel Name: `LIVEBOXPREVIEW`
* Engine: Viz Preview Engine
* Port: `6100`
* Renderer Mode: **PREVIEW**

#### Purpose

The `LIVEBOXPREVIEW` channel is used specifically for the Livebox workflow.

It is not only used for generating preview snapshots. It also allows the HTML Livebox Controller to update the Preview Engine when the operator presses:

**SEND TO PREVIEW**

This allows Livebox changes made in the HTML interface to be sent to and displayed on the dedicated Preview Engine before going On-Air.

---

## 2. Viz Engine Configuration

### Viz Engine - On-Air

Use the current Viz Engine assigned to the Full Frame or Livebox output.

**IP Address:** Current FF / Livebox Viz Engine IP
**Port:** `6100`

### Viz Engine - Preview

Use the dedicated Viz Engine for preview.

**IP Address:** Viz Preview Engine IP
**Port:** `6100`

---

## 3. Pilot Server

Pilot Server:

`https://aja-vip`

---

## 4. Playlist ID

The **Playlist ID** is obtained from the playlist selected in the application.

The application uses this ID to identify which MSE playlist should be accessed and controlled.

---

## 5. Template ID

The **Template ID** is used to filter the data elements retrieved from the playlist.

Only elements associated with the required template should be displayed/processed by the application.

The Template ID can be obtained using:

* Viz Template Wizard
* Viz Template Builder

---

## Configuration Summary

| Setting                 | Configuration                                    |
| ----------------------- | ------------------------------------------------ |
| MSE On-Air Profile      | Existing Studio/PCR profile                      |
| MSE Preview Profile     | `PREVIEW`                                        |
| Preview Program Channel | Same name as On-Air channel, e.g. `VIZ2`         |
| Preview Program Engine  | Viz Preview Engine                               |
| Preview Program Port    | `6100`                                           |
| Preview Program Mode    | PROGRAM                                          |
| Livebox Preview Channel | `LIVEBOXPREVIEW`                                 |
| Livebox Preview Engine  | Viz Preview Engine                               |
| Livebox Preview Port    | `6100`                                           |
| Livebox Preview Mode    | PREVIEW                                          |
| On-Air Viz Engine       | Current FF / Livebox Engine                      |
| On-Air Viz Port         | `6100`                                           |
| Pilot Server            | `https://aja-vip`                                |
| Playlist ID             | Obtained from playlist selection                 |
| Template ID             | Obtained from Template Wizard / Template Builder |
