---
term: PRUNED NODE
---

Узел с обрезкой, на английском "Pruned Node", является полным узлом, который выполняет обрезку блокчейна. Это включает в себя постепенное удаление старейших блоков после их должной проверки, чтобы сохранять только самые последние блоки. Лимит хранения указывается в файле `bitcoin.conf` через параметр `prune=n`, где `n` - это максимальный размер, занимаемый блоками в мегабайтах (MB). Если после этого параметра указано `0`, то обрезка отключена, и узел сохраняет блокчейн в полном объеме.

Узлы с обрезкой иногда рассматриваются как отличные от полных узлов. Использование узла с обрезкой может быть особенно интересно для пользователей, сталкивающихся с ограничениями по объему хранилища. В настоящее время полный узел должен иметь почти 600 ГБ только для хранения блокчейна. Узел с обрезкой может ограничить необходимый объем хранения до 550 МБ. Несмотря на то что он использует меньше места на диске, узел с обрезкой поддерживает уровень проверки и валидации, аналогичный полному узлу. Таким образом, узлы с обрезкой предлагают своим пользователям больше уверенности по сравнению с легкими узлами (SPV).