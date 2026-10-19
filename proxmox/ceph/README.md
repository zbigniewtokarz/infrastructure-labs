# Proxmox VE + Ceph — test awarii węzła

## Cel testu

Sprawdzenie zachowania trzywęzłowego klastra Proxmox VE
z rozproszoną pamięcią masową Ceph podczas awarii jednego
z węzłów.

## Zakres testu

- Automatyczne uruchomienie VM na innym węźle przez Proxmox HA
- Reakcja Ceph na utratę jednego OSD
- Przejście OSD ze stanu down/in do down/out
- Zachowanie klastra w stanie degradacji
- Weryfikacja dostępności maszyny wirtualnej
- Kontrola integralności danych za pomocą SHA-256

## Wynik

Mechanizm Proxmox HA automatycznie uruchomił maszynę
wirtualną na innym węźle.

Ceph kontynuował pracę w stanie degradacji.
Po około 600 sekundach niedostępny OSD został
automatycznie oznaczony jako out.

Po około 5 godzinach potwierdzono dostępność maszyny,
zgodność sumy kontrolnej pliku oraz możliwość zapisu danych.

## Dokumentacja

[Raport z testu Ceph (PDF)](Ceph-test-3-node.pdf)
