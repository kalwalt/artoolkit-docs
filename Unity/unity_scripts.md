#Scripts in ARToolKit for Unity

##ARController
The ARController script manages the overall operation of the tracking plugin. It performs the necessary native plugin calls, and allows the developer to configure general settings. There should only ever be one ARController script in a scene. *Prior to ARToolKit for Unity v5.1.3, this script was named ARToolKit.*

![ARToolKit Panel][artoolkit_panel]

-   Version: The version number of ARToolKit on which the plugin is built.

###Video Options

-   Configuration: Configuration string passed to the video capture module (more [details][details]).
-   Near Plane: Near plane value used when constructing projection matrix. Measured in metres by default. Decrease to allow a closer camera.
-   Far Plane: Far plane value used when constructing projection matrix. Measured in metres by default. Increase to allow a more distant camera.
-   Layer: The Unity layer in which the video plane will be rendered.

###Threshold Options

-   Mode: The thresholding mode to use. The standard ARToolKit options are available: Manual, Median, Otsu, Adaptive. Different configuration options appear depending on the selected mode.

##ARMarker
The ARMarker script represents one tracked marker in the system. Add one for each individual marker that you want to track. *Prior to ARToolKit for Unity v5.1.3, this script was named Marker.*

![Marker Panel][marker_panel]

-   Tag: A unique name that identifies this marker.
-   ID: The internal ID number for this marker. Starting at -1, this number will simply increase. It can be safely ignored.
-   Type: The type of marker. Currently only single template markers are supported.
-   Marker: The marker to use. This list is populated by the marker
    files placed in the Assets/Resources/ardata/markers directory.
-   Width: The width of the marker in metres.

##ARCamera
TheARCamera script associates markers with cameras. Add this to a camera and link it to a marker to update the camera's pose at runtime. *Prior to ARToolKit for Unity v5.1.3, this script was named TrackedCamera.*

![AR Camera Panel][camera_panel]

-   Tag: The unique name of the marker that this camera should take its pose from. This should match an existing Marker script's tag.
-   Stay Visible: The length in seconds of how long the camera should stay active after marker tracking is lost. For example, using a value of 0.25 will give one quarter of a second delay before the marker's content disappears. This can reduce the effect of flickering.
-   Got marker: Simply displays whether the entered tag matches an existing Marker.
-   Marker ID: The ID of the marker that is linked to this camera via the tag. May be -1 until the pattern is actually loaded.

###Events
The ARCamera generates the following events, using Unity's SendMessage command. To handle these events, implement the matching event handler in a script, and attach it to the ARCamera.

-   void OnMarkerLost(ARMarker marker)
-   void OnMarkerFound(ARMarker marker)

[artoolkit_panel]:/File:ARToolKitPanel.png "wikilink"
[details]:/Configuring_video_capture_in_ARToolKit_Professional "wikilink"
[marker_panel]:/File:MarkerPanel.png "wikilink"
[camera_panel]:/File:TrackedCameraPanel.png "wikilink"

##Gizmos
Markers are visually represented within the Unity editor so that you can scale and position your content accordingly.
[Marker Gizmo][gizmo]

[gizmo]:/File:MarkerGizmo.png "wikilink"
[Category:ARToolKit for Unity](/Category:ARToolKit_for_Unity "wikilink")