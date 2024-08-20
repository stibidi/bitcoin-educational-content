---
term: ADDR
---

Сетевое сообщение, ранее использовавшееся в Bitcoin для передачи адресов узлов, принимающих входящие соединения. Этот старый формат, ограниченный 128 битами на адрес, подходил только для адресов IPv6, IPv4 и Tor версии 2. С появлением новых протоколов, таких как Tor V3, и необходимостью лучшей масштабируемости для будущих сетевых протоколов, формат `addr` был заменен на `addrv2`, введенный в BIP155.