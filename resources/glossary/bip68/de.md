---
term: BIP68
---

Führte die Möglichkeit ein, relative Sperrzeiten durch das `nSequence` Feld zu nutzen. Dies erlaubt es einer Transaktion, eine relative Verzögerung anzugeben, bevor sie in einem Block aufgenommen werden kann. Diese Verzögerung kann in Form der Anzahl von Blöcken oder als ein Vielfaches von 512 Sekunden (d.h., in Echtzeit) definiert werden. Beachten Sie, dass diese neue Interpretation des `nSequence` Feldes nur gültig ist, wenn das `nVersion` Feld größer oder gleich `2` ist. Diese Interpretation des `nSequence` Feldes erfolgt auf der Ebene der Konsensregeln von Bitcoin. Die relative Zeitverriegelung setzt eine Verzögerung ab der Annahme einer vorherigen Transaktion, während die absolute Zeitverriegelung einen präzisen Moment angibt, vor dem die Transaktion nicht in einem Block aufgenommen werden kann. BIP68 wurde am 4. Juli 2016 über einen Soft Fork eingeführt, zusammen mit BIP112 und BIP113, aktiviert zum ersten Mal unter Verwendung der BIP9 Methode.