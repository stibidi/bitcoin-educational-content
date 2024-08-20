---
term: BIP44
---

Предложение по улучшению, которое вводит стандартную иерархическую структуру производных ключей для HD-кошельков. BIP44 базируется на принципах, установленных BIP32 для производства ключей, и на BIP43 для использования поля "purpose" (цель). Вводится пятиуровневая структура производства: `m / purpose' / coin_type' / account' / change / address_index`. Вот детали каждого уровня:
* `m /` указывает на мастер-ключ кошелька. Он уникален для кошелька и не может иметь соседей на том же уровне. Мастер-ключ напрямую производится из сида кошелька;
* `m / purpose' /` указывает на цель производства, которая помогает идентифицировать следуемый стандарт. Это поле описано в BIP43. Например, если кошелек следует стандарту BIP84 (SegWit V0), индекс будет `84'`;
* `m / purpose' / coin-type' /` указывает на тип криптовалюты. Это позволяет четко различать ветви, посвященные одной криптовалюте, от ветвей, посвященных другой криптовалюте в мультивалютном кошельке. Индекс, посвященный Биткойну, — `0'`;
* `m / purpose' / coin-type' / account' /` указывает номер счета. Этот уровень позволяет легко различать и организовывать кошелек на разные счета. Эти счета нумеруются начиная с `0'`. Расширенные ключи (`xpub`, `xprv`...) находятся на этом уровне;
* `m / purpose' / coin-type' / account' / change /` указывает на цепочку. Каждый счет, определенный на уровне 3, имеет две цепочки на уровне 4: внешнюю цепочку и внутреннюю цепочку (также называемую "change"). Внешняя цепочка производит адреса, предназначенные для публичного сообщения, то есть адреса, которые предлагаются нам, когда мы нажимаем на "получить" в программном обеспечении нашего кошелька. Внутренняя цепочка производит адреса, не предназначенные для публичного обмена, то есть в основном адреса для сдачи. Внешняя цепочка идентифицируется индексом `0`, а внутренняя цепочка - индексом `1`. Вы заметите, что с этого уровня мы больше не выполняем усиленное производство, а обычное (нет апострофа). Благодаря этому механизму мы способны производить все дочерние публичные ключи из их `xpub`;
* `m / purpose' / coin-type' / account' / change / address-index` просто указывает номер получающего адреса и его пару ключей, чтобы отличить его от его собратьев на том же уровне на той же ветви. Например, первый произведенный адрес имеет индекс `0`, второй адрес - индекс `1` и так далее...
Например, если мой получающий адрес имеет путь производства `m / 86' / 0' / 0' / 0 / 5`, мы можем вывести следующую информацию:
* `86'` указывает, что мы следуем стандарту производства BIP86 (Taproot или SegWitV1);
* `0'` указывает, что это адрес Биткойна;
* `0'` указывает, что мы находимся на первом счете кошелька;
* `0` указывает, что это внешний адрес;
* `5` указывает, что это шестой внешний адрес этого счета.

![](../../dictionnaire/assets/18.png)