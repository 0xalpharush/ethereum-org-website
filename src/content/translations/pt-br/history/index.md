---
title: Histórico e bifurcações do Ethereum
description: Uma história da blockchain Ethereum, incluindo marcos importantes, versões e bifurcações.
lang: pt-br
sidebarDepth: 1
---

# A história do Ethereum {#the-history-of-ethereum}

Uma linha do tempo dos principais marcos, bifurcações e atualizações da blockchain Ethereum.

<ExpandableCard title="O que são bifurcações?" contentPreview="Changes to the rules of the Ethereum protocol which often include planned technical upgrades.">

Bifurcações ocorrem quando grandes atualizações ou alterações técnicas precisam ser feitas na rede, que geralmente são decorrentes de [Propostas de Melhoria do Ethereum (EIPs)] (/ eips /) e alteram as "regras" do protocolo.

Quando é necessário atualizar um software tradicional, com controle centralizado, a empresa apenas publica uma nova versão para o usuário final. Blockchains funcionam de maneira diferente porque não há propriedade centralizada. [Clientes Ethereum](/developers/docs/nodes-and-clients/) devem atualizar seu software para implementar as novas regras da bifurcação. Além disso, os criadores de bloco (mineradores em um mundo com prova de trabalho, validadores em um mundo com prova de participação) e nós devem criar blocos e validá-los conforme as novas regras. [Mais sobre mecanismos de consenso](/developers/docs/consenus-mechanisms/)

Essas mudanças de regra podem criar uma divisão temporária na rede. Novos blocos podem ser produzidos conforme as novas regras ou as antigas. Geralmente, as bifurcações são acordadas antes do tempo, para que os clientes adotem as mudanças de uníssono e para que a bifurcação com as melhorias se torne a cadeia principal. No entanto, em casos raros, desacordos sobre as bifurcações podem fazer com que a rede seja dividida permanentemente. Esse foi notadamente o caso para a criação do Ethereum Classic com a [bifurcação DAO] (#dao-fork).

</ExpandableCard>

Procurando por futuras melhorias de protocolo? [Saiba mais sobre as próximas atualizações do Ethereum](/upgrades/).

<Divider />

## 2023 {#2023}

### Shanghai (_planejado_) {#shanghai}

<NetworkUpgradeSummary name="shanghai" />

#### Resumo {#shanghai-summary}

A atualização Shangai traz saques de participação para a camada de execução. Em conjunto com a atualização Capella, isso permite que os blocos aceitem operações de retirada, permitindo aos participantes retirar seu ETH da Beacon Chain para a camada de execução.

<ExpandableCard title="EIPs da Shanghai" contentPreview="Official improvements included in this upgrade.">

- [EIP-3651](https://eips.ethereum.org/EIPS/eip-3651) – _Inicia o endereço `COINBASE`_
- [EIP-3855](https://eips.ethereum.org/EIPS/eip-3855) – \_Nova instrução `PUSH0`
- [EIP-3860](https://eips. thereum.org/EIPS/eip-3860) – _Limite e medidor initcode_
- [EIP-4895](https://eips.ethereum.org/EIPS/eip-4895) – _Saques por push da Beacon Chain como operações_

</ExpandableCard>

- [Leia a especificação de atualização Shangai](https://github.com/ethereum/execution-specs/blob/master/network-upgrades/mainnet-upgrades/shanghai.md)

---

### Capella (_planejado_) {#capella}

<NetworkUpgradeSummary name="capella" />

#### Resumo {#capella-summary}

A atualização Capella é a terceira maior atualização para a camada de consenso (Beacon Chain), que permite saques de participação. Capella ocorrerá em simultâneo com a atualização Shangai, que ocorre na camada de execução para habilitar a funcionalidade de retirada em sincronia entre elas.

Esta atualização em camada de consenso traz a habilidade para os participantes que não forneceram credenciais de saque com seu depósito inicial de fazer isso, permitindo assim os saques.

A atualização também fornece a funcionalidade de varredura de contas automáticas, que processa continuamente contas de validador para quaisquer pagamentos de recompensas disponíveis ou saques completos.<!-- - \[More on staking withdrawals\](/staking/withdrawals/). -->- [Leia a especificação da atualização Capella](https://github.com/ethereum/consensus-specs/blob/dev/specs/capella/)

<Divider />

## 2022 {#2022}

### Paris (A Fusão) {#paris}

<NetworkUpgradeSummary name="paris" />

#### Resumo {#paris-summary}

A atualização Paris foi desencadeada pela cadeira de blocos de prova de trabalho, passando uma [dificuldade total final](/glossary/#terminal-total-difficulty) de 58 750 000 000 000 000 000 000. Isso aconteceu no bloco 15537393, em 15 de setembro de 2022, iniciando a atualização Paris para o próximo bloco. Paris foi a transição da [Fusão](/upgrades/merge/) – seu maior recurso era desativar o algoritmo de mineração da [prova de trabalho](/developers/docs/consensus-mechanisms/pow) e a lógica de consenso associada e ativar a [prova de participação](/developers/docs/consensus-mechanisms/pos) no lugar dele. Paris em si foi uma atualização para os [clientes de execução](/developers/docs/nodes-and-clients/#execution-clients) (equivalente à Bellatrix na camada de consenso) que permitiu que eles recebessem instruções de seus [clientes de consenso](/developers/docs/nodes-and-clients/#consensus-clients) conectados. Isso exigiu um novo conjunto de métodos internos da API, coletivamente conhecido como [API do mecanismo](https://github.com/ethereum/execution-apis/blob/main/src/engine/common.md), a ser ativado. Esta foi, indiscutivelmente, a atualização mais significativa na história do Ethereum desde o [Homestead](#homestead)!

- [Leia a especificação de atualização Paris](https://github.com/ethereum/execution-specs/blob/master/network-upgrades/mainnet-upgrades/paris.md)

<ExpandableCard title="EIPs da Paris" contentPreview="Official improvements included in this upgrade.">

– [EIP-3675](https://eips.ethereum.org/EIPS/eip-3675) – _Atualização do consenso para prova de participação_
– [EIP-4399](https://eips.ethereum.org/EIPS/eip-4399) – _Substituir o opcode DIFFICULTY por PREVRANDAO_

</ExpandableCard>

---

### Bellatrix {#bellatrix}

<NetworkUpgradeSummary name="bellatrix" />

#### Resumo {#bellatrix-summary}

A atualização Bellatrix foi a segunda atualização agendada para a [Cadeia de Sinalização](/upgrades/beacon-chain), preparando a cadeia para [A Fusão](/upgrades/merge/). Ela traz penalidades ao validador para seus valores totais por inatividade e ofensas sancionáveis. Bellatrix também inclui uma atualização nas regras de escolha de bifurcações para preparar a cadeia para A Fusão e a transição do último bloco de prova de trabalho para o primeiro bloco de prova de participação. Isso inclui informar os clientes de consenso sobre o [dificuldade total do terminal](/glossary/#terminal-total-difficulty) de 58750000000000000000000.

- [Leia a especificação da atualização Bellatrix](https://github.com/ethereum/consensus-specs/tree/dev/specs/bellatrix)

---

### Gray Glacier {#gray-glacier}

<NetworkUpgradeSummary name="grayGlacier" />

#### Resumo {#gray-glacier-summary}

A atualização Gray Glacier atrasou a ["bomba de dificuldade"](/glossary/#difficulty-bomb) por 3 meses. Esta é a única mudança introduzida nessa atualização, sendo parecida com a natureza das atualizações [Arrow Glacier](#arrow-glacier) e [Muir Glacier](#muir-glacier). Mudanças semelhantes foram realizadas nas implementações de rede [Byzantium](#byzantium), [Constantinople](#constantinople) e [London](#london).

- [Blog da EF – Comunicado da atualização Gray Glacier](https://blog.ethereum.org/2022/06/16/gray-glacier-announcement/)

<ExpandableCard title="EIPs da Gray Glacier" contentPreview="Official improvements included in this upgrade.">

– [EIP-5133](https://eips.ethereum.org/EIPS/eip-5133) – _atrasa a bomba de dificuldade até setembro de 2022_

</ExpandableCard>

<Divider />

## 2021 {#2021}

### Arrow Glacier {#arrow-glacier}

<NetworkUpgradeSummary name="arrowGlacier" />

#### Resumo {#arrow-glacier-summary}

A implementação de rede Glacier Arrow adia a [bomba de dificuldade](/glossary/#difficulty-bomb) por vários meses. Essa é a única mudança introduzida nesta implementação, sendo de natureza similar à implementação [Muir Glacier](#muir-glacier). Mudanças semelhantes foram realizadas nas implementações de rede [Byzantium](#byzantium), [Constantinople](#constantinople) e [London](#london).

- [Blog da EF – Comunicado da atualização Arrow Glacier](https://blog.ethereum.org/2021/11/10/arrow-glacier-announcement/)
- [Ethereum Cat Herders – Atualização Ethereum Arrow Glacier](https://medium.com/ethereum-cat-herders/ethereum-arrow-glacier-upgrade-e8d20fa4c002)

<ExpandableCard title="EIPs da Arrow Glacier" contentPreview="Official improvements included in this upgrade.">

– [EIP-4345](https://eips.ethereum.org/EIPS/eip-4345) – _atrasa a bomba de dificuldade até junho 2022_

</ExpandableCard>

---

### Altair {#altair}

<NetworkUpgradeSummary name="altair" />

#### Resumo {#altair-summary}

A Altair foi a primeira implementação programada para a [Beacon Chain](/upgrades/beacon-chain). Foi adicionado suporte para "comitês de sincronização", permitindo clientes leves, aumentando a inatividade do validador e removendo penalidades à medida que o desenvolvimento avançava para A Fusão.

- [Leia a especificação de melhoria da Altair](https://github.com/ethereum/consensus-specs/tree/dev/specs/altair)

#### <emoji text=":tada:" size={1} mr="0.5rem" />Fato engraçado! {#altair-fun-fact}

Altair foi a primeira grande atualização de rede que teve um tempo exato de implantação. Todas as atualizações anteriores eram baseadas em um número de bloco declarado na cadeia de prova de trabalho, na qual o tempo de mineração de cada bloco varia. A Beacon Chain não requer resolver a prova de trabalho, em vez disso, ela funciona segundo um sistema de tempo em épocas, composto de 32 "intervalos" de 12 segundos cada, durante os quais os validadores podem propor blocos. É por isso que sabíamos exatamente quando atingiríamos a época 74.240 e a data de lançamento da Altair!

- [Tempo do bloco](/developers/docs/blocks/#block-time)

---

### London {#london}

<NetworkUpgradeSummary name="london" />

#### Resumo {#london-summary}

A implementação London introduziu a [EIP-1559](https://eips.ethereum.org/EIPS/eip-1559), que reformou o mercado de taxas de transação, além de implementar mudanças na forma como os reembolsos de gás são realizados e no agendamento da [Ice Age](/glossary/#ice-age).

- [Você é um desenvolvedor de dapp? Certifique-se de atualizar suas bibliotecas e ferramentas.](https://github.com/ethereum/execution-specs/blob/master/network-upgrades/london-ecosystem-readiness.md)
- [Leia o comunicado da Ethereum Foundation](https://blog.ethereum.org/2021/07/15/london-mainnet-announcement/)
- [Leia a explicação do Ethereum Cat Herder](https://medium.com/ethereum-cat-herders/london-upgrade-overview-8eccb0041b41)

<ExpandableCard title="EIPs da London" contentPreview="Official improvements included in this upgrade.">

– [EIP-1559](https://eips.ethereum.org/EIPS/eip-1559) – _melhora a taxa de transação do mercado_
– [EIP-3198](https://eips. thereum.org/EIPS/eip-3198) – _retorna o "BASEFEE" de um bloco_
– [EIP-3529](https://eips.ethereum. rg/EIPS/eip-3529) – _reduz os reembolsos de gás para operações de EVM_
– [EIP-3541](https://eips.ethereum. rg/EIPS/eip-3541) – _evita a implantação de contratos que iniciam com "0xEF"_
– [EIP-3554](https://eips.ethereum.org/EIPS/eip-3554) – _atrasa a Ice Age até 2021_

</ExpandableCard>

---

### Berlin {#berlin}

<NetworkUpgradeSummary name="berlin" />

#### Resumo {#berlin-summary}

A atualização Berlim otimizou o custo de gás para certas ações de EVM e aumenta o suporte para vários tipos de transação.

- [Leia o anúncio da Fundação Ethereum](https://blog.ethereum.org/2021/03/08/ethereum-berlin-upgrade-announcement/)
- [Leia a explicação do Ethereum Cat Herder](https://medium.com/ethereum-cat-herders/the-berlin-upgrade-overview-2f7ad710eb80)

<ExpandableCard title="EIPs da Berlim" contentPreview="Official improvements included in this upgrade.">

– [EIP-2565](https://eips.ethereum.org/EIPS/eip-2565) - _reduz o custo de gás para ModExp_
– [EIP-2718](https://eips. thereum.org/EIPS/eip-2718) – _permite suporte mais fácil para vários tipos de transação_
– [EIP-2929](https://eips. thereum.org/EIPS/eip-2929) – _o custo de gás aumenta para os opcodes de acesso ao estado_
– [EIP-2930](https://eips.ethereum.org/EIPS/eip-2930) – _adiciona listas de acesso opcionais_

</ExpandableCard>

<Divider />

## 2020 {#2020}

### Origem da Beacon Chain {#beacon-chain-genesis}

<NetworkUpgradeSummary name="beaconChainGenesis" />

#### Resumo {#beacon-chain-genesis-summary}

A [Beacon Chain](/upgrades/beacon-chain/) precisava de 16.384 depósitos de 32 ETH de participação para ser transferida com segurança. Isso aconteceu em 27 de novembro, ou seja, a Beacon Chain começou a produzir blocos em 1 de dezembro de 2020. Este é um primeiro passo importante para alcançar a [visão Ethereum](/upgrades/vision/).

[Leia o anúncio da Ethereum Foundation](https://blog.ethereum.org/2020/11/27/eth2-quick-update-no-21/)

<DocLink to="/upgrades/beacon-chain/">
  A Beacon Chain
</DocLink>

---

### Contrato de depósito de participação implantado {#staking-deposit-contract}

<NetworkUpgradeSummary name="stakingDepositContractDeployed" />

#### Resumo {#deposit-contract-summary}

O contrato de depósito fixo introduziu a [participação](/glossary/#staking) no ecossistema Ethereum. Embora fosse um contrato da [Rede principal](/glossary/#mainnet), ela teve um impacto direto na linha do tempo para o lançamento da [Beacon Chain](/upgrades/beacon-chain/), uma importante [atualização do Ethereum](/upgrades/).

[Leia o comunicado da Ethereum Foundation](https://blog.ethereum.org/2020/11/04/eth2-quick-update-no-19/)

<DocLink to="/staking/">
  Participação
</DocLink>

---

### Muir Glacier {#muir-glacier}

<NetworkUpgradeSummary name="muirGlacier" />

#### Resumo {#muir-glacier-summary}

A bifurcação Muir Glacier introduziu um atraso na [bomba de dificuldade](/glossary/#difficulty-bomb). O aumento da dificuldade dos blocos do mecanismo de consenso da [prova de trabalho](/developers/docs/consensus-mechanisms/pow/) ameaçava degradar a usabilidade do Ethereum, aumentando os tempos de espera para o envio de transações e usando dapps.

- [Leia o comunicado da Ethereum Foundation](https://blog.ethereum.org/2019/12/23/ethereum-muir-glacier-upgrade-announcement/)
- [Leia a explicação do Ethereum Cat Herder](https://medium.com/ethereum-cat-herders/ethereum-muir-glacier-upgrade-89b8cea5a210)

<ExpandableCard title="Muir Glacier" contentPreview="Official improvements included in this fork.">

– [EIP-2384](https://eips.ethereum.org/EIPS/eip-2384) – _atrasa a bomba de dificuldade por mais 4.000.000 blocos, ou ~611 dias._

</ExpandableCard>

<Divider />

## 2019 {#2019}

### Istambul {#istanbul}

<NetworkUpgradeSummary name="istanbul" />

#### Resumo {#istanbul-summary}

A bifurcação Istanbul:

- Otimizado o custo de [gás](/glossary/#gas) de certas ações no [EVM](/developers/docs/ethereum-stack/#ethereum-virtual-machine).
- Melhoria na resiliência a ataques de negação de serviço.
- Criou soluções de [escalonamento da Camada 2](/developers/docs/scaling/#layer-2-scaling)com soluções baseadas em SNARKs e STARKs de melhor desempenho.
- Interoperação entre Ethereum e Zcash habilitada.
- Contratos permitidos para introduzir funções mais criativas.

[Leia o comunicado da Ethereum Foundation](https://blog.ethereum.org/2019/11/20/ethereum-istanbul-upgrade-announcement/)

<ExpandableCard title="EIPs da Istanbul" contentPreview="Official improvements included in this fork.">

– [EIP-152](https://eips.ethereum.org/EIPS/eip-152) – _permite que o Ethereum trabalhe com moedas que preservam a privacidade, como o Zcash._
– [EIP-1108](https://eips.ethereum.org/EIPS/eip-1108) – _criptografia mais barata para melhorar os custos de [gas](/glossary/#gas)._
– [EIP-1344](https://eips.ethereum.org/EIPS/eip-1344) – _protege o Ethereum contra ataques de reprodução adicionando "CHAINID" [opcode](/developers/docs/ethereum-stack/#ethereum-virtual-machine)._
– [EIP-1884](https://eips.ethereum.org/EIPS/eip-1884) – _otimização dos preços do gás dos códigos de operação baseados em consumo._
– [EIP-2028](https://eips.ethereum.org/EIPS/eip-2028) – _reduz o custo dos dados de chamada para permitir mais dados nos blocos – bom para [escalonamento de Camada 2](/developers/docs/scaling/#layer-2-scaling)._
– [EIP-2200](https://eips.ethereum.org/EIPS/eip-2200) – _outras alterações do preço do gás dos códigos de operação._

</ExpandableCard>

---

### Constantinopla {#constantinople}

<NetworkUpgradeSummary name="constantinople" />

#### Resumo {#constantinople-summary}

A bifurcação Constantinople:

- Assegurou que a cadeia de blocos não congelasse antes de a [prova de participação ser implementada](#beacon-chain-genesis).
- Otimizado o custo de [gás](/glossary/#gas) de certas ações no [EVM](/developers/docs/ethereum-stack/#ethereum-virtual-machine).
- Adicionada a capacidade de interagir com endereços que ainda não foram criados.

[Leia o comunicado da Ethereum Foundation](https://blog.ethereum.org/2019/02/22/ethereum-constantinople-st-petersburg-upgrade-announcement/)

<ExpandableCard title="EIPs da Constantinople" contentPreview="Official improvements included in this fork.">

– [EIP-145](https://eips.ethereum.org/EIPS/eip-145) – _otimiza o custo de certas ações em cadeia.
– [EIP-1014](https://eips.ethereum.org/EIPS/eip-1014) – \_permite que você interaja com endereços que ainda não foram criados.
– [EIP-1052](https://eips.ethereum.org/EIPS/eip-1052) – \_otimiza o custo de certas ações em cadeia.
– [EIP-1234](https://eips.ethereum.org/EIPS/eip-1234) – \_verifica se a cadeia de blocos não congela antes da prova de participação._

</ExpandableCard>

<Divider />

## 2017 {#2017}

### Byzantium {#byzantium}

<NetworkUpgradeSummary name="byzantium" />

#### Resumo {#byzantium-summary}

A bifurcação Byzantium:

- Reduziu as recompensas de [mineração](/developers/docs/consensus-mechanisms/pow/mining/) de bloco de 5 para 3 ETH.
- A [bomba de dificuldade](/glossary/#difficulty-bomb) foi atrasada por um ano.
- Adicionada a capacidade de fazer chamadas sem alteração de estado para outros contratos.
- Adicionados alguns métodos de criptografia para permitir o [escalonamento da Camada 2](/developers/docs/scaling/#layer-2-scaling).

[Leia o comunicado da Ethereum Foundation](https://blog.ethereum.org/2017/10/12/byzantium-hf-announcement/)

<ExpandableCard title="EIPs da Byzantium" contentPreview="Official improvements included in this fork.">

– [EIP-140](https://eips.ethereum.org/EIPS/eip-140) – _adiciona o código de operação "REVERT"._
– [EIP-658](https://eips.ethereum.org/EIPS/eip-658) – _campo de status adicionado aos recibos de transação para indicar êxito ou falha._
– [EIP-196](https://eips.ethereum.org/EIPS/eip-196) – _adiciona curva elíptica e multiplicação escalar para permitir [ZK-Snarks](/developers/docs/scaling/zk-rollups/)._
– [EIP-197](https://eips.ethereum.org/EIPS/eip-197) – _adiciona curva elíptica e multiplicação escalar permitir [ZK-Snarks](/developers/docs/scaling/zk-rollups/)._
– [EIP-198](https://eips.ethereum.org/EIPS/eip-198) – _habilita a verificação de assinatura RSA._
– [EIP-211](https://eips.ethereum.org/EIPS/eip-211) – _adiciona suporte para valores de retorno de tamanho variável._
– [EIP-214](https://eips.ethereum.org/EIPS/eip-214) – _adiciona o código de operação "STATICCALL", permitindo chamadas sem alteração sem estado para outros contratos._
– [EIP-100](https://eips.ethereum.org/EIPS/eip-100) – _altera a fórmula de ajuste de dificuldade._
– [EIP-649](https://eips.ethereum.org/EIPS/eip-649) – _atrasa a [difficulty bomb](/glossary/#difficulty-bomb) em um ano e reduz a recompensa de bloco de 5 para 3 ETH._

</ExpandableCard>

<Divider />

## 2016 {#2016}

### Spurious Dragon {#spurious-dragon}

<NetworkUpgradeSummary name="spuriousDragon" />

#### Resumo {#spurious-dragon-summary}

A bifurcação Spurious Dragon foi a segunda resposta aos ataques de negação de serviço (DoS) na rede (setembro / outubro de 2016), incluindo:

- ajustar preços do código de operação para evitar ataques futuros à rede.
- permitindo "desinchar" do estado da cadeia de blocos.
- adicionando proteção contra ataques de repetição.

[Leia o comunicado da Ethereum Foundation](https://blog.ethereum.org/2016/11/18/hard-fork-no-4-spurious-dragon/)

<ExpandableCard title="EIPs da Spurious Dragon" contentPreview="Official improvements included in this fork.">

– [EIP-155](https://eips.ethereum. rg/EIPS/eip-155) – _evita que as transações de uma cadeia Ethereum sejam retransmitidas em uma cadeia alternativa, por exemplo, uma transação de rede de testes sendo reproduzida na cadeia principal Ethereum.
– [EIP-160](https://eips.ethereum. rg/EIPS/eip-160) – \_ajusta os preços do código de operação "EXP" – dificulta a desaceleração da rede pode meio de operações contratuais computacionalmente caras.
– [EIP-161](https://eips.ethereum.org/EIPS/eip-161) – \_permite a remoção de contas vazias adicionadas por meio dos ataques DOS (DOS).
– [EIP-170](https://eips.ethereum.org/EIPS/eip-170) – \_muda o tamanho máximo de código que um contrato na cadeia de blocos pode ter – para 24576 bytes._

</ExpandableCard>

---

### Tangerine Whistle {#tangerine-whistle}

<NetworkUpgradeSummary name="tangerineWhistle" />

#### Resumo {#tangerine-whistle-summary}

A bifurcação Whistle Tangerine foi a primeira resposta aos ataques de negação de serviço (DoS) na rede (setembro / outubro de 2016), incluindo:

- resolução de problemas urgentes de integridade da rede relacionados a códigos de operação com preços reduzidos.

[Leia o comunicado da Ethereum Foundation](https://blog.ethereum.org/2016/10/18/faq-upcoming-ethereum-hard-fork/)

<ExpandableCard title="EIPs da Tangerine Whistle" contentPreview="Official improvements included in this fork.">

– [EIP-150](https://eips.ethereum.org/EIPS/eip-150) – _aumenta os custos de gás de códigos de operação que podem ser usados em ataques de spam._
– [EIP-158](https://eips.ethereum. rg/EIPS/eip-158) – _reduz o tamanho do estado removendo muitas contas vazias que foram colocadas no estado a um custo muito baixo, devido a falhas em versões anteriores do protocolo Ethereum._

</ExpandableCard>

---

### Bifurcação DAO {#dao-fork}

<NetworkUpgradeSummary name="daoFork" />

#### Resumo {#dao-fork-summary}

A bifurcação DAO foi em resposta ao [ataque DAO de 2016](https://www.coindesk.com/markets/2016/06/25/understanding-the-dao-attack/), duranto o qual um contrato inseguro de [DAO](/glossary/#dao) foi esvaziado em mais de 3 milhões de ETH em um hack. A bifurcação moveu os fundos do contrato defeituoso para um [novo contrato](https://etherscan.io/address/0xbf4ed7b27f1d666546e30d74d50d173d20bca754) com uma única função: fazer saque. Qualquer pessoa que tenha perdido fundos poderia sacar 1 ETH para cada 100 tokens DAO em suas carteiras.

Esse curso de ação foi votado pela comunidade Ethereum. Qualquer titular de ETH pôde votar por meio de uma transação em [uma plataforma de votação](http://v1.carbonvote.com/). A decisão de fazer a bifurcação ultrapassou 85% dos votos.

Alguns mineradores recusaram a bifurcação porque o incidente da DAO não era um defeito do protocolo. Eles começaram a formar a [Ethereum Classic](https://ethereumclassic.org/).

[Leia o comunicado da Ethereum Foundation](https://blog.ethereum.org/2016/07/20/hard-fork-completed/)

---

### Homestead {#homestead}

<NetworkUpgradeSummary name="homestead" />

#### Resumo {#homestead-summary}

A bifurcação Homestead que olhou para o futuro. Incluiu várias alterações no protocolo e uma alteração na rede que deu ao Ethereum a capacidade de fazer mais atualizações na rede.

[Leia o comunicado da Ethereum Foundation](https://blog.ethereum.org/2016/02/29/homestead-release/)

<ExpandableCard title="EIPs do Homestead" contentPreview="Official improvements included in this fork.">

– [EIP-2](https://eips.ethereum.org/EIPS/eip-2) – _faz edições no processo de criação do contrato._
– [EIP-7](https://eips.ethereum. rg/EIPS/eip-7) – _adiciona um novo código de operação: `DELEGATECALL`_
– [EIP-8](https://eips.ethereum.org/EIPS/eip-8) – _introduz os requisitos de compatibilidade devp2p_

</ExpandableCard>

<Divider />

## 2015 {#2015}

### Frontier thawing {#frontier-thawing}

<NetworkUpgradeSummary name="frontierThawing" />

#### Resumo {#frontier-thawing-summary}

A bifurcação Frontier Thawing aumentou o limite de [gás](/glossary/#gas) de 5.000 por [bloco](/glossary/#block) e definiu o preço padrão do gás para 51 [gwei](/glossary/#gwei). Isso é permitido para transações – as transações requerem 21.000 gás. A bomba de dificuldade [](/glossary/#difficulty-bomb) foi introduzida para garantir uma futura bifurcação fixa para a [prova de participação](/glossary/#pos).

- [Leia o comunicado da Ethereum Foundation](https://blog.ethereum.org/2015/08/04/the-thawing-frontier/)
- [Leia a atualização do protocolo Ethereum 1](https://blog.ethereum.org/2015/08/04/ethereum-protocol-update-1/)

---

### Frontier {#frontier}

<NetworkUpgradeSummary name="frontier" />

#### Resumo {#frontier-summary}

Frontier era a implementação mais simples do projeto Ethereum. Ela veio após a fase de testes bem-sucedida da Olympic. Ela era destinada a usuários técnicos, especificamente a desenvolvedores. [Blocos](/glossary/#block) tiveram um limite de gás [](/glossary/#gas) de 5.000. Esse período de "escavação" permitiu que os mineradores iniciassem as suas operações e que os primeiros adotantes instalassem os seus clientes sem “pressa”.

[Leia o comunicado da Ethereum Foundation](https://blog.ethereum.org/2015/07/22/frontier-is-coming-what-to-expect-and-how-to-prepare/)

<Divider />

## 2014 {#2014}

### Venda de Ether {#ether-sale}

<NetworkUpgradeSummary name="etherSale" />

O Ether permaneceu à venda oficialmente por 42 dias. Era possível comprá-lo com BTC.

[Leia o comunicado da Ethereum Foundation](https://blog.ethereum.org/2014/07/22/launching-the-ether-sale/)

---

### Lançamento do Yellow Paper {#yellowpaper}

<NetworkUpgradeSummary name="yellowpaperRelease" />

O Yellow Paper, de autoria do Dr. Gavin Wood, é uma definição técnica do protocolo Ethereum.

[Ver o Yellow Paper](https://github.com/ethereum/yellowpaper)

<Divider />

## 2013 {#2013}

### Lançamento do Whitepaper {#whitepaper}

<NetworkUpgradeSummary name="whitepaperRelease" />

Este artigo introdutório foi originalmente publicado em 2013 por Vitalik Buterin, fundador da Ethereum, antes do lançamento do projeto em 2015.

<DocLink to="/whitepaper/">
  Whitepaper
</DocLink>
