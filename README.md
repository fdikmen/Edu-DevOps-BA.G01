# Edu-DevOps-BA.G01

**BA DevOps Eğitimi** · Grup 01

Bilgisayar mimarisi → ağ → Linux → DevOps yolculuğu için ders notları ve özetler.

---

## Modüller

| | Modül | Klasör | Notlar |
| :---: | --- | --- | --- |
| **01** | Computer Architecture | [`01-computer-architecture/`](01-computer-architecture/) | [README](01-computer-architecture/README.md) |
| **02** | Network | [`02-network/`](02-network/) | [README](02-network/README.md) |
| **03** | Linux | [`03-linux/`](03-linux/) | [README](03-linux/README.md) |
| **04** | DevOps | [`04-devops/`](04-devops/) | [README](04-devops/README.md) |

```text
01 Architecture  →  02 Network  →  03 Linux  →  04 DevOps
```

---

## Network

> Tam liste: [02-network/README.md](02-network/README.md) · Kahoot: [network-kahoot-arsiv.md](02-network/network-kahoot-arsiv.md)

| | | | | |
| --- | --- | --- | --- | --- |
| [01 · Temeller](02-network/Network01-ozet.md) | [02 · Bileşenler](02-network/Network02-ozet.md) | [03 · Kablosuz](02-network/Network03-ozet.md) | [04 · Ev ağı](02-network/Network04-ozet.md) | [05 · TCP/IP · OSI](02-network/Network05-ozet.md) |
| [06 · Media](02-network/Network06-ozet.md) | [07 · Access / MAC](02-network/Network07-ozet.md) | [08 · IPv4](02-network/Network08-ozet.md) | [09 · Unicast / Subnet](02-network/Network09-ozet.md) | [10 · IPv6](02-network/Network10-ozet.md) |
| [11 · DHCP](02-network/Network11-ozet.md) | [12 · Gateway / NAT](02-network/Network12-ozet.md) | [13 · ARP](02-network/Network13-ozet.md) | [14 · Segmentasyon](02-network/Network14-ozet.md) | [15 · TCP · UDP](02-network/Network15-ozet.md) |
| [16 · Uygulama](02-network/Network16-ozet.md) | [17 · Test araçları](02-network/Network17-ozet.md) | | | |

---

## Linux

> Tam liste: [03-linux/README.md](03-linux/README.md) · [LPIC-1 Objectives V5.0](https://wiki.lpi.org/wiki/LPIC-1_Objectives_V5.0)

### 101 — System Architecture

| Ders | Konu |
| --- | --- |
| [01 · Giriş](03-linux/01.101.Giris.md) | Sistemi önyükleme — Boot the system |
| [02 · Hardware](03-linux/02.101.1_Determine-and-Configure-Hardware-Settings.md) | `/sys`, `/proc`, `/dev`, `modprobe`, `lspci`, `lsusb` |
| [03 · Boot Part 1](03-linux/03.101.2_Part1_Linux_Boot_Process.md) | Firmware, POST, GRUB, initramfs, init/systemd |
| [04 · Boot Part 2](03-linux/04.101.2_Part2_Linux_Boot_Process.md) | `dmesg`, `journalctl`, kernel ring buffer, boot logları |
| [05 · Runlevels](03-linux/05.101.3_Part1_Runlevels_ve_Boot_Targets.md) | `systemctl isolate`, rescue/emergency, SysVinit |

### 102 — Linux Installation & Virtualization

| Ders | Konu |
| --- | --- |
| [06 · Virtualization Guest](03-linux/06.102.6.Linux-as-Virtualization-Guest-VM-Hypervisor-Containers-IaaS.md) | VM, hipervizör, konteyner, IaaS, klon / machine ID |
| [06 · Commands](03-linux/06.102.6_Linux-Commands-Used-in-This-Lesson.md) | 102.6 doğrulama ve machine ID komutları |

### 103 — GNU & Unix Commands

| Ders | Konu |
| --- | --- |
| [07 · Bash Env Vars](03-linux/18.103.1_Bash-Environment-Variables-PS1-export-PATH-and-Command-History.md) | `PS1`, `export`, `PATH`, komut geçmişi |
| [07 · Commands](03-linux/18.103.1_Linux-Commands-Used-in-This-Lesson.md) | 103.1 ders komutları |
| [08 · Streams / Pipe / Text](03-linux/19.103.2.LinuxStreams-Pipe-ViewingText-CatZcat-Less-More-Od-SelectingParts-Split-Head-Tail-Cut.md) | `cat`/`zcat`, `less`/`more`, `od`, `split`, `head`/`tail`, `cut` |
| [08 · Commands](03-linux/19.103.2_Linux-Commands-Used-in-This-Lesson.md) | 103.2 görüntüleme / seçme komutları |
| [09 · wc & Hash](03-linux/20.103.2.wc-Hash-Statistics-Meta-md5sum-sha256sum-sha512sum.md) | `wc`, hash, `md5sum`, `sha256sum`, `sha512sum` |
| [09 · Commands](03-linux/20.103.2_Linux-Commands-Used-in-This-Lesson.md) | 103.2 istatistik / hash komutları |
| [10 · File Management](03-linux/21.103.3.Basic-File-Management-Wildcard-ls-cp-mv-rm-find-tar-dd.md) | wildcard, `ls`/`cp`/`mv`/`rm`, `find`, `tar`, `dd` |
| [10 · Commands](03-linux/21.103.3_Linux-Commands-Used-in-This-Lesson.md) | 103.3 dosya yönetimi komutları |
| [11 · Streams / Redirects / Jobs](03-linux/22.103.4.Streams-Redirects-Pipes-tee-xargs-Jobs-fg-bg-nohup-kill.md) | yönlendirme, pipe, `tee`/`xargs`, `fg`/`bg`/`nohup`/`kill` |
| [11 · Commands](03-linux/22.103.4_Linux-Commands-Used-in-This-Lesson.md) | 103.4 / process yönetimi temel komutları |
| [12 · Process Monitoring](03-linux/23.103.5.Process-Monitoring-ps-pgrep-top-free-uptime-watch-screen-tmux.md) | `ps`/`top`/`pgrep`, `free`/`uptime`/`watch`, `screen`/`tmux` |
| [12 · Commands](03-linux/23.103.5_Linux-Commands-Used-in-This-Lesson.md) | 103.5 izleme ve multiplexer komutları |
| [13 · Process Priorities](03-linux/24.103.6.Process-Priorities-nice-renice-niceness.md) | `nice`, `renice`, niceness, process statuses, zombie |
| [13 · Commands](03-linux/24.103.6_Linux-Commands-Used-in-This-Lesson.md) | 103.6 öncelik komutları |
