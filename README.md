# NetLogoIIA

Introdução

O NetLogo é um software que simula um ambiente (2D ou 3D) onde os agentes assumem o papel determinante. Através do software fornecido é possível programar o comportamento dos agentes e algumas propriedades da interface e do ambiente
O ambiente é constituído pelos Limpadores, Comilões, lixo, comida e depósitos. Os comilões têm de comer as células verdes, que simboliza a comida (e fornece energia) para se manterem vivos e manterem-se afastado das células vermelhas e amarelas (lixo tóxico e normal, respetivamente) para reduzirem a probabilidade de morrer, os comilões têm o principal objetivo de “apanhar” o lixo e “despejá-lo” nos depósitos.
Este ambiente que criámos desafia e causa impacto nos agentes, mediante as escolhas que o utilizador faz na interface, regulando algumas variáveis e número de agentes, permitindo-nos responder a algumas questões pertinentes.
A simulação termina quando todos os Limpadores e os Comilões “morrem”. 


Interface Gráfica

Criámos a interface gráfica com o objetivo de ser intuitiva, versátil e informativa. Conseguimos alterar os valores iniciais dos comilões, dos limpadores, do número de depósitos de lixo, da energia configurável, das células vermelhas, das células verdes, das células amarelas, da capacidade máxima que os limpadores transportam de lixo e da comida. Para além disto, conseguimos ter informação dos valores que variam ao longo da simulação através do monitor e do gráfico.


Ambiente

O ambiente é um mapa 2D que possui as coordenadas X e Y. O ambiente é constituído por “patches”. Desde a inicialização até ao fim da função “go” aparecem apenas “patches” como as células pretas, verdes (comida), amarelas (lixo normal), vermelhas (lixo tóxico), azuis (contentores de lixo), cor-de-laranja (Limpadores) e cor de rosa (Comilões). 
Agentes

Os agentes têm as seguintes funções e características:
Comilões – Comer as células verdes para obterem a energia que os vai manter vivos. Quando estão a uma célula da comida (isto é, quando a comida está à esquerda, à direita ou à frente) dirigem-se à mesma, efetuando rotações de 90ª ou avançando uma célula, mas quando estão nas mesmas condições com o lixo, fogem, usando rotações para desviarem o seu trajeto e, inevitavelmente, perdendo energia.
Limpadores – Têm o objetivo de guardar o lixo até o largarem no depósito quando atingirem a capacidade máxima. Para “sobreviverem” têm de manter a energia com níveis superiores a 0, tal como os comilões. Basicamente, “comem” e fazem depósitos de lixo para ganhar energia.
Alerto também para o facto das células de comida e de lixo serem repostas ao longo da simulação permitindo que o número inicial das mesmas se mantenha.


Funções e variáveis

Função Setup: Na função “setup” começamos por limpar o ecrã e criamos as “patches” e as “turtles”. No final, colocamos o contador de “ticks” a zero.
Função go: Verifica se existem “turtles” no ambiente (se existirem, continua a executar o código, se não a execução para) e depois executa um tick. Há, de seguida uma, verificação se alguma “turtle” tem energia igual ou inferior a 0 e, por fim, crescem as “patches” em falta, se assim for necessário. A função acaba com a maioria das funções dentro do respetivo “ask”.
Função mover_comiloes: Dá capacidade para os comilões se moverem para a frente e para rodarem 90ª para a direita ou para a esquerda.
Função mover_limpadores: Dá capacidade para os comilões se moverem para a frente e para rodarem 90ª para a direita ou para a esquerda.
Funções Ahead_turtles, left_turtles, right_turtles: Servem como apoio às funções mover_comiloes e mover_limpadores.
Função comiloesComem: Os comilões quando estiverem em cima de uma célula verde substitui-a por uma preta e incrementa a sua energia.
Função limpadores_comem: Quando os limpadores estiverem em cima de uma célula verde substituem por uma célula preta e a sua energia é incrementada, quando estiverem em cima de uma célula amarela ou vermelha fazem a substituição por uma célula preta e aumentam o número de lixo guardado.
Função regrow: Garante que o nível de células verdes, amarelas e vermelhas se mantêm ao longo da simulação.
Função deitarLixo: Quando a capacidade máxima dos limpadores guardarem lixo atinge o limite e a cor do patch atual é azul, os contentores de resíduos é incrementado com a atual capacidade máxima, a energia incrementada é igual a 10 vezes o valor do lixo da capacidade máxima e o numero de lixo que os limpadores têm atualmente passa a zero.  
Função guardarLixo: Se os Limpadores estiverem numa célula amarela ou azul, a célula passa a ter a cor preta e o lixo é incrementado em 1 ou em 2, respetivamente.
Função Percecao_Comiloes: Ao ser detetada uma célula verde à frente, à esquerda ou à direita, será efetuado um avanço de uma célula, ou ruma rotação de 90º graus para a esquerda, ou uma rotação de 90º graus para a direita, respetivamente. Se a célula detetada for amarela ou vermelha haverá sempre uma rotação e uma perda de energia de 5% ou 10%, respetivamente.
Função Percecao_Limpadores: Leva os Limpadores em direção às células de cor verde, amarela e vermelha. Se estiverem à frente, avançam uma casa, se estiverem ao lado direito, roda 90ºgraus para a direita.
Função death: Se as turtles tiverem energia maior ou igual a 0, “morrem”.

comiloes – nome da “turtle” que representa os Comilões.
limpadores – nome da “turtle” que representa os Limpadores.
energy – Memória das “turtles”.
nLixo – Número de lixo na posse dos Limpadores .
ResiduosDepositados – Total de resíduos depositados.
celG – Variável global para guardar o valor inicial das células verdes.
celY - Variável global para guardar o valor inicial das células amarelas.
celR - Variável global para guardar o valor inicial das células vermelhas..
ncomida – variável que identifica as “patches” da cor verde, as da comida.
NumeroComiloesInicial – Variável que representa o número de comilões iniciais no ecrã.
NumeroLimpadoresInicial - Variável que representa o número de comilões iniciais no ecrã.
NumeroLocaisDepositos - Variável que representa o número de depósitos iniciais no ecrã.
energia_configurável – Quantidade de energia que pode ser adicionada por “patch” depois da inicialização do setup.
celulasAmarelas – Células que representam o lixo normal.
celulasVermelhas – Células que representam o lixo tóxico.
capMax – Capacidade máxima de lixo que os limpadores podem transportar.


Análise das Simulações

		A nossa análise baseou-se no estudo da sobrevivência dos comilões e dos limpadores variando a percentagem de comida existente no ecrã entre 0%, 10% e 20% e o número de agentes entre 25 e 50, mas com condições base, nas quais a energia é igual a 100, existe um valor de lixo, tanto tóxico, como normal, igual a 7%, os limpadores apresentam uma capacidade máxima de 5 resíduos e apenas existem 5 depósitos disponíveis para os limpadores.
		Com base no estudo feito, estando as simulações limitadas as 10.000 “ticks”, podemos concluir que, independentemente do número de agentes, sempre que existe uma percentagem de comida igual a 10, ou a 20 porcento, os comilões têm uma taxa de sobrevivência nula, isto é, morrem sempre, enquanto que os limpadores acabam sempre por sobreviver todos, concluindo que estes últimos acabam sobrevivendo devido ao ganho de energia por parte do lixo depositado, indo sempre até ao limitador de iterações.
	Quando a percentagem de comida é igual a 0%, ambos os agentes acabam por morrer ao fim de poucas iterações. 


Conclusão
		Neste trabalho, criámos um ambiente em Netlogo, onde estavam inseridas “patches”, como o lixo, tanto o residual, como o normal, a comida e os depósitos, e “turtles” que eram os limpadores e os comilões. 
		Neste nosso ambiente, criado a partir de código em Netlogo, os limpadores tinham o objetivo de limpar o ambiente em que estavam inseridos, podendo também comer, enquanto que os comilões comiam.
		Depois das simulações ao ambiente estudando a taxa de sobrevivência dos agentes, mantendo valores fixos em todos os parâmetros, exceto na percentagem de comida e nos números inicial de agentes, podemos concluir que, quando ao valor da comida é diferente de 0, os limpadores conseguem sempre sobreviver, ao contrário dos comilões que morrem sempre, nunca indo além das 10000 iterações, à qual as simulações tão limitadas. Quando a percentagem de comida é igual a 0, ambos agentes morrem mais rapidamente em poucas iterações.
		Os resultados obtidos deram para confirmar que a mudança de variáveis altera de forma significante os resultados obtidos na simulação.
		Na realização do trabalho tivemos dificuldades relativamente à perceção dos alimentos por parte dos agentes, mas também no que toca à simulação de resultados, mas mesmo assim os agentes estão a trabalhar conforme foi pedido no enunciado.

