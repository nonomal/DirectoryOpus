# OnGetHelpContent

The **OnGetHelpContent** event can be implemented by a [script add-in](/Manual/scripting/script_add-ins/README.md) to add its own help content to the Directory Opus local F1 help. You can add a single page of help, or multiple pages (in which case the first page becomes the "topic header" and all subsequent pages appear below it in the index). You can also add images which can be displayed in the help content. Note that script-added help is only possible if the user has local http help enabled (which is the default) - if the user has chosen to use the old *HtmlHelp* interface then your content won't appear. 

<table>
<thead><tr><th>

**Method Name:**</th><th>
OnGetHelpContent
</th></tr></thead><tbody><tr><td>

**Argument Type:**</td><td>

**[GetHelpContentData](../scripting_objects/gethelpcontentdata.md)**
</td></tr><tr><td>

**Return Type:**</td><td>
None.
</td></tr><tr><td>

**Description:**</td><td>

Use the **AddHelpPage** and **AddHelpImage** methods to add your help content.
</td></tr></tbody>
</table>

