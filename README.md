## Hide-current-working-directory-in-terminal


##### To change it for the current terminal instance only 
Just enter below command in terminal in press enter
```sh
PS1='\u:\W\$ '
```
![1](https://cloud.githubusercontent.com/assets/11232063/23983187/9d1a0d88-0a38-11e7-8224-0d174b73ddf9.png)
```sh
PS1='\u@\h: '
```
![2](https://cloud.githubusercontent.com/assets/11232063/23983234/f102f28e-0a38-11e7-9faa-600aae4ca1c9.png)

```sh
PS1='> '
```
![3](https://cloud.githubusercontent.com/assets/11232063/23983315/54e6df54-0a39-11e7-89c9-c6628bb59474.png)
##### To change it "permanently"
In your ~/.bashrc, find the following section:
```sh
if [ "$color_prompt" = yes ]; then
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
else
    PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
fi
```
Remove the @\h, and replace the \w with an uppercase \W, so that it becomes:
```sh
if [ "$color_prompt" = yes ]; then
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u\[\033[00m\]:\[\033[01;34m\]\W\[\033[00m\]\$ '
else
    PS1='${debian_chroot:+($debian_chroot)}\u:\W\$ '
fi
```
Save, exit, close terminal and start another to see the result.

#### More
http://askubuntu.com/a/145626/353374

https://www.cyberciti.biz/tips/howto-linux-unix-bash-shell-setup-prompt.html

http://askubuntu.com/a/16729/353374
