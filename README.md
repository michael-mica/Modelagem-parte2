# Modelagem-Banco-de-Dados-Atividade-2

Atividade-01 Modelagem de Banco de Dados

# Projeto ERP - Lavanderia Sta. Bárbara

## 1. Identificação da equipe

### Michael, Kaik, Iago, Enzo, Vinícius, Victor, Veronica e Leo

## 2. Caracterização da empresa

### Qual é o nome da empresa?

Lavanderia Sta. Bárbara.

### Qual é o segmento?

Prestação de serviços de lavanderia, com atendimento a diferentes tipos de peças e clientes.

### O que ela vende ou oferece?

Oferece lavagem, secagem, passadoria e restaurações em casos específicos.

### Quem são seus principais clientes?

Pessoas físicas e empresas que procuram lavagem e cuidados especializados.

### Quais são seus principais setores?

Atendimento ao cliente, área de coleta e recebimento de peças, lavagem, secagem e passadoria.

### Como funciona atualmente?

O atendimento é registrado manualmente em comandas. A responsável anota as peças recebidas, os serviços solicitados e o prazo de entrega. As peças seguem para processamento e o cliente é avisado pelo celular quando o pedido está pronto. Em situações específicas, a empresa realiza entrega.

### Quais informações são importantes para o negócio?

Dados dos clientes, identificação das peças, cuidados necessários, serviços contratados, preços, prazos, situação do pedido e registro de quem retirou as peças e de quem realizou o atendimento.

## 3. Justificativa da escolha

Escolhemos a Lavanderia Sta. Bárbara devido à ausência de um banco de dados estruturado para gerenciar suas operações, uma vez que as informações estão concentradas na memória da proprietária, dificultando o controle de pedidos, entregas, despesas e resultados financeiros.

Dessa forma, o projeto tem como finalidade desenvolver do zero um banco de dados que centralize e organize as informações da lavanderia, permitindo registrar e acompanhar clientes, pedidos, serviços, movimentações financeiras e entregas. O objetivo é proporcionar maior controle operacional, facilitar a gestão do negócio.

## 4. Problemas identificados

### Ausência de cadastro digital

As informações dos clientes e pedidos ficam dispersas nos controles manuais. Precisamos centralizar os registros e facilitar a consulta do histórico.

### Falta de padronização dos pedidos

As comandas não oferecem uma estrutura uniforme para identificar peças, cuidados e serviços. Precisamos registrar cada peça e relacioná-la ao pedido e aos serviços contratados.

### Conhecimento concentrado na responsável

Parte do conhecimento sobre preços e prazos depende da experiência da proprietária. Precisamos documentar as condições comerciais por tipo de peça e serviço.

### Dificuldade de acompanhamento

A consulta do andamento depende do controle manual. Precisamos acompanhar a situação do pedido e identificar quando está pronto para retirada.

### Necessidade de organização financeira

O levantamento também identificou falta de controle de despesas. Nesta primeira modelagem, delimitamos o escopo ao atendimento e à operação dos pedidos. Financeiro, pagamentos, estoque e logística são áreas de expansão do ERP; não fazem parte do DER apresentado.

## 5. Processos de negócio

### Cliente → Pedido → Peças e serviços → Processamento → Pedido pronto → Retirada

### Recepção e contratação

O cliente solicita o serviço e apresenta as peças. O atendente identifica ou cadastra o cliente, registra o pedido, descreve cada peça e seus cuidados e seleciona os serviços. A combinação entre tipo de peça e serviço define preço e prazo da contratação.

### Processamento

O pedido confirmado possui pelo menos uma peça e cada peça possui pelo menos um serviço. As peças seguem pelas atividades necessárias, como lavagem, secagem e passadoria. O acompanhamento desta versão ocorre pelo status do pedido, sem registro individual de execução de cada etapa.

### Conclusão e retirada

Quando os serviços terminam, o pedido fica pronto para retirada. O cliente é avisado pelo contato utilizado no atendimento. O funcionário confere a pessoa que busca as peças e registra a retirada integral, com nome do retirante, horário e responsável pelo registro.

### Manutenção do catálogo e cancelamento

Os tipos de peça e serviços possuem condições comerciais cadastradas. Alterações do catálogo valem para novas contratações. Pedidos podem ser cancelados antes da retirada, preservando o histórico.

## 6. Requisitos funcionais

### RF01 - O sistema deverá cadastrar, alterar e consultar clientes.

### RF02 - O sistema deverá cadastrar funcionários, tipos de peça e serviços.

### RF03 - O sistema deverá manter preço, prazo e disponibilidade por combinação de tipo de peça e serviço.

### RF04 - O sistema deverá registrar pedidos vinculados ao cliente e ao funcionário de abertura.

### RF05 - O sistema deverá identificar cada peça física e registrar seus cuidados.

### RF06 - O sistema deverá associar serviços às peças e preservar as condições contratadas.

### RF07 - O sistema deverá acompanhar o status e os prazos dos pedidos.

### RF08 - O sistema deverá calcular o total a partir dos serviços contratados.

### RF09 - O sistema deverá permitir a consulta do histórico de pedidos do cliente.

### RF10 - O sistema deverá registrar cancelamentos, mantendo o histórico.

### RF11 - O sistema deverá registrar a retirada integral pelo cliente ou pela pessoa autorizada.

## 7. Requisitos não funcionais

### RNF01 - Segurança

O acesso aos dados e às operações deverá respeitar as permissões atribuídas aos responsáveis pelo atendimento e pela administração.

### RNF02 - Confiabilidade

O registro da retirada e a atualização da situação do pedido deverão ocorrer como uma única operação, evitando divergência entre a entrega e o status.

### RNF03 - Usabilidade

As informações de cliente, peças, serviços, prazo e situação deverão ser apresentadas com nomenclatura padronizada e mensagens claras, facilitando o atendimento.

### RNF04 - Recuperação

Os dados deverão contar com cópias de segurança e procedimento de recuperação para reduzir os efeitos de perda dos registros operacionais.

### RNF05 - Desempenho

As consultas de cliente, pedido e situação deverão oferecer tempo de resposta compatível com o atendimento, sem impedir a continuidade das atividades da recepção.

## 8. Regras de negócio

Um cliente pode realizar vários pedidos, e cada pedido pertence a um único cliente.

Um funcionário pode registrar vários pedidos, e cada pedido identifica um funcionário de abertura.

Todo pedido confirmado possui pelo menos uma peça. Cada peça representa um item físico e pertence a um único pedido.

Cada peça possui um tipo e recebe pelo menos um serviço no pedido confirmado.

Um tipo de peça pode possuir vários serviços tabelados, e um serviço pode ser oferecido para vários tipos de peça.

Somente combinações ativas de tipo de peça e serviço podem ser contratadas. Os responsáveis pela abertura e retirada devem estar ativos na operação.

Preço e prazo são copiados no momento da contratação. Alterações posteriores do catálogo não modificam as condições já contratadas.

O mesmo serviço não se repete na mesma peça. O total do pedido é a soma dos valores aplicados aos serviços.

O prazo-base corresponde à abertura acrescida do maior prazo contratado, em horas corridas. O prazo combinado não pode ser inferior ao base, e sua ampliação exige justificativa.

O pedido percorre as situações: em espera, em processo, pronto para retirada e retirado. O cancelamento é permitido antes da retirada.

Pedidos em espera podem estar em preparação. Para iniciar o processamento, devem possuir peças e serviços completos.

A roupa não pode ser retirada durante o processamento. A retirada é única e integral, pelo cliente ou pela pessoa indicada no pedido.

O funcionário confere a identidade do retirante e registra seu nome e o horário. A retirada não pode anteceder a abertura nem ser registrada com data futura.

Os dados de identificação do cliente incluem nome, CPF/CNPJ, telefone e endereço. A identificação da peça é composta pelo número do pedido e pela sequência dentro dele.

## 9. Restrições e políticas organizacionais

A proprietária é a referência para as decisões comerciais e para a definição das permissões operacionais.

O atendimento deve identificar o pedido apresentado pelo cliente e conferir a autorização antes de entregar as peças. O recibo é utilizado como referência operacional do atendimento; sua emissão não constitui uma entidade própria neste modelo.

O pedido admite uma pessoa autorizada para retirada. Na ausência dessa indicação, a retirada é feita pelo próprio cliente.

As alterações de preço e prazo no catálogo não devem reescrever as contratações anteriores. Cadastros inativos permanecem disponíveis para a compreensão do histórico.

O cancelamento encerra o pedido sem apagar os registros. A atualização cadastral não deve romper os vínculos com pedidos anteriores.

As políticas de armazenamento, doação de peças, entrega em domicílio e pagamento pertencem ao contexto ampliado da lavanderia. Não são automatizadas no recorte conceitual desta entrega.

## 10. Fluxogramas dos principais processos


### 10.1 Recebimento e processamento

```text
                       [ INÍCIO: RECEBER PEÇAS ]
                                   |
                                   v
                       < Cliente cadastrado? >
                            |             |
                           NÃO           SIM
                            |             |
                            v             |
                    [ Cadastrar cliente ] |
                            |             |
                            +------+------+ 
                                   |
                                   v
                      [ Abrir pedido em espera ]
                                   |
                                   v
                [ Identificar peças e registrar cuidados ]
                                   |
                                   v
                [ Selecionar serviços com tabela ativa ]
                                   |
                                   v
                [ Copiar preço e prazo da contratação ]
                                   |
                                   v
                 < Peças e serviços estão completos? >
                          |                  |
                         NÃO                SIM
                          |                  |
                          v                  v
               [ Manter em espera ]  [ Calcular prazo-base ]
               [ Informar pendências ]       |
                          |                  v
                          v          < Prazo ampliado? >
                    [ FIM DESTA          |          |
                      TENTATIVA ]       SIM        NÃO
                                         |          |
                                         v          |
                              [ Registrar motivo ]  |
                                         |          |
                                         +-----+----+
                                               |
                                               v
                                  [ Iniciar processamento ]
                                               |
                                               v
                                    [ Executar serviços ]
                                               |
                                               v
                                  [ Pronto para retirada ]
                                               |
                                               v
                                            [ FIM ]
```

### 10.2 Retirada

```text
                  [ INÍCIO: SOLICITAR RETIRADA ]
                                |
                                v
                       [ Localizar pedido ]
                                |
                                v
                       < Pedido está pronto? >
                           |            |
                          NÃO          SIM
                           |            |
                           v            v
                [ Informar impedimento ] [ Conferir identidade
                           |              e autorização ]
                           v                    |
                  [ FIM SEM ENTREGA ]           v
                                      < Conferência válida? >
                                          |           |
                                         NÃO         SIM
                                          |           |
                                          v           v
                              [ Informar impedimento ]
                              [ FIM SEM ENTREGA ]     |
                                                      v
                                 [ Conferir funcionário ativo
                                   e validade do horário ]
                                                      |
                                                      v
                                 [ Registrar retirada e status
                                   na mesma transação ]
                                                      |
                                                      v
                                 [ Entregar todas as peças ]
                                                      |
                                                      v
                                      [ FIM: RETIRADO ]
```

### 10.3 Cancelamento

```text
                 [ INÍCIO: SOLICITAR CANCELAMENTO ]
                                  |
                                  v
                 [ Localizar pedido e conferir autorização ]
                                  |
                                  v
             < Em espera, em processo ou pronto para retirada? >
                          |                       |
                         NÃO                     SIM
                          |                       |
                          v                       v
                 [ Negar transição ]    [ Marcar como cancelado ]
                          |             [ Preservar o histórico ]
                          |                       |
                          +-----------+-----------+
                                      |
                                      v
                                   [ FIM ]
```

A manutenção dos cadastros e do catálogo antecede a contratação. A função de avisar o cliente pode continuar manual; automação de mensagens não foi implementada pelo modelo.

## 11. Entidades do modelo conceitual

### CLIENTE

Identificar o contratante e seus dados de contato/endereço.

### FUNCIONÁRIO

Identificar responsáveis pela abertura e pelo registro da retirada.

### PEDIDO

Reunir a solicitação, situação, autorização e condições de prazo.

### ITEM

Identificar uma peça física pertencente a um pedido; entidade fraca.

### TIPO DE PEÇA

Classificar peças e participar da definição das condições comerciais.

### SERVIÇO

Identificar os serviços ofertados.


No DER em notação de Chen, **TABELA**, **RECEBE** e **RETIRADA** são relacionamentos com atributos. Na conversão lógica, originam as relações `preco_tabelado`, `servico_item` e `retirada`.

Assim, o modelo lógico possui nove tabelas: `cliente`, `funcionario`, `tipo_peca`, `servico`, `pedido`, `item`, `preco_tabelado`, `servico_item` e `retirada`. ITEM permanece entidade fraca; não se torna entidade associativa por possuir chave composta.

## 12. Atributos e classificações

### CLIENTE

cpf_cnpj, nome, telefone, endereço composto por logradouro, numero, complemento, bairro, cidade, uf e cep.

### FUNCIONÁRIO

matricula, nome, ativo.

### PEDIDO

numero_pedido, data_abertura, status, observacoes, autorizado_retirada, prazo_base, prazo_combinado, motivo_ampliacao e valor_total derivado.

### ITEM

sequencia, identificacao e observacoes_cuidado; identificação completa depende do pedido.

### TIPO DE PEÇA

nome_tipo e ativo.

### SERVIÇO

nome_servico e ativo.

### TABELA

valor_vigente, prazo_padrao_horas e ativo.

### RECEBE

valor_aplicado e prazo_aplicado_horas.

### RETIRADA

nome_retirante e data_hora.


- **Identificadores:** CPF/CNPJ, matrícula, número do pedido e nomes padronizados dos catálogos.
- **Chave parcial:** sequência da peça dentro do pedido.
- **Composto:** endereço.
- **Derivado:** valor total do pedido.
- **Multivalorados:** não foram definidos neste escopo. Telefone e autorizado representam um valor por cadastro/pedido.


## 13. Relacionamentos

### REALIZA

- **Elementos associados:** CLIENTE e PEDIDO
- **Informação própria:** Sem atributos próprios.

### REGISTRA

- **Elementos associados:** FUNCIONÁRIO e PEDIDO
- **Informação própria:** Representa a abertura do pedido.

### CONTÉM

- **Elementos associados:** PEDIDO e ITEM
- **Informação própria:** Relacionamento identificador da entidade fraca.

### CLASSIFICA

- **Elementos associados:** TIPO DE PEÇA e ITEM
- **Informação própria:** Sem atributos próprios.

### TABELA

- **Elementos associados:** TIPO DE PEÇA e SERVIÇO
- **Informação própria:** Preço vigente, prazo padrão e disponibilidade da combinação.

### RECEBE

- **Elementos associados:** ITEM e SERVIÇO
- **Informação própria:** Preço e prazo aplicados na contratação.

### RETIRADA

- **Elementos associados:** PEDIDO e FUNCIONÁRIO
- **Informação própria:** Nome de quem retirou e horário do evento.


TABELA e RECEBE são N:N. Atributos comerciais pertencem às associações, pois não descrevem isoladamente o serviço, o tipo ou a peça.

## 14. Cardinalidades

Cada linha responde aos dois sentidos do relacionamento. A notação abaixo informa quantas ocorrências do outro elemento podem estar associadas a uma ocorrência do elemento indicado.

### CLIENTE / PEDIDO

- **Primeiro sentido:** Um cliente realiza 0..N pedidos.
- **Sentido inverso:** Cada pedido tem 1 cliente.

### FUNCIONÁRIO / PEDIDO

- **Primeiro sentido:** Um funcionário abre 0..N pedidos.
- **Sentido inverso:** Cada pedido tem 1 funcionário de abertura.

### PEDIDO / ITEM

- **Primeiro sentido:** Um pedido confirmado contém 1..N peças.
- **Sentido inverso:** Cada peça pertence a 1 pedido.

### TIPO DE PEÇA / ITEM

- **Primeiro sentido:** Um tipo classifica 0..N peças.
- **Sentido inverso:** Cada peça possui 1 tipo.

### TIPO DE PEÇA / SERVIÇO

- **Primeiro sentido:** Um tipo pode ter 0..N serviços tabelados.
- **Sentido inverso:** Um serviço pode ser tabelado para 0..N tipos.

### ITEM / SERVIÇO

- **Primeiro sentido:** Uma peça do pedido confirmado recebe 1..N serviços.
- **Sentido inverso:** Um serviço pode ser contratado em 0..N peças.

### PEDIDO / FUNCIONÁRIO em RETIRADA

- **Primeiro sentido:** Um pedido possui 0..1 evento de retirada.
- **Sentido inverso:** Um funcionário registra 0..N retiradas; cada evento tem 1 pedido e 1 funcionário.


As cardinalidades mínimas de participação indicadas no DER descrevem pedidos confirmados. A regra de completude passa a ser exigida ao iniciar o processamento.

## 15. Dicionário de dados conceitual preliminar

### CLIENTE.cpf_cnpj

- **Descrição e finalidade:** Documento do contratante
- **Regra / observação:** Único e obrigatório; Identifica pessoa física ou jurídica.

### CLIENTE.nome

- **Descrição e finalidade:** Nome do cliente
- **Regra / observação:** Obrigatório e não vazio.

### CLIENTE.telefone

- **Descrição e finalidade:** Contato para atendimento
- **Regra / observação:** Contato do cliente para o atendimento.

### CLIENTE.logradouro

- **Descrição e finalidade:** Via do endereço
- **Regra / observação:** Obrigatório e não vazio.

### CLIENTE.numero

- **Descrição e finalidade:** Número ou indicação equivalente
- **Regra / observação:** Obrigatório e não vazio.

### CLIENTE.complemento

- **Descrição e finalidade:** Detalhe adicional do endereço
- **Regra / observação:** Opcional.

### CLIENTE.bairro

- **Descrição e finalidade:** Bairro do endereço
- **Regra / observação:** Obrigatório e não vazio.

### CLIENTE.cidade

- **Descrição e finalidade:** Município do endereço
- **Regra / observação:** Obrigatório e não vazio.

### CLIENTE.uf

- **Descrição e finalidade:** Unidade federativa
- **Regra / observação:** Obrigatória e pertencente à lista adotada de UFs.

### CLIENTE.cep

- **Descrição e finalidade:** Código postal
- **Regra / observação:** Obrigatório; oito dígitos no modelo lógico.

### FUNCIONÁRIO.matricula

- **Descrição e finalidade:** Identificador do trabalhador
- **Regra / observação:** Único e obrigatório; chamado RM no DER.

### FUNCIONÁRIO.nome

- **Descrição e finalidade:** Nome do trabalhador
- **Regra / observação:** Obrigatório e não vazio.

### FUNCIONÁRIO.ativo

- **Descrição e finalidade:** Habilitação para novas operações
- **Regra / observação:** Não elimina registros históricos.

### TIPO DE PEÇA.nome_tipo

- **Descrição e finalidade:** Identificador padronizado da categoria
- **Regra / observação:** Único e não vazio.

### TIPO DE PEÇA.ativo

- **Descrição e finalidade:** Disponibilidade da categoria
- **Regra / observação:** Conferida nas novas operações pertinentes.

### SERVIÇO.nome_servico

- **Descrição e finalidade:** Identificador padronizado do serviço
- **Regra / observação:** Único e não vazio.

### SERVIÇO.ativo

- **Descrição e finalidade:** Disponibilidade do serviço
- **Regra / observação:** Conferida na contratação.

### PEDIDO.numero_pedido

- **Descrição e finalidade:** Número operacional
- **Regra / observação:** Identificador único.

### PEDIDO.data_abertura

- **Descrição e finalidade:** Momento de abertura
- **Regra / observação:** Obrigatório; referência para o prazo.

### PEDIDO.status

- **Descrição e finalidade:** Situação do pedido
- **Regra / observação:** Domínio e transições definidos em RN11.

### PEDIDO.observacoes

- **Descrição e finalidade:** Informação complementar
- **Regra / observação:** Opcional.

### PEDIDO.autorizado_retirada

- **Descrição e finalidade:** Pessoa indicada pelo cliente
- **Regra / observação:** Opcional; uma pessoa por pedido.

### PEDIDO.prazo_base

- **Descrição e finalidade:** Prazo calculado do pedido
- **Regra / observação:** Abertura + maior prazo contratado.

### PEDIDO.prazo_combinado

- **Descrição e finalidade:** Prazo acordado
- **Regra / observação:** Não inferior ao base após confirmação.

### PEDIDO.motivo_ampliacao

- **Descrição e finalidade:** Justificativa para ampliar prazo
- **Regra / observação:** Obrigatória quando combinado exceder base.

### PEDIDO.valor_total

- **Descrição e finalidade:** Soma dos serviços contratados
- **Regra / observação:** Derivado da soma dos serviços contratados.

### ITEM.sequencia

- **Descrição e finalidade:** Identificação local da peça
- **Regra / observação:** Positiva e única dentro do pedido.

### ITEM.identificacao

- **Descrição e finalidade:** Descrição/identificação operacional da peça
- **Regra / observação:** Obrigatória e não vazia.

### ITEM.observacoes_cuidado

- **Descrição e finalidade:** Cuidados, alergias e particularidades
- **Regra / observação:** Opcional.

### TABELA.valor_vigente

- **Descrição e finalidade:** Preço atual da combinação
- **Regra / observação:** Não negativo.

### TABELA.prazo_padrao_horas

- **Descrição e finalidade:** Prazo padrão da combinação
- **Regra / observação:** Horas corridas, não negativas.

### TABELA.ativo

- **Descrição e finalidade:** Disponibilidade da combinação
- **Regra / observação:** Deve estar ativo ao contratar.

### RECEBE.valor_aplicado

- **Descrição e finalidade:** Preço contratado para peça e serviço
- **Regra / observação:** Copiado do catálogo e preservado.

### RECEBE.prazo_aplicado_horas

- **Descrição e finalidade:** Prazo contratado para peça e serviço
- **Regra / observação:** Copiado do catálogo e preservado.

### RETIRADA.nome_retirante

- **Descrição e finalidade:** Pessoa que efetivamente retira
- **Regra / observação:** Obrigatório; cliente ou autorizado.

### RETIRADA.data_hora

- **Descrição e finalidade:** Momento da retirada
- **Regra / observação:** Não anterior à abertura nem futuro.


## 16. Diagrama Entidade-Relacionamento

O DER utiliza a notação de Chen, com retângulos para entidades, losangos para relacionamentos e elipses para atributos. As vistas de pedido/retirada e peças/preços complementam a visão geral do mesmo modelo.

[Consultar o DER revisado](docs/DER_LAVANDERIA_REVISADO_COM_ASSOCIATIVAS.pdf)

As cardinalidades mínimas de peças e serviços representam os pedidos confirmados. A preparação em espera é uma etapa anterior à exigência de completude.

## 17. Justificativas técnicas

### Cadastro de cliente separado do pedido

Um cliente pode ser cadastrado antes da primeira contratação e realizar vários pedidos. Seu documento o identifica sem repetir todo o cadastro em cada pedido.

### ITEM como entidade fraca

A sequência de uma peça é única somente dentro do pedido. Por isso, sua identificação depende de numero_pedido e sequencia, e CONTÉM é um relacionamento identificador.

### Uma ocorrência por peça física

Cada peça pode apresentar cuidados e serviços próprios. O registro individual permite distinguir peças do mesmo tipo sem agrupá-las apenas por quantidade.

### TABELA como relacionamento N:N com atributos

O preço e o prazo padrão dependem da combinação entre tipo de peça e serviço. Não pertencem apenas ao tipo ou apenas ao serviço. Essa associação origina PRECO_TABELADO na conversão lógica.

### RECEBE como relacionamento N:N com atributos

Uma peça pode receber vários serviços e o mesmo serviço pode ser contratado para várias peças. Valor e prazo aplicados descrevem essa contratação. A associação origina SERVICO_ITEM no modelo lógico.

### Preço vigente e preço aplicado

O primeiro representa a oferta atual; o segundo registra a condição contratada para uma peça. A separação preserva o histórico quando o catálogo muda.

### Total derivado

O total é obtido pela soma dos valores contratados. Representá-lo como derivado evita manter um valor independente que possa divergir dos serviços do pedido.

### Retirada opcional e única

Um pedido pode ainda não ter sido retirado. Quando ocorre a entrega, ela é integral e identifica o funcionário que registrou o evento e a pessoa que recebeu as peças.

### Delimitação do modelo

O primeiro módulo integra atendimento, peças, contratação, prazos e retirada. Financeiro, estoque e logística não foram transformados em entidades sem detalhamento de seus próprios requisitos. As atividades de lavagem, secagem e passadoria são serviços ou atividades operacionais, e não entidades criadas apenas por aparecerem no processo.

## 18. Conclusão

A modelagem da Lavanderia Sta. Bárbara organiza os dados necessários ao recebimento, processamento e retirada dos pedidos. Partimos dos registros manuais e da necessidade de padronizar o atendimento para definir requisitos, regras, entidades, atributos e relacionamentos.

O DER representa o cadastro de clientes e funcionários, os pedidos e suas peças, as combinações comerciais e os serviços contratados. As decisões são sustentadas pelas necessidades de identificação, consulta, preservação das condições comerciais e controle de retirada.

Essa estrutura constitui a entrega conceitual do módulo operacional e estabelece a base para a evolução ao modelo lógico, à normalização e à implementação do banco de dados.

