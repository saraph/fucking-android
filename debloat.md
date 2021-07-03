In directory `/system/app`:


| File or directory          | Safe to remove? | Description             |
| -------------------------- | --------------- | ----------------------- |
| `AASAservice`              | Safe            | Samsung Knox Component  |
| `ARCore`                   | Safe            | Google AR SDK           |
| `ARDrawing`                | Safe            | Samsung AR Drawing?     |
| `ARZone`                   | Safe            | Samsung AR SDK?         |
| `AllShareAware`            | Safe            | Samsung Sharing Spyware | 
| `AllshareFileShare`        | Safe            | Samsung Sharing Spyware | 
| `AllshareMediaShare`       | Safe            | Samsung Sharing Spyware | 
| `ApexService`              | Unsafe          |
| `AppLinker`                | Unsafe          |
| `AutomationTest_FB`        | Safe            |
| `BBCAgent`                 | Safe            |
| `BCService`                | Safe            |
| `BGMProvider`              | Safe            |
| `BasicDreams`              | Safe            |
| `Bluetooth`                | Unsafe          |
| `BluetoothMidiService`     | Safe            |
| `BluetoothTest`            | Safe            |
| `BookmarkProvider`         | Safe            |
| `BrightnessBackupService`  | Safe            |
| `Cameralyzer`              | Safe            |
| `CaptivePortalLoginGoogle` | Safe            |
| `CarrierDefaultApp`        | Safe            |
| `CertInstaller`            | Safe            |
| `Chrome`                   | Safe            |

In directory `/system/framework`:

Important (cause boot failure if removed)

- `boot-knoxanalyticssdk.vdex`
- `boot-knoxsdk.vdex`
- `fipstimakeystore.jar`

Irrelevant (safely removed)

- `com.dsi.ant.antradio_library.jar`
- `gamemanager.jar`
- `gamesdk.jar`
- `gamesdkWrapper.jar`
- `perfsdk.jar`
- `perfsdkservice.jar`
