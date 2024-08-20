---
term: WITNESSSCRIPT
---

Скрипт, который определяет условия, при которых биткоины могут быть потрачены из UTXO P2WSH или P2SH-P2WSH. Обычно, `witnessScript` определяет условия мультиподписного кошелька в соответствии со стандартом SegWit. В этих стандартах скриптов `scriptPubKey` UTXO (выхода) содержит хеш `witnessScript`. Чтобы использовать этот UTXO в качестве входа в новой транзакции, владелец должен раскрыть оригинальный `witnessScript`, чтобы доказать его соответствие отпечатку в `scriptPubKey`. Затем `witnessScript` должен быть включен в `scriptWitness` транзакции, который также содержит элементы, необходимые для проверки скрипта, такие как подписи. Таким образом, `witnessScript` является аналогом `redeemScript` в транзакции P2SH для SegWit, с тем отличием, что он размещается в свидетельстве транзакции, а не в `scriptSig`.

> ► *Осторожно, `witnessScript` не следует путать с `scriptWitness`. В то время как `witnessScript` определяет условия расходования UTXO P2WSH или P2SH-P2WSH и является скриптом сам по себе, `scriptWitness` содержит данные свидетельства любого входа SegWit.*