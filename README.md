# Edu-DevOps-BA.G01

**BA DevOps Eğitimi** · Grup 01

Bilgisayar mimarisi → ağ → Linux → DevOps yolculuğu için ders notları ve özetler.

---

## Modüller

| | Modül | Klasör | Durum |
| :---: | --- | --- | --- |
| **01** | Computer Architecture | [`01-computer-architecture/`](01-computer-architecture/) | [README](01-computer-architecture/README.md) · henüz içerik yok |
| **02** | Network | [`02-network/`](02-network/) | [README](02-network/README.md) · 17 özet |
| **03** | Linux | [`03-linux/`](03-linux/) | [README](03-linux/README.md) · LPIC-1 (101–105) · 18 ders |
| **04** | DevOps | [`04-devops/`](04-devops/) | [README](04-devops/README.md) · henüz içerik yok |

```text
01 Architecture  →  02 Network  →  03 Linux  →  04 DevOps
```

---

## Network

Slayt özetleri ve Kahoot arşivi: [02-network/README.md](02-network/README.md) · [network-kahoot-arsiv.md](02-network/network-kahoot-arsiv.md)

| | | | | |
| --- | --- | --- | --- | --- |
| [01 · Temeller](02-network/Network01-ozet.md) | [02 · Bileşenler](02-network/Network02-ozet.md) | [03 · Kablosuz](02-network/Network03-ozet.md) | [04 · Ev ağı](02-network/Network04-ozet.md) | [05 · TCP/IP · OSI](02-network/Network05-ozet.md) |
| [06 · Media](02-network/Network06-ozet.md) | [07 · Access / MAC](02-network/Network07-ozet.md) | [08 · IPv4](02-network/Network08-ozet.md) | [09 · Unicast / Subnet](02-network/Network09-ozet.md) | [10 · IPv6](02-network/Network10-ozet.md) |
| [11 · DHCP](02-network/Network11-ozet.md) | [12 · Gateway / NAT](02-network/Network12-ozet.md) | [13 · ARP](02-network/Network13-ozet.md) | [14 · Segmentasyon](02-network/Network14-ozet.md) | [15 · TCP · UDP](02-network/Network15-ozet.md) |
| [16 · Uygulama](02-network/Network16-ozet.md) | [17 · Test araçları](02-network/Network17-ozet.md) | | | |

---

## Linux

LPIC-1 odaklı sistem yönetimi. Tam ders listesi: [03-linux/README.md](03-linux/README.md) · [LPIC-1 Objectives V5.0](https://wiki.lpi.org/wiki/LPIC-1_Objectives_V5.0)

| Topic | Kapsam | Dersler |
| --- | --- | :---: |
| **101** · System Architecture | Donanım, boot process, runlevels / boot targets | 01–05 |
| **102** · Installation & Virtualization | VM, hipervizör, konteyner, IaaS | 06 |
| **103** · GNU & Unix Commands | Shell, streams, dosya yönetimi, process’ler, Vim | 07–14 |
| **104** · Devices, Filesystems, FHS | Link, FHS, mount / umount, izinler / sahiplik | 15–17 |
| **105** · Shell Environment | `export`, `source`, alias, `.bashrc`, shell türleri | 18 |

```text
101 Architecture  →  102 Virtualization  →  103 Commands  →  104 Filesystems  →  105 Shell
```

| | | | | |
| --- | --- | --- | --- | --- |
| [01 · Giriş / Boot](03-linux/01.101.Giris.md) | [02 · Donanım](03-linux/02.101.1_Determine-and-Configure-Hardware-Settings.md) | [03 · Boot · 1](03-linux/03.101.2_Part1_Linux_Boot_Process.md) | [04 · Boot · 2](03-linux/04.101.2_Part2_Linux_Boot_Process.md) | [05 · Runlevels](03-linux/05.101.3_Part1_Runlevels_ve_Boot_Targets.md) |
| [06 · Virtualization](03-linux/06.102.6.Linux-as-Virtualization-Guest-VM-Hypervisor-Containers-IaaS.md) | [07 · Bash / PATH](03-linux/18.103.1_Bash-Environment-Variables-PS1-export-PATH-and-Command-History.md) | [08 · Streams / Text](03-linux/19.103.2.LinuxStreams-Pipe-ViewingText-CatZcat-Less-More-Od-SelectingParts-Split-Head-Tail-Cut.md) | [09 · wc / Hash](03-linux/20.103.2.wc-Hash-Statistics-Meta-md5sum-sha256sum-sha512sum.md) | [10 · Dosya yönetimi](03-linux/21.103.3.Basic-File-Management-Wildcard-ls-cp-mv-rm-find-tar-dd.md) |
| [11 · Redirect / Jobs](03-linux/22.103.4.Streams-Redirects-Pipes-tee-xargs-Jobs-fg-bg-nohup-kill.md) | [12 · Process izleme](03-linux/23.103.5.Process-Monitoring-ps-pgrep-top-free-uptime-watch-screen-tmux.md) | [13 · nice / renice](03-linux/24.103.6.Process-Priorities-nice-renice-niceness.md) | [14 · Vim](03-linux/25.103.8.Basic-File-Editing-Vim-Modes-Navigation-Edit-Search-Exit.md) | [15 · Link / FHS](03-linux/29.104.6-104.7.Hard-Soft-Links-ln-FHS-PATH-locate-updatedb.md) |
| [16 · mount / fstab](03-linux/27.104.3.Control-Mounting-Unmounting-mount-umount-UUID-fstab.md) | [17 · İzinler](03-linux/28.104.5.Manage-File-Permissions-Ownership-chmod-chown-SUID-SGID-Sticky-umask.md) | [18 · Shell ortamı](03-linux/30.105.1.Customize-Shell-Environment-export-source-alias-PS1-bashrc.md) | | |

> **Not:** **103.7** ve **104.4** (quotas, LPIC-1 5.0’da yok) bu seride işlenmiyor. Her ders için ayrı [komut tabloları](03-linux/README.md) mevcuttur.
