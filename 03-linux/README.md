# 03 – Linux

LPIC-1 odaklı Linux sistem yönetimi notları.

[← Depo README](../README.md) · [LPIC-1 Objectives V5.0](https://wiki.lpi.org/wiki/LPIC-1_Objectives_V5.0)

---

## Yol haritası

| Topic | Kapsam | Dersler |
| --- | --- | :---: |
| **101** · System Architecture | Donanım, boot, runlevels / targets | 01–05 |
| **102** · Installation & Virtualization | VM, hipervizör, konteyner, IaaS | 06 |
| **103** · GNU & Unix Commands | Shell, streams, dosya, process, Vim | 07–14 |
| **104** · Devices, Filesystems, FHS | Link, FHS, mount, izinler | 15–17 |
| **105** · Shell Environment & Scripting | export, source, alias, bashrc | 18 |

```text
101 Architecture  →  102 Virtualization  →  103 Commands  →  104 Filesystems  →  105 Shell
```

> **103.7** bu seride yok; **104.4** (disk quotas) LPIC-1 5.0’da kaldırıldı.

---

## 101 — System Architecture

| # | Kod | Ders | Özet |
| :---: | :---: | --- | --- |
| 1 | 101.2 | [Giriş](01.101.Giris.md) | Sistemi önyükleme — Boot the system |
| 2 | 101.1 | [Hardware Settings](02.101.1_Determine-and-Configure-Hardware-Settings.md) | `/sys`, `/proc`, `/dev`, `modprobe`, `lspci`, `lsusb` |
| 3 | 101.2 | [Boot Process · Part 1](03.101.2_Part1_Linux_Boot_Process.md) | Firmware, POST, GRUB, initramfs, init/systemd |
| 4 | 101.2 | [Boot Process · Part 2](04.101.2_Part2_Linux_Boot_Process.md) | `dmesg`, `journalctl`, kernel ring buffer, boot logları |
| 5 | 101.3 | [Runlevels & Boot Targets](05.101.3_Part1_Runlevels_ve_Boot_Targets.md) | `systemctl isolate`, rescue/emergency, SysVinit |

---

## 102 — Linux Installation & Virtualization

| # | Kod | Ders | Özet |
| :---: | :---: | --- | --- |
| 6 | 102.6 | [Linux as a Virtualization Guest](06.102.6.Linux-as-Virtualization-Guest-VM-Hypervisor-Containers-IaaS.md) | VM, hipervizör, konteyner, IaaS, klon / machine ID |
| — | 102.6 | [Commands Used in This Lesson](06.102.6_Linux-Commands-Used-in-This-Lesson.md) | 102.6 doğrulama ve machine ID komutları |

---

## 103 — GNU & Unix Commands

| # | Kod | Ders | Özet |
| :---: | :---: | --- | --- |
| 7 | 103.1 | [Bash Environment Variables](18.103.1_Bash-Environment-Variables-PS1-export-PATH-and-Command-History.md) | `PS1`, `export`, `PATH`, komut geçmişi |
| — | 103.1 | [Commands Used in This Lesson](18.103.1_Linux-Commands-Used-in-This-Lesson.md) | 103.1 ders komutları |
| 8 | 103.2 | [Streams, Pipe & Viewing Text](19.103.2.LinuxStreams-Pipe-ViewingText-CatZcat-Less-More-Od-SelectingParts-Split-Head-Tail-Cut.md) | `cat`/`zcat`, `less`/`more`, `od`, `split`, `head`/`tail`, `cut` |
| — | 103.2 | [Commands Used in This Lesson](19.103.2_Linux-Commands-Used-in-This-Lesson.md) | 103.2 görüntüleme / seçme komutları |
| 9 | 103.2 | [wc, Hash & Meta Bilgi](20.103.2.wc-Hash-Statistics-Meta-md5sum-sha256sum-sha512sum.md) | `wc`, hash, `md5sum`, `sha256sum`, `sha512sum` |
| — | 103.2 | [Commands Used in This Lesson](20.103.2_Linux-Commands-Used-in-This-Lesson.md) | 103.2 istatistik / hash komutları |
| 10 | 103.3 | [Basic File Management](21.103.3.Basic-File-Management-Wildcard-ls-cp-mv-rm-find-tar-dd.md) | wildcard, `ls`/`cp`/`mv`/`rm`, `find`, `tar`, `dd` |
| — | 103.3 | [Commands Used in This Lesson](21.103.3_Linux-Commands-Used-in-This-Lesson.md) | 103.3 dosya yönetimi komutları |
| 11 | 103.4 | [Streams, Redirects, Pipes & Jobs](22.103.4.Streams-Redirects-Pipes-tee-xargs-Jobs-fg-bg-nohup-kill.md) | yönlendirme, pipe, `tee`/`xargs`, `fg`/`bg`/`nohup`/`kill` |
| — | 103.4 | [Commands Used in This Lesson](22.103.4_Linux-Commands-Used-in-This-Lesson.md) | 103.4 / process yönetimi temel komutları |
| 12 | 103.5 | [Process Monitoring & Multiplexers](23.103.5.Process-Monitoring-ps-pgrep-top-free-uptime-watch-screen-tmux.md) | `ps`/`top`/`pgrep`, `free`/`uptime`/`watch`, `screen`/`tmux` |
| — | 103.5 | [Commands Used in This Lesson](23.103.5_Linux-Commands-Used-in-This-Lesson.md) | 103.5 izleme ve multiplexer komutları |
| 13 | 103.6 | [Process Priorities](24.103.6.Process-Priorities-nice-renice-niceness.md) | `nice`, `renice`, niceness, process statuses, zombie |
| — | 103.6 | [Commands Used in This Lesson](24.103.6_Linux-Commands-Used-in-This-Lesson.md) | 103.6 öncelik komutları |
| 14 | 103.8 | [Basic File Editing · Vim](25.103.8.Basic-File-Editing-Vim-Modes-Navigation-Edit-Search-Exit.md) | modlar, gezinme, düzenleme, arama, çıkış, `EDITOR`, `vimtutor` |
| — | 103.8 | [Commands Used in This Lesson](25.103.8_Linux-Commands-Used-in-This-Lesson.md) | 103.8 Vim / VI komutları |

---

## 104 — Devices, Linux Filesystems, FHS

| # | Kod | Ders | Özet |
| :---: | :---: | --- | --- |
| 15 | 104.6 / 104.7 | [Hard/Soft Links & FHS](29.104.6-104.7.Hard-Soft-Links-ln-FHS-PATH-locate-updatedb.md) | `ln`, FHS, `PATH`, `which`, `locate`, `updatedb` |
| — | 104.6 / 104.7 | [Commands Used in This Lesson](29.104.6-104.7_Linux-Commands-Used-in-This-Lesson.md) | 104.6 / 104.7 link ve dosya bulma komutları |
| 16 | 104.3 | [Control Mounting & Unmounting](27.104.3.Control-Mounting-Unmounting-mount-umount-UUID-fstab.md) | `mount`/`umount`, UUID, `/etc/fstab`, `blkid`/`lsblk` |
| — | 104.3 | [Commands Used in This Lesson](27.104.3_Linux-Commands-Used-in-This-Lesson.md) | 104.3 bağlama / ayırma komutları |
| 17 | 104.5 | [Permissions & Ownership](28.104.5.Manage-File-Permissions-Ownership-chmod-chown-SUID-SGID-Sticky-umask.md) | `chmod`/`chown`, SUID/SGID/sticky, `umask`, paylaşımlı dizin |
| — | 104.5 | [Commands Used in This Lesson](28.104.5_Linux-Commands-Used-in-This-Lesson.md) | 104.5 izin / sahiplik komutları |

---

## 105 — Shell Environment & Scripting

| # | Kod | Ders | Özet |
| :---: | :---: | --- | --- |
| 18 | 105.1 | [Customize Shell Environment](30.105.1.Customize-Shell-Environment-export-source-alias-PS1-bashrc.md) | `export`, `source`, `alias`, `PS1`, login/non-login shell, `.bashrc` |
| — | 105.1 | [Commands Used in This Lesson](30.105.1_Linux-Commands-Used-in-This-Lesson.md) | 105.1 shell ortamı komutları |

```text
01 Architecture  →  02 Network  →  03 Linux  →  04 DevOps
```
