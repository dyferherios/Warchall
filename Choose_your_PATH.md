## Choose your PATH 1
This is the level10 mini challenge found in /home/level/10/ on the warchall box.
You can view the source here.
### level 10
1- Use the cd command to navigate into the challenge repository.
```bash
  cd /home/level/10_choose_your_path
```
2- Execute the following command to redirect the solution to the personnal directory:
```bash
   ./charp "so & cat solution.txt > ~/s.txt"
```
- ./charp: Runs the program or script named "charp."
- "so": Provides a string as an argument to "charp."
- &: Indicates that "so" will run in the background.
- cat solution.txt > ~/s.txt: Displays the content of "solution.txt" and redirects it to a new file "s.txt" in the user's home directory.

3- Open the "s.txt" file in the home directory.
```bash
  cat ~/s.txt
```
