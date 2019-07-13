# picoctf-2018-practice
This repository documents my attempts at solving various practices of PicoCTF 2018.

# Forensics Warmup 1
![](/screenshots/forensicsWarmUp1.jpg)
* Unzip the file (`flag.zip`), open `flag.jpg`: `picoCTF{welcome_to_forensics}`.
* On Linux, `file flag.zip` shows that it is Zip archive data. Run `unzip flag.zip`, and open `flag.jpg`.
![](/screenshots/forensicsWarmUp1_unzip.jpg)
![](/screenshots/forensicsWarmUp1_flag.jpg)
* The flag is `picoCTF{welcome_to_forensics}`.

# Forensics Warmup 2
![](/screenshots/forensicsWarmUp2.jpg)
* Download the file (`flag.png`). I was able to open it using FastStone on Windows without any problem, but attempting to open it in Linux results in this error:
![](/screenshots/forensicsWarmUp2_error.jpg)
* Run `mv flag.png flag.jpeg` to rename `flag.png` to `flag.jpeg`, and open it: `picoCTF{extensions_are_a_lie}`.
![](/screenshots/forensicsWarmUp2_flag.jpg)
* Note: Renaming the file to `flag.jpg` works as well.
* The flag is `picoCTF{extensions_are_a_lie}`.

# General Warmup 1
![](/screenshots/generalWarmup1.jpg)
* Seeing 0x41 in hexadecimal made me recall of ASCII character A immediately because we would normally use many 'A's in buffer overflows to find out where we are.
* Alternatively, google for something like `hexadecimal to ascii table`, or use a converter like [RapidTables](https://www.rapidtables.com/convert/number/hex-to-ascii.html).
* The flag is `picoCTF{A}`.

# General Warmup 2
![](/screenshots/generalWarmup2.jpg)
* We could work this out as a form of mental arithmetic.
* Alternatively, use a converter like [RapidTables](https://www.rapidtables.com/convert/number/decimal-to-binary.html).
* The flag is `picoCTF{11011}`.

# General Warmup 3
![](/screenshots/generalWarmup3.jpg)
* We could work this out as a form of mental arithmetic: `3 * 16 + 13`.
* Alternatively, use a converter like [RapidTables](https://www.rapidtables.com/convert/number/hex-to-decimal.html).
* The flag is `picoCTF{61}`.

# Resources
![](/screenshots/resources.jpg)
* Visit the [link](https://picoctf.com/resources) and scan the page to find the flag. After scrolling to the bottom, we see the flag!
![](/screenshots/resources_flag.jpg)
* Fun fact: The flag is in Chinese, thanking you for visiting the page.
* The flag is `picoCTF{xiexie_ni_lai_zheli}`.

# Reversing Warmup 1
![](/screenshots/reversingWarmup1.jpg)
* Login to the shell, enter `cd /problems/reversing-warmup-1_3_7c0eade7faf60ffe3485e12098e2a6c2`, `./run`, and we get the flag:
![](/screenshots/reversingWarmup1_flag.jpg)
* The flag is `picoCTF{welc0m3_t0_r3VeRs1nG}`.

# Reversing Warmup 2
![](/screenshots/reversingWarmup2.jpg)
* Method 1 (preferred): Run `data:text;base64,dGg0dF93NHNfczFtcEwz` to get the flag:
![](/screenshots/reversingWarmup2_flag.jpg)
* Credits to [Crazy Danish Hacker](https://www.youtube.com/watch?v=xhqUIfZlBxg&t=915s) from whom I learnt this.
* Method 2: Use an online base64 decoder such as this [one](https://www.base64decode.net/).
* The flag is `picoCTF{th4t_w4s_s1mpL3}`.

# Crypto Warmup 1
![](/screenshots/cryptoWarmup1.jpg)
* This is what we see when we download and open `table.txt`:
![](/screenshots/cryptoWarmup1_table.jpg)
* We are given a message `llkjmlmpadkkc` (i.e. ciphertext) and a key `thisisalilkey`.
* I was not quite sure on how I should use the table, and googled for `message and key and table cipher`. The first few results told us that we were probably working with the `Vigenère Cipher`.
![](/screenshots/cryptoWarmup1_google.jpg)
* Fill in the `VIGENERE CIPHERTEXT` field (the first one), and select `KNOWING THE KEY` before filling it in. Press the `DECRYPT VIGENERE` to see the results on the left-hand-side of the page:
![](/screenshots/cryptoWarmup1_onlineDecode.jpg)
* Note: Under `Hints`, one of the points says that we have to "use all caps for the message".
* The flag is `picoCTF{SECRETMESSAGE}`.

# Crypto Warmup 2
![](/screenshots/cryptoWarmup2.jpg)
* ROT13 stands for "rotate by 13 places".
* According to this [Wikipedia page](https://en.wikipedia.org/wiki/ROT13), ROT13 "is a simple letter substitution cipher that replaces a letter with the 13th letter after it, in the alphabet".
* Our given string is `cvpbPGS{guvf_vf_pelcgb!}`.
* Using [rot13.com](https://rot13.com/), just paste the above string into the textfield on top, and it immediately tells us the decoded message:
![](/screenshots/cryptoWarmup2_flag.jpg)
* The flag is `picoCTF{this_is_crypto!}`.

# grep 1
![](/screenshots/grep1.jpg)
* Login to the shell, enter `cd /problems/grep-1_2_ee2b29d2f2b29c65db957609a3543418` and `cat file | grep picoCTF{`.
* Note: If you were to view the contents of `file` (e.g. using `cat`), you will be greeted by greeted by chunks of random characters, and as what the challenge description says, "this will be really obnoxious to look through by hand".
![](/screenshots/grep1_flag.jpg)
* The flag is `picoCTF{grep_and_you_will_find_42783683}`.

# netcat
![](/screenshots/netcat.jpg)
* Login to the shell, enter `nc 2018shell.picoctf.com 37721` and we get our flag!
![](/screenshots/netcat_flag.jpg)
* Note: We could also run the same command using our own machine - we would still get the same flag:
![](/screenshots/netcat_flagOwnVM.jpg)
* The flag is `picoCTF{NEtcat_iS_a_NEcESSiTy_0b4c4174}`.

# HEEEEEEERE'S Johnny!
![](/screenshots/hereIsJohnny.jpg)
* Login to the shell, and when we run `nc 2018shell.picoctf.com 35225`, we find ourselves being prompted for a username and password:
![](/screenshots/hereIsJohnny_initialConnect.jpg)
* Digression: Interestingly, the password is shown in plaintext - perhaps it was allowed for convenience.
* I suppose that we are suppose to get a set of credentials from `passwd` and `shadow`.
* `passwd` has a one-liner: root:x:0:0:root:/root:/bin/bash.
* `shadow` also has a one-liner: root:$6$HRMJoyGA$26FIgg6CU0bGUOfqFB0Qo9AE2LRZxG8N3H.3BK8t49wGlYbkFbxVFtGOZqVIq3qQ6k0oetDbn2aVzdhuVQ6US.:17770:0:99999:7:::.
* First part of the puzzle regarding the username is solved - `root`.
* From this [article](https://www.aychedee.com/2012/03/14/etc_shadow-password-hash-formats/), we understand that there are several algorithms supported by GNU/Linux, where the 'toughest' one is SHA512. Its hash is prefixed with `$6$`, which is exactly what we see in our `shadow` file.
* Run `unshadow passwd shadow > unshadowed.txt` to combine the 2 provided files and redirect them to a new file, according to [john's Kali page](https://tools.kali.org/password-attacks/john).
* After that, run `john unshadowed.txt`. Within a few seconds, we get the password `hellokitty`:
![](/screenshots/hereIsJohnny_johnCracking.jpg)
* With our set of credentials `root:hellokitty`, let us re-attempt a login using the given `nc` command:
![](/screenshots/hereIsJohnny_flag.jpg)
* The flag is `picoCTF{J0hn_1$_R1pp3d_99c35524}`.

# strings
![](/screenshots/strings.jpg)
* Login to the shell, and run `cd /problems/strings_0_bf57524acf558aca2081eb97ece8e2ee`. When we attempt to run the program, we got an advice to use `strings` instead (and did not get our flag):
![](/screenshots/strings_attemptExecution.jpg)
* When we attempt to view the contents of `strings` (e.g. using `cat` or `strings`), we get a seemingly never-ending file of random text (similar to `grep 1`, but this time, the random text is separated by a newline at regular junctures). Unlike the earlier challenge, CTRL + C (SIGINT) does not seem to stop the never-ending loading of `strings` - I had to resort to reloading the shell by refreshing the page.
* Run `strings strings | grep picoCTF{`, and we get our flag!
![](/screenshots/strings_flag.jpg)
* The flag is `picoCTF{sTrIngS_sAVeS_Time_c09b1444}`.
* Note: Attempting to run the program on a 32-bit machine will result in the error "32-bit machine: cannot execute binary file: Exec format error". Run `uname -m` to check if your Linux is running on 32-bit or 64-bit. Running `file strings` would also tell us that the file is a "ELF 64-bit LSB executable".

* 