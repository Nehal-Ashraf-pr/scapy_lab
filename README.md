# Scapy

[![Scapy unit tests](https://github.com/secdev/scapy/workflows/Scapy%20unit%20tests/badge.svg?event=push)](https://github.com/secdev/scapy/actions?query=workflow%3A%22Scapy+unit+tests%22+branch%3Amaster+event%3Apush) <!-- ignore_ppi -->
[![AppVeyor Build status](https://ci.appveyor.com/api/projects/status/os03daotfja0wtp7/branch/master?svg=true)](https://ci.appveyor.com/project/secdev/scapy/branch/master) <!-- ignore_ppi -->
[![Codecov Status](https://codecov.io/gh/secdev/scapy/branch/master/graph/badge.svg)](https://codecov.io/gh/secdev/scapy) <!-- ignore_ppi -->
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/30ee6772bb264a689a2604f5cdb0437b)](https://www.codacy.com/app/secdev/scapy) <!-- ignore_ppi -->
[![PyPI Version](https://img.shields.io/pypi/v/scapy.svg)](https://pypi.python.org/pypi/scapy/)
[![Python Versions](https://img.shields.io/pypi/pyversions/scapy.svg)](https://pypi.python.org/pypi/scapy/)
[![License: GPL v2](https://img.shields.io/badge/License-GPL%20v2-blue.svg)](LICENSE)
[![Join the chat at https://gitter.im/secdev/scapy](https://badges.gitter.im/secdev/scapy.svg)](https://gitter.im/secdev/scapy) <!-- ignore_ppi -->

Scapy is a powerful Python-based interactive packet manipulation program and
library.

It is able to forge or decode packets of a wide number of protocols, send them
on the wire, capture them, store or read them using pcap files, match requests
and replies, and much more. It is designed to allow fast packet prototyping by
using default values that work.

It can easily handle most classical tasks like scanning, tracerouting, probing,
unit tests, attacks or network discovery (it can replace `hping`, 85% of `nmap`,
`arpspoof`, `arp-sk`, `arping`, `tcpdump`, `wireshark`, `p0f`, etc.). It also
performs very well at a lot of other specific tasks that most other tools can't
handle, like sending invalid frames, injecting your own 802.11 frames, combining
techniques (VLAN hopping+ARP cache poisoning, VoIP decoding on WEP protected
channel, ...), etc.

Scapy supports Python 2.7 and Python 3 (3.4 to 3.8). It's intended to
be cross platform, and runs on many different platforms (Linux, OSX,
\*BSD, and Windows).

## Getting started

Scapy is usable either as a **shell** or as a **library**.
For further details, please head over to [Getting started with Scapy](https://scapy.readthedocs.io/en/latest/introduction.html), which is part of the documentation.

### Shell demo

![Scapy install demo](https://secdev.github.io/files/doc/animation-scapy-install.svg)

Scapy can easily be used as an interactive shell to interact with the network.
The following example shows how to send an ICMP Echo Request message to
`github.com`, then display the reply source IP address:

```python
sudo ./run_scapy
Welcome to Scapy
>>> p = IP(dst="github.com")/ICMP()
>>> r = sr1(p)
Begin emission:
.Finished to send 1 packets.
*
Received 2 packets, got 1 answers, remaining 0 packets
>>> r[IP].src
'192.30.253.113'
```

### Resources

The [documentation](https://scapy.readthedocs.io/en/latest/) contains more
advanced use cases, and examples.

Other useful resources:

-   [Scapy in 20 minutes](https://github.com/secdev/scapy/blob/master/doc/notebooks/Scapy%20in%2015%20minutes.ipynb)
-   [Interactive tutorial](https://scapy.readthedocs.io/en/latest/usage.html#interactive-tutorial) (part of the documentation)
-   [The quick demo: an interactive session](https://scapy.readthedocs.io/en/latest/introduction.html#quick-demo)
(some examples may be outdated)
-   [HTTP/2 notebook](https://github.com/secdev/scapy/blob/master/doc/notebooks/HTTP_2_Tuto.ipynb)
-   [TLS notebooks](https://github.com/secdev/scapy/blob/master/doc/notebooks/tls)

## [Installation](https://scapy.readthedocs.io/en/latest/installation.html)

Scapy works without any external Python modules on Linux and BSD like operating
systems. On Windows, you need to install some mandatory dependencies as
described in [the
documentation](http://scapy.readthedocs.io/en/latest/installation.html#windows).

On most systems, using Scapy is as simple as running the following commands:

```bash
git clone https://github.com/secdev/scapy
cd scapy
./run_scapy
```

To benefit from all Scapy features, such as plotting, you might want to install
Python modules, such as `matplotlib` or `cryptography`. See the
[documentation](http://scapy.readthedocs.io/en/latest/installation.html) and
follow the instructions to install them.

<!-- stop_ppi_description -->

# Scapy Lab

This repository contains a minimal subset of files from the [Scapy](https://github.com/secdev/scapy) project (version v2.4.5) for educational and experimental use.

### 📂 Included Components
- `examples/` — Jupyter notebooks from Scapy’s `doc/notebooks/` directory (modern usage examples)
- `run_scapy` & `run_scapy.bat` — launcher scripts for UNIX and Windows environments
- `LICENSE` — GPL-2.0 license from the original Scapy project
- `README.md` — this explanatory file

### ⚙️ Purpose
This repo serves as a lightweight environment to explore and test Scapy’s functionality without cloning the entire project.

### ⚠️ License & Attribution
All files are © the original Scapy authors under the **GNU GPL-2.0 license**.  
This repo is **not affiliated** with or endorsed by the official Scapy maintainers.  
For the full project, documentation, and updates, visit:  
👉 [https://github.com/secdev/scapy](https://github.com/secdev/scapy)

---

💡 *Maintained for academic demonstration and network security learning purposes only.*

