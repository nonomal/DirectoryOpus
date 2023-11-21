# Rename

You can use the evaluator in the [advanced rename](/Manual/file_operations/renaming_files/advanced_rename/RAEDME.md) tool to insert text returned by the evaluation.

Use the \`{= ... =}\` code to insert an evaluation expression. The return value of the expression is inserted into the info tip.

In this evaluation context, the following variables are available:

\<commandtable columns="3"\> \$\$ Variable \$\$ Type \$\$ Description \$\$ \<nobr\>*column name*\</nobr\> \$\$ *varies* \$\$ All the [column keywords](/Manual/reference/metadata_keywords/keywords_for_columns.md) are available as variables in this evaluation context.

Note that some keywords may use characters like a \`:\` that aren't valid in variable names - to access them, use the [val](/Manual/reference/evaluator/val.md) function.

Additionally, the info tip-specific keywords **foldersize**, **foldercontents** and **infotip** are also supported. \$\$ is_dir \$\$ *bool* \$\$ **True** if the expression is being run for a folder, **false** if it's being run for a file. \$\$ oldname \$\$ *str* \$\$ The value of the "old name" field. \$\$ newname \$\$ *str* \$\$ The value of the "new name" field. \</commandtable\>

The return value should be a *str* that will be inserted into the new filename.