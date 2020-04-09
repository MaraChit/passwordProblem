# passwordProblem

A password is considered strong if below conditions are all met: 
1.  It has at least 6 characters and at most 20 characters.  
2.  It must contain at least one lowercase letter, at least one uppercase letter, and at least one digit.  
3.  It must NOT contain three repeating characters in a row ("...aaa..." is weak, but "...aa...a..." is strong, assuming other conditions are met). 
Write an algorithm that takes a string s as input, and return the MINIMUM change required to make s a strong password. If s is already strong, return 0.  
Insertion, deletion or replace of any one character are all considered as one change

We presume the user will only use digits, uppercase and lowercase letters.
In order to have a minimum number of changes, there are 3 possibilities.
1) The users introduces a password that is too short. (which means at most 5 characters) If the password contains sequences of three identical characters, a new character will be introduced between the 2nd and the 3rd from the sequence. The character too be introduced depends on the number of digits, uppercase and lower case letters already existing in the password (the type of character that appeares less will be introduced). If there are no sequences left, if there are no digits, one digit will be added. If there are no uppercase letters, an uppercase letter will be added. If there are no lowercase letter, a lower case letter will be added. In the end, if the password still doesn't have the length = 6, random digits will be added.
2) The password introduced has at least 6 and at most 20 characters. If the password contains sequences of 3 identical characters, the 3rd one will be replaced ( again depending on the number of digits, uppercase and lower case letters already existing in the password;the type of character that appeares less will be replacing the 3rd element of the sequence). After that, we must check to have all 3 types of characters in the password, and in case there arent't, the must be added.
3) The user introduces a password that is too long. Then a new password of length 20 should be created from the given password and each sequence of this length will be checked like a normal size password. The sequence with the minimum number of changes will be selected.

The number of changes will be returned
