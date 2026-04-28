# Experiment 6: 

Title:
Exploring Virtual Terminals, Display Managers, X Clients, and Window Managers in Linux

## Aim
To study how Linux manages multiple sessions through virtual terminals and graphical environments.

## Theory
Linux supports 6+ virtual terminals (Ctrl+Alt+F1 to F6). Display manager (gdm/lightdm) handles GUI login. X Window System manages graphics.

## Commands Used
| Command              | Description |
|----------------------|-------------|
| tty                  | Current terminal |
| who / w              | Logged-in users |
| systemctl status gdm | Display manager status |
| echo $DISPLAY        | X session variable |
| ps -e \| grep X      | X processes |

## Step-by-Step Procedure
1. `tty`
2. Switch: Ctrl+Alt+F2 (login)
3. Switch back: Ctrl+Alt+F7
4. `who`
5. `systemctl status gdm`
6. `echo $DISPLAY`
7. `ps -e | grep X`

## Configuration Commands
tty
who
systemctl status gdm
echo $DISPLAY
ps -e | grep X

Outcomes: 
 ✓ Explain how Linux supports multi-user environments through virtual terminals. 
 ✓ Differentiate between display servers, display managers, and window managers. 
 ✓ Demonstrate switching between graphical and text-based sessions. 
 ✓ Identify running X clients and window managers in a Linux system. 
 ✓ Apply this knowledge in system administration tasks and cybersecurity operations 
such as session monitoring and privilege management. 

Result: 
 ❖ Successful identification and use of multiple virtual terminals (Ctrl + Alt + F1–F6). 
 ❖ Ability to switch between CLI and GUI environments. 
 ❖ Clear understanding of the interaction between: 
      • Display server 
      • Display manager
      • Window manager 
      • X clients 
❖ Practical knowledge of managing Linux sessions for troubleshooting and security 
monitoring. 
