# dataset_project

> Realizado pelas alunas Eduarda Moresco, discente de Informática Biomédica na Universidade Federal do Paraná em seu 6° semestre; e Fernanda Kawasaki, discente de Ciências da Computação na Universidade Federal do Paraná em seu 5° semestre.


Projeto desenvolvido para a aula de Data Science em Segurança, ministrada pelo professor André Grégio da Universidade Federal do Paraná, no primeiro semestre de 2021; visando a aplicação de técnicas de ciência de dados em um dataset de escolha dos alunos.
 
link para o notebook com as análises :  https://colab.research.google.com/drive/1srPPDyg2OVFv35qPwGaG5ri4qGKnXEU9?usp=sharing 

## Exploração de dados

Os dados da análise são compostos por um conjunto de arquivos com resultados de detecção de malware por um grupo de antivirus disponibilizados pela plataforma VirusTotal. Eles são constituidos majoritariamente por atributos textuais. 

Os modelos dos arquivos possuem os seguintes atributos: 

- scan_id: identificador da análise
- md5: função hash do arquivo contendo o malware de análise
- sha1: função hash do arquivo contendo o malware de análise
- sha256: função hash do arquivo contendo o malware de análise
- resource: --
- response_code: --
- verbose_msg: --
- scan_date: data de realização da análise
- permalink: url para a análise realizada pela plataforma VirusTotal
- total: total de detecção
- positives: total de detecção positiva
- scans: objeto com os resultados da análise por cada antivirus. Cada um deles corresponde a uma chave no objeto que abriga outro objeto. Nele temos as informações : detected , informa se o malware foi identificado por aquele antivirus ; version, versão do antivirus, update, data de atualização do antivirus; e result , rótulo dado ao malware pelo antivirus caso detected == true. 

A rotulação é realizada pelas engines dentro dos antivírus. De forma geral, elas identificam os malwares com base em um banco de dados próprio e, com o resultado em mãos, atribuem um rótulo utilizando um padrão definido. Como cada engine possui padrão diferente de nomear os malwares encontrados, temos diversos rótulos para um mesmo hash (MD5, SHA1, SHA256). Nota-se, também, que a diferença vai além da nomenclatura, pois a interpretação de cada engine tem sua variação, fazendo com que um malware possa ser considerado _Trojan_ por um antivírus e _Worm_ por outro.
 
O objetivo principal do projeto está no estudo sobre a rotulação e suas relações, analisando a possibilidade de se construir uma árvore ou um grafo de rótulos gerados por entidades distintas que no final, pode-se aplicar uma redução e normalização para uma label "padrão".

Tendo o objetivo em vista realizaremos a análise em cima de um dataset a ser criado com os dados modelo explicados no começo do tópico. Até o momento os dados julgados relevantes para a análise são md5, sha1, sha256, por serem os identificadores do objeto de análise; e os rótulos dados por cada antivirus ao malware. 
