================================================================================
                           nEon_decK - REGRAS DO JOGO
================================================================================

--------------------------------------------------------------------------------
                              OBJETIVO DO JOGO
--------------------------------------------------------------------------------

O objetivo é ser o primeiro jogador a descartar todas as suas cartas.

--------------------------------------------------------------------------------
                              COMPOSIÇÃO DO BARALHO
--------------------------------------------------------------------------------

O baralho contém variação de quantidade cartas conforme progresso, desbloqueio e configuração:

CARTAS VALORES (quantidade com mínimo de 2 temas seguindo conforme configuração/desbloqueio):
- Valores de 0 a 9 de cada tema
- Uma carta "0" por tema
- Duas cartas de cada tema dos valores restantes

CARTAS PODER:
- Pular (⏭): 2 por tema
- Mudar rotação (⟲): 2 por tema
- Obriga próximo a comprar duas cartas (+2): 2 por tema

CARTAS POÇÃO (desbloqueio conforme progresso):
- Poção escolha de tema
- Poção escolha de tema e obriga próximo a comprar 4 cartas
- Poção de troca: troca de mão com o próximo

CARTAS CASTIGO (desbloqueio conforme progresso):
- Obriga próximo a descatar 2 cartas conectadas
- Obriga próximo a descartar 4 cartas conectadas
--------------------------------------------------------------------------------
                         PREPARAÇÃO DO JOGO
--------------------------------------------------------------------------------

1. EMBARALHAMENTO:
   - Todas as cartas são embaralhadas usando o algoritmo Fisher-Yates,
     garantindo uma distribuição aleatória uniforme.

2. DISTRIBUIÇÃO:
   - Cada jogador recebe 7 cartas.
   - As cartas são distribuídas uma por vez, em rodadas, até que cada
     jogador tenha suas 7 cartas.

3. MONTE DE COMPRAS:
   - As cartas restantes formam o monte de compras, posicionado virado
     para baixo no centro da mesa.

4. CARTA INICIAL:
   - Uma carta é virada do monte para iniciar o monte de descarte.
   - Se a carta inicial for um Poção ou carta de Castigo, outra carta é
     escolhida até que seja uma carta numerada.

5. INÍCIO:
   - O primeiro jogador começa a partida.
   - A direção inicial é horária (sentido positivo).

--------------------------------------------------------------------------------
                           FLUXO DO JOGO
--------------------------------------------------------------------------------

TURNO DO JOGADOR:

1. O jogador deve jogar uma carta que corresponda à carta do topo do
   monte de descarte por:
   - TEMA: mesma cor da carta no topo
   - VALOR/NÚMERO: mesmo número ou símbolo
   - PODER/POÇÃO/CASTIGO: cartas especiais podem ser jogadas a qualquer momento

2. Se o jogador não tiver carta jogável:
   - Deve comprar UMA carta do monte de compras
   - Se a carta comprada puder ser jogada, pode jogá-la imediatamente
   - Se não puder jogar, passa a vez para o próximo jogador
   - REGRA: Só é permitido comprar uma carta por turno

3. Após jogar uma carta, a vez passa para o próximo jogador
   (respeitando a direção atual do jogo).

REPOSIÇÃO DO MONTE:
- Quando o monte de compras acabar, as cartas do monte de descarte
  (exceto a carta do topo) são embaralhadas e formam um novo monte
  de compras.

--------------------------------------------------------------------------------
                        CARTAS DE AÇÃO (COLORIDAS)
--------------------------------------------------------------------------------

PULAR (⏭)
- O próximo jogador perde a vez.
- A vez passa para o jogador seguinte ao que foi pulado.
- Só pode ser jogada sobre carta da mesma cor ou outra carta Pular.

Rotação Inversa (⟲)
- Inverte a direção do jogo.
- Se estava indo no sentido horário, passa a ir no anti-horário e vice-versa.
- Em partida com 2 jogadores, funciona como "Pular".
- Só pode ser jogada sobre carta da mesma cor ou outra carta Inverter.

Obriga Compra duas cartas (+2)
- O próximo jogador deve comprar 2 cartas e perde a vez.
- Só pode ser jogada sobre carta da mesma TEMA ou outra carta +2.

   *** REGRA DE ACÚMULO DO +2 ***
   - Se o próximo jogador tiver uma carta +2, ele pode jogá-la em vez
     de comprar, passando a punição acumulada (+4) para o jogador seguinte.
   - O acúmulo continua até que um jogador não tenha +2 para jogar.
   - O jogador que não puder jogar +2 compra TODAS as cartas acumuladas.
   
   Exemplo: Jogador A joga +2. Jogador B tem +2 e joga. Jogador C não
   tem +2 e deve comprar 4 cartas.

--------------------------------------------------------------------------------
                         CARTAS ESPECIAIS
--------------------------------------------------------------------------------

TROCA DE MÃO (⇄)
- Carta coringa: pode ser jogada a qualquer momento.
- O jogador que a joga escolhe outro jogador.
- Ambos trocam TODAS as suas cartas entre si.
- Estratégia: Use quando tiver muitas cartas e outro jogador tiver poucas,
  ou para atrapalhar um adversário prestes a vencer.



--------------------------------------------------------------------------------
                           FIM DO JOGO
--------------------------------------------------------------------------------

VITÓRIA:
- O primeiro jogador a descartar todas as suas cartas vence a partida.
- O jogo termina imediatamente quando isso acontece.

DICA "ONE":
- Quando um jogador ficar com apenas 1 carta, deve ficar atento!
- Os outros jogadores devem tentar impedi-lo de vencer.

--------------------------------------------------------------------------------
                        COMPORTAMENTO DOS BOTS
--------------------------------------------------------------------------------

Os jogadores controlados pelo computador (Bots) seguem esta lógica:

1. PRIORIDADE DE JOGADA:
   - Cartas de Ação (Pular, Inverter, +2)
   - Cartas VAlores
   - Cartas Especiais (Troca, Renove) - apenas com 5+ cartas
  

2. ESCOLHA DE TEMA (ao jogar PODER):
   - O Bot escolhe o tema mais frequente em sua mão.

3. TROCA DE MÃO:
   - O Bot sempre escolhe o jogador com MENOS cartas para trocar.

--------------------------------------------------------------------------------
                           DICAS ESTRATÉGICAS
--------------------------------------------------------------------------------

• Guarde cartas PODER para momentos críticos.
• Use descarte de repetições, tentando manter maior variação de possibilidades na mão.
• Observe quantas cartas os adversários têm.
• A carta "Troca de Mão" pode virar o jogo completamente.
• Cartas de PODER são valiosas para controlar o ritmo do jogo.

================================================================================
                     © nEon_decK - Todos os direitos reservados
                        Contato: faleconosco@neonone.com.br
================================================================================
