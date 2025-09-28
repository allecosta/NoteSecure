# NoteSecure

*Para este projeto foi utilizado a aplicação Zotion, um projeto open-source, clone do Notion. Segue abaixo o aplicativo e o repositório oficial:*

- https://zotion-app.vercel.app/
- https://github.com/adityaphasu/notion-clone

*Para as práticas de segurança aplicadas ao projeto, serão utilizadas ferramentas open-source.*

*Toda documentação das práticas do programa de AppSec, estão disponivel na Wiki deste repositório - Ainda em fase de desenvolvimento!*

![Programa de AppSec](/assets/doc/img/wiki.png)



## Descrição 

*A NoteSecure é uma startup - fictícia - fundada há 18 meses por três sócios: Maria (CEO,
ex-consultora de negócios), João (CTO, desenvolvedor full-stack) e Ana (CPO, designer
UX). A empresa está desenvolvendo o “WorkSpace+ AI Assistant” , uma plataforma colaborativa de produtividade que combina funcionalidades do Notion com recursos avançados de colaboração em tempo real.*

- O Produto e Arquitetura Atual - O WorkSpace+ permite que usuários criem
espaços de trabalho compartilhados com documentos, kanban boards, calendários e
wikis colaborativos. A aplicação possui:
    - Frontend: React.js com TypeScript hospedado na Vercel
    - Backend: Node.js/Express com MongoDB Atlas
    - Autenticação: JWT + integração com Google OAuth
    - Storage: AWS S3 para arquivos e imagens
    - Real-time: Socket.io para colaboração simultânea
    - Infraestrutura: AWS (EC2, RDS, S3, CloudFront)

- Contexto do negócio:
    - Usuários: 15.000 usuários ativos (crescimento de 40% ao mês)
    - Equipe: 7 pessoas (4 devs, 1 QA, 1 designer , 1 marketing)
    - Financiamento: Série A de R$ 8 milhões captados há 6 meses
    - Clientes: 200 empresas pagantes, incluindo 3 grandes corporações
    - Dados sensíveis: Documentos corporativos, estratégias empresariais, dados
    Pessoais.

- Processo de desenvolvimento atual
    - Planejamento e Gestão:
        - Sprints de 2 semanas usando Jira
        - Reuniões diárias de 15min via Google Meet
        - Product roadmap trimestral
        - Sem processo formal de levantamento de requisitos de segurança

- Desenvolvimento
    - Git flow com feature branches
    - Code review obrigatório por peer (sem checklist de segurança)
    - Testes unitários (~60% cobertura)
    - Deploy manual via scripts bash
    - Sem treinamento formal em secure coding
    - Sem testes de segurança específicos
    - Ambiente de staging que replica produção

- Deploy e Operações:
- Deploy manual 2x por semana
- Monitoramento básico com CloudWatch
- Logs centralizados no ELK Stack
- Sem processo de incident response definido
- Sem IAM roles específicos (muita gente com admin)
- Secrets hardcoded em algumas variáveis de ambiente
- Sem WAF ou proteção DDoS

*Nos últimos meses, ocorreram alguns incidentes que prejudicam a reputação da
organização, bem como causaram perda considerável de receita com o churn de cerca de 2
mil usuários. Sem um processo estruturado de resposta a incidentes, o tratamento das
vulnerabilidades foi tardio e não houve aprendizado organizacional com os incidentes. A
única documentação existente descreve de forma simplificada apenas o impacto:*

- Vazamento menor: Logs com dados sensíveis foram expostos por 3 dias
- Indisponibilidade: Aplicação ficou fora do ar por 4 horas devido a pico de tráfego
- Bug de autorização: Usuários conseguiam ver documentos de outros workspaces
por 1 dia

