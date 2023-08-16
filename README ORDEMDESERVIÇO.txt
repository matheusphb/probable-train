###########################################################*README*####################################################

                                              _._     _,-'""`-._                                                    
                                             (,-.`._,'(       |\`-/|                                                
                                                 `-.-' \ )-`( , o o)                                                
                                                       `-    \`_`"'-                                                
                                                                                                                    
   _;;        _;^      :^-    -^^^^^^^^: -,_      ,_   _______  __      __     _^;^_  ''''-----  ------       _,,_-        
   P@@8      *@@@     *@@@-   _FFF@@Htti !@%     !@%  :@@3333T  @@_     @@  _Q@yvv3O :SSS@@8yye r@@PPPPr  -5@&PuuS8^       
   P@Q@P    ;@@@@    _@g*@%       %@*    !@%     *@%  ,@@       @@_     @@  3@O          N@*    r@8      _@@;              
   P@Tt@h  !@8:@@   -@@- J@X      B@!    *@@88888g@N  ,@@8888;  @@_     @@   Tg@%u,      %@*    r@@XXXX_ X@u               
   U@c S@t^@g _@&   8@@HdH@@L     0@!    *@%-----c@8  ,@@----   @@_     @@     -*b@g_    %@!    L@%:,,,  P@E               
   X@c  G@@@- _@&  u@U____^@@_    g@;    *@8     *@8  ^@@       G@j    L@8  _-    H@3    %@!    c@#      _@@r              
   Fg;   P8-  _gb ,gG      _Q8    b@^    ;@P     ;@P  :@@ggggg   ig@gg@0i   i@@gB&gF     D@;    r@@gggg8   T%@g8%Q@^    
                                                                                                                    
## Esquema Conceitual para Sistema de Ordem de Serviço em Oficina Mecânica

Este esquema conceitual representa as entidades, atributos e relacionamentos para um sistema de controle e gerenciamento de execução de ordens de serviço em uma oficina mecânica.

### Entidades e Atributos:

- **Cliente:** Armazena os dados dos clientes, incluindo ID, nome, telefone e email.
- **Veiculo:** Armazena os dados dos veículos dos clientes, como ID, cliente, modelo e placa.
- **Mecanico:** Armazena os dados dos mecânicos, incluindo ID, nome, endereço e especialidade.
- **OrdemServico:** Armazena os dados das ordens de serviço emitidas pelos mecânicos para os veículos dos clientes, como número, data de emissão, valor total, status, data de conclusão, mecânico e veículo.
- **Servico:** Armazena os dados dos serviços que podem ser realizados pelos mecânicos, incluindo ID, descrição e valor.
- **ItemServico:** Armazena os dados dos itens de serviço que compõem cada ordem de serviço, como ID, ordem de serviço e serviço.
- **ItemPeca:** Armazena os dados das peças que são utilizadas em cada ordem de serviço, incluindo ID, ordem de serviço, descrição e valor.

### Relacionamentos:

Os relacionamentos entre as entidades são definidos da seguinte maneira:

- **Cliente - Veículo**: Relacionamento de 1 para N, onde cada cliente pode ter vários veículos.
- **Mecânico - Ordem de Serviço**: Relacionamento de 1 para N, indicando que cada mecânico pode ser responsável por várias ordens de serviço.
- **Veículo - Ordem de Serviço**: Relacionamento de 1 para N, mostrando que cada veículo pode ter várias ordens de serviço associadas.
- **Ordem de Serviço - Serviço**: Relacionamento de N para M, permitindo que uma ordem de serviço contenha vários serviços diferentes.
- **Ordem de Serviço - Peça**: Relacionamento de N para M, usando a tabela intermediária `ItemPeca` para associar várias peças a uma ordem de serviço.

Cada tabela tem uma chave primária que a identifica de forma única. Algumas tabelas também têm chaves estrangeiras que referenciam outras tabelas e estabelecem relacionamentos entre elas. Por exemplo, a tabela Veiculo tem uma chave estrangeira ClienteID que referencia a tabela Cliente. Isso significa que cada veículo pertence a um cliente e tem um registro correspondente na tabela Cliente.

### Tipos de Dados:

O código SQL também mostra os tipos de dados de cada atributo, como INT, VARCHAR, DATE, DECIMAL e ENUM. Esses tipos definem o formato e o tamanho dos valores que podem ser armazenados em cada atributo. Por exemplo, o tipo VARCHAR(255) significa que o atributo pode armazenar uma cadeia de caracteres com até 255 caracteres.

