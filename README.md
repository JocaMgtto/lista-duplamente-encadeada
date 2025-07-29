TAD Fila de Banco com Prioridade
Este projeto é uma implementação do Tipo Abstrato de Dados (TAD) de uma Fila, utilizando uma estrutura de lista duplamente encadeada em Python. O objetivo é simular uma fila de banco com uma regra de negócio específica para dar prioridade a clientes idosos.

Este trabalho foi desenvolvido como parte das atividades da disciplina de Estrutura de Dados.

Regras de Negócio da Fila
A fila segue o comportamento padrão (primeiro a entrar, primeiro a sair), mas com uma exceção para clientes com mais de 60 anos, considerados idosos:

Prioridade para Idosos: Clientes idosos têm prioridade sobre os não idosos.

Mecanismo de Troca: Quando um cliente idoso entra na fila, ele "sobe" na fila, trocando de lugar com os clientes não idosos que estão imediatamente à sua frente.

Limite de Trocas: Para garantir que clientes não idosos não sejam indefinidamente adiados, um cliente não idoso pode ser ultrapassado por, no máximo, 2 clientes idosos. Após ser ultrapassado duas vezes, sua posição se torna "fixa" em relação a novos idosos que entrarem na fila, e ele não poderá mais ser ultrapassado.

Estrutura do Código
O código está organizado em três classes principais:

Cliente
Armazena os dados de cada pessoa na fila.

ident: Identificador único do cliente.

idade: Idade do cliente, usada para determinar a prioridade.

trocas: Um contador que armazena quantas vezes um cliente não idoso já foi ultrapassado por um idoso.

No
Representa um nó na lista duplamente encadeada.

cliente: O objeto Cliente armazenado no nó.

anterior: Aponta para o nó anterior na fila.

proximo: Aponta para o nó seguinte na fila.

Encadupla
A classe principal que implementa a fila duplamente encadeada e todas as regras de negócio. Ela gerencia a inserção, remoção e a lógica de prioridade.

enfileira(cliente):	Adiciona um cliente ao final da fila e, se for idoso, aplica as regras de prioridade para movê-lo para frente.
desenfileira():	Remove e retorna o primeiro cliente da fila.
mostrar_fila():	Retorna uma string que representa o estado atual da fila, mostrando todos os clientes em ordem.
primeiro_elemen():	Retorna o primeiro cliente da fila sem removê-lo.
vazia():	Retorna True se a fila estiver vazia e False caso contrário.
__len__():	Retorna o número total de clientes na fila (permite o uso da função len()).
esvazia():	Remove todos os elementos da fila, deixando-a vazia.

Ao executar o script com o main() fornecido, a saída será:
  (cliente: 3, idade: 67), (cliente: 4, idade: 61), (cliente: 5, idade: 72), (cliente: 7, idade: 75), (cliente: 1, idade: 21), (cliente: 2, idade: 34), (cliente: 6, idade: 54)

Os clientes idosos (3, 4, 5 e 7) foram para o início da fila.

Os clientes não idosos (1, 2 e 6) ficaram para o final.

A ordem entre os próprios idosos e entre os não idosos é mantida com base na ordem de chegada. Por exemplo, o cliente 1 chegou antes do 2.

O cliente 6 (54 anos), apesar de ter entrado depois de vários idosos, ficou no final por não ter prioridade.
