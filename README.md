# Warchall






## Live RFI
One reason why I wanted the warchall box is to offer more realistic webhacking challenges.
You may now try the Live RFI challenge hosted on it.
### Level 15
Your objective is to retrieve the content of the `solution.php` file using RFI. Follow the steps below to complete the challenge.
1- Visit the following link in the web browser:
```
https://rfi.warchall.net/index.php?lang=solution.php
```
2- Try using the LFI vulnerability by appending the following payload to the URL:
```
https://rfi.warchall.net/index.php?lang=data:text/plain,%3C?php%20system(%22cat%20solution.php%22)?%3E%E3%80%82
```
The lang parameter of the URL is set to data:text/plain, the string <?php system("cat solution.php")?>. This parameter tells the PHP server to return the content of the PHP file solution.php as plain text.
The string <?php system("cat solution.php")?> is a PHP instruction that calls the function system(). The function system() executes a program or script as a child process. In this case, the program or script executed is the program cat. The program cat reads the contents of a file and displays them on the standard output.
3- After visiting the link above, please inspect the site :
```
  right click and choose the inspect option
```

