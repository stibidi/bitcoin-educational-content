---
termo: RICOCHET
---

Uma técnica que envolve a realização de múltiplas transações falsas para si mesmo para simular uma transferência de propriedade de bitcoins. Ricochet é usado para desfocar os detalhes que poderiam comprometer a fungibilidade de uma moeda Bitcoin. Por exemplo, se você realizar um coinjoin, sua moeda resultante será identificada como tal. Este rótulo de "_moeda de um coinjoin_" pode afetar a fungibilidade de um UTXO. Entidades reguladas, como plataformas de troca, podem recusar aceitar um UTXO que passou por um coinjoin, ou até mesmo exigir explicações de seu proprietário, com o risco de ter sua conta bloqueada ou seus fundos congelados. Em alguns casos, a plataforma pode até mesmo reportar seu comportamento às autoridades estaduais. É aqui que o método Ricochet entra em jogo. Para obscurecer o rastro deixado por um coinjoin, Ricochet executa quatro transações sucessivas onde o usuário transfere seus fundos para si mesmo em diferentes endereços. Após esta sequência de transações, a ferramenta Ricochet finalmente encaminha os bitcoins para seu destino final, como uma plataforma de troca. O objetivo é criar distância entre a transação original de coinjoin e o ato final de gasto. Desta forma, ferramentas de análise de cadeia provavelmente assumirão que houve uma transferência de propriedade após o coinjoin, e portanto, é desnecessário iniciar ações contra o emissor. O caso de uso mais comum para Ricochet ocorre quando é necessário ocultar a participação anterior em um coinjoin em um UTXO, especialmente para evitar ser alvo de políticas de AML/CTF de plataformas reguladas ou listas negras. A ferramenta Ricochet está disponível na Samourai Wallet.