# Projeto-APC

Lista de Oferta
A Coordenação de um curso é uma tarefa difícil, ainda mais com um sistema como o SIGAA gerenciando os dados... E se algumas funcionalidades fossem agregadas? Poder verificar as distribuição de alunos e as atividades dos docentes tornariam a experiência com o sistema muito melhor. Capaz de atender esta demanda, a turma de APC resolveu implementar o ☹️☹️ (vulgarmente conhecido como SAAD - Sistema de Acompanhamento e Análise Docente), uma plataforma flexível que proverá soluções para todos!

Implemente as seguintes funcionalidades para os comandos indicados:

carga DOCENTE lista a carga horária do docente de nome DOCENTE, apresentando todas as disciplinas e turmas em ordem alfabética do nome da disciplina. Ao final, apresenta a carga horária total de aulas do docente e a média de horas por aluno (com precisão de 2 casas decimais), considerando apenas as disciplinas com pelo menos 6 discentes matriculados. Utilize a função print com .2f para precisão de 2 casas decimais.
disciplina D lista as disciplinas (item) com turmas que têm pelo menos D (≥0) docentes como responsáveis. Mostra apenas as turmas que atendem esta condição, e as lista em ordem alfabética, indicando quantos docentes estão efetivamente registrados.
leia ARQ carrega na memória as informações no arquivo ARQ para processamento. O arquivo é um CSV (codificado em UTF-8) que lista a oferta de turmas de um departamento.
matriculas COD1 COD2 ... CODN calcula a quantidade total de matriculados em cada turma das disciplinas fornecidas (COD) e as mostra em ordem decrescente (a ordem alfabética do nome da disciplina deve ser usada para desempate). Há um espaço entre cada elemento do comando.
FIM interrompe a execução do programa.
Entrada
A entrada consiste de uma quantidade indeterminada de instruções, dentre as 4 primeiras descritas acima, apresentadas uma por linha, seguidas da instrução de finalização do processamento.

Saída
A saída consiste na apresentação das informações, quando solicitadas/necessárias. Todo nome de disciplina deve ser seguido de seu código, entre parênteses. No caso da listagem dos comandos carga e disciplina, todo use o prefixo " * " (espaço - asterisco - espaço) para cada disciplina. Para carga, acrescente 5 espaços antes de cada turma; e para disciplina, mostre a quantidade de docentes entre parênteses e liste as turmas separadas por vírgula e espaço. Caso não seja possível encontrar um DOCENTE, um COD ou uma turma com D docentes, apresente a mensagem "No hay [DOCENTE|COD|D]...".

Observações
Muita atenção aos exemplos, eles mostram o funcionamento e a formatação dos comandos.

É garantido que todo arquivo que for solicitado nos testes existe e está corretamente formatado. Você pode acessá-los aqui: arquivos_csv.zip. Arquivos diferentes pode ser utilizados em um mesmo caso de teste.

Todo COD tem o formato XXX####, onde XXX identifica a unidade responsável pela oferta e #### o identificador da disciplina. Por exemplo, CIC0004 é Algoritmos e Programação de Computadores, que é ofertada pelo Departamento de Ciência da Computação.

A ordenação de elementos é um processo simples, além do método sort apresentado na referência, é possível usar sorted (melhor ainda, veja um pouco mais sobre ordenação).

No primeiro exemplo, nota-se que a média de alunos atendidos considera apenas as turmas A de INTRODUCAO A INTELIGENCIA ARTIFICIAL e de TEORIA E APLICAÇÃO DE GRAFOS (as demais turmas não têm alunos suficientes matriculados).


For example:

Input	Result
leia CIC20211.csv
carga DIBIO LEANDRO BORGES
FIM

DIBIO LEANDRO BORGES:
 * INTRODUCAO A INTELIGENCIA ARTIFICIAL (CIC0135):
     Turma A: 60h (33 alunos)
 * PROJETO FINAL EM ENGENHARIA DE COMPUTAÇÃO 2 (CIC0356):
     Turma DL: 90h (1 alunos)
 * TEORIA E APLICAÇÃO DE GRAFOS (CIC0199):
     Turma 02: 60h (1 alunos)
     Turma A: 60h (27 alunos)
 * TRABALHO DE GRADUAÇÃO 2 (CIC0167):
     Turma DL: 60h (1 alunos)
     
[Carga total considerada: 120h (2.00h/aluno)]
carga ANDRE DA COSTA DRUMMOND
FIM
No hay ANDRE DA COSTA DRUMMOND...
leia ENM20211.csv
disciplina 2
FIM
Turmas com pelo menos 2 docentes:
 * DESENHO MECANICO ASSISTIDO POR COMPUTADOR 1 (ENM0131): 01A (2), 04 (2)
 * ENERGIA E AMBIENTE (DPG0782): 03 (2)
 * FENOMENOS DE TRANSPORTE (ENM0080): E (2), F (2), G (2), H (2), I (2)
 * INTRODUCAO A ENGENHARIA MECATRONICA (ENM0133): A (3)
 * MECANICA DOS FLUIDOS 2 (ENM0082): C (2), D (2)
 * TÓPICOS AVANÇADOS EM SISTEMAS MECATRÔNICOS 1 (DPG0384): 02 (2)
 * VIBRACOES 1 (ENM0109): A (2), B (2)
leia ENM20211.csv
disciplina 1000
FIM
No hay 1000...
leia CIC20211.csv
leia CIC20211.csv
matriculas CIC0090 CIC0004 CIC0169
FIM
537 matriculados em ALGORITMOS E PROGRAMAÇÃO DE COMPUTADORES (CIC0004)
167 matriculados em ESTRUTURAS DE DADOS (CIC0090)
37 matriculados em PROGRAMAÇÃO COMPETITIVA (CIC0169)
