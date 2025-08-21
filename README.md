<h1 align="center">
    <br>
    AWS Certified Developer – Associate (DVA-C02)
    <br>
    Resumo Estratégico para o Exame
</h1>

<div align="center">
<img src="image.png" alt="AWS Certified Developer Associate DVA-C02" width="20%" />
</div>

<div align="center">

  <img alt="Repository size" src="https://img.shields.io/github/repo-size/klerytondev/aws-certified-AI-practitioner-roadmap.svg">
  <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/klerytondev/aws-certified-AI-practitioner-roadmap.svg">
  <a href="https://github.com/klerytondev/aws-certified-AI-practitioner-roadmap/issues">
  <img alt="Repository issues" src="https://img.shields.io/github/issues/klerytondev/aws-certified-AI-practitioner-roadmap.svg">
  </a>
  <img alt="GitHub" src="https://img.shields.io/github/license/klerytondev/aws-certified-AI-practitioner-roadmap.svg">
</div>

<br />

© 2025 · Curado por **Kleryton de Souza** · Siga no [LinkedIn](https://www.linkedin.com/in/kleryton-souza/)  
Baseado em revisão pessoal e práticas recomendadas · Compartilhe com colegas · Não comercialize  
**Versão 1.0**

Este guia estratégico foi desenvolvido para auxiliar desenvolvedores na preparação para o exame AWS Certified Developer Associate (DVA-C02). Contém informações essenciais sobre os domínios do exame, melhores práticas e um [simulado prático](#simulado-do-exame) com 65 questões.

##  Índice

- [Estrutura do Exame](#estrutura-do-exame)
- [Domínio 1: Desenvolvimento com Serviços AWS (32%)](#domínio-1-desenvolvimento-com-serviços-aws-32)
- [Domínio 2: Segurança (26%)](#domínio-2-segurança-26)
- [Domínio 3: Implantação (24%)](#domínio-3-implantação-24)
- [Domínio 4: Solução de Problemas e Otimização (18%)](#domínio-4-solução-de-problemas-e-otimização-18)
- [Principais Serviços AWS - Resumo](#principais-serviços-aws---resumo)
- [Simulado do Exame](#-simulado-do-exame)
- [Links Úteis](#-links-úteis)
- [Licença](#-licença)
- [Autor](#-autor)

## Estrutura do Exame

**Domínios do Exame:**

- **Desenvolvimento com AWS:** 32%
- **Segurança:** 26%
- **Implantação:** 24%
- **Solução de Problemas/Otimização:** 18%

**Detalhes do exame:**

- **Questões:** 65
- **Formato:** múltipla escolha, múltiplas respostas, ordenação e associação
- **Tempo:** 130 minutos
- **Pontuação mínima:** 720 de 1000
- **Realização:** Pearson VUE (online/presencial)

> **💡 Dica:** É possível errar de 13 a 16 questões ainda assim sendo aprovado. Foque no conhecimento prático das integrações AWS, segurança IAM e estratégias de CI/CD.

**Sobre a Certificação:**

A certificação AWS Certified Developer Associate valida conhecimentos técnicos em desenvolvimento, deployment e debugging de aplicações baseadas em nuvem usando AWS. É ideal para desenvolvedores com experiência em pelo menos uma linguagem de programação de alto nível.

**Pré-requisitos recomendados:**
- Experiência prática com AWS Core Services
- Conhecimento de pelo menos uma linguagem de programação
- Entendimento de arquiteturas de aplicações em nuvem
- Familiaridade com conceitos de DevOps e CI/CD
## Domínio 1: Desenvolvimento com Serviços AWS (32%)

### Serviços Principais

**Lambda:** Computação serverless, execução orientada por eventos, atenção ao cold start (especialmente na VPC), tratamento de repetição e idempotência. Gatilhos: API Gateway (síncrono), S3/SNS (assíncrono), SQS/Kinesis (polling). Deploy por .zip ou imagem de contêiner. Permissões via role de execução.

**API Gateway:** Pontos de entrada REST/HTTP para APIs. Variáveis de ambiente por estágio. Autorização via IAM, Cognito ou funções Lambda. Cache (REST). Suporte a mapeamento de requests.

**SQS:** Filas para desacoplar componentes. Standard = entrega pelo menos uma vez, ordem não garantida. FIFO = entrega única, ordem garantida. Visibility timeout. Fila de mensagens de erro (DLQ). Lambda como consumidor.

**SNS:** Mensageria Pub/Sub, distribuição para Lambda, SQS e endpoints HTTP. Políticas de filtro para distribuição segmentada. Não persiste mensagens.

**DynamoDB:** Banco NoSQL, baixo tempo de resposta. Chave de partição deve ser única/diversificada. Índices GSI/LSI. Query (por chave) vs Scan (todos os itens). Expiração automática (TTL). Streams permitem disparo de funções Lambda. Leituras consistentes ou eventuais. Controle de throughput (WCU/RCU).

**EventBridge:** Roteamento avançado de eventos com filtros. Ideal para microsserviços. Possui bus padrão (eventos AWS) e customizado (eventos de aplicações). Alvos: Lambda, Step Functions, SQS.

**Step Functions:** Orquestração de workflows e controle de etapas, com tolerância a falhas e paralelismo. Express (execução rápida) e Standard (processos longos).

**Kinesis:** Processamento em tempo real, baixa latência. Shards para paralelismo. Integração com Lambda. Firehose para ingestão automática em S3/Redshift.

**S3:** Armazenamento de objetos. Criptografia SSE-S3/SSE-KMS. Versionamento e regras de ciclo de vida. Gatilhos para Lambda/EventBridge. Consistência leitura após gravação. Classes: Standard, IA, One Zone, Glacier.

### Padrões de Arquitetura:
- Desacoplamento usando SQS/SNS/EventBridge
- Microsserviços via APIs/mensageria
- Idempotência para segurança de repetição
- Serviços stateless facilitam escala
- Coreografia (eventos) vs Orquestração (Step Functions)
## Domínio 2: Segurança (26%)

### Gerenciamento de Identidade e Acesso

**IAM:** Gerenciamento de usuários, grupos e roles. Prefira roles ao invés de credenciais fixas. Políticas baseadas em identidade/recurso. Princípios de menor privilégio. Políticas de confiança para delegação. STS para credenciais temporárias.

**Autenticação:** Cognito User Pools gerencia usuários e tokens JWT. Cognito Identity Pools entrega credenciais IAM via federação. OIDC/SAML para login federado. API Gateway pode autorizar via Cognito ou Lambda.

**Autorização:** JWT para autenticação portadora. Políticas IAM com condições. RBAC via grupos Cognito.

### Criptografia:
- **Repouso:** SSE-S3, SSE-KMS, SSE-C, cifragem RDS
- **Trânsito:** TLS/SSL
- **KMS** gerencia chaves do cliente/AWS. Rotação de chave (manual/automática)
- **Envelope encryption** e cifragem lado cliente

### Gerenciamento de Segredos:
- **Secrets Manager** para guardar e rotacionar segredos automaticamente
- **Parameter Store** para gerenciamento seguro sem rotação automática
- Evite armazenar segredos como variáveis de ambiente sem cifragem

### Práticas Seguras:
- Não utilizar credenciais fixas
- Auditar atividades IAM via CloudTrail
- Empregar MFA, SCPs e permission boundaries
## Domínio 3: Implantação (24%)

### Ferramentas de CI/CD

**CodePipeline:** Organiza fluxo CI/CD: fonte → build → testes → deploy. Pode disparar por push ou manual. Aprovações e notificações personalizadas.

**CodeBuild:** Compila e testa código. buildspec.yml define etapas do build. Gerencia variáveis de ambiente e segredos com segurança.

**CodeDeploy:** Realiza deploy em EC2, Lambda, ECS. Suporta métodos in-place, blue/green e canário para Lambda.

### Estratégias de Deploy:
- **All-at-once** (rápido, mais arriscado)
- **Rolling** (em lotes)
- **Blue/green** (ambientes paralelos, troca de tráfego)
- **Canary** (testa com parte dos usuários)
- Utilize estágios (API Gateway), aliases (Lambda), stacks (CloudFormation)

### Ferramentas de Infraestrutura como Código:
- **CloudFormation** (YAML/JSON)
- **AWS SAM** para serverless
- **CDK** para código em Python/TypeScript
- **Copilot** para ECS/Fargate
- **Amplify CI/CD** para apps web

### Artefatos e Configuração:
- **CodeArtifact:** gerência pacotes (npm, Maven)
- **ECR** para Docker
- **AppConfig** para configurações dinâmicas e feature flags
- **Parameter Store** e variáveis de ambiente (lembre da segurança)
## Domínio 4: Solução de Problemas e Otimização (18%)

### Monitoramento

**CloudWatch:** Para métricas, alarmes e dashboards. CloudWatch Logs Insights para buscas avançadas nos logs. Lambda, EC2, ECS integram logs a CloudWatch.

**X-Ray:** Rastreio distribuído, visualização de latência entre serviços. Útil para diagnosticar gargalos e erros complexos.

### Erros Comuns:
- **4XX** (client), **5XX** (server), timeout, limite de memória/excesso de throughput
- Backoff em DynamoDB por limitação de throughput

### Otimização:
- **Cache** (ElastiCache, DAX), operações em lote (SQS/DynamoDB)
- **CloudFront** para distribuição global
- **API Gateway cache** (REST APIs)

### Concorrência:
- Lambda escala automático, mas requer atenção aos limites de concorrência
- Provisioned concurrency reduz cold starts

### Ferramentas de Profiling:
- **CodeGuru Profiler** para identificar pontos críticos
- Ajuste de memória/CPU para Lambda/EC2

### Debug e Notificações:
- Combine logs com X-Ray para rastrear causas de erro
- ID de rastreamento para correlação
- SNS para alertas e notificações
- Alarme para erros, latência ou uso excessivo

### Quotas de Serviço:
- Fique atento aos limites: Lambda (timeout 15min), SQS (256KB por mensagem)
- Utilize Trusted Advisor e Service Quotas
## Principais Serviços AWS - Resumo

| Serviço | Pontos-chave a saber |
|---------|---------------------|
| **Lambda** | Execução sem servidor, idempotência, gatilhos |
| **API Gateway** | Front das APIs, autorizações, cache, throttling |
| **S3** | Armazenamento de objetos, versionamento, triggers Lambda/EventBridge |
| **DynamoDB** | NoSQL, índices, throughput, TTL, streams |
| **SQS/SNS** | Filas, pub/sub, desacoplamento, DLQ, filtros |
| **EventBridge** | Roteamento de eventos, microserviços, filtros |
| **Step Functions** | Orquestração de workflows, tolerância a falhas, paralelismo |
| **CloudWatch/X-Ray** | Monitoramento, tracing, alarmes, análise de logs |
| **IAM/Cognito** | Gerenciamento de identidades, autenticação, políticas, credenciais temporárias |
| **CodePipeline/Build/Deploy** | CI/CD, automação de builds, deploy flexível, integrações variadas |
| **KMS/SecretsMgr/ParamStore** | Gestão de chaves, segredos, criptografia dos dados |
| **CloudFront** | Cache de conteúdo, baixa latência, CDN para APIs/S3 |

##  Simulado do Exame

Pratique com questões específicas para a certificação AWS Certified Developer Associate na página [Simulado DVA-C02](contents/dva_perguntas.md).

## 🔗 Links Úteis

- [Página Oficial da Certificação AWS Certified Developer Associate](https://aws.amazon.com/pt/certification/certified-developer-associate/)
- [AWS Skill Builder](https://explore.skillbuilder.aws/learn)
- [Documentação dos Serviços AWS para Desenvolvedores](https://docs.aws.amazon.com/)
- [AWS Developer Guide](https://docs.aws.amazon.com/developer-guide/)
- [AWS Serverless Application Lens](https://docs.aws.amazon.com/wellarchitected/latest/serverless-applications-lens/)
- [AWS SDK Documentation](https://aws.amazon.com/tools/)

## 📄 Licença

Este projeto está licenciado sob a [LICENSE](LICENSE). Sinta-se à vontade para usar e distribuir este guia, desde que mantenha os créditos apropriados.

---

###  Autor

<a href="https://github.com/klerytondev/">
 <img style="border-radius: 50%;" src="https://avatars.githubusercontent.com/klerytondev" width="100px;" alt=""/>
 <br />
 <h3><b>Kleryton Souza</b></h3>
</a>

Desenvolvido por Kleryton de Souza 👋🏽 Entre em contato!

[![Twitter Badge](https://img.shields.io/badge/-@SouzaKleryton-1ca0f1?style=flat-square&labelColor=1ca0f1&logo=twitter&logoColor=white&link=https://twitter.com/SouzaKleryton)](https://twitter.com/SouzaKleryton) [![Linkedin Badge](https://img.shields.io/badge/-kleryton-souza?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/kleryton-souza/)](https://www.linkedin.com/in/kleryton-souza/) 
[![Gmail Badge](https://img.shields.io/badge/kleryton.dev@gmail.com-c14438?style=flat-square&logo=Gmail&logoColor=white&link=mailto:kleryton.dev@gmail.com)](mailto:kleryton.dev@gmail.com)
