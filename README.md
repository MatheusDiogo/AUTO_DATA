<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
</head>
<body>
  <h1>Código de Processamento de Dados para Faturamento</h1>
  
  <h2>Descrição</h2>
  <p>Este repositório contém um script em Python para processamento de dados de faturamento. O código lê arquivos de entrada contendo informações sobre clientes e medidores, realiza o tratamento desses dados e gera um arquivo de saída no formato CSV com os resultados do faturamento.</p>
  
  <h2>Dependências</h2>
  <p>O script requer as seguintes bibliotecas Python:</p>
  <ul>
    <li>pandas</li>
    <li>numpy</li>
  </ul>
  <p>Certifique-se de que essas bibliotecas estão instaladas no ambiente em que o script será executado.</p>
  
  <h2>Uso</h2>
  <ol>
    <li>Execute o script em um ambiente Python.</li>
    <li>Será solicitada a entrada do usuário para fornecer informações sobre os caminhos dos arquivos a serem utilizados, o nome do cliente a ser faturado e a data do faturamento.</li>
    <li>O script processará os dados e gerará um arquivo de saída contendo os resultados do faturamento.</li>
  </ol>
  
  <h2>Interatividade com o Usuário</h2>
  <p>Durante a execução do script, o usuário será solicitado a fornecer algumas informações necessárias para o processamento dos dados. Essas informações incluem:</p>
  <ul>
    <li>Opção de ignorar ou considerar o valor do medidor A3.</li>
    <li>Nome do cliente a ser faturado.</li>
    <li>Data do faturamento.</li>
  </ul>
  <p>Certifique-se de fornecer as informações corretas ao interagir com o script.</p>
  
  <h2>Arquivos de Entrada</h2>
  <p>O script espera que os seguintes arquivos estejam presentes no diretório de execução:</p>
  <ul>
    <li>Arquivo NDD: "NDD - [nome do cliente] - [ano] - [mês] - 01 a 30 a.csv"</li>
    <li>Arquivo de relatório Ilux: "Relatorio de Clientes - Equipamento - [nome do cliente] [mês]_[ano].xls"</li>
  </ul>
  <p>Certifique-se de que esses arquivos estejam presentes e possuam os nomes e formatos esperados pelo script.</p>
  
  <h2>Arquivo de Saída</h2>
  <p>O script gerará um arquivo de saída no formato CSV contendo os resultados do faturamento. O nome do arquivo de saída seguirá o padrão "NDD - [nome do cliente] - [ano] - [mês] - 01 a 31.csv", em que [nome do cliente], [ano] e [mês] são substituídos pelos valores fornecidos pelo usuário.</p>
  <p>Certifique-se de que o diretório de execução tenha permissões de gravação para que o arquivo de saída possa ser criado
