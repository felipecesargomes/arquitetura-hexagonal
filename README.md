# Arquitetura Hexagonal

## O que é arquitetura hexagonal?

R - É uma padrão de projeto. A arquitetura hexagonal se divide em 2 grupos, classes de domínio e classes referentes a infraestrutura, integração de sistema e persistência. E o mais importante, a classes de domínio devem ser totalmente separada de qualquer tecnologia ou componente.

Tendo como focos principais:

- Desenvolvimento orientado a TDD.
- foco nos requisitos de negócio.
- adiar decisões técnicas o máximo possível.

Então podemos concluir que quando adotamos essa arquitetura estamos dando o máximo de importância para o desenvolvimento da regra de negócio e tudo que for relacionado a tecnologias, seja API's ou banco de dados será segundo plano.

A arquitetura hexagonal é composto de portas e adaptadores. Sendo as portas as interfaces que são utilizada para comunicação para nossas classes de domínios. E adaptadores todos os outros componentes que nossa aplicação precisa, por exemplo, uma API, um banco de dados, uma chamada externa a um sistema. Logo os adaptadores é algum componente já existente que precisamos utilizar e levar até nossa regra de negócio, o responsável por levar os adaptadores ate os dominios serão as portas de entrada (intefaces de fora para dentro) e saída (interfaces e de dentro para fora).

## Qual objetivo principal?

R - Separar as classes de dominio (regras de negócios) do restante do sistema, ou seja, separada da infra do sistema, persistência, comunicação com outros sistemas ou com banco de dados.

## Quais vantagens de utilizar esse padrão?

R - Reusabilidade do código, alta coesão, baixo acoplamento da regra de negócio com o restante das tecnologias da linguagem ou componentes diversos.

## Isolamento (Separation of concerns - SoC)

É um principío básico da engenharia de software que visa modularizar uma solução de forma que cada módulo esteja focado em resolver apenas um único problema. no SoC existe 3 áreas distintas e isoladas:

- Centro como hexágono.
- Lado superior esquerdo, fora do hexágono.
- Lado inferior direito, fora do hexágono.

![image](https://github.com/user-attachments/assets/9efd90d0-fed3-4fd3-9659-8adc52f9b996)

### Centro Hexágono

<b>Interno Hexágono</b>

Este é o ponto pelo qual as interações externas são introduzidas no sistema. Vamos explorar mais sobre esse lado da arquitetura:

<b>Lado Esquerdo</b>
Descrição: Representa interfaces ou pontos de contato através dos quais a aplicação recebe entradas. Estes podem ser APIs, interfaces de usuário (GUIs), ou qualquer outro meio através do qual um ator externo (como um usuário ou outro sistema) interage com a aplicação.
Exemplos:
- Web services (APIs RESTful ou SOAP)
- Interfaces de usuário (por exemplo, uma aplicação web ou móvel)
- Sistemas de mensagens (como filas de mensagens)

<b>Lado Direito</b>
Descrição: Representa interfaces ou pontos de contato através dos quais a aplicação interage com recursos externos (serviços de infraestrutura). Estes podem ser sistemas de armazenamento de dados, serviços externos, ou qualquer outro meio pelo qual a aplicação envia ou recebe dados do mundo exterior.

Exemplos:
- Bancos de Dados: Interfaces que permitem à aplicação ler e gravar dados em bancos de dados relacionais (SQL) ou não relacionais (NoSQL).
- APIs de Terceiros: Interfaces que permitem à aplicação se comunicar com serviços externos, como APIs de pagamento, serviços de envio de e-mail, ou APIs de redes sociais.
- Sistemas de Arquivos: Interfaces que permitem à aplicação ler e gravar arquivos em sistemas de arquivos locais ou em armazenamento em nuvem.
- Sistemas de Mensagens: Interfaces que permitem à aplicação se comunicar através de sistemas de mensagens, como filas de mensagens (RabbitMQ, Kafka) para enviar e receber dados assíncronos.
