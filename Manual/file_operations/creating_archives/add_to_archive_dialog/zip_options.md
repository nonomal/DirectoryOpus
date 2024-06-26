# Zip Options

When using the **[Add to Archive](/Manual/file_operations/creating_archives/add_to_archive_dialog/README.md)** dialog to add files to a Zip archive, the following options are available:

- **Compression level**: This lets you set the compression level used when adding the files to the archive. There are six compression levels available, ranging from *Store* (which does no compression at all and so is the fastest) to *Best* (which produces the highest level of compression but takes longer to archive).
  - **Enhanced compression level**: This activates an [enhanced compression algorithm](http://en.wikipedia.org/wiki/DEFLATE#Deflate64.2FEnhanced_Deflate) that may not be backwards compatible with some Zip tools - if you are sending Zip files to other people you should make sure they can decompress such archives.

- **Encryption method**: If you want to encrypt the files in the Zip archive, you can choose the encryption method to use here.

*Standard* is the oldest, most backwards-compatible encryption method, and all Zip tools should be able to decompress archives encrypted with this method. However it's also the least secure method. If you want a more secure encryption you can select one of the *AES* options from the drop-down (the three [AES algorithms](http://en.wikipedia.org/wiki/Advanced_Encryption_Standard) are the same, just with different key lengths). If you are sending Zip files to other people you should make sure they can decompress AES-encrypted archives before using this option.

- **Password**: If you want to encrypt the files you are adding to the Zip archive, enter a password here. If the **Mask password** option is on, the password you enter here will be hidden - and so for security you must enter the password again in the **Verify password** field. If you leave the **Password** field empty no encryption will be performed.
- **Verify password**: If you have entered a password in the **Password** field you need to enter the same password here as a confirmation (unless **Mask password** is turned off).
- **Mask password**: If this option is on the passwords you enter to encrypt the files you are adding will be masked (not displayed).
- **Make self-extracting archive**: Turn this option on if you want to make a [Self-Extracting Zip File](../zip_files/self-extracting_zip_files.md) out of the Zip archive once it has been created.
- **Split archive**: The Zip archive format supports the concept of split archives - a larger archive that is stored as multiple files instead of one large file.

A split archive (as long as you have all the pieces) can be accessed just like it was all the one file, and it may be useful to use this when emailing large archives (or for backup on removable media, etc). Turn this option on if you want to make a split archive. You can choose a pre-defined chunk size from the drop-down list, or enter your own size. If you enter a manual size you can specify it in kilobytes (**KB**), megabytes (**MB**) or gigabytes (**GB**) by entering the number followed by the appropriate suffix. For example, **1.87 MB**. If no suffix is given, the chunk size is taken to mean bytes.

- **Save full file paths**: If this option is turned on then the full paths of files you add to the archive will be stored in the archive. If this option is off the path is stored relative to the current folder.

For example, say you go into **C:\Test**, select a folder called Reports that contains one file (**Sales.docx**) and add it to an archive. If this option was off, the path of **Sales.docx** in the archive would be stored as **Reports\Sales.docx**. If the **Save full file paths** option was on, the path stored would be **C:\Test\Reports\Sales.docx**.

 
