---
term: BARE-MULTISIG
---

Standard-Skriptmodell P2MS, das verwendet wird, um Ausgabebedingungen für ein UTXO festzulegen. Es ermöglicht das Sperren von Bitcoins mit mehreren öffentlichen Schlüsseln. Um diese Bitcoins auszugeben, muss eine Signatur mit einer vordefinierten Anzahl von zugehörigen privaten Schlüsseln bereitgestellt werden. Zum Beispiel erfordert ein `2/3` P2MS `3` öffentliche Schlüssel mit `3` zugehörigen geheimen privaten Schlüsseln. Um die mit diesem P2MS-Skript gesperrten Bitcoins auszugeben, muss eine Signatur mit mindestens `2` der `3` privaten Schlüssel erfolgen. Dies ist ein Schwellenwertsicherheitssystem. Dieses Skript wurde 2011 von Gavin Andresen erfunden, als er gerade die Wartung des Haupt-Bitcoin-Clients übernommen hatte. Heute wird P2MS nur noch am Rande von einigen Anwendungen genutzt. Die überwiegende Mehrheit der modernen Multisignaturen verwendet andere Skriptmodelle wie P2SH oder P2WSH. Im Vergleich dazu ist P2MS extrem trivial. Die öffentlichen Schlüssel, aus denen es besteht, werden bei Erhalt der Transaktion offenbart. Die Verwendung eines P2MS ist auch teurer als andere Multisignatur-Skripte.