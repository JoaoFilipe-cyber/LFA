Identificação do grupo
Campo	Preenchimento
Turma	Ciências da computação
Data	02/09 
Integrante 1	João Filipe Diogo 
Integrante 2	Leandro Cruz
Integrante 3	André Luis 


Questão 01
01-	Existem dois estados
02-	O estado inicial é desligado, pois a lâmpada começa apagada.
03-	A entrada é pressionar o botão
04-	 Desligado  pressionar Ligado = Ligado
05-	Desligado pressionar Ligado pressionar Desligado = desligado 
06-	O sistema possui dois estados e alterna entre eles sempre que o botão é pressionado. Se a lâmpada estiver desligada, o acionamento a liga; se estiver ligada, o acionamento a desliga.

Questão 02
Estado atual	Entrada	Próximo estado
Fechado	pessoa_detectada	Aberto
Fechado	nenhuma_pessoa	Fechado
Aberto	pessoa_detectada	Aberto
Aberto	nenhuma_pessoa	Fechado

Estado inicial = fechado 
              pessoa_detectada
        ┌────────────────────────┐
        │                                                          ▼
     (Fechado) ──────────────> (Aberto)
        ▲                                                          │
        │                                                             │
        └──── nenhuma_pessoa ─────┘	


Parte 02

Exercício 03
01- Alfabeto (\Sigma):** \{0, 1\} — Conjunto de símbolos aceitos pela máquina para processamento.
02- Conjunto de estados (Q):** \{q0, q1\} — Todos os estados possíveis do autômato.
03- Estado inicial:** \q0 — Estado onde a leitura da entrada é iniciada.
04 - Conjunto de estados finais (F):** \{q1\} — Conjunto contendo os estados de aceitação.
05- Símbolos que podem ser lidos:** 0 e 1 — Os símbolos do alfabeto que acionam as transições.
06- Significado do círculo duplo:** Representa um estado final (de aceitação), indicando que a cadeia é válida se o processamento terminar nele.
07- Significado da seta sem origem:** Indica qual é o estado inicial do autômato.

Exercício 04
 
Elemento	Significado
Σ	Alfabeto (conjunto finito de símbolos de entrada)
Q	Conjunto finito de estados
δ	Função de transição de estados
q0	Estado inicial
F	Conjunto de estados finais (de aceitação)

Explicação:
Esses cinco elementos são suficientes porque cobrem completamente a estrutura e a dinâmica do autômato: Σ define as entradas válidas; Q estabelece as configurações internas possíveis; q0 determina o ponto de partida do processamento; δ define como a máquina muda de estado a cada símbolo lido de forma determinística; e F estabelece o critério para decidir se a palavra de entrada é aceita ou rejeitada ao final da leitura.


Exercício 05
O AFD possui:
Σ = {0,1}
Q = {q0,q1,q2}
q0 = inicial
F = {q1}.

Tabela:	
Estado	0	1
q0	q0	q1
q1	q2	q1
q2	q1	q1

1. δ(q0,0)
q0
2. δ(q0,1)
q1
3. δ(q1,0)
q2
4. δ(q2,1)
q1

5. O estado de aceitação é:
q1





Diagrama

             1
        ┌──────────┐
        │          ▼
      (q0) ──1──> ((q1))
       │           │ ▲
       │0          │ │1
       ▼           │ │
      (q0)         ▼ │
                   (q2)
                    │
                    └──1──> ((q1))

q0 --0--> q0
q0 --1--> q1

q1 --0--> q2
q1 --1--> q1

q2 --0--> q1
q2 --1--> q1


exercício 06

a)	q0 --1--> q1
estado final = q1 
Aceita
b)	0011001
q0 --0--> q0
q0 --1--> q1
q1 --0--> q2
q2 --0--> q1
q1 --1--> q1
q1 --0--> q2

estado final = q2
resultado: não aceito

D) 1101
q0 --1--> q1
q1 --1--> q1
q1 --0--> q2
q2 --1--> q1

Estado final: q1

Resultado: ACEITA


E) 000011010
q0 --0--> q0
q0 --0--> q0
q0 --0--> q0
q0 --0--> q0
q0 --1--> q1
q1 --1--> q1
q1 --0--> q2
q2 --1--> q1
q1 --0--> q2

Estado final: q2

Resultado: REJEITA

Cadeia	Estado final	Resultado
1	q1	ACEITA
0011001	q1	ACEITA
010010	q2	REJEITA
1101	q1	ACEITA
000011010	q2	REJEITA



exercício 07

1. Definição Formal do AFD
Conjunto de estados (Q): {q0, q1}
Alfabeto (Σ): {0, 1}
Estado inicial: q0
Conjunto de estados finais (F): {q1}



2. Tabela de Transição (δ)

δ - 0 - 1 
q0 - q0- q1
q1 - q0- q1

3. Diagrama de Estados
       ┌───┐ 0
       │   │
       ▼   │
───► ( q0 ) ────── 1 ──────► (( q1 )) ◄──┐
       ▲                       │         │ 1
       └────────── 0 ──────────┘         │
                                         └──┘


4. Teste de Cadeias
Cadeia "1": q0 →1 q1 (Termina em q1 ∈ F → Aceita)
Cadeia "01": q0 →0 q0 →1 q1 (Termina em q1 ∈ F → Aceita)
Cadeia "101": q0 →1 q1 →0 q0 →1 q1 (Termina em q1 ∈ F → Aceita)
Cadeia "0": q0 →0 q0 (Termina em q0 ∉ F → Rejeitada)
Cadeia "10": q0 →1 q1 →0 q0 (Termina em q0 ∉ F → Rejeitada)


Exercício 8 — Número par de símbolos 1
1. Definição Formal do AFD
O AFD é representado por M = (Σ, Q, δ, q0, F), onde:
•	Σ (Alfabeto): {0, 1}
•	Q (Conjunto de estados): {q0, q1}
o	q0: quantidade par de símbolos '1' lidos (incluindo zero '1's)
o	q1: quantidade ímpar de símbolos '1' lidos
•	q0 (Estado inicial): q0
•	F (Conjunto de estados finais): {q0}
•	δ (Função de transição): definida na tabela abaixo
2. Tabela de Transição (δ)
δ	0	1
 
*q0	q0	q1
q1	q1	q0
3. Diagrama de Estados
           ┌───┐ 0                           			        ┌───┐ 0
           │        │                                			        │        │
           ▼       │                                 			        ▼       │
───► (( q0 )) ────────── 1 ──────────► ( q1 )
             ▲                                                                               │
             └───────────── 1 ──────────────┘


4. Processamento das Cadeias Solicitadas
•	Cadeia ε (vazia): q0 (Permanecem 0 '1's → q0 ∈ F → Aceita)
•	Cadeia "0": q0 →0 q0 (Termina em q0 ∈ F → Aceita)
•	Cadeia "1": q0 →1 q1 (Termina em q1 ∉ F → Rejeitada)
•	Cadeia "11": q0 →1 q1 →1 q0 (Termina em q0 ∈ F → Aceita)
•	Cadeia "101": q0 →1 q1 →0 q1 →1 q0 (Termina em q0 ∈ F → Aceita)
•	Cadeia "1100": q0 →1 q1 →1 q0 →0 q0 →0 q0 (Termina em q0 ∈ F → Aceita)
•	Cadeia "10101": q0 →1 q1 →0 q1 →1 q0 →0 q0 →1 q1 (Termina em q1 ∉ F → Rejeitada)


Exercício 9 — Pelo menos dois zeros consecutivos
Respostas às Perguntas Prévias
1.	O que o estado inicial representa? Representa o estado em que nenhum '0' consecutivo foi encontrado ainda e o último símbolo lido não foi '0' (ou a cadeia está no início).
2.	O que ocorre quando aparece o primeiro 0? A máquina transita para um estado intermediário (q1) que memoriza que exatamente um '0' acabou de ser lido.
3.	O que ocorre quando outro 0 aparece imediatamente depois? A máquina transita para o estado final/de aceitação (q2), pois a sequência "00" foi encontrada.
4.	Depois de encontrar 00, a cadeia pode deixar de ser aceita? Não. Uma vez alcançado o estado de aceitação, qualquer símbolo subsequente (0 ou 1) mantém o autômato nesse mesmo estado.
5.	Quantos estados são necessários? São necessários 3 estados (q0: nenhum '0' recente; q1: um '0' recente; q2: sequência '00' encontrada).
1. Definição Formal (Quíntupla)
M = (Σ, Q, δ, q0, F)
•	Σ (Alfabeto): {0, 1}
•	Q (Conjunto de estados): {q0, q1, q2}
•	q0 (Estado inicial): q0
•	F (Conjunto de estados finais): {q2}
•	δ (Função de transição): descrita na tabela abaixo
2. Tabela de Transição (δ)
δ	0	1
 
q0	q1	q0
q1	q2	q0
*q2	q2	q2

3. Diagrama de Estados
           ┌───┐ 1                                    				          ┌───┐ 0, 1
           │        │                                      				          │        │
           ▼       │                                       				          ▼       │
───► ( q0 ) ────── 0 ──────► ( q1 ) ────── 0 ──────► (( q2 ))
             ▲                                                     │
             └──────── 1 ──────────┘


4. Teste de Cadeias
Cadeias Aceitas:
•	"00": q0 →0 q1 →0 q2 (Termina em q2 ∈ F → Aceita)
•	"001": q0 →0 q1 →0 q2 →1 q2 (Termina em q2 ∈ F → Aceita)
•	"100": q0 →1 q0 →0 q1 →0 q2 (Termina em q2 ∈ F → Aceita)
•	"1001": q0 →1 q0 →0 q1 →0 q2 →1 q2 (Termina em q2 ∈ F → Aceita)
•	"110011": q0 →1 q0 →1 q0 →0 q1 →0 q2 →1 q2 →1 q2 (Termina em q2 ∈ F → Aceita)
•	"0000": q0 →0 q1 →0 q2 →0 q2 →0 q2 (Termina em q2 ∈ F → Aceita)
Cadeias Rejeitadas:
•	ε (vazia): q0 (Termina em q0 ∉ F → Rejeitada)
•	"0": q0 →0 q1 (Termina em q1 ∉ F → Rejeitada)
•	"1": q0 →1 q0 (Termina em q0 ∉ F → Rejeitada)
•	"01": q0 →0 q1 →1 q0 (Termina em q0 ∉ F → Rejeitada)
•	"10": q0 →1 q0 →0 q1 (Termina em q1 ∉ F → Rejeitada)
•	"10101": q0 →1 q0 →0 q1 →1 q0 →0 q1 →1 q0 (Termina em q0 ∉ F → Rejeitada)


Exercício 10 — Semáforo
1. Definição Formal
O semáforo é modelado como um autômato finito M = (Σ, Q, δ, q0, F), onde:
•	Σ (Alfabeto): {tempo} (evento de temporizador que aciona a mudança de cor)
•	Q (Conjunto de estados): {Verde, Amarelo, Vermelho}
•	q0 (Estado inicial): Verde
•	F (Conjunto de estados finais): ∅ (conjunto vazio)
•	δ (Função de transição): definida na tabela abaixo
2. Tabela de Transição (δ)
Estado Atual	Entrada (tempo)	Próximo Estado
 
Verde	tempo	Amarelo
Amarelo	tempo	Vermelho
Vermelho	tempo	Verde
3. Diagrama de Estados
                 ┌──────────── tempo ───────────┐
                 │                                     				    │
                 ▼                                   				    │
───► ( Verde ) ────── tempo ──────► ( Amarelo ) │
              ▲                           				   │          │
              │                        				   │          │
              └──────── tempo ─────── ( Vermelho ) ◄┘


4. Explicação do Funcionamento
O modelo inicia no estado Verde. Cada pulso de entrada tempo aciona a transição sequencial para a próxima cor do ciclo: de Verde para Amarelo, de Amarelo para Vermelho, e de Vermelho retornando ao Verde, garantindo a repetição contínua e cíclica do semáforo.
5. Discussão e Justificativa sobre Estados de Aceitação
Em um sistema reativo ou de controle contínuo como um semáforo, não faz sentido prático definir estados de aceitação (F = ∅).
Justificativa: Autômatos finitos tradicionais com estados de aceitação são projetados para reconhecer e classificar linguagens (decidir se uma cadeia de entrada é válida ao chegar ao fim). Um semáforo, por outro lado, é um sistema executado indefinidamente em loop contínuo, cuja função é alternar estados operacionais sem um ponto final de parada ou validação de "aceite/rejeição".


Exercício 11 — Sistema de login
Resposta da Pergunta Prévia
Não, apenas os estados Aguardando, Autenticado e Bloqueado NÃO são suficientes.
Justificativa: Autômatos finitos não possuem memória interna além do seu próprio estado atual. Para contar até três tentativas incorretas, o sistema precisa de estados distintos que registrem exatamente quantas falhas já ocorreram (0, 1 ou 2 erros). Um único estado "Aguardando" não consegue diferenciar se o usuário errou 0, 1 ou 2 vezes, impossibilitando o bloqueio preciso na terceira tentativa incorreta.
1. Definição Formal do AFD
M = (Σ, Q, δ, q0, F)
•	1. Todos os estados necessários (Q):
o	Tentativa_0 (q0): Estado inicial (0 erros cometidos).
o	Tentativa_1 (q1): 1 erro cometido.
o	Tentativa_2 (q2): 2 erros cometidos.
o	Autenticado (qA): Usuário autenticado com sucesso.
o	Bloqueado (qB): Sistema bloqueado após 3 erros consecutivos.
•	2. Alfabeto de entrada (Σ): {senha_correta, senha_incorreta}
•	3. Estado inicial: Tentativa_0 (q0)
•	4. Estados finais (F): {Autenticado}
2. Tabela de Transições (δ)
Estado Atual	senha_correta	senha_incorreta
 
Tentativa_0	Autenticado	Tentativa_1
Tentativa_1	Autenticado	Tentativa_2
Tentativa_2	Autenticado	Bloqueado
*Autenticado	Autenticado	Autenticado
Bloqueado	Bloqueado	Bloqueado

4. Comportamento Após Autenticação e Bloqueio
•	Após a Autenticação (Autenticado): O usuário ganha acesso. Quaisquer entradas subsequentes (senha_correta ou senha_incorreta) mantêm o sistema no estado Autenticado (estado poço de sucesso).
•	Após o Bloqueio (Bloqueado): O sistema impede o acesso permanentemente. Quaisquer tentativas subsequentes de login são ignoradas e mantêm o sistema no estado Bloqueado (estado poço de falha).
Exercício 12 — Implementação e testes
AFD Escolhido: Resolução baseada no Exercício 7 (Autômato Finito Determinístico que reconhece cadeias sobre o alfabeto Σ = {0, 1} que terminam com o símbolo '1').
1. Breve Explicação do AFD
O autômato possui dois estados para monitorar o último caractere lido da entrada:
•	q0 (Estado Inicial): Representa o estado em que a cadeia está vazia ou o último caractere lido foi '0'.
•	q1 (Estado Final / Aceitação): Representa o estado em que o último caractere lido foi '1'.
2. Definição Formal e Estrutura no JFLAP
•	Estados: {q0, q1}
•	Estado Inicial: q0
•	Estados Finais: {q1}
•	Transições:
o	q0 com entrada '0' → permanece em q0
o	q0 com entrada '1' → vai para q1
o	q1 com entrada '0' → retorna para q0
o	q1 com entrada '1' → permanece em q1






3. Representação do Diagrama
             ┌─┐ 0
             │   │
             ▼  │
───► ( q0 ) ────── 1 ──────► (( q1 )) ◄──┐
       ▲                   				│               │ 1
       └────────── 0 ──────────┘               │
                                                                                        └──┘


4. Tabela de Testes
Para realizar os testes no JFLAP, utilize a funcionalidade Input → Multiple Run.
Cadeia	Resultado esperado	Resultado no JFLAP	Conferência
 
1	Aceita	Accept	OK
01	Aceita	Accept	OK
101	Aceita	Accept	OK
0	Rejeitada	Reject	OK
10	Rejeitada	Reject	OK
1110	Rejeitada	Reject	OK


Exercício 13 — Crie seu próprio problema: Catraca de Acesso
1. Descrição do Problema e Suas Regras
Modelagem do funcionamento de uma catraca eletrônica de acesso:
•	A catraca inicia travada (Bloqueada).
•	Quando o usuário insere um cartão válido, ela passa para o estado Liberada.
•	Se o usuário passar e girar a catraca, ela libera a passagem e retorna ao estado Bloqueada.
•	Se o usuário tentar girar a catraca enquanto ela estiver Bloqueada, a tentativa é rejeitada e ela permanece Bloqueada.
•	Se o usuário inserir um cartão válido enquanto ela já estiver Liberada, o sistema mantém o estado Liberado.
2, 3 e 6. Definição Formal M = (Σ, Q, δ, q0, F)
M = (Σ, Q, δ, q0, F), onde:
•	Σ (Alfabeto de entradas): {cartao, giro}
o	cartao: Inserção ou leitura de cartão válido.
o	giro: Empurrar ou girar o braço da catraca.
•	Q (Conjunto de estados):
o	Bloqueada (q0): Catraca travada aguardando leitura de cartão.
o	Liberada (q1): Catraca destravada aguardando a passagem.
•	q0 (Estado inicial): Bloqueada
•	F (Conjunto de estados finais): {Bloqueada} (O ciclo de uso seguro é concluído quando a catraca retorna ao estado bloqueado/inicial).
4. Tabela de Transições (δ)
Estado Atual	cartao	giro
 
*Bloqueada (q0)	Liberada (q1)	Bloqueada (q0)
Liberada (q1)	Liberada (q1)	Bloqueada (q0)

5. Diagrama de Estados (AFD)
               ┌────── cartao ──────┐
               │                                              │
               ▼                  	                 │
──► (( Bloqueada )) ──── cartao ───► ( Liberada )
         ▲                                                                      │
         └───────────── giro ─────────┘


7. Teste de Sequências de Entrada
Sequência	Processamento / Transição de Estados	Resultado
 
cartao, giro	q0 → cartao → q1 → giro → q0	Aceita
giro	q0 → giro → q0	Rejeitada (permaneceu travada)
cartao, cartao, giro	q0 → cartao → q1 → cartao → q1 → giro → q0	Aceita
cartao	q0 → cartao → q1	Rejeitada (ficou liberada sem girar)
cartao, giro, giro	q0 → cartao → q1 → giro → q0 → giro → q0	Aceita no 1º giro, rejeita o 2º giro
8. Por que o modelo é determinístico?
O modelo é um Autômato Finito Determinístico (AFD) pelos seguintes motivos:
1.	Para cada estado do conjunto Q (Bloqueada ou Liberada) e para cada símbolo de entrada do alfabeto Σ (cartao ou giro), existe exatamente uma única transição de saída definida na função δ.
2.	Não existem transições vazias (ε-transições) ou não-determinísticas que permitam ao sistema escolher entre múltiplos estados para a mesma entrada.
9. Conclusão sobre o Aprendizado
A realização deste exercício demonstrou a aplicação prática da Teoria dos Autômatos na modelagem de sistemas físicos e computacionais do dia a dia. Compreendemos que abstrair um comportamento real em estados e transições determinísticas garante a previsibilidade e a segurança do software de controle, assegurando que o dispositivo responda corretamente a qualquer sequência de eventos operacionais.

