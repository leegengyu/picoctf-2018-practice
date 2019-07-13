# picoctf-2018-practice
This repository documents my attempts at solving various practices of PicoCTF 2018.

# Forensics Warmup 1
![](/screenshots/forensicsWarmUp1.jpg)
* Unzip the file (`flag.zip`), open `flag.jpg`: `picoCTF{welcome_to_forensics}`.
* On Linux, `file flag.zip` shows that it is Zip archive data. Run `unzip flag.zip`, and open `flag.jpg`.
![](/screenshots/forensicsWarmUp1_unzip.jpg)
![](/screenshots/forensicsWarmUp1_flag.jpg)

# Forensics Warmup 2
![](/screenshots/forensicsWarmUp2.jpg)
* Download the file (`flag.png`). I was able to open it using FastStone on Windows without any problem, but attempting to open it in Linux results in this error:
![](/screenshots/forensicsWarmUp2_error.jpg)
* Run `mv flag.png flag.jpeg` to rename `flag.png` to `flag.jpeg`, and open it: `picoCTF{extensions_are_a_lie}`.
![](/screenshots/forensicsWarmUp2_flag.jpg)
* Note: Renaming the file to `flag.jpg` works as well.

# General Warmup 1
![](/screenshots/generalWarmup1.jpg)
* To-be-filled-in.

# General Warmup 2
![](/screenshots/generalWarmup2.jpg)
* To-be-filled-in.

# General Warmup 3
![](/screenshots/generalWarmup3.jpg)
* To-be-filled-in.

# Resources
![](/screenshots/resources.jpg)
* Visit the [link](https://picoctf.com/resources), scroll to the bottom and find the flag `picoCTF{xiexie_ni_lai_zheli}`.
![](/screenshots/resources_flag.jpg)
* Fun fact: The flag is in Chinese, thanking you for visiting the page.

# Reversing Warmup 1
![](/screenshots/reversingWarmup1.jpg)
* `cd /problems/reversing-warmup-1_3_7c0eade7faf60ffe3485e12098e2a6c2`, `./run`, and we get the flag: `picoCTF{welc0m3_t0_r3VeRs1nG}`.

# Reversing Warmup 2
![](/screenshots/reversingWarmup2.jpg)
* Run `data:text;base64,dGg0dF93NHNfczFtcEwz` to get the flag `picoCTF{th4t_w4s_s1mpL3}`:
![](/screenshots/reversingWarmup2_flag.jpg)
* Credits to [Crazy Danish Hacker](https://www.youtube.com/watch?v=xhqUIfZlBxg&t=915s) from whom I learnt this.
* Alternatively, use an online base64 decoder such as this [one](https://www.base64decode.net/).

# Crypto Warmup 1
![](/screenshots/cryptoWarmup1.jpg)
* 

# Crypto Warmup 2
![](/screenshots/cryptoWarmup2.jpg)
* 

# grep 1
![](/screenshots/grep1.jpg)
* 