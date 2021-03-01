# dataset_project

> Realizado pelas alunas Eduarda Moresco, discente de Informática Biomédica na Universidade Federal do Paraná em seu 6° semestre; e Fernanda Kawasaki, discente de Ciências da Computação na Universidade Federal do Paraná em seu 5° semestre.


Projeto desenvolvido para a aula de Data Science em Segurança, ministrada pelo professor André Grégio da Universidade Federal do Paraná, no primeiro semestre de 2021; visando a aplicação de técnicas de ciência de dados em um dataset de escolha dos alunos.


## Exploração de dados

Os dados da análise são compostos por um conjunto de arquivos com resultados de detecção de malware por um grupo de antivirus disponibilizados pela plataforma VirusTotal. Ele é constituido majoritariamente por atributos textuais, com o foco na rotulação por antivirus. 

Os modelos dos arquivos possuem os seguintes atributos: 

- scan_id: identificador da análise
- md5: função hash do arquivo contendo o malware de análise
- sha1: função hash de ..
- sha256: função hash de ..
- resource: --
- response_code: --
- verbose_msg: --
- scan_date: data de realização da análise
- permalink: url para a análise realizada pela plataforma VirusTotal
- total: total de detecção
- positives: total de detecção positiva
- scans: objeto com os resultados da análise por cada antivirus. Cada um deles corresponde a uma chave no objeto que abriga outro objeto. Nele temos as informações : detected , informa se o malware foi identificado por aquele antivirus ; version, versão do antivirus, update, data de atualização do antivirus; e result , rótulo dado ao malware pelo antivirus caso detected == true. 



- Seu dataset é rotulado de que maneira?

A rotulação do dataset é feita pelos antivírus. De forma geral, as engines identificam os malwares com base em um banco de dados próprio e, com base no resultado, atribuem um rótulo utilizando o padrão definido. Como cada engine possui padrão diferente de nomear os malwares encontrados, temos diversos rótulos para um mesmo hash (MD5, SHA1, SHA256). Também nota-se que a diferença vai além da nomenclatura, pois a interpretação de cada engine também pode variar, fazendo com que um malware possa ser considerado _Trojan_ por um antivírus e _Worm_ por outro.

- Como é a distribuição dos dados do dataset?

 
O objetivo principal do projeto está no estudo sobre a rotulação e suas relações, analisando a possibilidade de se construir uma árvore ou um grafo de rótulos gerados por entidades distintas que no final, pode-se aplicar uma redução e normalização para uma label "padrão".

Tendo o objetivo em vista realizaremos a análise em cima de um dataset a ser criado com os dados modelo explicados no começo do tópico. Até o momento os dados julgados relevantes para a análise são md5 e os rótulos dados por cada antivirus ao malware. O md5 por ser o identificador do objeto de análise e os rótulos, por conterem as strings do foco do projeto.
