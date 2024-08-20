---
term: SIGHASH_ALL (0X01)
---

Тип флага SigHash, используемый в подписях транзакций Bitcoin, чтобы указать, что подпись применяется ко всем компонентам транзакции. Используя `SIGHASH_ALL`, подписывающий охватывает все входы и все выходы. Это означает, что ни входы, ни выходы не могут быть изменены после подписания без её инвалидации. Этот тип флага SigHash является наиболее распространенным в транзакциях Bitcoin, поскольку он обеспечивает полную окончательность и целостность транзакции.