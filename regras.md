================================================================================
                           nEon_onE - REGRAS DO JOGO
================================================================================

--------------------------------------------------------------------------------
                              OBJETIVO DO JOGO
--------------------------------------------------------------------------------

O objetivo é ser o primeiro jogador a descartar todas as suas cartas.

--------------------------------------------------------------------------------
                              COMPOSIÇÃO DO BARALHO
--------------------------------------------------------------------------------

O baralho contém 110 cartas no total:

CARTAS NUMERADAS (76 cartas):
- Números de 0 a 9 nas cores: Vermelho, Azul, Verde e Amarelo
- Uma carta "0" por cor (4 cartas)
- Duas cartas de cada número 1-9 por cor (72 cartas)

CARTAS DE AÇÃO (24 cartas):
- Pular (⏭): 2 por cor = 8 cartas
- Inverter (⟲): 2 por cor = 8 cartas
- Compra +2 (+2): 2 por cor = 8 cartas

CARTAS CORINGA (10 cartas):
- Coringa Colorido (★): 4 cartas
- Coringa Compra +4 (+4): 4 cartas
- Troca de Mão (⇄): 1 carta
- Renove suas Cartas (🔄): 1 carta

--------------------------------------------------------------------------------
                         PREPARAÇÃO DO JOGO
--------------------------------------------------------------------------------

1. EMBARALHAMENTO:
   - Todas as 110 cartas são embaralhadas usando o algoritmo Fisher-Yates,
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
   - Se a carta inicial for um Coringa ou carta de Ação, outra carta é
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
   - COR: mesma cor da carta no topo
   - VALOR/NÚMERO: mesmo número ou símbolo
   - CORINGA: cartas coringa podem ser jogadas a qualquer momento

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

INVERTER (⟲)
- Inverte a direção do jogo.
- Se estava indo no sentido horário, passa a ir no anti-horário e vice-versa.
- Em partida com 2 jogadores, funciona como "Pular".
- Só pode ser jogada sobre carta da mesma cor ou outra carta Inverter.

COMPRA +2 (+2)
- O próximo jogador deve comprar 2 cartas e perde a vez.
- Só pode ser jogada sobre carta da mesma cor ou outra carta +2.

   *** REGRA DE ACÚMULO DO +2 ***
   - Se o próximo jogador tiver uma carta +2, ele pode jogá-la em vez
     de comprar, passando a punição acumulada (+4) para o jogador seguinte.
   - O acúmulo continua até que um jogador não tenha +2 para jogar.
   - O jogador que não puder jogar +2 compra TODAS as cartas acumuladas.
   
   Exemplo: Jogador A joga +2. Jogador B tem +2 e joga. Jogador C não
   tem +2 e deve comprar 4 cartas.

--------------------------------------------------------------------------------
                           CARTAS CORINGA
--------------------------------------------------------------------------------

CORINGA COLORIDO (★)
- Pode ser jogada a qualquer momento, independente da cor ou valor no topo.
- O jogador que a joga escolhe a nova cor ativa.
- Não possui cor própria (é "wild").

CORINGA COMPRA +4 (+4)
- Pode ser jogada a qualquer momento.
- O jogador escolhe a nova cor ativa.
- O próximo jogador deve comprar 4 cartas e perde a vez.

   *** REGRA DE ACÚMULO DO +4 ***
   - Se o próximo jogador tiver uma carta +4, ele pode jogá-la em vez
     de comprar, passando a punição acumulada (+8) para o jogador seguinte.
   - O acúmulo continua até que um jogador não tenha +4 para jogar.
   - O jogador que não puder jogar +4 compra TODAS as cartas acumuladas.

   *** INTERAÇÃO ENTRE +2 e +4 ***
   - Cartas +2 e +4 NÃO se combinam entre si.
   - Um +2 só pode ser respondido com outro +2.
   - Um +4 só pode ser respondido com outro +4.

--------------------------------------------------------------------------------
                         CARTAS ESPECIAIS
--------------------------------------------------------------------------------

TROCA DE MÃO (⇄)
- Carta coringa: pode ser jogada a qualquer momento.
- O jogador que a joga escolhe outro jogador.
- Ambos trocam TODAS as suas cartas entre si.
- Estratégia: Use quando tiver muitas cartas e outro jogador tiver poucas,
  ou para atrapalhar um adversário prestes a vencer.
- Após a troca, o jogador escolhe a nova cor ativa.

RENOVE SUAS CARTAS (🔄)
- Carta coringa: pode ser jogada a qualquer momento.
- O jogador que a joga descarta TODAS as suas cartas atuais.
- As cartas descartadas são embaralhadas no monte de compras.
- O jogador compra a MESMA QUANTIDADE de cartas que descartou.
- Estratégia: Use quando tiver uma mão ruim ou precisar de novas opções.
- Após renovar, o jogador escolhe a nova cor ativa.

--------------------------------------------------------------------------------
                           FIM DO JOGO
--------------------------------------------------------------------------------

VITÓRIA:
- O primeiro jogador a descartar todas as suas cartas vence a partida.
- O jogo termina imediatamente quando isso acontece.

DICA "UNO":
- Quando um jogador ficar com apenas 1 carta, deve ficar atento!
- Os outros jogadores devem tentar impedi-lo de vencer.

--------------------------------------------------------------------------------
                        COMPORTAMENTO DOS BOTS
--------------------------------------------------------------------------------

Os jogadores controlados pelo computador (Bots) seguem esta lógica:

1. PRIORIDADE DE JOGADA:
   - Cartas de Ação (Pular, Inverter, +2)
   - Cartas Numeradas
   - Cartas Especiais (Troca, Renove) - apenas com 5+ cartas
   - Coringa +4
   - Coringa Colorido

2. ESCOLHA DE COR (ao jogar coringa):
   - O Bot escolhe a cor mais frequente em sua mão.

3. TROCA DE MÃO:
   - O Bot sempre escolhe o jogador com MENOS cartas para trocar.

--------------------------------------------------------------------------------
                           DICAS ESTRATÉGICAS
--------------------------------------------------------------------------------

• Guarde cartas Coringa para momentos críticos.
• Use +2 e +4 estrategicamente para acumular punições.
• Observe quantas cartas os adversários têm.
• A carta "Troca de Mão" pode virar o jogo completamente.
• Use "Renove suas Cartas" quando sua mão estiver desfavorável.
• Cartas de Ação são valiosas para controlar o ritmo do jogo.

================================================================================
                     © nEon_onE - Todos os direitos reservados
                        Contato: faleconosco@neonone.com.br
================================================================================
