---
termo: BIP16
---

O BIP16 introduziu o conceito de *Pay-to-Script-Hash* (P2SH), que se traduz para "pagar para o hash do script". Inicialmente proposto em 2012 e ativado em 2013, o BIP16 tinha como objetivo simplificar o uso de transações que requerem scripts complexos, como transações multisignature, permitindo que os usuários pagassem a um hash do script necessário para gastar aqueles bitcoins em vez do próprio script. Essa inovação reduziu a quantidade de dados necessários na transação inicial, transferindo o ônus de fornecer o script completo para a parte que gastava os bitcoins. Isso também permitiu que o script fosse revelado apenas no momento em que os bitcoins eram gastos, em vez de no momento do recebimento. O BIP16 possui significado histórico, pois representa uma das primeiras grandes modificações no protocolo Bitcoin após a retirada de Nakamoto em 2011. Este BIP foi o centro de debates muito acalorados que levaram até mesmo Gavin Andresen, sucessor de Satoshi como o principal mantenedor, a tirar um período de licença. Existiam inúmeras outras propostas, e algumas estavam até próximas de ser ativadas em vez do BIP16.