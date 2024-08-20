---
term: P2SH-P2WSH
---

P2SH-P2WSH означает *Pay to Script Hash - Pay to Witness Script Hash*. Это стандартная модель скрипта, используемая для установления условий расходования UTXO, также известного как "Вложенный SegWit".

P2SH-P2WSH был введен с реализацией SegWit в августе 2017 года. Этот скрипт описывает P2WSH, обернутый в P2SH. Он блокирует биткойны на основе хеша скрипта. Отличие от классического P2WSH заключается в том, что скрипт обернут в `redeemScript` классического P2SH.

Этот скрипт был создан при запуске SegWit для облегчения его принятия. Он позволяет использовать этот новый стандарт даже с сервисами или кошельками, которые еще не поддерживают SegWit нативно. Сегодня, таким образом, использование таких типов обернутых скриптов SegWit уже не очень актуально, поскольку большинство кошельков реализовали нативный SegWit. Адреса P2SH-P2WSH записываются с использованием кодировки `Base58Check` и всегда начинаются с `3`, как и любой адрес P2SH.