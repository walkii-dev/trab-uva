# Matrículas de aluno para cursos on-line
O desenvolvimento de aplicações web modernas exige a integração entre um frontend eficiente, com boa experiência de usuário (UX), e um back-end estruturado, seguro e escalável. O trabalho propõe a resolução de uma situação-problema, incentivando o pensamento crítico, a organização de um fluxo de dados entre cliente e servidor e o uso de boas práticas de programação.

Imagine que uma empresa de serviços educacionais está lançando uma plataforma para alunos realizarem matrículas em cursos on-line. O sistema deve permitir que os usuários vejam uma lista de cursos disponíveis, selecionem um deles e realizem a matrícula informando seus dados pessoais. Para isso, será necessário criar uma interface responsiva e acessível, além de um servidor que receba e armazene essas informações.

Atualmente, a empresa já tem uma equipe de designers, mas precisa que os desenvolvedores construam um protótipo funcional que una uma boa experiência do usuário à operação real de requisições, com armazenamento em um banco de dados (simulado). O desafio está em garantir a qualidade da interface e a robustez do back-end, mesmo sem a integração real com um banco no momento.

Crie uma aplicação web que ofereça uma experiência fluida e interativa ao usuário para a matrícula em cursos on-line, garantindo que os dados informados sejam enviados corretamente a uma API construída com boas práticas e segurança.

 

### Procedimentos para elaboração do TD

Criação do Frontend com Vue.js:

Criar um componente principal chamado FormularioMatricula.vue.

Incluir campos para nome completo, e-mail e curso selecionado.

Utilizar princípios de UX antecipada: mensagens de erro claras, validações imediatas, botões com feedback visual.

Exibir a lista de cursos a partir de um array local ou uma chamada à API.

Criação da API com Node.js, Express e TypeScript:

### Criar um projeto Node com TypeScript e Express.

Criar uma rota GET/cursos que retorna uma lista de cursos.

Criar uma rota POST/matrícula que recebe os dados do aluno.

Validar os dados recebidos usando TypeScript (tipagem via interface).

Responder com os códigos HTTP adequados: 201 Created, 400 Bad Request etc.

### Integração Vue.js + API:

Realizar uma requisição GET no carregamento da página para exibir os cursos disponíveis.

Fazer uma requisição POST ao submeter o formulário com os dados preenchidos.
Exibir mensagens de sucesso ou erro com base na resposta da API.
