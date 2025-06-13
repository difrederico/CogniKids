# COGNIKIDS

**Solução Educacional com Inteligência Artificial para Inclusão de Alunos Neurodivergentes**



Documentação Técnica do Protótipo CogniKids v13.0, um projeto desenvolvido no Curso Superior de Tecnologia em Inteligência Artificial da Faculdade SENAI Fatesg.

📝 Índice
Visão Geral do Sistema
Arquitetura e Estruturas de Dados
Descrição dos Módulos e Funções
Gerenciamento de Sessão
Módulo do Professor
Módulo do Aluno
Módulo dos Pais
Função de Desempenho
🛠️ Tecnologias Utilizadas
▶️ Como Executar o Protótipo
👨‍💻 Autores e Contato
🎯 Visão Geral do Sistema
O CogniKids é um protótipo funcional de um sistema de software educacional, desenvolvido para simular uma plataforma integrada de apoio à inclusão de alunos neurodivergentes. O sistema foi concebido com uma arquitetura modular, centrada em três perfis de usuário: Pais, Professores e Alunos.

O objetivo principal do protótipo é validar os fluxos de informação e as interações lógicas entre esses três atores, demonstrando a viabilidade de um ecossistema digital colaborativo. A aplicação opera inteiramente em um ambiente de console, utilizando estruturas de dados em memória para simular um banco de dados, o que significa que os dados não são persistentes entre as execuções.

🏗️ Arquitetura e Estruturas de Dados
O núcleo do sistema é sustentado por um conjunto de estruturas de dados globais que funcionam como um banco de dados em memória. A escolha por esta abordagem visa a simplicidade e a agilidade na prototipagem.

Listas de Usuários (vetores)
Python

# Armazena dicionários, onde cada dicionário representa o perfil de um pai/mãe.
usuarios_pais = []

# Armazena dicionários com os perfis dos professores.
usuarios_professores = []

# Armazena dicionários com os perfis dos alunos.
usuarios_alunos = []
Estruturas de Dados de Interação
Python

# Armazena cada pergunta de um aluno e a resposta do professor.
perguntas_alunos = []

# Modela um sistema de mensagens diretas entre pais e professores.
mensagens_pais_professores = []

# Simula um fórum de discussão compartilhado entre pais e professores.
forum_geral = []

# Armazena eventos, provas e atividades criadas pelo professor.
agenda_global = []
Estruturas de Dados de Avaliação
Python

# Dicionário que armazena os pesos (prova, atividade, participação) definidos pelo professor para cada turma.
pesos_por_turma = {}
📜 Descrição dos Módulos e Funções
O código é segmentado em funções que representam as principais ações e "telas" do sistema.

🔑 Funções de Gerenciamento de Sessão
main(): Função de entrada do programa. Contém o loop principal que gerencia a seleção de perfil (Pai, Aluno, Professor) e direciona o usuário para o fluxo de cadastro ou de login.
realizar_login(): Solicita usuário e senha, itera sobre todas as listas de usuários, valida as credenciais e retorna o dicionário do usuário logado ou None.
cadastrar_pai(), cadastrar_aluno(), cadastrar_professor(): Funções específicas que coletam os dados de cada perfil e os adicionam à lista global correspondente. O cadastro de aluno inclui seleção de avatar via menu.
🧑‍🏫 Módulo do Professor (tela_professor)
Centraliza as ferramentas de gestão acadêmica e comunicação.

Acesso a Dados de Apoio: Consulta os perfis dos pais (usuarios_pais) para exibir informações qualitativas sobre o aluno (neurodivergência, Kit de Apoio).
Definição de Pesos: Permite ao professor atribuir pesos para "Provas", "Atividades" e "Participação" para cada turma, armazenando-os em pesos_por_turma.
Lançamento de Notas: Fluxo otimizado para que o professor selecione um aluno e insira notas e faltas em uma única tela.
Visualização de Desempenho: Chama a função exibir_grafico_desempenho() para o aluno selecionado.
Painel de Sentimentos: Exibe o histórico de registros emocionais (emoji e texto) inseridos pelo aluno.
Responder Perguntas: Filtra perguntas sem resposta, permite que o professor responda e atualiza a estrutura de dados perguntas_alunos.
🎓 Módulo do Aluno (tela_aluno)
Interface focada na experiência do estudante, com elementos de gamificação e autoexpressão.

Painel de Sentimentos: Permite ao aluno registrar seu estado emocional com um emoji e um texto descritivo.
Desafios do Sol: Exibe 10 desafios pré-definidos. O progresso é rastreado e exibido visualmente com emojis de sol (☀️).
Perguntas e Respostas: Permite ao aluno fazer perguntas ao professor e visualizar as respostas quando disponíveis.
👨‍👩‍👧‍👦 Módulo dos Pais (tela_pais)
Painel de controle para acompanhamento do desenvolvimento do aluno.

Kit de Apoio e Neurodivergência: Permite aos pais inserir e atualizar informações qualitativas essenciais sobre o filho.
Visualização de Dados: Atua como um "leitor" das estruturas de dados globais, filtrando e exibindo informações relevantes (Agenda, Painel de Sentimentos, Desempenho, Perguntas/Respostas) sobre seu filho.
📊 Função de Desempenho (exibir_grafico_desempenho)
Função-chave, acessível por todos os perfis, que:

Recebe um dicionário de aluno como parâmetro.
Busca os pesos da turma em pesos_por_turma.
Calcula a média aritmética simples de provas, atividades e participação.
Aplica a fórmula da média ponderada: ((media_provas * peso_p) + ...) / soma_pesos.
Imprime uma matriz formatada detalhando o cálculo e exibindo a Média Ponderada Final.
🛠️ Tecnologias Utilizadas
Linguagem: Python 3.x
Ambiente de Execução: Terminal de Console / Google Colab
▶️ Como Executar o Protótipo
Clone este repositório:
Bash

git clone https://github.com/seu-usuario/cognikids.git
Navegue até o diretório do projeto:
Bash

cd cognikids
Execute o arquivo principal do Python:
Bash

python nome_do_arquivo_principal.py
👨‍💻 Autores e Contato
Este projeto foi desenvolvido por:

Aluna: Maria Clara Ribeiro Di Bragança
Aluno: Frederico Lemes Rosa
Orientadora: Profª. Ma. Marielly Mota
Instituição: Faculdade SENAI Fatesg – Curso Superior de Tecnologia em Inteligência Artificial
