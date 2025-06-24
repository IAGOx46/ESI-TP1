# H2 (Registro de Nível dos Rios)

A seleção das classes foi baseada nos campos obrigatórios do registro (data, hora, local e valor), e nos critérios de validade dos dados inseridos. Foram consideradas entradas completas e válidas, ausência de campos, valores negativos e formatos incorretos. Também se testou o uso de evidências opcionais e a manutenção de histórico de versões ao editar. As combinações garantem que o sistema aceite apenas registros coerentes e seguros, e rejeite entradas incompletas ou com erros.

| Condição de Entrada | Classes Válidas | Classes Inválidas |
| ----- | ----- | ----- |
| Preencher todos os campos obrigatórios (data, hora, local, valor do nível) | Dados completos (1) | Campo obrigatório ausente (2)|
| Valor de nível dentro de um intervalo aceitável (\>0 e \<100 metros) | Valor entre 0.1 e 100m  (3) | Valor negativo ou zero (4)|
| Formato correto para data | Data (5) | Data em Formato Invalido (6) |
| Anexar evidências (opcionais) | Com evidência (foto ou comentário)  (7) | |

## Tabela de Casos de Testes

| Caso de Teste | Classes de Equivalência | Entradas | Resultados Esperados |
| :---- | :---- | :---- | :---- |
| Caso 1 | 1, 3, 5, 7 | Dados completos, nível \= 10m, data: 23/06/2025 e foto anexada. | Registro Válido |
| Caso 2 | 2, 3, 5 | Dados incompletos faltando preencher o campo localização, nível \= 10 | Registro inválido (erro de campo obrigatório) |
| Caso 3 | 1 , 4, 5 | Dados completos, data 23/06/2025, nível \-5m | Registro inválido (error de valor inválido) |
| Caso 4 | 1, 3, 6 | Dados completos, Data: 34/13/15, nível: 10m,  | Registro inválido (erro de formato de data) |

# H3 (Download de Conteúdos)

As classes consideram os principais fatores que afetam o sucesso do download: espaço disponível, permissão de escrita, existência do arquivo e conexão ativa com a internet. As combinações foram pensadas para validar tanto o caminho ideal quanto situações que causam falhas esperadas. Isso garante que o sistema se comporte corretamente ao lidar com restrições do dispositivo ou do ambiente.

| Condição de Entrada | Classes Válidas | Classes Inválidas |
| ----- | ----- | ----- |
| Existe espaço suficiente no dispositivo | Espaço Disponível (1) | Sem espaço suficiente  (2) |
| Usuário permitiu o acesso à memória | Permissão concedida  (3) | Permissão negada (4) |
| Arquivo disponível para download | Arquivo existe  (5) | Arquivo inexistente (6) |
| Conexão de internet ativa no momento do download | Conexão presente  (7) | Sem Conexão (8) |

## Tabela Casos de Testes

| Caso de Teste | Classes de Equivalência | Entradas | Resultados Esperados |
| :---- | :---- | :---- | :---- |
| Caso 1 | 1, 3, 5, 7 | Espaço Disponível, permissão concedida, arquivo disponível, conexão disponível | Download concluído |
| Caso 2 | 2, 3, 5, 7 | Dispositivo sem armazenamento, permissão concedida, arquivo disponível, conexão disponível | Erro: Espaço insuficiente |
| Caso 3 | 1, 4, 5, 7 | Espaço Disponível, permissão negada, arquivo disponível, conexão disponível | Erro: Falta de permissão |
| Caso 4 | 1, 3, 6, 7 | Espaço Disponível, permissão concedida, arquivo indisponível, conexão disponível | Erro: Arquivo indisponível |
| Caso 5 | 1, 3, 5, 8 | Espaço disponível, permissão concedida, arquivo disponível, sem conexão. | Erro: Sem Conexão |

# H4 (Edição de Texto de Alertas)

O foco aqui foi garantir que apenas usuários autorizados possam editar alertas e que os textos estejam preenchidos e dentro do limite de caracteres. Também foi considerada a obrigatoriedade de manter um histórico de versões após cada edição. As combinações testam tanto o fluxo ideal quanto erros comuns, como falta de permissão, texto vazio ou histórico perdido.

| Condição de Entrada | Classes Válidas | Classes Inválidas |
| ----- | ----- | ----- |
| Usuário tem permissão para editar | Possui permissão (1) | Não possui permissão (2) |
| Texto de alerta não está vazio | Texto Preenchido (3) | Texto Vazio (4) |
| Texto atende ao limite máximo de caracteres | Texto com até 500 caracteres (5) | Texto ultrapassa 500 caracteres (6) |

## Tabela Caso de Teste

| Caso de Teste | Classes de Equivalência | Entradas | Resultados Esperados |
| :---- | :---- | :---- | :---- |
| Caso 1 | 1, 3, 5 | Usuário autorizado, texto: Chuva Prevista ás 20:00h., texto válido | Edição salva com sucesso |
| Caso 2 | 2, 3, 5 | Usuário sem permissão, texto: Chuva Prevista ás 20:00h., texto válido | Erro: Permissão insuficiente |
| Caso 3 | 1, 4, 5 | Usuário autorizado, texto: Chuva Prevista ás 20:00h., texto invalido | Erro: Texto obrigatório |
| Caso 4 | 1, 3, 6 | Usuário autorizado, texto com mais de 500 caracteres: Chuva Prevista ás 20:00h…………….., texto válido | Erro: Limite de caracteres excedido  |

# H5 (Recebimento de Alertas)

As classes testam se o usuário tem localização configurada, se o nível do rio exige alerta, se o recebimento está ativado e se o sistema de notificação está disponível. A ideia foi validar que alertas só sejam enviados quando todas essas condições forem atendidas, evitando notificações incorretas ou não entregues.

| Condição de Entrada | Classes Válidas | Classes Inválidas |
| ----- | ----- | ----- |
| Usuário está cadastrado e com localização definida | Localização definida (1) | Localização não definida (2) |
| Nível do rio está acima do limite de alerta | Nível acima do limite  (3) | Nível dentro do Normal  (4) |
| Configuração de recebimento de alertas está ativada | Recebimentos de alertas ativado (5) | Recebimentos de alertas ativado (6) |

## Tabela Casos de Teste

| Caso de Teste | Classes de Equivalência | Entradas | Resultados Esperados |
| :---- | :---- | :---- | :---- |
| Caso 1 | 1, 3, 5 | Localização: Comunidade  Arary, nível: 18 m, alertas ativados. | Alerta enviado com sucesso |
| Caso 2 | 2, 3, 5 | Sem localização, nível: 18 m, alertas ativados. | Erro: Localização não definida |
| Caso 3 | 1, 4, 5 | Localização: Comunidade  Arary, nível: 10 m, alertas ativados. | Alerta não enviado(nível dentro do limite) |
| Caso 4 | 1, 3, 6 | Localização: Comunidade  Arary, nível: 18 m, alertas desativados. | Erro: Recebimento de Alertas Desativasdo  |

# H6 (Notificação de Dias Secos)

A escolha das classes de equivalência para a história H6 foi baseada nas condições essenciais para que o alerta de “dia seco” seja enviado: a probabilidade de chuva deve ser 0%, a data da previsão precisa ser o dia atual, o usuário deve ter ativado o recebimento de alertas, e o sistema de notificações precisa estar funcional. Cada classe representa um cenário válido ou inválido para testar o comportamento esperado do sistema. As combinações nos testes cobrem situações típicas, limites e falhas, garantindo que o sistema envie alertas apenas quando todas as condições forem atendidas.

| Condição de Entrada | Classes Válidas | Classes Inválidas |
| ----- | ----- | ----- |
| Probabilidade de chuva igual a 0% | Probabilidade de Chuva 0% (1) | Probabilidade de Chuva maior que 0% (2) |
| Data de Previsão do dia correspondente ao dia atual | Data da previsão do dia Atual (3) | Data Passada ou futura (4) |
| Configuração de recebimento de alertas está ativada | Recebimentos de alertas ativado (5) | Recebimentos de alertas ativado (6) |

## Tabela Casos de Teste 

| Caso de Teste | Classes de Equivalência | Entradas | Resultados Esperados |
| :---- | :---- | :---- | :---- |
| Caso 1 | 1, 3, ,5 | Probabilidade de 0% de chuva | Alerta de dia seco enviado com sucesso |
| Caso 2 | 2, 3, 5 | Probabilidade de 20%, data de hoje, alerta ativado, sistema ativo | Nenhum alerta enviado |
| Caso 3 | 1, 4, 5 | Probabilidade 0%, mas previsão para data futura | Nenhum Alerta enviado |
| Caso 4 | 1, 3, 6 | Probabilidade 0%, data de hoje, alerta ativado, sistema de notificação desativado | Nenhum Alerta enviado |

H1 \- Classes de equivalência

| Condição de entrada | Classes válidas | Classes inválidas |
| :---: | :---: | :---: |
| Todos os campos obrigatórios preenchidos (nome, e-mail, senha, tipo) | Dados completos (1) | Dados ausentes (2) |
| Formato correto de dados (ex.: e-mail inválido, senha com critérios mínimos ) | Dados válidos (3) | Dados  com formato inválidos (4) |
| E-mail não cadastrado anteriormente | E-mail disponível (5) | E-mail já cadastrado (6) |
| Sistema de autenticação funcionando | Sistema operacional (7) | Sistema fora do ar (8) |

 

H1- Casos de teste

| Caso | Classe de Equivalência | Entrada | Resultado esperado |
| :---: | :---: | ----- | :---: |
| Caso 1 | 1, 3, 5, 7 | Nome: João Silva, Email: joao@gmail.com, Senha: Joao@1234, Tipo: Ribeirinho  | Cadastro realizado com sucesso |
| Caso 2 | 2, 3, 5, 7 | Nome: João Silva, Email: (vazio), Senha: Joao@123, Tipo: Ribeirinho | Erro: Campo obrigatório ausente |
| Caso 3 | 1, 4, 5,7 | Nome: João Silva, Email: joao\#gmail.com, Senha: Joao@123, Tipo: Ribeirinho | Erro: e-mail inválido |
| Caso 4 | 1, 3, 6, 7 | Nome: João Silva, Email: joao@gmail.com (já cadastrado), Senha: Joao@123, Tipo: Ribeirinho | Erro: e-mail em uso |
| Caso 5 | 1, 3, 5, 8 |      Nome: João Silva, Email: joao@gmail.com, Senha: Joao@123, Tipo: Ribeirinho, Sistema fora do ar     | Erro: Serviço indisponível |

 

 

H10 \- Classe de equivalência

| Condição de entrada | Classes válidas | Classe inválidas |
| :---: | :---: | :---: |
| Localização e perfil do usuário configurados | Dados configurados (1) | Dados ausentes (2) |
| API de previsão do tempo funcionando | API ativa (3) | API inoperante(2) |
| Dados personalizados disponíveis (baseados nas atividades do usuário) | Dados disponíveis (5) | Dados não encontrados (6) |
| Sistema de recomendação funcionado | Sistema operantes (7) | Sistema fora do ar(8) |

 

H10 \- Caso de teste

| Caso | Classe de equivalêcia | Entrada | Resultado esperado |
| :---: | :---: | ----- | :---: |
| Caso 1 | 1, 3, 5, 7 | Usuário: Pedro (Pescador), Local: Lago do Limão, API funcionando, Dados disponíveis, Sistema operante | Dados climáticos personalizados exibidos com sucesso |
| Caso 2 | 2, 3, 5, 7 | Usuário: Pedro, Local: (não configurado), API funcionando | Erro: Dados de localização ausentes |
| Caso 3 | 1, 4, 5, 7 | Usuário: Pedro, Local: Lago do Limão, API fora do ar | Erro: não foi possível obter os dados |
| Caso 4 | 1, 3, 6, 7 | Usuário: Pedro, Local: Lago do Limão, API fora do ar | Mensagens: “Nenhuma recomendação disponível” |
| Caso 5 | 1, 3, 5, 8 |      Usuário: Pedro, Local: Lago do Limão, Sistema de recomendação com falha   | Erro: Serviço indisponível |

 

 

H9 \- Classe de equivalência

| Condição de entrada | Classes válidas | Classes inválidas |
| :---: | :---: | :---: |
| Localização do usuário configurada corretamente | Localização definida (1) | Localização ausente (2) |
| Dados  da API de monitoramento funcionando | API funcionando (3) | API fora do ar (4) |
| Dados recebidos são válidos ( nível ≥ 0 e ≤ limite aceitável) | Dados corretos (5) |  Dados inválidos ou inconsistentes (6) |
| Sistema de atualização operando | Sistema ativo (7) | Sistem com falha (8) |

 

H9 \- Caso de teste

| Caso | Classes de equivalência | Entrada | Resultado esperado |
| :---: | :---: | ----- | :---: |
| Caso 1 | 1, 3, 5, 7 | Local: Porto do Açu, API funcionando, Nível: 8.5m, Sistema operante | Nível atualizados com sucesso |
| Caso 2 | 2, 3, 5, 7 |      Local: (não configurado), API funcionando, Nível: 8.5m   | Atualização não realizada (erro de localização) |
| Caso 3 | 1, 4, 5, 7 | Local: Porto do Açu, API fora do ar, Nível: 8.5m | Atualização não realizada (erro de API) |
| Caso 4 | 1, 3, 6, 7 | Local: Porto do Açu, API funcionando, Nível: \-2.0m (inválido) | Atualização rejeitada (erro de dados inválidos) |
| Caso 5 | 1, 3, 5, 8 |      Local: Portodo Açu, API funcionando, Nível: 8.5m, Sistema com falha   | Atualização não realizada (erro no sistema) |

 

 

H8 \- Teste de equivalência

| Condição de entrada | Classes válidas | Classes inválidas |
| :---: | :---: | :---: |
| Código de verificação inserido corretamente | Código válido (1) | Código inválido ou incorreto (2) |
| Código dentro do tempo limite de validade | Código no prazo (3) | Código expirado (4) |
| Usuário com e-mail ou número de telefone cadastrado | Contato cadastrado (5) | Sem contato cadastrado (6) |
| Sistema de envio funcionando | Envio bem-sucedido (7) | Falha no envio (8) |

 

H8- Caso de teste

| Caso | Classe de equivalência | Entrada | Resultado esperado |
| :---: | :---: | :---: | :---: |
| Caso 1 | 1, 3, 5, 7 | Código: 854623, Enviado para: maria@gmail.com, Inserido em: 2 min | Validação realizada com sucesso |
| Caso 2 | 2, 3, 5, 7 | Código: 854623 (incorreto), Enviado para: maria@gmail.com | Erro: Código inválido |
| Caso 3 | 1, 4, 5, 7 | Código: 854623, Enviado para: maria@gmail.com, Inserido após: 10 min (expirado) | Erro: Código expirado |
| Caso 4 | 1, 3, 6, 7 | Código: 854623, Sem e-mail ou telefone cadastrado | Erro: Dados de contato ausentes |
| Caso 5 | 1, 3, 5, 8 | Código: 854623, Falha no envio do código (servidor offline) | Erro: Não foi possível enviar o código |

 

 

H7 \- Teste de equivalência

| Condição de entrada | Classe válida | Classe inválida |
| :---: | :---: | :---: |
| Localização ativada e configurada | Localização correta (1) | Localização não definida/desativada (2) |
| Fonte de dados meteorológicos funcionando | Fonte disponível (3) | Fonte indisponível (4) |
| Existe previsão de tempestade para a região | Tempestade prevista (5) | Sem tempestade prevista (6) |
| Sistema de notificações habilitada | Notifcações ativas (7) | Notificações desativa ou falha (8) |

 

 

H7 \- Caso de teste

| Caso | Classe de equivalência | Entrada | Resultado esperado |
| :---: | :---: | :---: | :---: |
| Caso 1 | 1, 3, 5, 7 | Local: Manaus, Previsão: Tempestade forte, Ventos: 70km/h, Notificações ativas, Sistema funcionando | Alerta enviado com sucesso |
| Caso 2 | 2, 3, 5, 7 | Local: (não configurado), Previsão: Tempestade, Ventos: 70km/h | Alerta não enviado (erro por falta de localização) |
| Caso 3 | 1, 4, 5, 7 | Local: Manaus, Previsão: Tempestade, API meteorológica fora do ar | Alerta não enviado (erro na fonte de dados) |
| Caso 4 | 1, 3, 6, 7 | Local: Manaus, Previsão: Sem tempestade, Tempo estável | Nenhum alerta enviado |
| Caso 5 | 1, 3, 5, 8 | Local: Manaus, Previsão: Tempestade, Sistema de notificações com falha | Alerta não entregue ao usuário |

 

