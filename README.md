# Apex-Validations

✔ Email Validation-
1 - Create a text item for email id.
2 - Right click the field and select Create Validation from the menu.
3 - Enter the name of your validation as by default it will be New like validate_email_id.
4 - Select Item matches Regular Expression from the Type drop down.
5 - In the next Item field select your field name you created for email (on which this validation is being created).
6 - Next Regular Expression field enter the following,

^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*\.(\w{2}|(com|co.in|in|net|org|edu|int|mil|gov|arpa|biz|aero|name|coop|info|pro|museum))$

Save and test and now validation should work.


✔ Password Validation-
Type-Function Body(returning Error text)
Language-PL/SQL
PL/SQL Function Body Returning Error Text-

BEGIN
IF 8 <= LENGTH(:P3_PASSWORD) AND  LENGTH(:P3_PASSWORD) <= 15  THEN
    IF REGEXP_LIKE(:P3_PASSWORD, '^.*[0-9]') THEN
 IF REGEXP_LIKE(:P3_PASSWORD, '^.*[a-z]', 'c') THEN
 IF REGEXP_LIKE(:P3_PASSWORD, '^.*[A-Z]', 'c') THEN
 IF REGEXP_LIKE(:P3_PASSWORD, '^.*[!@#$%^&*()_]', 'c') THEN
 RETURN '';
 ELSE
    RETURN 'Password has not one special character';
 END IF;
 ELSE
    RETURN 'Password has not one UpperCase';
 END IF;   
 ELSE
    RETURN 'Password has not one LowerCase';
 END IF;
 ELSE
    RETURN 'Password has not a numeric value';
 END IF; 
ELSE
RETURN 'Password Length Must be min 8 char and max 15 char
and your password length is'||' '||LENGTH(:P3_PASSWORD);
END IF;

END;

Help text-
1.Password Length must be 8 characters and not more than 15 characters.<br>
2.The password must have one numeric value.<br>
3.The password must have one LowerCase.<br>
4.The password must have one UpperCase.<br>
5.The password must have one  special character.
