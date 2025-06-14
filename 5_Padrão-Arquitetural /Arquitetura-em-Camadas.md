# Arquitetura em Camdadas

A Arquitetura em Camadas foi escolhida por estar alinhada aos objetivos e características do projeto, pois:

- Favorece a organização e modularização do sistema, facilitando o desenvolvimento em equipe (UI, backend, banco de dados).

- Permite reaproveitamento e manutenção facilitada: alterações em uma camada não afetam as demais diretamente.

- Oferece clareza na separação de responsabilidades, ideal para um sistema que tem usuários com diferentes níveis de acesso (como meteorologistas, ribeirinhos e pesquisadores).

- É compatível com funcionalidades offline/online, além de suportar futuras integrações com sensores, IA e alertas.

- Atende aos requisitos não funcionais como escalabilidade, segurança e manutenibilidade.

     <img src="https://github.com/user-attachments/assets/f0c990a3-f4cf-4d7f-952c-a195319843f8" width="600">

## Neste Diagrama temos os seguintes componentes:
- Usuário: que é quem interage com o sistema  e Utiliza o app para acessar previsões, alertas, registrar dados ou baixar relatórios.

- Camada de Apresentação: Fornece a interface visual e interação ao usuário. Nela se apenas exibe as previsões climáticas, gráficos, níveis do rio, alertas e formulários para envio de registros. Esta camada apenas apresenta e recebe dados.

- Camada de Serviços:  Esta camada é responsável por controlar a lógica do app, vai ser feito o processamento das regras de negócios, vai definir o que e quando mostrar e por fim realizar a manipulação dos dados antes de exibir na interface.

- Camada de Dados: Esta camada é responsável por armazenar e consultar as informações, ela vai salvar os dados na nuvem no Firebase por exemplo, e gerência o histórico de clima, cheia e dados sobre o clima e geral.

- Camada de Infraestrutura: Tem como principal função fazer a comunicação com serviços externos, faz a integração do app com as APIs de meteorologia por exemplo.
