# ExtracaoScieloUFMG
O presente repositório colaciona os códigos utilizados para a extração de dados, via WebScraping, da base de dados da Scielo

##REQUISITOS 

São requisitos de instalação para rodar o script 
1. Instalação correta do Python
2. Instalação correta do Pycharm
3. Excel
4. Chrome
5. Webdiver do Chrome (versão compatível com o seu chrome) 

Ainda, para detalhamentos do requisito de instalação se dirija para o [tutorial aqui](url): https://docs.google.com/document/d/1zSzzGeP3eKtjSqQVaCZB5XosMOLHjDMRwUs7LowIq-Y/edit?usp=sharing 

##Rodando o Script MainExtracaoScielo.py

O primeiro código que tem que ser rodado é o código "mainExtracaoScielo.py" que está nesse repositório. 

A tela que vai ser usada para a extração desse código é a seguinte: 

![Captura de Tela 2024-05-17 às 13 57 31](https://github.com/marcellacstr/ExtracaoScieloUFMG/assets/112347434/723902ef-6f3c-499b-83a8-2b9df10aa828)


Esse script vai extrair metadados do artigo como: 
1. Título do artigo - colocado na coluna 1 da tabela
2. Nome dos autores - colocado na coluna 2 da tabela
3. Nome do 1º autor - colocado na coluna 3 da tabela
4. Gênero do 1º autor - colocado na coluna 6 da tabela
5. Fonte e revista da publicação do artigo - colocado na coluna 7 da tabela
6. Link do artigo - colocado na coluna 13 da tabela

 - Primeiro, crie a planilha que você quer que os dados sejam colocados 
 - Depois de definir qual palavra chave que será feita a extração, vá no site da Scielo e MANUALMENTE insira a palavra chave na busca. Depois, clique para “buscar”. Ex: “tribunal de justiça” 

<img width="487" alt="Captura de Tela 2024-05-17 às 13 27 46" src="https://github.com/marcellacstr/ExtracaoScieloUFMG/assets/112347434/139609b1-2eef-4825-9fbe-2c7c5090c10b">

 - Feita a busca, você vai pegar o link dessa página. O link deve parecer com esse daqui:

   https://search.scielo.org/?lang=pt&count=15&from=0&output=site&sort=&format=summary&fb=&page=1&q=%22tribunal+de+justiça%22
 
O link nos diz muita coisa sobre a página. Vamos colocar o link no código, além de outras informações que extraímos da tela. A parte que precisa ser alterada está deviadmente indicada no código como VARIÁVEIS PARA ALTERAÇÃO PELO USUÁRIO 

    #VARIÁVEIS PARA ALTERAÇÃO PELO USUÁRIO
    diretorio_trabalho_pycharm = '/Users/Marcella/Downloads/UFMG/ExtracaoSCIELO'
    nome_planilha = 'parquet.xlsx'
    nome_folha = 'Planilha1'
    caminho_webDriver = '/Users/Marcella/PycharmProjects/webscrapper101/chromedriver'
    pagina_inicial_pesquisa = 'https://search.scielo.org/?lang=en&count=15&from=0&output=site&sort=&format=summary&fb=&page=1&q=%22parquet%22'
    num_paginas = 2

 diretorio_trabalho_pycharm = é o diretório do seu projeto, onde estão os arquivos que precisam ser alterados, incluindo a planilha que você criou
 nome_planilha = nome da planilha que você criou 
 caminho_webDriver = caminho dentro do seu computador para o webDriver que você instalou 
 pagina_inicial_pesquisa = o link do site da scielo por onde vai começar a extração 
 num_paginas = número de páginas do resultado da pesquisa com a palavra-chave selecionada 

##Rodando o Script ExtracaoScieloTitulacao.py

O Script de extração da titulação vai extrair, em cima da tabela criado após o primeiro script ter sido rodado, outros dados sobre os autores 

A tela que vai ser usada para a extração desse código é a seguinte: 
![Captura de Tela 2024-05-17 às 13 58 05](https://github.com/marcellacstr/ExtracaoScieloUFMG/assets/112347434/6f611eb9-71d9-4e48-a420-e806f9bce225)


O script extrai do site dados como: 

1. Instituição do 1o autor - colocado na coluna 5 da tabela
2. Localidade do 1ø autor - - colocado na coluna 10, 11 e 12 da tabela como país, estado e cidade (se houver)
3. Grau de titulação do 1o autor - colocado na coluna 4 da tabela

As variáveis a serem alteradas estão no código e devem seguir a orientação do primeiro script para serem alteradas

    #VARIÁVEIS PARA ALTERAÇÃO PELO USUÁRIO
    diretorio_trabalho_pycharm = '/Users/Marcella/Downloads/UFMG/ExtracaoSCIELO'
    nome_planilha = 'parquet.xlsx'
    nome_folha = 'Planilha1'
    caminho_webDriver = '/Users/Marcella/PycharmProjects/webscrapper101/chromedriver'

##Rodando o Script ExtracaoScieloResumo.py

 Script de extração da resumo vai extrair, em cima da tabela criado após o primeiro script ter sido rodado, outros dados sobre o artigo 

 A tela que vai ser usada para a extração desse código é a seguinte: 
![Captura de Tela 2024-05-17 às 13 58 28](https://github.com/marcellacstr/ExtracaoScieloUFMG/assets/112347434/023d59e5-2099-4deb-b553-24dc38583d58)

 O script extrai do site dados como: 

1. Resumo do artigo - colocado na coluna 14 da tabela
2. Palavras Chave - colocado na coluna 15 da tabela
3. mês de publicação - colocado na coluna 8 da tabela
4. Ano de publicação - colocado na coluna 9 da tabela

As variáveis a serem alteradas estão no código e devem seguir a orientação do primeiro script para serem alteradas

    #VARIÁVEIS PARA ALTERAÇÃO PELO USUÁRIO
    diretorio_trabalho_pycharm = '/Users/Marcella/Downloads/UFMG/ExtracaoSCIELO'
    nome_planilha = 'parquet.xlsx'
    nome_folha = 'Planilha1'
    caminho_webDriver = '/Users/Marcella/PycharmProjects/webscrapper101/chromedriver'


Depois disso, se terá uma planilha no excel recheada de dados que podem render análises bibliométricas produtivas 

Qualquer dificuldade, entre em contato conosco pelos emails indicados na publicação do artigo. 


