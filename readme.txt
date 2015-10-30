~WHAT IS THIS?~~~~
What is this?! This is a firewall, for CMPUT 333's second assignment. Given two
unique clients (windows and a linux) I must manage the incoming and outgoing traffic.

Why? Because we cannot arbitrarily trust that the network will be safe. The firewall
is being put directly smack infront of the servers to act as a gate guardian to these
two clients. 




~MISC QUESTIONS~~~~

So this project may cause a lot of questions to arise...
I want to dispell these here!

#1: "What the hell is a .sh?"
This is going to be the file type for a shell script file.
Why a shell script file...? Because that is what I need to
run on the actual firewall itself. This is where I will be
putting into the firewall the actual rules it will abide!

~General commands I enjoy utilizing~~~~
#1: netstat -tupan
What will this do?

#2: chmod 7


~Notation used in the script~~~~
#1: #!/bin/sh
This is going to be utilized to actually make this shell script into an 
executable file.

#2: iptables --flush
This is used to remove all of my past rules, I just don't want to deal with
a massive horde of past rules. Just going to put this at the top so I don't need
to manage them all.

#3: "Why are the server IP's (all IP's I deal with) variables?"
Because I, as a human, would strongly prefer to deal with inserting
variables into the shellscript for the rules rather than massive IP addresses
(THAT I CAN EASILY MAKE A TYPO IN!). I would rather double check ONE line at the top.

#4: Defaults! Very very critical to this application.
Say I want to have a default policy of denying incoming access to everything that is NOT 
specified in some manner.

The command is as follows:
iptables --policy INPUT DROP
--policy dictates that the default policy for any incoming thing (that fails to go through
the chain at some point) is to drop it. 

#5: Drop, why DROP? Why not REJECT?
Because dropping the packet sends no information to a denied user about my server.
If I say, sent things by informing them that they were denied access this yields to them
more information than I care to give them (such as the fact that I am INDEED occupying the
particular IP address! As far as I want them to be aware is they aren'table to connect to me.
Put simply, whether I actively denied them or not is none of their business. 
Common practice is if they are not in my LAN (Local area network) then they should be dropped
and if they ARE in my LAN I should reject it to let them know- but that's because I care about
MY clients in MY LAN. 

As said here:
http://serverfault.com/questions/157375/reject-vs-drop-when-using-iptables

