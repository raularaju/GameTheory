# Dilema do Prisioneiro
Este trabalho faz parte de um conjunto de trabalhos feitos para a disciplina "Introdução à Física Estatística na UFMG". Este trabalho em específico tem objetivo de aplicar as ferramentas da Física Estatística no Dilema do Prisioneiro e, assim, entender melhor como as estratégias de cooperação e de deserção (traição) se espalham numa população.

## Problema

O dilema do prisioneiro é um problema clássico da teoria dos jogos que ilustra a dificuldade de dois indivíduos agirem de maneira cooperativa, mesmo quando isso seria do interesse mútuo. A situação típica envolve dois prisioneiros que são presos, mas as evidências contra eles são insuficientes para condená-los por um crime grave. No entanto, eles são acusados de um delito menor, e cada um é mantido isolado, sem comunicação.

Os prisioneiros são confrontados com a escolha de cooperar (ficar em silêncio) ou trair (testemunhar contra o outro). As possíveis combinações de escolhas levam a diferentes resultados. Se ambos cooperarem, recebem penas mais leves. Se ambos traírem, recebem penas mais severas. No entanto, se um cooperar enquanto o outro trair, o cooperador enfrenta a pena mais alta, enquanto o traidor recebe a pena mais leve.

O dilema reside no fato de que, mesmo sendo do interesse mútuo cooperar para obter as penas mais leves, a falta de confiança mútua e a possibilidade de ganhar vantagem pessoal levam os prisioneiros a hesitar em cooperar. Esse dilema é frequentemente usado para analisar situações em que o benefício individual imediato pode entrar em conflito com o benefício conjunto a longo prazo, destacando os desafios da cooperação quando os participantes buscam otimizar seus próprios resultados.

## Modelo a ser considerado
Trataremos aqui de uma versão simplificada do dilema do prisioneiro entre os jogadores A e B descrito pela seguinte matriz de ganhos (matriz de payoff) [4]
| A/B     | Deserta | Coopera |
|---------|---------|---------|
| Deserta | 0       | b       |
| Coopera | 0       | 1       |

Neste caso, se ambos cooperam, ambos recebem a mesma recompensa, 1. Caso ambos
desertem, não há recompensa para nenhum dos dois. No caso de A desertar e B
cooperar, A receberá a recompensa b, fator que indica a tentação à deserção. Nesta
versão simplificada, A não terá nenhum ganho caso B deserte. Para o jogo capturar
adequadamente a essência do dilema do prisioneiro que foi descrita acima, devemos
escolher b>1, ou seja, o ganho para um desertor caso o oponente coopere é maior que
o ganho que ele obteria com a cooperação mútua.
Para levar em conta o fator evolucionário no modelo, assim como o papel
desempenhado pela estrutura espacial das interações entre indivíduos, consideraremos
uma rede quadrada onde cada nó representa um indivíduo que poderá adotar uma de
duas estratégias, ser um cooperador (C) ou ser um desertor (D). Inicialmente cada
indivíduo será classificado como cooperador ou desertor e ao longo da evolução do
sistema poderá trocar sua estratégia de acordo com uma regra a ser estabelecida que
envolve suas interações com sua vizinhança e consigo mesmo. Consideraremos aqui o
modelo para evolução considerado por Szabó e Töke [4]. Neste modelo, um indivíduo
escolhido ao acaso, X, tem o seu ganho total apurado ao considerar sua interação com
os quatro vizinhos mais próximos da rede quadrada, sendo 𝐸! seu ganho total. Caso
este indivíduo esteja cercado apenas por desertores, seu ganho total será nulo se ele for
um desertor e 1 caso seja um cooperador. No caso de ser um desertor cercado por
cooperadores, seu ganho total será 4b, enquanto um cooperador cercado por
cooperadores terá ganho total igual a 5. Dentre seus quatro vizinhos, ele escolherá
aleatoriamente um deles, Y, cujo ganho total é 𝐸". O jogador X irá adotar a estratégia
do jogador Y com probababilidade:


$W = \frac{1}{1 + \exp\left(-\frac{E_y - E_x}{K}\right)}$


onde 𝐾 é um fator que introduz um ruído relacionado à irracionalidade das escolhas.
Para 𝐾 = 0 o jogador X adotará a estratégia de Y caso 𝐸" > 𝐸!. Para valores positivos
de 𝐾, haverá um intervalo de diferenças no ganho total no qual decisões irracionais
poderão ser tomadas, ou seja, X poderá não adotar a estratégia de Y mesmo ela sendo
melhor que a sua. Vamos nos restringir apenas a casos onde 𝐾 < 1.

## Tarefa

Considerando uma configuração inicial aleatória de cooperadores e desertores na rede
evoluiremos o sistema de acordo com o modelo descrito acima. O modelo possui duas
fases absorventes, que são fases onde a dinâmica cessa após todos indivíduos
assumirem o mesmo estado, seja ele cooperativo ou desertor. Para 𝑏 < 𝑏1 a densidade
de cooperadores, 𝑐, será 1, enquanto para 𝑏 > 𝑏2 teremos 𝑐 = 0. Para 𝑏1 < 𝑏 < 𝑏2,
após um tempo suficientemente longo, o sistema irá tender a um estado estacionário
onde a concentração de cooperadores oscilará em torno de um valor constante. Escolha
um valor de 𝐾 no intervalo de 0,02 a 0,5 e simule redes de tamanho 𝐿 = 200 para
valores de 𝑏 entre 1 e 2. Observe a evolução temporal do sistema e a distribuição
espacial de cooperadores e desertores. Estime os valores de 𝑏1 e 𝑏2 para o valor de K
escolhido. Não se esqueça de indicar claramente o valor de K escolhido e de apresentar
os dados que suportam as estimativas de 𝑏# e 𝑏$ assim como a distribuição de
cooperadores e desertores para valores intermediários de 𝑏.

## Referências
[1] M.A. Amaral, “Teoria dos jogos evolucionários e o surgimento da cooperação:
dinâmicas inovativas e jogos mistos” Tese de Doutorado, Departamento de Física, UFMG
(2017). http://lilith.fisica.ufmg.br/posgrad/Teses_Doutorado/decada2010/marco-amaral/MarcoAntonioAmaral-tese.pdf\
[2] E. Pennisi, Science 309, 93 (2005).\
[3] M. A. Nowak e R. M. May, Nature 359, 826 (1992).\
[4] G. Szabo e C. Toke, Physical Review E, 58, 69 (1998).



