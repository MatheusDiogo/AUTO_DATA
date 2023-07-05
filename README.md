#Código de Processamento de Dados para Faturamento
Este repositório contém um script em Python para processamento de dados de faturamento. O código lê arquivos de entrada contendo informações sobre clientes e medidores, realiza o tratamento desses dados e gera um arquivo de saída no formato CSV com os resultados do faturamento.

#Dependências
O script requer as seguintes bibliotecas Python:

-pandas
-numpy
Certifique-se de que essas bibliotecas estão instaladas no ambiente em que o script será executado.

#Uso
1° Execute o script em um ambiente Python.
2° Será solicitada a entrada do usuário para fornecer informações sobre os caminhos dos arquivos a serem utilizados, o nome do cliente a ser faturado e a data do faturamento.
3° O script processará os dados e gerará um arquivo de saída contendo os resultados do faturamento.

#Interatividade com o Usuário
Durante a execução do script, o usuário será solicitado a fornecer algumas informações necessárias para o processamento dos dados. Essas informações incluem:

°Opção de ignorar ou considerar o valor do medidor A3.
°Nome do cliente a ser faturado.
°Data do faturamento.
Certifique-se de fornecer as informações corretas ao interagir com o script.

#Arquivos de Entrada
O script espera que os seguintes arquivos estejam presentes no diretório de execução:

Arquivo NDD: "NDD - [nome do cliente] - [ano] - [mês] - 01 a 30 a.csv"
Arquivo de relatório Ilux: "Relatorio de Clientes - Equipamento - [nome do cliente] [mês]_[ano].xls"
Certifique-se de que esses arquivos estejam presentes e possuam os nomes e formatos esperados pelo script.

#Arquivo de Saída
O script gerará um arquivo de saída no formato CSV contendo os resultados do faturamento. O nome do arquivo de saída seguirá o padrão "NDD - [nome do cliente] - [ano] - [mês] - 01 a 31.csv", em que [nome do cliente], [ano] e [mês] são substituídos pelos valores fornecidos pelo usuário.

Certifique-se de que o diretório de execução tenha permissões de gravação para que o arquivo de saída possa ser criado.
