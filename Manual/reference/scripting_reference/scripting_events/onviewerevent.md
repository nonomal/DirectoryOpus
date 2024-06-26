# OnViewerEvent

The **OnViewerEvent** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to receive notification whenever certain events occur in the [standalone image viewer](/Manual/additional_functionality/viewing_images/README.md). One possible use would be a script that automatically displays a floating toolbar whenever a standalone viewer is active, and hides it again when the window goes inactive or closes. 

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnViewerEvent
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[ViewerEventData](../scripting_objects/viewereventdata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>

*none*
</td></tr><tr><td>

**Description:**</td><td>

The **ViewerEventData.viewer** property identifies the **[Viewer](../scripting_objects/viewer.md)** that the event occurred in. The **event** property returns a string identifying the event that occurred, and if applicable the **item** property identifies the **Item** involved.
</td></tr></tbody>
</table>

