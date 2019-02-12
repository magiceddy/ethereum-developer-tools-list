# Ethereum Audit & Hacking Risorse utili

## Indice
- [Learning](#learning)
    - [Vettori di attacco](#vettori-di-attacco)
    - [Filosofia in generale](#filosofia-in-generale)
    - [Regole generali da seguire](#pattern-generali-da-seguire)
    - [Prepatati al fallimento](#preparati-al-fallimento)
    - [Layout Smart Contract](#layout-smart-contract)
    - [Sicurezza Token](#sicurezza-token)
    - [Blog utili](#blog-utili)
    - [Formal Verification](#formal-verification)
    - [Test](#test)
    - [Audit Tutorial](#audit-tutorial)
    - [Verie ed eventual](#learning-varie-ed-eventuali)
- [Tools](#tools)
    - [Visualizzazione](#visualizzazione)
    - [Analisi statica e dinamica](#analisi-statica-e-dinamica)
    - [Test&Coverage](#test-&-coverage)
    - [Linters](#linters)
    - [OS](#os)
    - [Reversing](#reversing)
    - [Tool Automatici](#tool-automatici)
    - [Varie ed eventuali](#tools-varie-ed-eventuali)
- [Training](#training)
    - [Giochi](#giochi)
    - [Soluzioni](#soluzioni)
- [Audit](#audit)

## Learning
In questo paragrafo si vogliono presentare tutta una serie di strumenti di learning in merito a vulneranilità degli smart contract, best practices nello scrivere il codice e più in generale quelle risolrse utili al fine di capire i tool che si andranno ad utilizzare. La lista al momento è ridondante, ma si è scelto di offrire varie fonti in modo da capire con il tempo quale/i possano essere utilizzate come riferimento "ufficiale".
#### Vettori di attacco
* https://blog.sigmaprime.io/solidity-security.html - Lista di attacchi conosciuti con descrizione della funzionalità che può portare alla vulnerabilità, esempio della vulnerabilità, esempio di attacco e soluzione per mitigare vulnerabilità 
* https://consensys.github.io/smart-contract-best-practices/known_attacks/ - Lista di attacchi conosciuti e soluzioni per mitigare, meno chiara rispetto alla losta precedente ma più "ufficiale".
* https://smartcontractsecurity.github.io/SWC-registry/ - Lista ufficiale delle vulnerabilità, descrizione e soluzioni (viene presa come rirerimento da alcuni tool). 
* https://www.comp.nus.edu.sg/~loiluu/papers/oyente.pdf - Paper riguardante la sicurezza degli Smart Contract con una proposta di un tool per la loro verifica. Utile per evidenze accademiche
* https://github.com/trailofbits/not-so-smart-contracts altra lista di vulnerabilità con esempi di codice e indicazioni su come mitigare mantenuta da Trailofbits (sembrano essere molto attivi nel settore)
* https://osolmaz.com/2018/10/18/anatomy-block-stuffing/ - Descrizione dettagliata dello Stuffing. Attacco che utilizza il limite di Gas in un blocco.
* https://medium.com/coinmonks/the-phenomena-of-smart-contract-honeypots-755c1f943f7b - Tecniche di HoneyPots. Far finta di creare vulnerabilità per rubare ai ladri, molto divertente :)
* https://media.consensys.net/discovering-signature-verification-bugs-in-ethereum-smart-contracts-424a494c6585  - vettori di attacco sulla digital signature
* https://arxiv.org/pdf/1806.01143.pdf - white paper del tool Securify
* https://medium.com/swlh/ethereum-aint-hiding-your-secrets-703e89088937 - guida su come leggere lo store di ethereum
* https://medium.com/consensys-diligence/silent-but-vulnerable-ethereum-gas-security-concerns-adadf8bfb180 attacchi causati da un uso malevolo del gas
* https://www.reddit.com/r/ethereum/comments/a9ftkm/backdoored_smart_contract_challenge_including/ - video corso su attacca basato su Jump-Oriented Programming
* https://yondon.blog/2019/01/01/how-not-to-use-ecdsa/ - come non utilizzare ACSDA signature
* https://medium.com/altcoin-magazine/security-considerations-while-developing-ethereum-smart-contracts-in-solidity-aed8970341c3 - considerazioni utili in ambito sicurezza quando si programma uno Smart Contract: Diamond problem, check sul valore di ritorno, ...
* https://www.youtube.com/watch?v=WIEessi3ntk - video sull'hacking di uno smart contract
* https://medium.com/modular-network/introduction-to-smart-contract-and-dapp-security-556502629d54 - sicurezza orientata lato Dapp
* https://eprints.cs.univie.ac.at/5433/7/sanerws18iwbosemain-id1-p-380f58e-35576-preprint.pdf - paper sui pattern di sicurezza

#### Filosofia in generale
* https://consensys.github.io/smart-contract-best-practices/general_philosophy/ - best practices nello scrivere uno smart contract

#### Regole generali da seguire
* https://consensys.github.io/smart-contract-best-practices/recommendations/ - pattern "ufficiali" da seguire nella scrittura di uno smart contract
* http://chriseth.github.io/notes/talks/safe_solidity/#/ - slide su come scrivere uno smart contract sicuro
* https://blog.trailofbits.com/2018/09/05/contract-upgrade-anti-patterns/ - pattern di scrittura con analisi delle problematiche nella scrittura di smart contract aggiornabili
* https://blog.trailofbits.com/2018/03/23/use-our-suite-of-ethereum-security-tools/ - suite di strumenti utilizzati da trailofbits per prevenire ed identificare problematiche di sicurezza
#### Preparati al fallimento
* https://consensys.github.io/smart-contract-best-practices/software_engineering/ - best practice da utilizzare per mitigare i comportamenti anomali degli smart contract
* https://medium.com/@peterborah/we-need-fault-tolerant-smart-contracts-ec1b56596dbc - tecniche da utilizzare nel caso vengano scoperti bug nel codice e tecniche per aggiornare gli smart contract
#### Layout Smart Contract
* https://solidity.readthedocs.io/en/v0.5.3/style-guide.html#introduction - standard di scrittura di uno smart contract, indentazione, stile, convenzione nomi, ...
* https://solidity.readthedocs.io/en/v0.4.24/layout-of-source-files.html - commenti nel codice
#### Sicurezza Token
* https://github.com/sec-bit/awesome-buggy-erc20-tokens - vulnerabilità nei token, lista token deployati e buggati, lista dei token non standard. Utile anche nel caso si debbano utilizzare token non proprietari e capire quali problematiche si possono incontrare
* https://medium.com/coinmonks/missing-return-value-bug-at-least-130-tokens-affected-d67bf08521ca - analisi sulla mancanza dei valori di ritorno nei token
#### Blog Utili
* http://hackingdistributed.com/ - blog sulla sicurezza nei sistemi distribuiti
* https://blog.trailofbits.com/ - blog trailofbits
#### Formal Verification
* https://github.com/MaiaVictor/Formality - linguaggio su Formal verification
* https://medium.com/ethworks/formal-verification-for-n00bs-part-1-b4781db2a383 - tutorial formal verification
#### Test
* https://blog.zeppelinos.org/testing-real-world-contract-upgrades/ - tecniche per testare l'upgrade di smart contract
* https://hackernoon.com/minimal-solidity-contract-testing-with-ganache-and-jest-f735547d9643 - unit test smart contract con jest e ganache
#### Audit Tutorial
* https://blog.smartdec.net/ - blog di smartdec con molti esempi di audit di smart contract 
* https://medium.com/quillhash/quill-audits-the-smart-contract-security-audit-platform-9ea1950ad6e - spiegazione sulla piattaforma di quillhash
#### Learning Varie ed eventuali
* https://solidity.readthedocs.io/en/latest/050-breaking-changes.html - breaking changes introdotti da solidity 0.5
* https://medium.com/coinmonks/vertcoin-vtc-is-currently-being-51-attacked-53ab633c08a4 - 51% attack su vertcoin

## Tools
In questa sezione vengono presentati i tool di analisi e sviluppo di smart contract.
#### Visualizzazione
* [Surya](https://github.com/ConsenSys/surya) - Tool di inspezione di smart contract. Visualizzazione funzioni, gerarchia contratti, etc...
* [Solgraph](https://github.com/raineorshine/solgraph) - Generazione grafico smart contract
* [evmlab](https://github.com/ethereum/evmlab) - Utilities per interagire con la EVM
* [ethereum-graph-debugger](https://github.com/fergarrui/ethereum-graph-debugger) - debugger visuale
* [sol-function-profiler](https://github.com/EricR/sol-function-profiler) - report visuale di tutte le funzioni di uno smart contract
#### Analisi statica e dinamica
* [mythril classic](https://github.com/ConsenSys/mythril-classic) - tool check analisi di sicurezza su smart contract
* [Slinter](https://github.com/trailofbits/slither) - Analisi statica scritta in python
* [Echidna](https://github.com/trailofbits/echidna) - fuzzing/property-based testing
* [manticore](https://github.com/trailofbits/manticore) - tool esecuzione automatica per testing
* [oyente](https://github.com/melonproject/oyente) - tool analisi smart contract
* [actopus](https://github.com/quoscient/octopus) - analisi vulnerabilità e check su cosa viene memorizzato nello stack
* [solstice](https://github.com/rajeevgopalakrishna/Solstice) - tool investigazione smart contract
#### Test&Coverage
* [solidity-coverage](https://github.com/sc-forks/solidity-coverage) - tool analisi coverage dei test
* [meadown](https://github.com/MeadowSuite/Meadow) - unit test 
* [waffle](https://github.com/EthWorks/Waffle) - libreria unit testing smart contract
#### Linters
* [solcheck](https://github.com/federicobond/solcheck)
* [solint](https://github.com/SilentCicero/solint)
* [solium](https://github.com/duaraghav8/Ethlint)
* [solhint](https://github.com/protofire/solhint)
#### OS
* [zeppelin](https://zeppelinos.org/) - OS con implementati smart contract sicuri
#### Reversing
* [ethereum-dasm](https://github.com/tintinweb/ethereum-dasm)
* [ethersplay](https://github.com/trailofbits/ethersplay)
* [evmlab](https://github.com/ethereum/evmlab) - tool interazione con EVM
* [rattle](https://github.com/trailofbits/rattle)
#### Tool Automatici
* [MythX](https://mythx.io/) - Smart Contract security API
* [Securify](https://securify.chainsecurity.com/) - tool 
online analisi 
* [quantstamp](https://betanet.quantstamp.com/start)
* [smartdec](https://tool.smartdec.net/) - check 
vulnerabilità e best practices
* [chainsecurity](https://chainsecurity.com/)
#### Tools Varie ed eventuali
* [buidler](https://github.com/nomiclabs/buidler) - task runner

## Training
Lista di challenges interattivi e relative soluzioni 
#### Giochi
* [capture the ether](https://capturetheether.com/)
* [ethernaut](https://ethernaut.zeppelin.solutions/)
* [etherhack](https://etherhack.positive.com/#/)
#### Soluzioni
* [trailofbits](https://blog.trailofbits.com/2017/11/06/hands-on-the-ethernaut-ctf/) - soluzione primi 6 esercizi ethernaut
* [coinmonks](https://medium.com/coinmonks/ethernaut-naught-coin-erc20-exploitation-218c86bb953b) - soluzione naught coin ethernauts
* [etherhack](https://blog.positive.com/phdays-8-etherhack-contest-writeup-794523f01248) - soluzioni etherhack

## Audit
* [Guida audit di smartDec](https://blog.smartdec.net/smartdec-smart-contract-audit-beginners-guide-d04cc7f1c571)
* [Audit con slinter](https://blog.coinfabrik.com/auditing-solidity-code-with-slither/)
* [Lista servizi di audit](https://etherscan.io/directory/Smart_Contracts/Smart_Contracts_Audit_And_Security)
* [Prepararsi ad un Audit](https://www.smartcontractsecurityalliance.com/) - regole da seguire sulla documentazione da fornire e best practices generiche
* [Guida su come svolgere e organizzare un audit](https://medium.com/ethereum-developers/how-to-audit-a-smart-contract-most-dangerous-attacks-in-solidity-ae402a7e7868) 
* [Video tutorial su come svolgere un audit](https://www.youtube.com/watch?v=DkVpUqzU8SI)
* [Come prepararsi ad un Audit by Consensys](https://media.consensys.net/preparing-for-a-smart-contract-code-audit-83691200cb9c)