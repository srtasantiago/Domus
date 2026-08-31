# Domus

Uma aplicação colaborativa para manter a casa e a rotina em perfeita harmonia. Tarefas divididas e executadas garantem um lar funcional e uma convivência equilibrada.


## Sobre o Projeto

- PROBLEMA: Dividir as tarefas de casa costuma gerar falhas de comunicação, sobrecarga para alguns moradores e esquecimento de afazeres diários. Com rotinas e horários diferentes, fica difícil saber a disponibilidade de cada um para combinar quem faz o quê e saber tudo que tem pr a fazer. Além disso, usar papel ou grupos de WhatsApp não funciona bem, pois não há controle em tempo real de quem já concluiu as tarefas e nem integração com a agenda de cada pessoa.

- SOLUÇÃO: O projeto consiste no desenvolvimento de uma aplicação Web colaborativa voltada à organização e gestão integrada da rotina doméstica. A solução centraliza o cadastro, o agendamento e a delegação de tarefas domésticas entre os membros de uma residência, permitindo o acompanhamento do status (pendente/concluída) com atualização em tempo real.

Além da gestão de afazeres, o aplicativo integra um módulo de agenda compartilhada, permitindo que cada membro registre seus compromissos e visualize os horários ocupados dos demais moradores. Com isso, o sistema otimiza a distribuição de tarefas de acordo com a disponibilidade real de cada usuário, reduz conflitos de convivência, promove um ambiente colaborativo transparente e equilibrado.

# Funcionalidades Principais

- Gestão de Tarefas: Cadastro de atividades domésticas com detalhes, prazos e categorias.
- Divisão e Atribuição: Compartilhamento de tarefas entre os membros da casa com definição clara de responsáveis.
- Visualização Flexível: Filtro para consultar tarefas do dia atual ou visão geral de todas as pendências da residência.
- Lembretes e Notificações: Avisos automáticos de horários para evitar esquecimentos e atrasos.
- Agenda Integrada: Compartilhamento de horários e compromissos para alinhamento da disponibilidade dos moradores.



# Segurança: Princípio do Privilégio Mínimo (PoLP)

O sistema adota segurança e privacidade por padrão

- Isolamento de Residências: Moradores têm acesso restrito exclusivamente aos dados e tarefas vinculados à sua própria residência (house_id), impedindo acesso a informações de outros lares.
- Privacidade da Agenda Pessoal: Ao compartilhar compromissos, os membros visualizam apenas blocos de disponibilidade (status Livre/Ocupado), preservando a descrição detalhada e o sigilo de eventos particulares.
- Permissões Granulares: Cada usuário tem autorização para interagir e concluir suas próprias tarefas atribuídas, enquanto edições estruturais e exclusões são restritas aos criadores ou administradores.

# REQUISITOS: 
https://docs.google.com/document/d/1qwaCeihKyFpgJl_dzDiJJ_IwqoaZw3X5p2jj03T5hjw/edit?usp=sharing

# Regras de negócio
- Usuário Titular (Account Owner):
Faz o cadastro completo com e-mail e senha.
Cria o espaço da casa.
Tem permissão para criar, editar ou excluir perfis.

- Perfis de Membros (Sub-contas):
Não precisam de e-mail ou senha próprios.
Defini avartar/foto

- Uso no dia a dia:
Na tela inicial do app, é exibida a tela de seleção: "Quem está usando?".
O morador clica no seu perfil (digita o PIN, se houver) e passa a gerenciar suas tarefas e agenda.
Se os moradores usarem celulares diferentes, todos podem logar com a mesma conta titular e apenas selecionar seus respectivos perfis.

# Arquitetura de sistemas

O sistema adota o padrão Cliente-Servidor em 3 Camadas, utilizando uma  API REST e um Banco de Dados Relacional.

- Componentes

Frontend (Web): Interface do usuário, gerenciamento do perfil ativo (estilo Netflix) e envio de requisições HTTP para a API.
Backend (API REST): Centraliza as regras de negócio, autenticação (JWT), validação de perfis, controle de tarefas e agenda compartilhada.
Banco de Dados (PostgreSQL):Armazena de forma estruturada as contas, perfis, tarefas e eventos de agenda, garantindo a integridade dos dados via chaves relacionais.

- Infraestrutura na AWS

API Backend: Instância EC2 
Banco de Dados: RDS PostgreSQL 

# Custos
aproximadamente 6 dólares mensais da instancia EC2 t4g.small 
