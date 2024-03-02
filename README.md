# Apex-Validations

Emial Validation-
1 - Create a text item for email id.
2 - Right click the field and select Create Validation from the menu.
3 - Enter the name of your validation as by default it will be New like validate_email_id.
4 - Select Item matches Regular Expression from the Type drop down.
5 - In the next Item field select your field name you created for email (on which this validation is being created).
6 - Next Regular Expression field enter the following,

^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*\.(\w{2}|(com|co.in|in|net|org|edu|int|mil|gov|arpa|biz|aero|name|coop|info|pro|museum))$

Save and test and now validation should work.
