# Super SSH

```
Level: Easy
Author: Jeffery John

Description:
Using a Secure Shell (SSH) is going to be pretty important.
Can you ssh as ctf-player to titan.picoctf.net at port 58058 to get the flag?
You'll also need the password f3b61b38. If asked, accept the fingerprint with yes.
If your device doesn't have a shell, you can use: https://webshell.picoctf.org
If you're not sure what a shell is, check out our Primer: https://primer.picoctf.com/#_the_shell
```
Challenge link: [https://play.picoctf.org/practice/challenge/424](https://play.picoctf.org/practice/challenge/424)

## Solution

This challenge want us to use the ssh command. The [Linux man](https://linux.die.net/man/1/ssh) page is very useful.
But basically, a ssh command should look like this `ssh [optional flags are inserted here] [user@]hostname [command]`
where optional flags are port number, if custom username isnt specified then default will be used.
So the command is `ssh -p 58058 ctf-player@titan.picoctf.net` (each instance will have different port number), log into your assigned port and you will see the flag.
