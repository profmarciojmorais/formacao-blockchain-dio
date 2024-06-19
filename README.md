# formacao-blockchain-dio
Repositório contendo os desafios de projeto da formação
Codigos do projeto
//importando as depenedencias
const bi32 = require( 'bip32')
const bip39 = require ('bip39')
const bitcoin = require ('bitcoinjs-lib')

//denir a rede
// bitcoin - rede principal - mainnet
//testnet - rede de teste - testnet 
const network = bitcoin.networks.testnet

//derivacao de carteiras HD
const path = 'm\49'\1'\0'\0'

//crinado o mnemonic para a sedd (`alavras de senha)
let mnemonic = bip39.generateMnemonic()
const seed = bip39.mnemonicToSeedSync(mnemonic)

//criando a raiz da certeira HD
let root = bip32.fromSeed(sedd, network)

//criando uma conta - par de pvt - pub keys
let account = root.derivePath(path)
let node = acoount.derive(0).derive(0)

let btcAddress = bitcoin.payments.p2pk({
    pubkey : Node.publicKey,
    network: network,
}).address

console.log("Carteira gerada")
console.log("Endereço : ", btcAddress)
console.log("Chave privada:", node.toWIF())
console.log("Seed", mnemonic)










