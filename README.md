# Desafio_Projeto_Conceitual_BCSuzano
Primeiro desafio de projeto da Suzano, relacionado ao refinamento de um projeto conceitual de Banco de Dados utilizando do Modelo ER Extendido.

O objetivo do projeto inicial era utilizar dos conchecimentos de ER extendido passados durante os conteúdos previamente ensinados no BootCamp. Após recriar no meu próprio Workbench,
o objetivo era adicionar ao modelo os seguintes pontos:

  1. Cliente PJ e PF – Uma conta pode ser PJ ou PF, mas não pode ter as duas informações;
  2. Pagamento – Pode ter cadastrado mais de uma forma de pagamento;
  3. Entrega – Possui status e código de rastreio;

A partir desses pontos, fiz as adaptações necessárias, as quais explico a seguir:

  1. Em relação ao cliente só poder ter ou um número de CPF ou CNPJ, mas não ambos, fiz uma nova tabela no workbench chamada "CPF/CNPJ", onde a chave primária seria justamente o númerode cpf ou cnpj do cliente,       além de colocar esse dado como unique, evitando mais de um valor duplicado. Ápos isso, fiz uma relação 1:1 entre cliente e a nova tabela, sendo que a nova tabela "CPF/CNPJ" receberia o id_cliente como chave      estrangeira, sendo possível descobrir o cliente proprietário desse número de cadastro;
     
  2. Acerca de pagamento, fiz duas modificações. A primeira e mais simples, adicionei um "saldo" na própria tabela de clientes, porque, em muitos sites, um cliente pode ter um "saldo virtual", como na amazon por      exemplo. Além disso, adicionei uma nova tabela chamada "Forma Pagamento" (poderia ter a chamado de "cartões"), contendo as informações dos cartões registrados, exceto pelo CVV (a chave primária foi o             próprio número do cartão). Após isso, fiz uma relação 1:n entre cliente e Forma Pagamento, onde um cliente poderia ter diferentes formas de pagamento, porém, um cartão só pode estar relacionado a um cliente      em específico.

  3.Por último, Fiz uma nova tabela relacionada com a entrega (a chamei de "entrega" mesmo), contendo os Status e o código de rastreio da mesma. Fiz uma relação 1:n entre pedido e entrega, onde uma entrega pode      estar relacionada a vários pedidos, porém um pedido só pode ser realizado por uma entrega.

Pela plataforma utilizada, optei por seguir com a ideia acima para o ponto do CPF/CNPJ, porém, uma ideia que poderia que pensei, que poderia ser utilizada, era fazer uma relação disjunta, onde o cliente poderia
ter ou CPF ou CNPF, porém apenas um deles, Utilizando daquele círculo com um "D" para especificar essa disjunção. Além disso, adicionei o saldo apenas visando a consulta do cliente para saber quanto ele possuí na plataforma, e os cartões com o número como chave primária por serem únicos a cada cartão (pelo menos assim imagino). A parte de entrega me baseei na amazon, onde dentro dos status de pedido podemos ver sobre a entrega do mesmo, a qual acho muito satisfatória.
