# Keysight CTF
**Category:** Pwn  

---

## Challenge Description

> This was my first real ctf challenge, and although it was probably the easiest challenge to win, I'm still very proud of it. I accidentally entered the challenge by stumbling upon the router used for the ctf, assuming it was free wifi. The challenge involved recovering a flag from a hidden text file that was hosted in an ssh server.

---

## Information Provided

-  No information was given about the location of the flag except for an ssh login.

---

## Enumeration & Recon

- Upon entering the server, I immediately ran the `help` command to see what was available. To my dismay, pretty much every command for directory navigation and file manipulation was disabled. The only commands that were notable were `printf`, `md5hash`, `printflag`, and `hash`.

---

## Exploitation

- Running the `printflag` command returned an input prompt asking for a password. I tried navigating around to find the password, but as mentioned earlier, all navigation commands were disabled. I then tried using the `hash` command to see if it would give me any clues about the password, and it revealed hidden files in the bin directory called `md5hash` and `printflag`. I assumed these were the binaries for the commands. I then used the `printf` command to dump the contents of the printflag binary into hex, which I then copied to my local machine and converted back to binary (`scp` was disabled). I then opened up the binary and found what looked to be a hash of the password. I assumed it was an an md5 hash, so I used an online md5 hash cracker to find the password, which was "cracked" After entering the password into the `printflag` command, I was rewarded with the flag.

---

## Solution

- Although I don't remember the exact flag, it was in the format of `KEYSIGHT{0h_$0_$w33t}`. Afterwards, a raffle was conducted among those who solved the challenge, and I won a Keysight case containing a digital multimeter, oscilloscope, and a custom Riscure PCB board for practicing hardware hacking!

---

## Lessons Learned

- Even though this was a simple challenge with an element of luck to win, there were still only 6 solves. I learned the value of persistence, as the challenge took me over 2 hours to complete, by far the longest out of any of the people who had solved it. There was a lot more trial and error than described here, and I was fumbling around in the dark for quite a while before I found the right path. All in all, the experience was very rewarding, and I'm even more motivated to continue learning more about CTFs and cybersecurity in general.
