<h1 align="center">
  <img src="https://github.com/senthilpoo10/badges/blob/main/badges/ft_ircm.png" width="200"/>
</h1>

<p align="center">
  <b><i>Internet Relay Chat Server</i></b><br>
  <i>"The original real-time chat protocol"</i>
</p>

<p align="center">
  <img alt="score" src="https://img.shields.io/badge/score-125%2F100-brightgreen" />
  <img alt="team" src="https://img.shields.io/badge/team-3%20members-yellow" />
  <img alt="time spent" src="https://img.shields.io/badge/time%20spent-150%20hours-blue" />
  <img alt="XP earned" src="https://img.shields.io/badge/XP%20earned-672-orange" />
<p align="center">
  <img alt="GitHub code size in bytes" src="https://img.shields.io/github/languages/code-size/coding-school-projects/ft_irc?color=lightblue" />
  <img alt="GitHub top language" src="https://img.shields.io/github/languages/top/coding-school-projects/ft_irc?color=blue" />
  <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/coding-school-projects/ft_irc?color=green" />
</p>

## 📚 About The Project

ft_irc is a 42 School project that implements an RFC-compliant IRC server in C++98. This server handles multiple concurrent clients using non-blocking I/O and supports standard IRC commands, channels, and operator privileges.

**Key Features:**
- Multi-client support with non-blocking I/O (poll/epoll)
- Standard IRC commands (NICK, USER, JOIN, PRIVMSG, etc.)
- Channel operations (TOPIC, MODE, KICK, INVITE)
- Operator privileges and channel modes
- Bonus: File transfer and bot integration

## 🏁 Getting Started

### 🛠️ Installation & Usage

1. Clone the repository:
```bash
git clone https://github.com/coding-school-projects/ft_irc.git
cd ft_irc
```

2. Compile the server:
```bash
make
```

3. Run the server:
```bash
./ircserv <port> <password>
# Example:
./ircserv 6667 mysecretpassword
```

4. Connect with an IRC client:
```bash
irssi -c 127.0.0.1 -p 6667 -w mysecretpassword
```

### 🧪 Testing Protocol

1. Basic connection test:
```bash
nc 127.0.0.1 6667
PASS mysecretpassword
NICK testuser
USER testuser 0 * :Test User
```

2. Channel operations test:
```bash
JOIN #test
PRIVMSG #test :Hello world!
TOPIC #test :New topic
MODE #test +i
```

3. Stress test (multiple clients):
```bash
for i in {1..10}; do
  irssi -c 127.0.0.1 -p 6667 -w mysecretpassword &
done
```

## 🧠 Technical Implementation

### Core Architecture
| Component | Implementation | Details |
|-----------|----------------|---------|
| **I/O Model** | poll() | Non-blocking socket operations |
| **Protocol** | TCP/IP | RFC 1459 compliant |
| **Commands** | 15+ implemented | Full channel management |
| **Parsing** | State machine | Handles partial commands |
| **Concurrency** | Single-threaded | Event-driven architecture |

### Implemented Commands
| Command | Description |
|---------|-------------|
| PASS | Connection password |
| NICK | Set nickname |
| USER | Set username |
| JOIN | Join/create channel |
| PART | Leave channel |
| PRIVMSG | Send message |
| NOTICE | Send notice |
| KICK | Remove user from channel |
| INVITE | Invite user to channel |
| TOPIC | Set channel topic |
| MODE | Change channel modes |
| QUIT | Disconnect from server |

## 📝 Evaluation Criteria

1. **Correctness**: RFC compliance and command support
2. **Performance**: Handles 50+ concurrent clients
3. **Robustness**: No crashes on invalid input
4. **Code Quality**: Clean C++98 implementation
5. **Bonus**: Additional features implemented

### 🧑‍💻 Peer Evaluations (3/3)

> **Peer 1**: " Awesome work! We went through all the tests and your server works really nicely. You seemed to consider all possible edge cases and no issues occurred, even when only partially sending messages or 'killing' connections unexpectedly. You could also explain your set up and approach to poll and fcntl really well and help me refresh my memories on this project:) once more, good job and good luck with the upcoming evals on this! "

> **Peer 2**: " "

> **Peer 3**: " "

