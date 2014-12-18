delete-record-checklist
=======================

Checklist to confirm 'DELETE' record (for database driven app) is coded correctly

Whenever you code "DELETE" functionality for database driven app, use below listed items as checklist:

*Show JavaScript confirmation alert box asking user to confirm delete operation.

*Just before the snippet that deletes record from DB, make a check to confirm the ownership of record and user right to delete this record. The user or a script who is performing delete operation should have access rights to delete that specific record.
Generally, the user who create a record can also delete the same record. Admin user has access to delete any record. 

*If the record that is being deleted has some images or files attached to it, then delete those images / files as well conditionally. The condition depends on what kind of application you are working on. 
Example 1:
If you are working on custom CMS application like wordpress where all media (files / assets) are uploaded to one central library of assets, then you may not want to delete the atatched file once record is deleted. Because same image / file could have been used with other records as well.
Example 2:
Assume that you are working with users module. Once user is deleted from the app, then you may care to delete the user's profile image and all other assets uploaded by / for that user.

Before the snippet that deletes the images / files, you must add a check to confirm current user's right to delete those assets.  

*Once you delete the record,  you may want to set logic / algorithm to delete its associated records.


