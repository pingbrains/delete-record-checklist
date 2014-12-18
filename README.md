delete-record-checklist
=======================

Checklist to confirm 'DELETE' record (for database driven app) is coded correctly

Whenever you code "DELETE" functionality for database driven app, use below listed items as checklist:

* Show <b>JavaScript confirmation alert box</b> asking user to confirm delete operation.

* Just before the snippet that deletes record from DB, <b>make a check to confirm the ownership of record and user's right to delete this record</b>. The user or a script who is performing delete operation should have access rights to delete that specific record.
Generally, the user who create a record can also delete the same record. Admin user has access to delete any record. 

* If the record that is being deleted has some images or files attached to it, then <b>delete those images / files</b> as well conditionally. The condition depends on what kind of application you are working on. 
<br /><b>Example 1:</b> If you are working on custom CMS application like wordpress where all media (files / assets) are uploaded to one central library of assets, then you may not want to delete the atatched file once record is deleted. Because same image / file could have been used with other records as well.
<br /><b>Example 2:</b> Assume that you are working with users module. Once user is deleted from the app, then you may care to delete the user's profile image and all other assets uploaded by / for that user.
<br ><br >
Before the snippet that deletes the images / files, you must add a check to </b>confirm current user's right to delete those assets</b>.  

* Once you delete the record,  you may want to set logic to <b>delete / manage its associated records</b>.  
<br ><b>Case 1:</b> If you delete a user from user's table then you may use MySQL's cascading feature to delete its associated records wherever user_id has been used as foreign key.
<br><b>Case 2:</b> Altenatively, you may consider to assign a new user to the assoicated records of user that is crrently being deleted. If there is a post table that stores all the posts from users then you may code functionality such that when admin delete the user then that user's posts must be assigned to another user before her record is deleted.
<br ><b>Case 3:</b> In some cases, you may want to prevent delete operation. For example, consider that you are working with 'Orders' module. You may want to prevent the delete operations on State, Country or Address that are associalted with the Pending Orders. 

* Finally, <b>show nice looking message</b> confirming the successful completion of the delete operations.


