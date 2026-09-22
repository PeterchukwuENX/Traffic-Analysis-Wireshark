Traffic Analysis: Normal Activity vs. a Port Scan

This one's about learning to actually read raw network traffic instead of just knowing the theory behind it. I captured everyday network activity with Wireshark, then ran an nmap scan against my own Ubuntu server on purpose, so I'd have a real side-by-side of what normal traffic looks like versus what a scan looks like in the packets themselves.

The server I scanned is the same one from my [hardening project](../linux-server-hardening) - so this also ended up showing me what my own firewall rules look like from the outside, not just from a config file.

What I did
- Started a Wireshark capture on Kali Linux
- Generated some normal traffic (browsing, SSHing into my server normally)
- Ran `nmap -sV` against my hardened Ubuntu server to scan its ports
- Stopped the capture and went through it to pick the scan traffic out from the normal traffic mixed in with it

What I was actually looking for
Not just "what does a scan look like," but genuinely being able to tell the two apart in a pile of mixed traffic - since that's closer to what reading real traffic is actually like. A SOC analyst isn't handed a clean, pre-sorted capture; they have to know what to look for in the middle of everything else.

Why I'm doing this
Part of my path toward a SOC analyst role. Reading traffic and telling normal activity apart from something worth flagging is one of the core, repeated skills in that job - this was my first real attempt at practicing it with actual packets instead of just descriptions of what an attack "would" look like.
