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
* `passwd` has a one-liner: `root:x:0:0:root:/root:/bin/bash`.
* `shadow` also has a one-liner: `root:$6$HRMJoyGA$26FIgg6CU0bGUOfqFB0Qo9AE2LRZxG8N3H.3BK8t49wGlYbkFbxVFtGOZqVIq3qQ6k0oetDbn2aVzdhuVQ6US.:17770:0:99999:7:::`.
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

# pipe
![](/screenshots/pipe.jpg)
* Run `nc 2018shell.picoctf.com 48696 > comms.txt` to save the output of the program to a new file.
* Opening up `comms.txt` shows us 10001 lines of repetitive messages - I am going to guess that the messages were generated in a bulk of 10000 and the author inserted the flag somewhere in the middle.
![](/screenshots/pipe_netcatOutput.jpg)
* Run `cat comms.txt | grep picoCTF{` to get our flag.
* Alternatively, we do not really need to save the output as suggested by a challenge description - we can simply `grep` for it using `nc 2018shell.picoctf.com 48696 | grep picoCTF{`:
![](/screenshots/pipe_flag.jpg)
* The flag is `picoCTF{almost_like_mario_f617d1d7}`.

# Inspect Me
![](/screenshots/inspectme.jpg)
* Opening `http://2018shell.picoctf.com:47428` gives us:
![](/screenshots/inspectme_site.jpg)
* I opened the page source straightaway and found part 1/3 of the flag, which is `picoCTF{ur_4_real_1nspe`:
![](/screenshots/inspectme_flag1.jpg)
* It says that the author has been practicing 3 categories of web skills: HTML, CSS and JS. I am guessing that each of these categories will give us a part of the flag.
* Since we have already got the flag for HTML, we will move onto CSS. At the top of the page source, we see `mycss.css`.
* Opening up `mycss.css`, we find part 2/3 of the flag, which is `ct0r_g4dget_e96dd105}`:
![](/screenshots/inspectme_flag2.jpg)
* Note: It seems that at this point we can already piece together the two parts of the flag which we have got so far, and submit it - but let us just examine the last part for completeness sake.
* Opening up `myjs.js` (which is also obtained from the original page source), we see:
![](/screenshots/inspectme_flag3.jpg)
* Well, as expected, part 3/3 of the flag is nothing.
* The flag is `picoCTF{ur_4_real_1nspect0r_g4dget_e96dd105}`.

# grep 2
![](/screenshots/grep2.jpg)
* Login to the shell, enter `cd /problems/grep-2_4_06c2058761f24267033e7ca6ff9d9144/files`. Running `ls` tells us that there are 10 directories. Unlike `grep 1` which had a bunch of random data in one file, we have a bunch of directories here. Either way, doing it manually would take too long.
* So let us run `grep -r picoCTF{`, where `-r` tells the command to search the directories recursively:
![](/screenshots/grep2_flag.jpg)
* Note: The shell just kind of 'hangs' without the `-r` option. I think it is still searching because the shell does not freeze up but somehow it does not return a blank result even after awhile.
* The flag is `picoCTF{grep_r_and_you_will_find_036bbb25}`.

# Aca-Shell-A
![](/screenshots/acashella.jpg)
* So we are told to connect with `nc 2018shell.picoctf.com 42334`, and upon doing so, we find that we are faced with some sort of interactive shell:
![](/screenshots/acashella_nc.jpg)
* The shell is not configured properly as it does not run linux commands such as `id` and running `pwd` does not give a newline for our next input. Some options such as `-a` with `ls` do not work because of the restricted shell that we are in.
* The hint given to us when we `echo 'Help Me!'` is that we should enter the files that we can look at. This probably means that we should look into the couple of directories that we can see.
* Note: Part of the initial message says that "There is not much time left" - this means that the nc connection will close after a fixed period of time (around 2 minutes I think), probably because our interactions are not considered as direct ones with the connection.
* Exploring the directories, we see that only `executables` and `secret` directories contain something.
![](/screenshots/acashella_exploration.jpg)
* There is a file in `executables` called `dontLookHere`. The `file` command is disabled - we cannot identify the type of file that it is.
* It seems like it is an executable since it has the executable bits enabled and its directory name is also `executables`. However, trying to execute it results in an error message telling us that the file is not found - hmm.
![](/screenshots/acashella_dontLookHere.jpg)
* So let us move onto the next directory, which has a bunch of files in it. The prompt told us to get rid of the files - let us try that. I will start by removing all of the files starting with the name `intel` (removing all of the files starting with the name `profile` works too):
![](/screenshots/acashella_deletingSecretFiles.jpg)
* Next, we type in the echo statement that was given to us, and it says to run the script in the `executables` directory.
* We head back to the `executables` directory, and find that we are now able to run `dontLookHere`, which prints a whole screen of hexadecimal values. It says that we have to print the username to the screen - `whoami` does the trick:
![](/screenshots/acashella_dontLookHereSuccess.jpg)
* Next it says that we have to copy a file called TopSecret in tmp directory into the passwords folder: `cp /tmp/TopSecret passwords`. Heading to the passwords directory to view the file before our connection closes, we get our flag at the end of the paragraph of message!
* The flag is `picoCTF{CrUsHeD_It_d6f202f1}`.
* Here's where I did not have a successful run at the first go - I went into the passwords folder and ran `cp /tmp/TopSecret .` instead, and this did not work unfortunately.

# Client Side is Still Bad
![](/screenshots/clientSideIsStillBad.jpg)
* Accessing `http://2018shell.picoctf.com:8420/`, we see:
![](/screenshots/clientSideIsStillBad_homepage.jpg)
* Entering a random credential gives a pop-up box that says "Incorrect password".
* Opening up the page source, we see the flag!
![](/screenshots/clientSideIsStillBad_flag.jpg)
* As expected, when we piece together the flag and submit it as the credential, we get a pop-up box that says "You got the flag!".
* The flag is `picoCTF{client_is_bad_5e06ac}`.

# Desrouleaux
![](/screenshots/desrouleaux.jpg)
* There is a file `incidents.json` that is given to us - opening it up reveals 10 ticket entries with data:
![](/screenshots/desrouleaux_incidents.jpg)
* Next, we connect with `nc 2018shell.picoctf.com 14079` and find ourselves facing 3 questions, before the flag is given to us.
* The first and last question is the same across all attempts - but if you were to make another attempt because you got one of it wrong, you would probably be facing a different second question. No pressure on the time though - it did not timeout as fast as the one in Aca-Shell-A.
* For the most common source IP address, `122.231.138.129` also counts as an answer because `210.205.230.140` and it both occurred 3 times. `93.124.108.240` occurred twice and the rest only appeared once.
![](/screenshots/desrouleaux_flag.jpg)
* The third question was a little tricky at first and I had to slow my reading down to ascertain that I had a correct understanding of the question. Doing the math, we find that there are 7 unique file hashes. 10 (no same file was sent to the same destination IP address twice) divided by 7 gives us ~1.428, which gives us 1.43 when rounded up.
* The flag is `picoCTF{J4y_s0n_d3rUUUULo_4f3aae0d}`.

# Logon
![](/screenshots/logon.jpg)
* This is what we see when we load `http://2018shell.picoctf.com:37861/`:
![](/screenshots/logon_site.jpg)
* I tried to login with `admin:password` and it tells us that we cannot get in that way.
* Opening up the page source, we do not see much of any useful information lying around. There is an interesting comment describing what the different categories mean based on a set of colours, but not quite sure what this piece of information relates to at this point in time.
![](/screenshots/logon_pagesource.jpg)
* Next, I tried some random credentials and found out that no matter what we entered, we always managed to login, but we could not see the flag. The page source did not reveal anything once again.
* I searched around for what was in the browser storage and found some interesting cookies!
![](/screenshots/logon_pagesource.jpg)
* Changing the value of `admin` cookie from False to True, and refreshing the page afterwards gave us our flag:
![](/screenshots/logon_flag.jpg)
* The flag is `picoCTF{l0g1ns_ar3nt_r34l_a280e12c}`.

# Reading Between the Eyes
![](/screenshots/readingbetweentheeyes.jpg)
* Downloading the image file `husky.png` and opening it shows us a photo of a husky.
* I ran `strings husky.png | grep picoCTF{` initially, just to confirm that we were not being tested on `strings` again, but found no result as expected. Removing the `grep` portion and going through the results did not yield anything either - just a bunch of random characters.
* I did not click under the Hints section, but the challenge description in itself gave a big hint I suppose - `Stego-Saurus`. This should probably refer to steganography.
* I tried an online steganography, but it tells me that either there was nothing encoded within it, or that I had entered the wrong password (I left this field blank when asked for it).
* I tried several other means but to no avail - and after looking to those who had completed it, I realised that I had actually found the [correct online decoder](http://stylesuxx.github.io/steganography/)! I abanadoned it because my browser session hung for quite some time after pressing `Decode`. What was weirder is that this actually worked on my guest VM, while my main machine hung.
![](/screenshots/readingbetweentheeyes_flag.jpg)
* This [post](https://tcode2k16.github.io/blog/posts/picoctf-2018-writeup/forensics/) said that this problem is about using the Least Significant Bit algorithm for image steganography - the link he referenced was dead. Googling about this gave many research articles about this topic, but I found an [article by geeksforgeeks](https://www.geeksforgeeks.org/lsb-based-image-steganography-using-matlab/) being very helpful.
* Alternatively, we can also use `zsteg` according to [another person](https://github.com/PlatyPew/picoctf-2018-writeup/tree/master/Forensics/Reading%20Between%20the%20Eyes).
* **Learning point**: Think simple - I had always thought that steganography required a password, and there were tons of application out there using different methods to implement this. Without any more hints given in the challenge, it was very much probable that a simple form of steganography was used (which we found out eventually).
* The flag is `picoCTF{r34d1ng_b37w33n_7h3_by73s}`.

# Recovering From the Snap
![](/screenshots/recoveringfromthesnap.jpg)
* Clicking on `animals` results in `animals.dd` being downloaded. Running `file` against it tells us that it is a DOS/MBR boot sector.
* After seeing that the file is a boot sector, I tried to re-use my previous efforts [here](https://github.com/leegengyu/ctf-practice/blob/master/beginners-quest.md), but that did not quite work out because "NTFS signature is missing.".
* I clicked onto the "Hint" which says that we should be looking into recovering files that were deleted from the disk image.
* So off I went searching for a solution with the search string "recovering files from disk image kali". Besides a YouTube tutorial that popped up first, there was `foremost` - which is a "forensic program to recover lost files based on their headers, footers, and internal data structures"
* I scrolled down the Kali tools page for the usage example, and used the same command - `foremost -t doc,jpg,pdf,xls -i animals.dd`.
* The command finished execution almost instantly, and opening up the new directory `output`, and then into directory `jpg`, I opened each image file from the top of the list. Each photo was a high-resolution capture of an animal in an adorable manner. After reaching the 8th (and last) one, we got our flag:
![](/screenshots/recoveringfromthesnap_flag.jpg)
* Alternatives: There appears to be many ways to go about recovering the images based on what I read from how others solved this challenge, such as `binwalk`.
* **Learning point**: This was something new for me - I had definitely learnt something here about using a tool to recover pictures.
* The flag is `picoCTF{th3_5n4p_happ3n3d}`.

# Admin Panel
![](/screenshots/adminpanel.jpg)
* Downloading the traffic file gives us `data.pcap`. Traffic here refers to Wireshark traffic.
* Opening up the file in Wireshark, we find 78 packets captured, with only 3 protocols involved - ARP, HTTP and TCP.
* We do not have to manually search for the flag here - simply enter `picoCTF{` into the search fields - set the search type to be `String` and to search `Packet bytes`. There will only be 1 result, which contains our flag:
![](/screenshots/adminpanel.jpg)
* Note to self: I made a mistake earlier in the searching to seach under `Packet details`, having this mistaken idea that it would definitely be there. I was also thrown off-guard by another set of credentials that I had found `jimmy:p4ssw0rd`, where the password had turned out to be incorrect.
* The flag is `picoCTF{n0ts3cur3_894a6546}`.