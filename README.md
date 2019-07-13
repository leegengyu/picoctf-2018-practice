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
* `cd /problems/reversing-warmup-1_3_7c0eade7faf60ffe3485e12098e2a6c2`, `./run`, and we get the flag:
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
* To-be-added.

# grep 1
![](/screenshots/grep1.jpg)
* To-be-added.