---
term: BIP32
---

BIP32 ввел концепцию иерархического детерминированного кошелька (HD кошелек). Это предложение позволяет генерировать иерархию пар ключей из общего `master seed` (главного ключа), используя однонаправленные функции производства. Каждая сгенерированная пара ключей может сама быть родителем других дочерних ключей, таким образом формируя древовидную (иерархическую) структуру. Преимущество BIP32 заключается в том, что оно позволяет управлять множеством различных пар ключей, необходимо лишь сохранить один главный ключ для их воссоздания. Это нововведение заметно помогло бороться с проблемой повторного использования адресов, что серьезно для конфиденциальности пользователя. BIP32 также позволяет создавать подветвления внутри одного и того же кошелька для облегчения его управления.