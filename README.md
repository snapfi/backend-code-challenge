# backend-code-challenge

## Overview

A Snapfi se propõe a resolver um problema identificado entre os MEI e autônomos: A dificuldade de gestão financeira que essas pessoa tem.

Nossa proposta é oferecer aos nossos clientes ferramentas de gestão financeira e serviços financeiros. Em um primeiro momento queremos alavancar o uso do PIX por ser mais barato para o cliente e ter liquidação instantânea.

Um fluxo comum de uma transação financeira, para que ela seja efetivada, exige que o saldo seja verificado para confirmar que tem recursos suficientes, esse saldo precisa ser provisionado, ou seja, bloqueado (_na prática o dinheiro é movimentado para uma conta de transição_) e depois a transação é efetivada.

Alguns pontos importantes:

* Podem haver transações concorrentes, por isso é muito importante que o saldo informado não corra o risco de mudar ao longo da operação (_até que o provisionamento seja feito_);
* Se a transação tiver algum problema, o provisionamento precisa ser compensado. As transações sempre são imutáveis, então não é possível apagá-la ou alterá-la;
* Apenas uma transação está disponível que é o `PIX OUT` (_transferência para outra conta bancária_);
* Os estados que as transações podem assumir são: OPEN, BOOKED e FAILED.

## Desafio

O desafio consiste em implementar uma API que simule o provisionamento (_bloqueio_) de um saldo para uma transação. A API deve ser capaz de:

* Criar uma transação;
* Consultar o saldo de uma conta;
* Provisionar o saldo de uma conta para uma transação;
* Compensar o provisionamento de uma transação;

### Requisitos

* A API deve ser escrita em Go;
* Escolha o framework http que mais se sentir confortável (ou talvez grpc);
* Escolha o banco de dados relacional que mais se sentir confortável;
* Docker compose para rodar o banco de dados e a API;
* Documentar sua solução para que possamos entender como executá-la e testá-la;

### Diferenciais

* Cobertura de código efetivo, ou cerca de 85% ou mais;
* Testes de integração;

### Referências

* [Standard Go Project Layout](https://github.com/golang-standards/project-layout)
* [Uber Go Stye Guide](https://github.com/uber-go/guide/blob/master/style.md)
* [Go Code Review Comments](https://github.com/golang/go/wiki/CodeReviewComments)

### O que será avaliado

* Qualidade do código;
* Organização do projeto;
* Boas práticas;
* Documentação;
* Testes;

### O que esperamos

* Um repositório __privado__ no Github com o código da sua solução;
* Adicionar o usuário @gandarez como colaborador do repositório;
* Um arquivo `README.md` com as instruções de como executar o projeto;
