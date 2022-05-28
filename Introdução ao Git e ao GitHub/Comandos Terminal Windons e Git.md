# * Linha da comando Terminal Windows

## Windows
cd = selecionar diretorio.
dir = lista.
cls = limpar terminal.
mkdir = criar um pasta.
echo > hello.txt = criação de arquivo.
del = só vai deletar, arquivos.
rmdir 'nomepasta' /s /q = excluir pasta com todos os arquivos.

## UNIX - linux
cd 
Is
mkdir
rm-rf


## * SHA
significa sercure hash algorithm (algoritmo de hash seguro), é um conjunto 
de funções hash criptográficas projetadas pela NSA(Agência de Segurança Naci
nal dos EUA)
  
A encriptação gera um conjunto de characteres identificador de 40 dígitos.

## + Comando seleção de arquivo:
openssl sha1 "arquivo"

## *Exemplo de arquivos e suas alterações:
eef94f412474fd9624bfdae79312946fc29a85ba
e340bc88f0510d7bcebe9e5157f4c5397f37629a
eaa8ff8c8ec6367a54d4064e1aad6e0f81e85900

## BLOBS: Os arquivos, objeto.
## TREES: Armazena os blobs, e o nome do arquivo.
## COMMITS: Aponta para a trees para a blobs e junta tudo para salva o arquivo.

CHAVES SSH E TOKENS

## SSH
Comandos para criação das chaves:
ssh-keygen -t ed25519 -C 'e-mail'

Caminho da pasta: (/c/Users/User/.ssh/id_ed25519)
senha: '******'

## + Primeiro entra na pasta onde foi gerado a chave publica. 
Logo depois comando: 
cat id_ed25519.pub

chave: ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIIyH9lh1oFzw/43qRCjx7Xf/UFoCqc0HhZH4TNr3a0Ex 'e-mail'
ls = lista
pwd = mostra o caminho

comando: 
eval $(ssh-agent -s)

## + Agora vamos entregar o caminho para o agente
colocando o id_ed25519 e vai pedir o passoword 557757

Pontos:
1-Gerar a chave.
2-Pegar o caminho e descobrir a chaves.
3-Validar a chaves. 

## comando para clona: git clone
https://github.com/lucasrmagalhaes/homework-issues.git

token: 
exemplo: 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
