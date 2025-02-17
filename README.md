# Flutter TDS Permission

**version : 1.0.0**

# [Change log](https://github.com/wahyuunt-organization/private_package/releases)

# Table of content

- [Minimum Requirement](https://www.notion.so/Flutter-TDS-Permission-1969b636c7a680dfbffdd101f437b5b6?pvs=21)
- [Setup](https://www.notion.so/Flutter-TDS-Permission-1969b636c7a680dfbffdd101f437b5b6?pvs=21)
    - [Android](https://www.notion.so/Flutter-TDS-Permission-1969b636c7a680dfbffdd101f437b5b6?pvs=21)
    - [iOS](https://www.notion.so/Flutter-TDS-Permission-1969b636c7a680dfbffdd101f437b5b6?pvs=21)
- [How To Use](https://www.notion.so/Flutter-TDS-Permission-1969b636c7a680dfbffdd101f437b5b6?pvs=21)
    - [Available Permission](https://www.notion.so/Flutter-TDS-Permission-1969b636c7a680dfbffdd101f437b5b6?pvs=21)
    - [Get Status](https://www.notion.so/Flutter-TDS-Permission-1969b636c7a680dfbffdd101f437b5b6?pvs=21)
    - [Request Permission](https://www.notion.so/Flutter-TDS-Permission-1969b636c7a680dfbffdd101f437b5b6?pvs=21)
- [Example](https://www.notion.so/Flutter-TDS-Permission-1969b636c7a680dfbffdd101f437b5b6?pvs=21)

- minimum requirement :
    - Flutter x.x.x
    - Android API 19+
    - iOS 16

# Setup

```bash
flutter pub add tds_permission
```

- Android
    
    ```json
    
    ```
    
- iOS
    
    ```json
    
    ```
    

# How To Use

---

### Available Permission

```dart
/**
 * Enum representing the different types of permissions that can be requested
 * by the plugin.  Each value corresponds to a specific permission, such as
 * location access, notification access, etc.
 */
enum TDSPermission {
	//Permission to access the device's location.
	location,
	
	//Permission to send and receive notifications.
	notification,
	
	//Permission to access the device's camera.
	camera,
	
	//Permission to use Bluetooth functionality.
	bluetooth,
	
	//Permission to access the device's storage.
	storage,
	
	//Permission to access the user's contacts.
	contact,
	
	//Permission to access media files (images, videos, etc.).
	media,
	
	//Permission to access the device's microphone/audio input.
	audio
}
```

### Get Status

with .status, you can get status permission. that available status is `.isAvailable` ,`.isDenied` ,`.isReject` , `.etc`

```dart
// Request the status of a specific permission using the TDSPermission package.
// Parameters:
// - "iOS": Specifies the platform for which permission is being checked.
// - .notification: Specifies the type of permission being requested (notification permission).
// The 'await' keyword ensures that the function waits for the status result before proceeding.
var status = await TDSPermission("iOS", .notification).status();

if (status[.location] == .isAvailable) {
	//todo: handle if permission is available
}
```

### Request Permission

```dart
// Request camera permission using the TDSPermission package.
// Parameters:
// - "iOS": Specifies that the permission request is for the iOS platform.
// - .camera: Specifies the type of permission being requested (camera permission).
TDSPermission("iOS", .camera).request({ (status) {
    
    // Check if the permission status is available
    if (status == .isAvailable) {
        // TODO: Handle the case when the permission is granted and available
    }

}});
```

# Example

```json

```
