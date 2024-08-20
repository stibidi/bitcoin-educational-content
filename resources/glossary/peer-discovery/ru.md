---
term: PEER DISCOVERY
---

Процесс, посредством которого узлы в сети Bitcoin соединяются с другими узлами для получения информации. Когда узел Bitcoin запускается в первый раз, он не имеет информации о других узлах в сети. Тем не менее, ему необходимо установить соединения для синхронизации с блокчейном, который имеет наибольшую накопленную работу. Для обнаружения этих пиров используются несколько механизмов в порядке приоритета:
* Узел начинает с консультации своего локального файла `peers.dat`, который хранит информацию о узлах, с которыми он ранее взаимодействовал. Если узел новый, этот файл будет пустым, и процесс перейдет к следующему шагу;
* В отсутствие информации в файле `peers.dat` (что нормально для вновь запущенного узла), узел выполняет DNS-запросы к DNS-сидам. Эти серверы предоставляют список IP-адресов предположительно активных узлов для установления соединений. Адреса DNS-сидов зашиты в код Bitcoin Core. Этот шаг обычно достаточен для завершения обнаружения пиров;
* Если DNS-сиды не отвечают в течение 60 секунд, узел может затем обратиться к сид-узлам. Это публичные узлы Bitcoin, перечисленные в статическом списке почти тысячи записей, интегрированных непосредственно в исходный код Bitcoin Core. Новый узел будет использовать этот список для установления первого соединения с сетью и получения IP-адресов других узлов;
* В крайне маловероятном случае, когда все предыдущие методы не удаются, оператор узла всегда имеет возможность вручную добавить IP-адреса узлов для установления первого соединения.