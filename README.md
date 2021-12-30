# Pacman-and-UDP-Communication-Protocol
The protocol specification contains information on how one should implement an improved version of pacman including the ABNF grammar.
# Running the game
In the simplest method, one player’s computer acts as a “server” and the other
as a “client”. The server must run first, and then the client connects to the
server. Once the network connection has been established, there is no difference
between how the server and client behave.
To run the server:
python3 pacman.py -r -s -p <passwd>
The server pacman will start, will display its IP address on screen, and
will wait for the client to connect. Substitute a password of your choice for
<passwd>.
To run the client:
python3 pacman.py -r -c <ip_address> -p <passwd>
The IP address must be that of the server pacman, and <passwd> must be
the same one they chose. The password is there to give some minimal control
over who can connect to a server pacman.
You can then play multi-player pacman. If your pacman goes through the
tunnel, it appears on the screen of your opponent, and can eat the food, eat the
powerpills, eat frightened ghosts, and die. At present, the two pacmen do not
directly interact. They simply pass straight through each other.
Client-server mode is useful when both players are on the same local network,
or when the server is on a computer that is reachable from the public Internet,
rather than behind a firewall.
  
In pacman-server there is a simple relay server
that passes messages between two clients. You can run the relay server as:
python3 pacman_server.py
Once the server is running, two clients can both connect to the server:
python3 pacman.py -r -c <ip_address> -p <passwd>
Again, both clients much choose the same password to be connected to each
other. Many pairs of clients can all use the same server - only pairs of clients
using the same password will be connected to each other. The IP address must
be the address of the computer running the server.
You can run your own server on any computer that is reachable from your
clients. 
