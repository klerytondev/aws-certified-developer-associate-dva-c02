## Simulado para o Exame de Certificação AWS Certified Developer Associate (DVA-C02)

Este simulado contém uma coleção de questões para ajudar na preparação para o exame de certificação AWS Certified Developer Associate (DVA-C02).

### Índice

1. [Questão 1](#questão-1)
2. [Questão 2](#questão-2)
3. [Questão 3](#questão-3)
4. [Questão 4](#questão-4)
5. [Questão 5](#questão-5)
6. [Questão 6](#questão-6)
7. [Questão 7](#questão-7)
8. [Questão 8](#questão-8)
9. [Questão 9](#questão-9)
10. [Questão 10](#questão-10)
11. [Questão 11](#questão-11)
12. [Questão 12](#questão-12)
13. [Questão 13](#questão-13)
14. [Questão 14](#questão-14)
15. [Questão 15](#questão-15)
16. [Questão 16](#questão-16)
17. [Questão 17](#questão-17)
18. [Questão 18](#questão-18)
19. [Questão 19](#questão-19)
20. [Questão 20](#questão-20)
21. [Questão 21](#questão-21)
22. [Questão 22](#questão-22)
23. [Questão 23](#questão-23)
24. [Questão 24](#questão-24)
25. [Questão 25](#questão-25)
26. [Questão 26](#questão-26)
27. [Questão 27](#questão-27)
28. [Questão 28](#questão-28)
29. [Questão 29](#questão-29)
30. [Questão 30](#questão-30)
31. [Questão 31](#questão-31)
32. [Questão 32](#questão-32)
33. [Questão 33](#questão-33)
34. [Questão 34](#questão-34)
35. [Questão 35](#questão-35)
36. [Questão 36](#questão-36)
37. [Questão 37](#questão-37)
38. [Questão 38](#questão-38)
39. [Questão 39](#questão-39)
40. [Questão 40](#questão-40)
41. [Questão 41](#questão-41)
42. [Questão 42](#questão-42)
43. [Questão 43](#questão-43)
44. [Questão 44](#questão-44)
45. [Questão 45](#questão-45)
46. [Questão 46](#questão-46)
47. [Questão 47](#questão-47)
48. [Questão 48](#questão-48)
49. [Questão 49](#questão-49)
50. [Questão 50](#questão-50)
51. [Questão 51](#questão-51)
52. [Questão 52](#questão-52)
53. [Questão 53](#questão-53)
54. [Questão 54](#questão-54)
55. [Questão 55](#questão-55)
56. [Questão 56](#questão-56)
57. [Questão 57](#questão-57)
58. [Questão 58](#questão-58)
59. [Questão 59](#questão-59)
60. [Questão 60](#questão-60)
61. [Questão 61](#questão-61)
62. [Questão 62](#questão-62)
63. [Questão 63](#questão-63)
64. [Questão 64](#questão-64)
65. [Questão 65](#questão-65)

---

## Domínio 1: Desenvolvimento com Serviços AWS (32%)

### Questão 1

**Pergunta:**  
Você está desenvolvendo uma função Lambda que precisa processar arquivos de imagem carregados no S3. Qual é a melhor abordagem para configurar o gatilho?

**Opções:**
- a) Configurar um gatilho S3 direto para a função Lambda
- b) Usar SNS como intermediário entre S3 e Lambda
- c) Usar EventBridge para rotear eventos do S3 para Lambda
- d) Usar SQS como buffer entre S3 e Lambda

**[Resposta](dva_respostas.md#questão-1)**

### Questão 2

**Pergunta:**  
Uma aplicação precisa implementar idempotência para evitar processamento duplicado de mensagens SQS. Qual estratégia é mais eficaz?

**Opções:**
- a) Usar o campo MessageId do SQS como chave de idempotência
- b) Implementar DynamoDB para rastrear mensagens processadas
- c) Configurar visibility timeout maior
- d) Usar FIFO queue com deduplicação

**[Resposta](dva_respostas.md#questão-2)**

### Questão 3

**Pergunta:**  
Como otimizar uma consulta DynamoDB que está resultando em hot partitions?

**Opções:**
- a) Aumentar o RCU/WCU da tabela
- b) Criar um GSI com melhor distribuição de chave de partição
- c) Usar Query ao invés de Scan
- d) Implementar cache com ElastiCache

**[Resposta](dva_respostas.md#questão-3)**

### Questão 4

**Pergunta:**  
Qual é a principal diferença entre EventBridge e SNS para arquiteturas de microsserviços?

**Opções:**
- a) EventBridge suporta filtros mais complexos e roteamento baseado em regras
- b) SNS tem melhor performance para alto volume de mensagens
- c) EventBridge é mais barato para poucos assinantes
- d) SNS suporta transformação de mensagens

**[Resposta](dva_respostas.md#questão-4)**

### Questão 5

**Pergunta:**  
Uma função Lambda em VPC está apresentando cold starts muito longos. Como resolver isso?

**Opções:**
- a) Aumentar a memória alocada para a função
- b) Configurar Provisioned Concurrency
- c) Mover a função para fora da VPC se possível
- d) Usar container images ao invés de ZIP deployment

**[Resposta](dva_respostas.md#questão-5)**

### Questão 6

**Pergunta:**  
Como implementar versionamento de APIs no API Gateway para suportar múltiplas versões em produção?

**Opções:**
- a) Usar stages diferentes para cada versão
- b) Criar recursos diferentes para cada versão
- c) Usar path parameters para identificar versões
- d) Implementar custom authorizers para controle de versão

**[Resposta](dva_respostas.md#questão-6)**

### Questão 7

**Pergunta:**  
Qual estratégia é mais eficiente para processar milhões de registros de um stream Kinesis?

**Opções:**
- a) Uma única função Lambda com timeout máximo
- b) Múltiplas funções Lambda processando shards paralelos
- c) Usar Enhanced Fan-Out para múltiplos consumidores
- d) Processar em batches com Kinesis Analytics

**[Resposta](dva_respostas.md#questão-7)**

### Questão 8

**Pergunta:**  
Como implementar circuit breaker pattern em uma aplicação serverless?

**Opções:**
- a) Usar Step Functions para controlar retry e fallback
- b) Configurar Dead Letter Queues no Lambda
- c) Implementar custom logic no código da função
- d) Usar API Gateway throttling

**[Resposta](dva_respostas.md#questão-8)**

### Questão 9

**Pergunta:**  
Qual é a melhor prática para gerenciar configurações sensíveis em funções Lambda?

**Opções:**
- a) Usar variáveis de ambiente com KMS encryption
- b) Armazenar em Systems Manager Parameter Store (SecureString)
- c) Usar Secrets Manager para rotação automática
- d) Todas as opções acima, dependendo do caso de uso

**[Resposta](dva_respostas.md#questão-9)**

### Questão 10

**Pergunta:**  
Como otimizar custos de uma aplicação que usa DynamoDB com padrões de acesso imprevisíveis?

**Opções:**
- a) Usar On-Demand billing mode
- b) Configurar Auto Scaling para RCU/WCU
- c) Implementar DAX para cache
- d) Usar Global Tables

**[Resposta](dva_respostas.md#questão-10)**

## Domínio 2: Segurança (26%)

### Questão 11

**Pergunta:**  
Qual é a melhor prática para uma função Lambda acessar recursos em diferentes contas AWS?

**Opções:**
- a) Usar credenciais hard-coded
- b) Implementar cross-account role assumption
- c) Usar API keys compartilhadas
- d) Configurar VPC peering

**[Resposta](dva_respostas.md#questão-11)**

### Questão 12

**Pergunta:**  
Como implementar autorização granular em APIs REST usando API Gateway?

**Opções:**
- a) Usar IAM roles e policies
- b) Implementar Lambda authorizer customizado
- c) Usar Cognito User Pools com scopes
- d) Todas as opções podem ser usadas dependendo do cenário

**[Resposta](dva_respostas.md#questão-12)**

### Questão 13

**Pergunta:**  
Qual é a diferença principal entre Cognito User Pools e Identity Pools?

**Opções:**
- a) User Pools gerencia autenticação, Identity Pools gerencia autorização AWS
- b) User Pools é para web, Identity Pools é para mobile
- c) User Pools é gratuito, Identity Pools é pago
- d) Não há diferença significativa

**[Resposta](dva_respostas.md#questão-13)**

### Questão 14

**Pergunta:**  
Como garantir que dados sensíveis em DynamoDB sejam criptografados?

**Opções:**
- a) Usar client-side encryption antes de armazenar
- b) Habilitar encryption at rest com KMS
- c) Usar HTTPS para encryption in transit
- d) Todas as opções acima

**[Resposta](dva_respostas.md#questão-14)**

### Questão 15

**Pergunta:**  
Qual é a melhor estratégia para rotação automática de secrets de banco de dados?

**Opções:**
- a) Usar AWS Secrets Manager com rotação automática
- b) Configurar CloudWatch Events para trigger manual
- c) Implementar rotation logic em Lambda functions
- d) Usar Parameter Store com versioning

**[Resposta](dva_respostas.md#questão-15)**

### Questão 16

**Pergunta:**  
Como implementar o princípio do menor privilégio em políticas IAM para funções Lambda?

**Opções:**
- a) Usar managed policies da AWS
- b) Criar custom policies com actions específicas e recursos limitados
- c) Usar wildcard permissions para flexibilidade
- d) Aplicar deny policies explícitas

**[Resposta](dva_respostas.md#questão-16)**

### Questão 17

**Pergunta:**  
Qual método é mais seguro para uma aplicação web acessar recursos AWS?

**Opções:**
- a) Embed AWS credentials no código client-side
- b) Usar STS para obter temporary credentials
- c) Usar long-term IAM user credentials
- d) Compartilhar root account credentials

**[Resposta](dva_respostas.md#questão-17)**

### Questão 18

**Pergunta:**  
Como auditar todas as chamadas de API em uma aplicação AWS?

**Opções:**
- a) Habilitar CloudTrail em todas as regiões
- b) Configurar VPC Flow Logs
- c) Usar AWS Config para compliance
- d) Implementar custom logging em cada serviço

**[Resposta](dva_respostas.md#questão-18)**

### Questão 19

**Pergunta:**  
Qual é a melhor prática para proteger APIs contra ataques DDoS?

**Opções:**
- a) Usar CloudFront com AWS Shield
- b) Configurar throttling no API Gateway
- c) Implementar rate limiting por IP
- d) Todas as opções acima

**[Resposta](dva_respostas.md#questão-19)**

### Questão 20

**Pergunta:**  
Como garantir que apenas usuários autorizados possam invocar uma função Lambda?

**Opções:**
- a) Usar resource-based policies
- b) Configurar API Gateway com authorizers
- c) Implementar application-level authentication
- d) Todas as opções podem ser apropriadas

**[Resposta](dva_respostas.md#questão-20)**

## Domínio 3: Implantação (24%)

### Questão 21

**Pergunta:**  
Qual estratégia de deployment é mais segura para atualizações de funções Lambda críticas?

**Opções:**
- a) All-at-once deployment
- b) Blue/Green deployment com aliases
- c) Canary deployment com gradual traffic shift
- d) Rolling deployment

**[Resposta](dva_respostas.md#questão-21)**

### Questão 22

**Pergunta:**  
Como configurar um pipeline CI/CD que automaticamente execute testes antes do deployment?

**Opções:**
- a) CodePipeline → CodeBuild → CodeDeploy
- b) CodeCommit → CodeBuild → Manual approval
- c) GitHub Actions → CodeBuild → Lambda
- d) Jenkins → CodeDeploy → CloudFormation

**[Resposta](dva_respostas.md#questão-22)**

### Questão 23

**Pergunta:**  
Qual é a principal vantagem do AWS SAM sobre CloudFormation para aplicações serverless?

**Opções:**
- a) SAM é mais rápido para deploy
- b) SAM tem templates mais simples e abstrações específicas para serverless
- c) SAM suporta mais recursos AWS
- d) SAM é gratuito enquanto CloudFormation é pago

**[Resposta](dva_respostas.md#questão-23)**

### Questão 24

**Pergunta:**  
Como implementar rollback automático em caso de falha no deployment?

**Opções:**
- a) Usar CloudWatch Alarms com CodeDeploy
- b) Configurar health checks no ALB
- c) Implementar custom scripts de rollback
- d) Usar versioning manual

**[Resposta](dva_respostas.md#questão-24)**

### Questão 25

**Pergunta:**  
Qual é a melhor prática para gerenciar diferentes ambientes (dev, staging, prod)?

**Opções:**
- a) Usar contas AWS separadas
- b) Usar stacks CloudFormation separadas na mesma conta
- c) Usar namespaces diferentes nos recursos
- d) Usar diferentes regiões AWS

**[Resposta](dva_respostas.md#questão-25)**

### Questão 26

**Pergunta:**  
Como configurar deployment zero-downtime para APIs no API Gateway?

**Opções:**
- a) Usar stages diferentes para deployment
- b) Implementar blue/green deployment com Route 53
- c) Usar canary releases com weighted routing
- d) Configurar auto-scaling groups

**[Resposta](dva_respostas.md#questão-26)**

### Questão 27

**Pergunta:**  
Qual ferramenta é melhor para Infrastructure as Code com TypeScript/Python?

**Opções:**
- a) AWS CDK
- b) CloudFormation
- c) Terraform
- d) AWS SAM

**[Resposta](dva_respostas.md#questão-27)**

### Questão 28

**Pergunta:**  
Como automatizar o build e deployment de imagens Docker para Lambda?

**Opções:**
- a) CodeBuild → ECR → Lambda deployment
- b) Docker Hub → Lambda direct deployment
- c) GitHub Actions → S3 → Lambda
- d) Jenkins → CodeDeploy → Lambda

**[Resposta](dva_respostas.md#questão-28)**

### Questão 29

**Pergunta:**  
Qual é a melhor estratégia para gerenciar configurações específicas por ambiente?

**Opções:**
- a) Systems Manager Parameter Store com prefixos por ambiente
- b) Hardcode valores no código
- c) Usar variáveis de ambiente no deployment
- d) Arquivos de configuração no S3

**[Resposta](dva_respostas.md#questão-29)**

### Questão 30

**Pergunta:**  
Como implementar aprovações manuais em pipelines CI/CD críticos?

**Opções:**
- a) CodePipeline com manual approval actions
- b) SNS notifications para aprovação por email
- c) Slack integration com approval workflows
- d) Custom Lambda functions para approval logic

**[Resposta](dva_respostas.md#questão-30)**

## Domínio 4: Solução de Problemas e Otimização (18%)

### Questão 31

**Pergunta:**  
Uma função Lambda está apresentando timeouts intermitentes. Como diagnosticar a causa?

**Opções:**
- a) Analisar CloudWatch Logs e métricas de duration
- b) Usar X-Ray para trace distributed calls
- c) Verificar conexões de rede e dependencies
- d) Todas as opções acima

**[Resposta](dva_respostas.md#questão-31)**

### Questão 32

**Pergunta:**  
Como identificar gargalos de performance em uma arquitetura de microsserviços?

**Opções:**
- a) CloudWatch custom metrics
- b) X-Ray service map e trace analysis
- c) AWS Personal Health Dashboard
- d) VPC Flow Logs analysis

**[Resposta](dva_respostas.md#questão-32)**

### Questão 33

**Pergunta:**  
Uma aplicação está recebendo muitos erros 5XX do API Gateway. Qual é o primeiro passo para investigar?

**Opções:**
- a) Verificar CloudWatch Logs do API Gateway
- b) Analisar logs da função Lambda backend
- c) Verificar throttling limits
- d) Todas as opções devem ser verificadas

**[Resposta](dva_respostas.md#questão-33)**

### Questão 34

**Pergunta:**  
Como otimizar uma consulta DynamoDB que está consumindo muitas RCUs?

**Opções:**
- a) Implementar eventually consistent reads
- b) Usar projection no GSI para reduzir dados retornados
- c) Implementar pagination com Limit parameter
- d) Todas as opções acima

**[Resposta](dva_respostas.md#questão-34)**

### Questão 35

**Pergunta:**  
Qual é a melhor estratégia para debug de cold starts em funções Lambda?

**Opções:**
- a) Usar CloudWatch Insights para analisar init duration
- b) Implementar warmup scheduling
- c) Otimizar código de inicialização
- d) Todas as opções acima

**[Resposta](dva_respostas.md#questão-35)**

### Questão 36

**Pergunta:**  
Como monitorar a saúde de uma aplicação distribuída em tempo real?

**Opções:**
- a) CloudWatch Dashboards com custom metrics
- b) X-Ray para visualização de traces
- c) AWS Health API para service status
- d) Combinação de todas as ferramentas

**[Resposta](dva_respostas.md#questão-36)**

### Questão 37

**Pergunta:**  
Uma fila SQS está acumulando mensagens. Como identificar o problema?

**Opções:**
- a) Verificar ApproximateNumberOfMessages metric
- b) Analisar consumer performance e errors
- c) Verificar visibility timeout configuration
- d) Todas as opções são relevantes

**[Resposta](dva_respostas.md#questão-37)**

### Questão 38

**Pergunta:**  
Como implementar alertas proativos para anomalias de performance?

**Opções:**
- a) CloudWatch Anomaly Detection
- b) Custom CloudWatch Alarms com thresholds estáticos
- c) Third-party monitoring tools
- d) Manual monitoring de métricas

**[Resposta](dva_respostas.md#questão-38)**

### Questão 39

**Pergunta:**  
Qual é a melhor abordagem para otimizar custos de uma aplicação serverless?

**Opções:**
- a) Ajustar memory allocation das funções Lambda
- b) Usar Reserved Capacity para DynamoDB
- c) Implementar caching strategies
- d) Todas as estratégias podem ser aplicadas

**[Resposta](dva_respostas.md#questão-39)**

### Questão 40

**Pergunta:**  
Como resolver problemas de concorrência em funções Lambda?

**Opções:**
- a) Aumentar reserved concurrency
- b) Implementar exponential backoff em retries
- c) Usar SQS como buffer para controlar throughput
- d) Todas as abordagens podem ser necessárias

**[Resposta](dva_respostas.md#questão-40)**

## Questões Adicionais (Casos Complexos)

### Questão 41

**Pergunta:**  
Você precisa implementar uma arquitetura event-driven que processe pedidos de e-commerce. O sistema deve garantir ordem de processamento, durabilidade e capacidade de replay. Qual combinação de serviços é mais adequada?

**Opções:**
- a) API Gateway → Lambda → DynamoDB
- b) SQS FIFO → Lambda → RDS
- c) Kinesis Data Streams → Lambda → DynamoDB Streams
- d) EventBridge → Step Functions → Aurora Serverless

**[Resposta](dva_respostas.md#questão-41)**

### Questão 42

**Pergunta:**  
Uma aplicação precisa processar uploads de arquivos grandes (até 5GB) de forma assíncrona. Qual arquitetura oferece melhor performance e custo?

**Opções:**
- a) API Gateway → Lambda → S3
- b) S3 Transfer Acceleration → Lambda trigger → SQS
- c) S3 Multipart Upload → EventBridge → Lambda
- d) Direct S3 upload → S3 Event → SQS → Lambda

**[Resposta](dva_respostas.md#questão-42)**

### Questão 43

**Pergunta:**  
Como implementar uma estratégia de caching multi-layer para uma API de alta performance?

**Opções:**
- a) CloudFront → API Gateway Cache → ElastiCache → DynamoDB
- b) Route 53 → ALB → ElastiCache → RDS
- c) CloudFront → Lambda@Edge → DynamoDB
- d) API Gateway → Lambda → DAX → DynamoDB

**[Resposta](dva_respostas.md#questão-43)**

### Questão 44

**Pergunta:**  
Qual é a melhor abordagem para implementar saga pattern em uma arquitetura serverless?

**Opções:**
- a) Step Functions com error handling e compensation
- b) EventBridge com dead letter queues
- c) SQS com custom orchestration logic
- d) Lambda functions com manual coordination

**[Resposta](dva_respostas.md#questão-44)**

### Questão 45

**Pergunta:**  
Como implementar rate limiting distribuído para uma API que serve milhões de requests?

**Opções:**
- a) API Gateway throttling apenas
- b) ElastiCache para counter distribuído
- c) DynamoDB com TTL para rate limiting
- d) Combinação de API Gateway + ElastiCache + custom logic

**[Resposta](dva_respostas.md#questão-45)**

## Questões de Cenários Reais

### Questão 46

**Pergunta:**  
Uma startup está migrando de arquitetura monolítica para microsserviços. Qual estratégia de decomposição é mais segura?

**Opções:**
- a) Strangler Fig pattern com API Gateway
- b) Big Bang migration para Lambda
- c) Database-per-service imediatamente
- d) Event sourcing desde o início

**[Resposta](dva_respostas.md#questão-46)**

### Questão 47

**Pergunta:**  
Como garantir GDPR compliance em uma aplicação serverless que processa dados de usuários europeus?

**Opções:**
- a) Usar só região eu-west-1
- b) Implementar data encryption e right to be forgotten
- c) Usar Cognito para user management apenas
- d) Evitar log de dados pessoais

**[Resposta](dva_respostas.md#questão-47)**

### Questão 48

**Pergunta:**  
Uma aplicação fintech precisa garantir consistência ACID. Qual abordagem é mais adequada?

**Opções:**
- a) DynamoDB Transactions
- b) RDS com ACID compliance
- c) EventBridge com compensation logic
- d) Step Functions para orchestration

**[Resposta](dva_respostas.md#questão-48)**

### Questão 49

**Pergunta:**  
Como implementar multi-tenancy em uma aplicação SaaS serverless?

**Opções:**
- a) Separate AWS accounts por tenant
- b) Separate databases com tenant isolation
- c) API Gateway custom authorizers para tenant routing
- d) Todas as abordagens têm casos de uso válidos

**[Resposta](dva_respostas.md#questão-49)**

### Questão 50

**Pergunta:**  
Qual estratégia oferece melhor disaster recovery para aplicações serverless?

**Opções:**
- a) Multi-region deployment com Route 53 health checks
- b) Database replication cross-region
- c) Infrastructure as Code para rapid rebuilding
- d) Todas as estratégias são complementares

**[Resposta](dva_respostas.md#questão-50)**

## Questões Avançadas de Performance

### Questão 51

**Pergunta:**  
Como otimizar uma função Lambda que processa imagens para reduzir cold start time?

**Opções:**
- a) Usar container images com otimizações específicas
- b) Implementar provisioned concurrency
- c) Otimizar dependencies e bundle size
- d) Todas as otimizações podem ser necessárias

**[Resposta](dva_respostas.md#questão-51)**

### Questão 52

**Pergunta:**  
Qual é a melhor estratégia para otimizar custos de DynamoDB em uma aplicação com picos de tráfego?

**Opções:**
- a) On-demand billing mode
- b) Auto-scaling com provisioned capacity
- c) Scheduled scaling baseado em patterns históricos
- d) Combinação de strategies dependendo do workload

**[Resposta](dva_respostas.md#questão-52)**

### Questão 53

**Pergunta:**  
Como implementar connection pooling eficiente em funções Lambda que acessam RDS?

**Opções:**
- a) RDS Proxy para connection pooling
- b) Global connection variables em Lambda
- c) External connection pooling service
- d) Connection-per-invocation approach

**[Resposta](dva_respostas.md#questão-53)**

### Questão 54

**Pergunta:**  
Qual abordagem oferece melhor performance para real-time analytics em streaming data?

**Opções:**
- a) Kinesis Data Analytics com SQL queries
- b) Lambda functions processando Kinesis streams
- c) DynamoDB Streams com aggregation logic
- d) Elasticsearch com Kinesis Firehose

**[Resposta](dva_respostas.md#questão-54)**

### Questão 55

**Pergunta:**  
Como otimizar uma API que serve dados quasi-estáticos para milhões de usuários?

**Opções:**
- a) CloudFront com long TTL
- b) API Gateway caching
- c) ElastiCache para data layer
- d) Combinação de todas as estratégias de cache

**[Resposta](dva_respostas.md#questão-55)**

## Questões de Debugging e Troubleshooting

### Questão 56

**Pergunta:**  
Uma função Lambda está falhando intermitentemente com "Task timed out". Como investigar?

**Opções:**
- a) Analisar CloudWatch Logs para patterns
- b) Usar X-Ray para identificar bottlenecks
- c) Verificar memory usage e external dependencies
- d) Todas as abordagens são necessárias

**[Resposta](dva_respostas.md#questão-56)**

### Questão 57

**Pergunta:**  
Como debugar problemas de conectividade entre Lambda em VPC e recursos externos?

**Opções:**
- a) Verificar security groups e NACLs
- b) Confirmar route tables e NAT Gateway
- c) Testar connectivity com VPC endpoints
- d) Todas as verificações de networking

**[Resposta](dva_respostas.md#questão-57)**

### Questão 58

**Pergunta:**  
Uma aplicação apresenta latência alta em queries DynamoDB. Como diagnosticar?

**Opções:**
- a) Verificar hot partitions com CloudWatch metrics
- b) Analisar access patterns e query efficiency
- c) Verificar consistent vs eventually consistent reads
- d) Todas as análises de performance

**[Resposta](dva_respostas.md#questão-58)**

### Questão 59

**Pergunta:**  
Como identificar memory leaks em funções Lambda de longa duração?

**Opções:**
- a) CloudWatch memory utilization metrics
- b) Custom application metrics
- c) X-Ray memory profiling
- d) Não há memory leaks em Lambda devido ao stateless nature

**[Resposta](dva_respostas.md#questão-59)**

### Questão 60

**Pergunta:**  
Uma API está retornando erros 502 Bad Gateway intermitentemente. Onde investigar primeiro?

**Opções:**
- a) API Gateway logs e metrics
- b) Lambda function errors e timeouts
- c) Backend service health
- d) Todas as camadas da arquitetura

**[Resposta](dva_respostas.md#questão-60)**

## Questões de Casos de Uso Específicos

### Questão 61

**Pergunta:**  
Como implementar uma arquitetura para processamento de logs em tempo real com alertas?

**Opções:**
- a) CloudWatch Logs → Lambda → SNS
- b) Kinesis Firehose → S3 → Athena
- c) Kinesis Data Streams → Lambda → CloudWatch Alarms
- d) EventBridge → Lambda → SES

**[Resposta](dva_respostas.md#questão-61)**

### Questão 62

**Pergunta:**  
Qual é a melhor arquitetura para um sistema de votação online que garanta integridade?

**Opções:**
- a) API Gateway → Lambda → DynamoDB com conditional writes
- b) ALB → ECS → RDS com transactions
- c) CloudFront → Lambda@Edge → DynamoDB Global Tables
- d) EventBridge → Step Functions → Audit trail

**[Resposta](dva_respostas.md#questão-62)**

### Questão 63

**Pergunta:**  
Como implementar um sistema de recomendação em tempo real usando AWS services?

**Opções:**
- a) Lambda → DynamoDB → ElastiCache
- b) Kinesis → Lambda → Neptune
- c) SageMaker → API Gateway → Lambda
- d) Personalize → API Gateway → CloudFront

**[Resposta](dva_respostas.md#questão-63)**

### Questão 64

**Pergunta:**  
Qual arquitetura suporta melhor um marketplace com múltiplos vendors?

**Opções:**
- a) Multi-tenant single database
- b) Microservices com database-per-service
- c) Event-driven architecture com CQRS
- d) Serverless with tenant isolation

**[Resposta](dva_respostas.md#questão-64)**

### Questão 65

**Pergunta:**  
Como implementar uma solução de backup e restore para uma aplicação serverless completa?

**Opções:**
- a) AWS Backup para todos os resources
- b) Infrastructure as Code com version control
- c) Manual snapshots de databases
- d) Combinação de automated backups e IaC

**[Resposta](dva_respostas.md#questão-65)**

---

© 2025 · Curado por **Kleryton de Souza** · [LinkedIn](https://www.linkedin.com/in/kleryton-souza/)
