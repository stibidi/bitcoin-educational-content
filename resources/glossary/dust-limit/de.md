---
term: DUST LIMIT
---

Bezieht sich auf den Schwellenwert in Sats, unterhalb dessen ein UTXO von einem Netzwerkknoten als "Staub" betrachtet wird. Dieser Schwellenwert ist Teil der Standardisierungsregeln, die unabhängig von jedem Knoten geändert werden können. In Bitcoin Core wird dieser Grenzwert durch eine spezifische Gebührenrate bestimmt, die standardmäßig auf 3.000 Sats pro virtuellem Kilobyte (Sats/kvB) festgelegt ist. Dieser Grenzwert zielt darauf ab, die Verbreitung von Transaktionen mit sehr kleinen Bitcoin-Beträgen einzuschränken. Tatsächlich impliziert ein als Staub qualifizierter UTXO, dass seine Nutzung ökonomisch nicht rational ist: Diesen UTXO auszugeben, würde mehr kosten, als ihn einfach aufzugeben. Wenn das Ausgeben von Staub nicht rational ist, deutet dies darauf hin, dass solche Ausgaben nur durch externe Anreize motiviert sein könnten, oft bösartiger Natur. Dies kann ein Problem darstellen, wenn ein bösartiger Akteur versucht, das Netzwerk mit Transaktionen, die winzige Beträge enthalten, zu sättigen, mit dem Ziel, die Betriebslast auf den Knoten zu erhöhen und möglicherweise zu verhindern, dass sie andere legitime Transaktionen verarbeiten. Um eine Analogie zu geben (wenn auch eine etwas holprige, gebe ich zu), es ist ein bisschen so, als würde jemand versuchen, einen Einkaufskorb von 100€ ausschließlich mit 1-Cent-Münzen zu bezahlen, um andere Kunden an der Kasse zu blockieren.