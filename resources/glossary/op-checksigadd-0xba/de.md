---
term: OP_CHECKSIGADD (0XBA)
---

Extrahiert die obersten drei Werte vom Stapel: einen `public key`, ein `CScriptNum` `n` und eine `Signatur`. Wenn die Signatur nicht der leere Vektor ist und nicht gültig ist, wird das Skript mit einem Fehler beendet. Wenn die Signatur gültig ist oder der leere Vektor (`OP_0`) ist, werden zwei Szenarien präsentiert:
* Wenn die Signatur der leere Vektor ist: Ein `CScriptNum` mit dem Wert von `n` wird auf den Stapel gelegt, und die Ausführung setzt sich fort;
* Wenn die Signatur nicht der leere Vektor ist und gültig bleibt: Ein `CScriptNum` mit dem Wert von `n + 1` wird auf den Stapel gelegt, und die Ausführung setzt sich fort.
Vereinfacht gesagt, führt `OP_CHECKSIGADD` eine Operation ähnlich wie `OP_CHECKSIG` durch, aber anstatt wahr oder falsch auf den Stapel zu legen, fügt es `1` zum zweiten Wert oben auf dem Stapel hinzu, wenn die Signatur gültig ist, oder lässt diesen Wert unverändert, wenn die Signatur den leeren Vektor darstellt. `OP_CHECKSIGADD` ermöglicht die Erstellung derselben Multisignatur-Richtlinien in Tapscript wie mit `OP_CHECKMULTISIG` und `OP_CHECKMULTISIGVERIFY`, jedoch auf eine weise, die stapelweise verifizierbar ist, was bedeutet, dass es den Suchprozess in der Verifizierung eines traditionellen Multisig entfernt und somit die Verifizierung beschleunigt, während es die Betriebslast auf den CPUs der Knoten reduziert. Dieser Opcode wurde ausschließlich für die Bedürfnisse von Taproot in Tapscript hinzugefügt.