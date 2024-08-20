---
term: CIOH
---

Аббревиатура для "*Common Input Ownership Heuristic*", что переводится как "Эвристика общего владения входами". Это эвристика, используемая в области анализа цепочек Bitcoin, которая предполагает, что все входы транзакции принадлежат одному и тому же субъекту или пользователю. Наблюдая за публичными данными транзакции Bitcoin и обнаружив несколько входов, если нет никаких паттернов или другой информации, опровергающей это, можно предположить, что все входы этой транзакции принадлежали одному человеку (или субъекту).

Эту эвристику анализа открыл сам Сатоши Накамото, который обсуждает её в части 10 Белой книги:

> "Однако связь неизбежна при многоинпутовых транзакциях, которые неизбежно выявляют, что их входы принадлежали одному и тому же владельцу. Риск заключается в том, что если владелец ключа будет раскрыт, связи могут выявить другие транзакции, принадлежащие тому же владельцу." - Накамото, С. (2008). "Bitcoin: Система электронных денег одноранговой сети". Консультировано на https://bitcoin.org/bitcoin.pdf.

Даже сегодня CIOH остается основной эвристикой, используемой компаниями по анализу цепочек, наряду с повторным использованием адресов.

![](../../dictionnaire/assets/13.png)

> ► *На английском "CIOH" может быть переведено как "Common Input Ownership Heuristic".*