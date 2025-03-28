# Instruções

- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 6 questões objetivas assinalando a alternativa correta
- Resolva as 4 questões dissertativas escrevendo no próprio arquivo .md
  - lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com ChatGPT e afins: entregar algo só para ganhar nota não faz você aprender e ficar mais inteligente. Não seja dependente da máquina! (E não se envolva em plágio!)
- ao final, publique seu arquivo lista_02.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas

**1)** Considere o seguinte código JavaScript:

```javascript
//EX01
let p = 10;
let q = 3;
let r = 6;

let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p);
console.log(resultado);

const valores = [3, 6, 9, 12, 15];
let produto = 1;

for (let j = 0; j < valores.length; j++) {
  produto *= valores[j];
}

console.log("O produto dos valores é:", produto);


```
Qual das seguintes alternativas melhor descreve o que o código faz?


**Resposta:**
A) O código avalia a expressão booleana, imprime `true`, calcula o produto dos números na lista e imprime o resultado no console.

______

**2)** O código a seguir contém duas funções que calculam o limite de crédito de um cliente com base nos seus gastos e na renda mensal.

```javascript
// Versão 1 da função de análise de crédito
function analisarCredito1() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    do {
        totalCompras += compras[i];
        i++;
    } while (limite >= totalCompras && i < compras.length);

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```

```javascript
// Versão 2 da função de análise de crédito
function analisarCredito2() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    while (limite >= totalCompras && i < compras.length) {
        totalCompras += compras[i];
        i++;
    }

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```
Se ambas as funções forem executadas com os valores fornecidos, qual será a saída exibida no console?

**Resposta:**
A) Ambas as funções exibirão: 'Seu crédito foi aprovado. Saldo disponível: 400.'

______

**3)** Considere o seguinte trecho de código em JavaScript:
```javascript
//EX03
const idade = 21;

if (idade >= 18 && idade < 60) {
  console.log("Você é um adulto!");
} else if (idade < 18) {
  console.log("Você é menor de idade!");
} else {
  console.log("Você está na melhor idade!");
}
```
Qual das seguintes alternativas melhor descreve o comportamento do código?

**Resposta:**
B) O código verifica se a idade pertence à faixa adulta. Se for, exibe "Você é um adulto!". Caso contrário, verifica se é menor de idade e exibe "Você é menor de idade!". Se nenhuma das condições anteriores for verdadeira, exibe "Você está na melhor idade!".

______

**4)** Qual será o resultado impresso no console após a execução do seguinte código?
```javascript
//EX04
var energiaDisponivel = 1200;
var bateriaExtra = 400;
var consumoDispositivos = [300, 600, 500, 200, 400];

for (var i = 0; i < consumoDispositivos.length; i++) {
    var consumo = consumoDispositivos[i];

    if (consumo <= energiaDisponivel) {
        console.log("Dispositivo " + (i+1) + " ligado. Energia restante: " + (energiaDisponivel - consumo));
        energiaDisponivel -= consumo;
    } else if (consumo <= energiaDisponivel + bateriaExtra) {
        console.log("Dispositivo " + (i+1) + " ligado com bateria extra. Energia restante: " + ((energiaDisponivel + bateriaExtra) - consumo));
        energiaDisponivel = 0;
        bateriaExtra -= (consumo - energiaDisponivel);
    } else {
        console.log("Dispositivo " + (i+1) + " não pode ser ligado. Energia insuficiente.");
    }
}
```

Escolha a opção que responde corretamente:

**Resposta:**

D)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado. Energia restante: 300

Dispositivo 3 ligado com bateria extra. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

______

**5)** Qual é a principal função do método update() em um jogo desenvolvido com Phaser.js?

Escolha a opção que melhor descreve seu propósito:

**Resposta:**

B) O método update() é chamado continuamente a cada quadro (frame) do jogo, sendo usado para atualizar a lógica, movimentação e interações dos objetos na cena.

______

**6)** Qual é o principal objetivo do módulo Matter.js Physics em Phaser.js?

Escolha a opção que responde corretamente:

**Resposta:**

A) Simular física avançada, incluindo corpos rígidos, colisões complexas e interação entre objetos com gravidade e forças.

______

# Questões dissertativas

**7)** Uma loja online deseja implementar um sistema de classificação de pedidos com base no valor total da compra. O sistema deve determinar a categoria de um pedido com as seguintes regras:

```

Pedidos abaixo de R$50,00 → "Frete não disponível!"

Pedidos entre R$50,00 e R$199,99 (inclusive) → "Frete com custo adicional!"

Pedidos de R$200,00 ou mais → "Frete grátis!"
```
Implemente um pseudocódigo que receba o valor total da compra e exiba a classificação correta do frete para o cliente.


**Resposta:**
```
// Função para classificar o frete com base no valor da compra
função classificarFrete(valorCompra)
    
    // Verificação do valor da compra para determinar a categoria do frete
    se valorCompra < 50.00 então
        retornar "Frete não disponível!"
    senão se valorCompra <= 199.99 então
        retornar "Frete com custo adicional!"
    senão
        retornar "Frete grátis!"
    fim se
fim função

// Programa principal
Algoritmo ClassificacaoDeFrete
    // Solicita o valor da compra ao usuário
    Escrever("Digite o valor total da compra: ")
    Ler(valorTotal)
    
    // Chama a função para classificar o frete
    mensagemFrete = classificarFrete(valorTotal)
    
    // Exibe a classificação do frete
    Escrever("Status do frete: ", mensagemFrete)
Fim Algoritmo
```
______

**8)** Considere a implementação da classe base Veiculo em um sistema de modelagem de veículos. Sua tarefa é implementar, utilizando pseudocódigo, as classes derivadas Carro e Moto, que herdam da classe Veiculo, adicionando atributos específicos e métodos para calcular o consumo de combustível de um carro e de uma moto, respectivamente.

```
Classe Veiculo:
Atributos:

modelo
ano
Método Construtor(modelo, ano):

Define os valores dos atributos modelo e ano com os valores passados como parâmetro.
Método CalcularConsumo():
```
Implementação genérica para cálculo de consumo, a ser sobrescrita pelas subclasses.
Agora, implemente as classes Carro e Moto, garantindo que ambas herdem de Veiculo e possuam métodos específicos para calcular o consumo de combustível com base na quilometragem e eficiência do veículo.

**Resposta:**
```
Classe Veiculo

    modelo
    ano

    Método Construtor(modelo, ano)
        this.modelo = modelo
        this.ano = ano
    Fim Método

    Método CalcularConsumo()
        retornar "Método a ser implementado pelas subclasses"  # Implementação genérica a ser sobrescrita
    Fim Método
Fim Classe

Classe Carro herda Veiculo
    potencia
    numeroPortas
    tipoCombustivel
    
    Método Construtor(modelo, ano, potencia, numeroPortas, tipoCombustivel)
        super(modelo, ano)  # Chama o construtor da classe pai
        this.potencia = potencia
        this.numeroPortas = numeroPortas
        this.tipoCombustivel = tipoCombustivel
    Fim Método
    
    Método CalcularConsumo(quilometragem, litrosConsumidos)  # Sobrescrita do método CalcularConsumo
        consumo = quilometragem / litrosConsumidos
        
        # Ajuste de consumo baseado no tipo de combustível
        se this.tipoCombustivel = "gasolina" então
            eficiencia = consumo
        senão se this.tipoCombustivel = "etanol" então
            eficiencia = consumo * 0.7  # Etanol é menos eficiente
        senão se this.tipoCombustivel = "diesel" então
            eficiencia = consumo * 1.2  # Diesel é mais eficiente
        senão se this.tipoCombustivel = "híbrido" então
            eficiencia = consumo * 1.5  # Híbridos são mais eficientes
        fim se
        
        retornar eficiencia
    Fim Método
Fim Classe

Classe Moto herda Veiculo
    # Atributos específicos
    cilindrada
    tipoMotor
    
    Método Construtor(modelo, ano, cilindrada, tipoMotor)
        super(modelo, ano)  # Chama o construtor da classe pai
        this.cilindrada = cilindrada
        this.tipoMotor = tipoMotor
    Fim Método
    
    # Sobrescrita do método CalcularConsumo
    Método CalcularConsumo(quilometragem, litrosConsumidos)
        consumo = quilometragem / litrosConsumidos
        
        # Ajuste de consumo baseado na cilindrada
        se this.cilindrada <= 150 então
            eficiencia = consumo * 1.3  # Motos pequenas são mais eficientes
        senão se this.cilindrada <= 500 então
            eficiencia = consumo * 1.1  # Motos médias
        senão
            eficiencia = consumo * 0.9  # Motos grandes são menos eficientes
        fim se
        
        retornar eficiencia
    Fim Método
Fim Classe
```
______

**9)** Você é um cientista da NASA e está ajudando no desenvolvimento de um sistema de pouso para sondas espaciais em Marte. Seu objetivo é calcular o tempo necessário para que a sonda reduza sua velocidade até um nível seguro para pouso, considerando uma velocidade inicial de entrada na atmosfera marciana e uma taxa de desaceleração constante causada pelo atrito atmosférico e retrofoguetes.

Entretanto, a sonda não pode ultrapassar um tempo máximo de descida para evitar desvios orbitais, nem pode desacelerar além de um limite mínimo, pois isso poderia causar instabilidade no pouso.

Implemente a lógica dessa simulação em pseudocódigo, considerando a seguinte equação para atualização da velocidade:

Considere a fórumla de atualização velocidade:
```
    velocidade = velocidadeInicial - desaceleracao * tempo
```
Seu programa deve determinar quanto tempo será necessário para que a sonda atinja uma velocidade segura de pouso, sem ultrapassar os limites estabelecidos.

**Resposta:**
```
Algoritmo CalcularTempoPouso
    # Definir parâmetros iniciais da sonda
    Ler(velocidadeInicial)       # Velocidade inicial em m/s
    Ler(velocidadeSegura)        # Velocidade segura para pouso em m/s
    Ler(desaceleracao)           # Taxa de desaceleração em m/s²
    Ler(tempoMaximoDescida)      # Tempo máximo permitido para descida em segundos
    Ler(desaceleracaoMinima)     # Taxa mínima de desaceleração permitida em m/s²
    
    # Verificar se a desaceleração é suficiente
    se desaceleracao < desaceleracaoMinima então
        Escrever("ALERTA: Taxa de desaceleração abaixo do mínimo seguro!")
        Escrever("Ajuste os retrofoguetes para aumentar a desaceleração.")
        retornar
    fim se
    
    # Calcular o tempo necessário para atingir a velocidade segura
    # Usando a fórmula: velocidade = velocidadeInicial - desaceleracao * tempo
    # Rearranjando: tempo = (velocidadeInicial - velocidade) / desaceleracao
    tempoNecessario = (velocidadeInicial - velocidadeSegura) / desaceleracao
    
    # Verificar se o tempo necessário excede o tempo máximo permitido
    se tempoNecessario > tempoMaximoDescida então
        Escrever("ALERTA: Tempo de descida excede o limite seguro!")
        Escrever("Tempo necessário: ", tempoNecessario, " segundos")
        Escrever("Tempo máximo permitido: ", tempoMaximoDescida, " segundos")
        Escrever("Aumentar a desaceleração ou ajustar a trajetória de entrada.")
        
        # Calcular a desaceleração necessária para cumprir o tempo máximo
        desaceleracaoNecessaria = (velocidadeInicial - velocidadeSegura) / tempoMaximoDescida
        Escrever("Desaceleração mínima necessária: ", desaceleracaoNecessaria, " m/s²")
    senão
        Escrever("Simulação de pouso bem-sucedida!")
        Escrever("Tempo estimado para atingir velocidade segura: ", tempoNecessario, " segundos")
        
        # Calcular a velocidade em intervalos de tempo para monitoramento
        Escrever("Perfil de desaceleração:")
        para t de 0 até tempoNecessario passo tempoNecessario/10 faça
            velocidadeAtual = velocidadeInicial - desaceleracao * t
            Escrever("Tempo: ", t, " segundos, Velocidade: ", velocidadeAtual, " m/s")
        fim para
        
        Escrever("Distância percorrida durante a desaceleração: ", (velocidadeInicial + velocidadeSegura) * tempoNecessario / 2, " metros")
    fim se
    
    retornar tempoNecessario
Fim Algoritmo
```
______

**10)** Em um sistema de análise financeira, as operações de investimento de uma empresa podem ser representadas por matrizes, onde cada linha representa um tipo de investimento e cada coluna representa um período de tempo.

A seguir, é fornecida a implementação da função SomarMatrizesInvestimento(matrizA, matrizB), que soma os valores de duas matrizes de investimento. Sua tarefa é implementar uma função semelhante, porém que realize a multiplicação das matrizes de investimento, determinando como os investimentos afetam os resultados ao longo do tempo.

```
Função SomarMatrizesInvestimento(matrizA, matrizB):  
    # Verifica se as matrizes têm o mesmo número de linhas e colunas  
    Se tamanho(matrizA) ≠ tamanho(matrizB) então:  
        Retornar "As matrizes não podem ser somadas. Elas têm dimensões diferentes."  
    Senão:  
        linhas <- tamanho(matrizA)  
        colunas <- tamanho(matrizA[0])  
        matrizResultado <- novaMatriz(linhas, colunas)  

        # Loop para percorrer cada elemento das matrizes e calcular a soma  
        Para i de 0 até linhas-1 faça:  
            Para j de 0 até colunas-1 faça:  
                matrizResultado[i][j] <- matrizA[i][j] + matrizB[i][j]  

        Retornar matrizResultado  

# Exemplo de uso da função  
investimentosAno1 <- [[1000, 2000], [1500, 2500]]  
investimentosAno2 <- [[1200, 1800], [1300, 2700]]  

totalInvestimentos <- SomarMatrizesInvestimento(investimentosAno1, investimentosAno2)  
Escrever("Total de investimentos acumulados:")  
ImprimirMatriz(totalInvestimentos)  
```
Agora, implemente a função MultiplicarMatrizesInvestimento(matrizA, matrizB), que multiplica as duas matrizes, simulando o efeito de diferentes fatores de crescimento e impacto financeiro nos investimentos ao longo do tempo.


**Resposta:**
```
Função MultiplicarMatrizesInvestimento(matrizA, matrizB):
    # Verifica se as matrizes são compatíveis para multiplicação
    # O número de colunas da matrizA deve ser igual ao número de linhas da matrizB
    Se tamanho(matrizA[0]) ≠ tamanho(matrizB) então:
        Retornar "As matrizes não podem ser multiplicadas. Dimensões incompatíveis."
    Senão:
        linhasA <- tamanho(matrizA)
        colunasA <- tamanho(matrizA[0])
        colunasB <- tamanho(matrizB[0])
        
        # Cria uma nova matriz para armazenar o resultado
        matrizResultado <- novaMatriz(linhasA, colunasB)
        
        # Loop para realizar a multiplicação das matrizes
        Para i de 0 até linhasA-1 faça:
            Para j de 0 até colunasB-1 faça:
                matrizResultado[i][j] <- 0
                
                # Calcula o produto escalar da linha i da matrizA com a coluna j da matrizB
                Para k de 0 até colunasA-1 faça:
                    matrizResultado[i][j] <- matrizResultado[i][j] + (matrizA[i][k] * matrizB[k][j])
                
        Retornar matrizResultado

# O resultado mostra o valor projetado para cada tipo de investimento (linhas) em cada período de tempo (colunas), considerando os fatores de impacto.
```

