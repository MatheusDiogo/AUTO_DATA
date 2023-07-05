import pandas as pd
import numpy as np

##################################################################################
# INTERACAO ENTRE O USUARIO E O SCRIPT                                           #
#                                                                                #
# O USUARIO ALIMENTARA COM INFORMACOES DOS CAMINHOS DOS ARQUIVOS OS QUAIS IRAO   #
# SER UTILIZADOS E TAMBEM NOME DOS CLIENTES E DATA A QUAL IRA SER FATURADA       #
#                                                                                #
##################################################################################

entradaA3 = input("\nDigite (1) p/Ignorar A3 (2) Considera Valor A3 (3) Novo medidor A3: ")
cliente = input("Digite o nome do cliente a ser faturado: ")
Data = input("Digite a data do faturamento: ")

##################################################################################
# INICIALIZANDO VARIAVEIS
##################################################################################

##################################################################################
# POSICAO DAS COLUNAS NECESSARIAS PARA O TRATAMENTO DE DADOS DA PLANILHA DO NDD

pos_series = 0 # POSICAO DA COLUNA QUE CONTEM AS SERIES NO ARQUIVO NDD
pos_MedFinalMono = 3 # POSICAO DA COLUNA DO VALOR DO MEDIDOR FINAL MONO NO ARQUIVO NDD
pos_MedFinalCor = 5 # POSICAO DA COLUNA DO VALOR DO MEDIDOR FINAL COLOR NO ARQUIVO NDD
pos_Medidor = 6 # POSICAO DA COLUNA QUE CONTEM OS TIPOS DE MEDIDORES NO ARQUIVO NDD

##################################################################################

##################################################################################
# INICIALIZACAO E CRIACAO DE LISTAS QUE IRAO CONTER TODAS AS INFORMACOES         #
# NECESSARIAS PARA A PLANILHA DO RESULTADO FINAL                                 #
##################################################################################

valoresPrintMono = []
valoresCopyMono = []
valoresCopyCor = []
valoresPrintCor = []
valoresTotalCor = []
valoresTotalMono = []
valoresA4Cor = []
valoresA4Mono = []
valoresA3Mono = []
valoresA3Cor = []
valoresDuplexMono = []
valoresDuplexCor = []
valoresA4CopyMono = []

seriesPrintMono = []
seriesPrintCor = []
seriesCopyMono = []
seriesCopyCor = []
seriesTotalMono = []
seriesTotalCor = []
seriesA4Mono = []
seriesA4Cor = []
seriesA3Mono = []
seriesA3Cor = []
seriesDuplexMono = []
seriesDuplexCor = []
seriesA4CopyMono = []

PrintCopyMono = []

a4Pb = []
a4Cor = []
a3Pb = []
a3Cor = []
data = []

##################################################################################

##################################################################################
# TRATAMENTO DO NOME DOS ARQUIVOS                                                #
##################################################################################

mes = '0'+str(int(Data[3:5])-1)
ano = Data[6:10]

#AbrirCliente = "/content/NDD - "+cliente+" - "+ano+" - "+mes+" - 01 a 15 a.csv"
AbrirCliente = "/content/NDD - PGE - 2023 - 06 - 01 a 30 a.csv"
SalvarCliente = "/content/NDD - "+cliente+" - "+ano+" - "+mes+" - 01 a 31.csv"

##################################################################################

##################################################################################
# UPLOAD DE ARQUIVO NDD E RELATORIO ILUX                                         #
##################################################################################

abreNDD = pd.read_csv(str(AbrirCliente), delimiter =';')
abreNDD.rename(columns={'SerialNumber' : 'Serie','PrinterModelName' : 'Modelo', 'StartCounterMono' : 'MedidorInicialMono','StartCounterColor' : 'MedidorInicialColor', 'EndCounterMono' : 'MedidorFinalMono', 'EndCounterColor' : 'MedidorFinalColor', 'CounterTypeName' : 'TipoDoContador' }, inplace = True)

abreIlux = pd.read_excel("/content/Relatorio de Clientes - Equipamento - PGE JUNHO_23.xls",engine = 'xlrd')
abreIlux.rename(columns={'Série' : 'Serie'}, inplace = True)

##################################################################################

##################################################################################
# SEPARANDO OS DADOS DA PLANILHA EM LISTAS                                       #
##################################################################################

##################################################################################
# ARQUIVO NDD                                                                    #
##################################################################################

serie = abreNDD['Serie']
modelo = abreNDD['Modelo']
medidorInicialMono = abreNDD['MedidorInicialMono']
medidorFinalMono = abreNDD['MedidorFinalMono']
medidorInicialColor = abreNDD['MedidorInicialColor']
medidorFinalColor = abreNDD['MedidorFinalColor']
tipoContador = abreNDD['TipoDoContador']

##################################################################################

matriz = np.array([serie,modelo,medidorInicialMono,medidorFinalMono,medidorInicialColor,medidorFinalColor,tipoContador])
matriz = matriz.T

# ARQUIVO ILUX
serie2 = abreIlux['Serie']
medidor = abreIlux['Medidor']

matriz2 = np.array([serie2, medidor])
matriz2 = matriz2.T

############################################################
#criando listas com medidores MONO
for posicao in range(len(matriz)):
   if((matriz[posicao][pos_Medidor] == 'A4Copy') or (matriz[posicao][pos_Medidor] == 'A3') or (matriz[posicao][pos_Medidor] == 'A4') or (matriz[posicao][pos_Medidor] == 'Print') or (matriz[posicao][pos_Medidor] == "Total") or (matriz[posicao][pos_Medidor] == "Copy")):
     if(matriz[posicao][pos_Medidor] == 'Print'):
       valoresPrintMono.append(matriz[posicao][pos_MedFinalMono])
       seriesPrintMono.append(matriz[posicao][pos_series])
     elif(matriz[posicao][pos_Medidor] == 'Copy'):
       valoresCopyMono.append(matriz[posicao][pos_MedFinalMono])
       seriesCopyMono.append(matriz[posicao][pos_series])
     elif(matriz[posicao][pos_Medidor] == 'Total'):
       valoresTotalMono.append(matriz[posicao][pos_MedFinalMono])
       seriesTotalMono.append(matriz[posicao][pos_series])
     elif(matriz[posicao][pos_Medidor] == 'A4'):
       valoresA4Mono.append(matriz[posicao][pos_MedFinalMono])
       seriesA4Mono.append(matriz[posicao][pos_series])
     elif((matriz[posicao][pos_Medidor] == 'A3') and ((entradaA3 == "2") or (entradaA3 == "3"))):
       valoresA3Mono.append(matriz[posicao][pos_MedFinalMono])
       seriesA3Mono.append(matriz[posicao][pos_series])
     elif((matriz[posicao][pos_Medidor] == 'A4Copy')):
       valoresA4CopyMono.append(matriz[posicao][pos_MedFinalMono])
       seriesA4CopyMono.append(matriz[posicao][pos_series])

#criando listas com medidores colorido
for posicao in range(len(matriz)):
   if((matriz[posicao][pos_Medidor] == 'Print') or (matriz[posicao][pos_Medidor] == "Total") or (matriz[posicao][pos_Medidor] == "Copy") or (matriz[posicao][pos_Medidor] == "A3" )):
     if(matriz[posicao][pos_Medidor] == 'Print'):
       valoresPrintCor.append(matriz[posicao][pos_MedFinalCor])
       seriesPrintCor.append(matriz[posicao][pos_series])
     elif(matriz[posicao][pos_Medidor] == 'Copy'):
       valoresCopyCor.append(matriz[posicao][pos_MedFinalCor])
       seriesCopyCor.append(matriz[posicao][pos_series])
     elif(matriz[posicao][pos_Medidor] == 'Total'):
       valoresTotalCor.append(matriz[posicao][pos_MedFinalCor])
       seriesTotalCor.append(matriz[posicao][pos_series])
     elif(matriz[posicao][pos_Medidor] == 'A4'):
       valoresA4Cor.append(matriz[posicao][pos_MedFinalCor])
       seriesA4Cor.append(matriz[posicao][pos_series])
     elif((matriz[posicao][pos_Medidor] == 'A3') and ((entradaA3 == "2") or (entradaA3 == "3"))):
       valoresA3Cor.append(matriz[posicao][pos_MedFinalCor])
       seriesA3Cor.append(matriz[posicao][pos_series])

#####################################################################
#somando Print+Copy+A4Copy MONO
for i in range(len(seriesPrintMono)):
  for j in range(len(seriesCopyMono)):
    if((seriesPrintMono[i] == seriesCopyMono[j])):
      valoresPrintMono[i] += valoresCopyMono[j]

for i in range(len(seriesPrintMono)):
  for j in range(len(seriesA4CopyMono)):
    if((seriesPrintMono[i] == seriesA4CopyMono[j])):
      valoresPrintMono[i] += valoresA4CopyMono[j]

if(entradaA3 == "2"):
  for i in range(len(seriesPrintMono)):
    for j in range(len(seriesA3Mono)):
      if((seriesPrintMono[i] == seriesA3Mono[j])):
        valoresPrintMono[i] += valoresA3Mono[j]

#comparando se A4 eh maior do que Print+Copy MONO
for i in range(len(seriesPrintMono)):
  for j in range(len(seriesA4Mono)):
    if((seriesPrintMono[i] == seriesA4Mono[j]) and (valoresPrintMono[i] < valoresA4Mono[j]) ):
      valoresPrintMono[i] = valoresA4Mono[j]

#somando Print+Copy COLOR
for i in range(len(seriesPrintCor)):
  for j in range(len(seriesCopyCor)):
    if((seriesPrintCor[i] == seriesCopyCor[j])):
      valoresPrintCor[i] += valoresCopyCor[j]

if(entradaA3 == 2):
  for i in range(len(seriesPrintCor)):
    for j in range(len(seriesA3Cor)):
      if((seriesPrintCor[i] == seriesA3Cor[j])):
        valoresPrintCor[i] += valoresA3Cor[j]

#comparando se A4 eh maior do que Print+Copy COR
for i in range(len(seriesPrintCor)):
  for j in range(len(seriesA4Cor)):
    if((seriesPrintCor[i] == seriesA4Cor[j]) and (valoresPrintCor[i] < valoresA4Cor[j]) ):
      valoresPrintCor[i] = valoresA4Cor[j]

###########################################################
#CONCATENACAO FINAL

final_serieMono = seriesPrintMono + seriesTotalMono
final_serieCor = seriesPrintCor + seriesTotalCor
final_valoresMono = valoresPrintMono + valoresTotalMono
final_valoresCor = valoresPrintCor + valoresTotalCor

for posicao in range(len(final_valoresMono)):
  a4Pb.append("A4 PB")
for posicao in range(len(final_valoresCor)):
  a4Cor.append("A4 COR")


if(entradaA3 == "3"):
  final_serieMono += seriesA3Mono
  final_serieCor += seriesA3Cor
  final_valoresMono += valoresA3Mono
  final_valoresCor += valoresA3Cor

if(entradaA3 == "3"):
  for posicao in range(len(valoresA3Mono)):
    a3Pb.append("A3 PB")
  for posicao in range(len(valoresA3Cor)):
    a3Cor.append("A3 COR")

for posicao in range(len(final_valoresCor+final_valoresMono)):
    data.append(Data)

matrizfinal = np.array([(final_serieMono+final_serieCor), data, (a4Pb+a3Pb+a4Cor+a3Cor), (final_valoresMono+final_valoresCor)])
matrizfinal = matrizfinal.T

#AJUSTE DOS MEDIDORES CORRETOS
for i in range(len(matriz2)):
  for j in range(len(matrizfinal)):
    if((matrizfinal[j][0] == matriz2[i][0]) and (matrizfinal[j][2] != matriz2[i][1]) and (matrizfinal[j][2] == "A4 PB") and (matriz2[i][1] == "PBA4")):
      matrizfinal[j][2] = matriz2[i][1]
    elif((matrizfinal[j][0] == matriz2[i][0]) and (matrizfinal[j][2] != matriz2[i][1]) and (matrizfinal[j][2] == "A4 COR") and (matriz2[i][1] == "COLOR")):
      matrizfinal[j][2] = matriz2[i][1]

ndd = pd.DataFrame(matrizfinal)
ndd.index = ndd[3]
ndd.drop(['0'], inplace = True)
ndd.sort_values(0, inplace = True)

ndd.to_csv(str(SalvarCliente),sep =';',index = False, header = False)
