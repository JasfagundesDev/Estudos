# Estudos
Primeiros passos na programação
# Calculando a quantidade de tijolos por m²
def aTijolo(x, y): # Nessa função é calculado a área do tijolo
  areaTijolo = x * y # Aqui temos a área do tijolo
  return areaTijolo

lado1 = float(input('Digite a altura do tijolo: '))
lado2 = float(input('Digite a largura do tijolo: '))
 
quantidade_tijolo = 1 / aTijolo(lado1, lado2) # Aqui está sendo calculado a quantidade de tijolos por m²
tijolo = quantidade_tijolo # Essa variável recebe a quantidade de tijolos por m²
print(f'São necessários {tijolo:.2f} para 1m².')

# Calculando a área das paredes
somaParede = 0 
b = 0
a = 0
areaParede = total_tijolos =  0 
resposta = ''
while resposta in 'S':
  print('-------------------------------------------------------------------------------------')
  b = float(input('Digite o valor da base da parede: '))
  a = float(input('Digite o valor da altura da parede: '))
  q = int(input('Total de paredes com essa dimenção: '))
  areaParede = b * a * q # Aqui está sendo calculado a área da parede e a quantidade de paredes com essa área
  quant_tijolos = areaParede / aTijolo(lado1, lado2) # Aqui está sendo calculado a quantidade de tijolos para essa área
  print(f'São {q} paredes com {b} X {a} com uma área total de {areaParede:.2f}m² gastando {quant_tijolos:.2f} tijolos')
  somaParede = somaParede + areaParede # Aqui está sendo somada todas as áreas
  total_tijolos +=  quant_tijolos # Já aqui, está sendo somado todos os tijolos
  print('-------------------------------------------------------------------------------------')
  resposta = str(input('Deseja acrescentar mais paredes: ')).upper()
  if resposta not in 'SN':
     print('Digite S para sim ou N para não')
  else:  
     print('------------------------------------------------------------------------------------')

# Calculando as aberturas da parede (portas e janelas)
resp = ''
totalAberturas = 0
while resp in 'S':
   base = float(input('Digite a base da abertura: '))
   alt = float(input('Digite a altura da abertura: ')) 
   quant = int(input('Quantas aberturas terão essas medidas: '))
   areaAbertura = base * alt * quant # Aqui está sendo calculado a área da abertura e a quantidade de aberturas
   print(f'A área total dessa abertura é: {areaAbertura}m²') 
   totalAberturas += areaAbertura # Aqui está pegando todas as áreas das aberturas e somando-as

   resp = str(input('Deseja acrescentar mais aberturas: ')).upper()
   if resp not in 'SN':
     print('Digite S para sim ou N para não')
   else:  
     print('------------------------------------------------------------------------------------')

areaTotal = somaParede - totalAberturas # Aqui estamos subtraindo todas as aberturas das paredes
quanTijolos = areaTotal / aTijolo(lado1, lado2)   #Aqui estamos calculando a quantidade de tijolos já descontando as aberturas    
print(f'A área total da casa é {areaTotal:.2f}m² com um total de {quanTijolos:.2f} tijolos.')
