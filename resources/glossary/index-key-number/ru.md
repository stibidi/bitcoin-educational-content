---
term: INDEX (KEY NUMBER)
---

В контексте HD-кошелька это относится к последовательному номеру, присвоенному дочернему ключу, сгенерированному из родительского ключа. Этот индекс используется в сочетании с родительским ключом и кодом цепочки родителя для детерминированного получения уникальных дочерних ключей. Это позволяет структурированно организовать и воспроизводимо генерировать множество пар дочерних ключей-братьев и сестер из одного и того же родительского ключа. Это 32-битное целое число, используемое в функции производного `HMAC-SHA512`. Таким образом, этот номер различает дочерние ключи-братья и сестры внутри HD-кошелька.