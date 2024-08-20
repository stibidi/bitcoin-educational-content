---
term: РЕСИНХРОНИЗАЦИЯ
---

Относится к явлению, при котором блокчейн подвергается изменению своей структуры из-за наличия конкурирующих блоков на одном и том же уровне. Это происходит, когда часть блокчейна заменяется другой цепочкой с большим количеством накопленной работы.

Эти ресинхронизации являются частью естественного функционирования Bitcoin, где разные майнеры могут находить новые блоки почти одновременно, тем самым разделяя сеть Bitcoin на две части. В таких случаях сеть может временно разделиться на конкурирующие цепочки. В конечном итоге, когда одна из этих цепочек накапливает больше работы, другие цепочки отвергаются узлами, и их блоки становятся так называемыми "устаревшими блоками" или "сиротскими блоками". Этот процесс замены одной цепочки другой называется ресинхронизацией.

![](../../dictionnaire/assets/9.png)

Ресинхронизации могут иметь различные последствия. Во-первых, если транзакция пользователя была подтверждена в блоке, который впоследствии оказывается отвергнутым, но эта транзакция не найдена в итоговой действительной цепочке, то его транзакция снова становится неподтвержденной. Поэтому рекомендуется всегда ждать по крайней мере 6 подтверждений, чтобы считать транзакцию действительно неизменной. После глубины в 6 блоков ресинхронизации настолько маловероятны, что вероятность их возникновения можно считать практически нулевой.

Кроме того, на глобальном уровне системы ресинхронизации подразумевают потерю вычислительной мощности майнеров. Действительно, когда происходит разделение, некоторые майнеры будут на цепочке `A`, а другие на цепочке `B`. Если цепочка `B` в конечном итоге отвергается во время ресинхронизации, то вся вычислительная мощность, задействованная майнерами на этой цепочке, по определению, теряется. Если ресинхронизаций в сети Bitcoin происходит слишком много, общая безопасность сети, следовательно, снижается. Это частично объясняет, почему увеличение размера блока или сокращение интервала между блоками (10 минут) может быть опасным.

> ► *Некоторые биткойнеры предпочитают использовать термин "сиротский блок" для обозначения устаревшего блока. Также, хотя это англицизм, в обиходе часто предпочитают использовать термин "реорганизация" или "реорг" вместо "ресинхронизация".*