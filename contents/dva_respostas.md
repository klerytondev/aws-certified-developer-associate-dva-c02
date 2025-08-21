## Respostas do Simulado para o Exame de Certificação AWS Certified Developer Associate (DVA-C02)

Esta página contém as respostas detalhadas para as questões do exame de certificação AWS Certified Developer Associate (DVA-C02).

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

**Resposta:** A) Configurar um gatilho S3 direto para a função Lambda

**Resumo:** Para processamento de imagens carregadas no S3, o gatilho direto é a abordagem mais simples e eficiente. O S3 pode invocar Lambda diretamente quando objetos são criados, oferecendo baixa latência e menos componentes na arquitetura. SNS ou EventBridge adicionariam complexidade desnecessária para este caso de uso específico.

**[Pergunta](dva_perguntas.md#questão-1)**

---

### Questão 2

**Resposta:** B) Implementar DynamoDB para rastrear mensagens processadas

**Resumo:** A estratégia mais robusta para idempotência é usar DynamoDB para rastrear messageIds ou custom deduplication keys. Isso permite verificar se uma mensagem já foi processada antes de executar a lógica de negócio. FIFO queues têm limitações de throughput, e MessageId pode ser reutilizado em diferentes queues.

**[Pergunta](dva_perguntas.md#questão-2)**

---

### Questão 3

**Resposta:** B) Criar um GSI com melhor distribuição de chave de partição

**Resumo:** Hot partitions são causadas por distribuição desigual de dados. Criar um GSI (Global Secondary Index) com uma chave de partição que distribua melhor os dados resolve o problema na origem. Aumentar RCU/WCU é uma solução temporária e cara que não resolve a causa raiz.

**[Pergunta](dva_perguntas.md#questão-3)**

---

### Questão 4

**Resposta:** A) EventBridge suporta filtros mais complexos e roteamento baseado em regras

**Resumo:** EventBridge oferece filtros avançados, transformação de mensagens, e roteamento baseado em regras de conteúdo. É ideal para arquiteturas event-driven complexas. SNS é mais simples e eficiente para casos de pub/sub básicos com alto volume.

**[Pergunta](dva_perguntas.md#questão-4)**

---

### Questão 5

**Resposta:** C) Mover a função para fora da VPC se possível

**Resumo:** Funções Lambda em VPC têm cold starts mais longos devido à criação de ENIs (Elastic Network Interfaces). Se a função não precisa acessar recursos privados, movê-la para fora da VPC elimina esse overhead. Provisioned Concurrency também resolve, mas tem custo adicional.

**[Pergunta](dva_perguntas.md#questão-5)**

---

### Questão 6

**Resposta:** A) Usar stages diferentes para cada versão

**Resumo:** Stages no API Gateway são a forma nativa de gerenciar diferentes versões. Cada stage pode apontar para diferentes versões de Lambda functions ou backends, permitindo deployment independente e rollback fácil. É mais limpo que usar path parameters ou recursos diferentes.

**[Pergunta](dva_perguntas.md#questão-6)**

---

### Questão 7

**Resposta:** C) Usar Enhanced Fan-Out para múltiplos consumidores

**Resumo:** Enhanced Fan-Out permite que múltiplos consumidores processem o mesmo stream em paralelo com throughput dedicado de 2MB/s por shard por consumidor. É ideal para processamento de alto volume com baixa latência.

**[Pergunta](dva_perguntas.md#questão-7)**

---

### Questão 8

**Resposta:** A) Usar Step Functions para controlar retry e fallback

**Resumo:** Step Functions oferece controle declarativo sobre retry logic, error handling, e circuit breaker patterns através de states como Choice, Wait, e Retry. Permite implementar timeouts, backoff exponencial, e fallback strategies de forma visual e gerenciável.

**[Pergunta](dva_perguntas.md#questão-8)**

---

### Questão 9

**Resposta:** D) Todas as opções acima, dependendo do caso de uso

**Resumo:** A escolha depende do cenário: variáveis de ambiente com KMS para configurações simples, Parameter Store para hierarquia de configurações, e Secrets Manager para secrets que precisam de rotação automática. Cada um tem seu lugar numa arquitetura bem projetada.

**[Pergunta](dva_perguntas.md#questão-9)**

---

### Questão 10

**Resposta:** A) Usar On-Demand billing mode

**Resumo:** Para workloads imprevisíveis, On-Demand elimina a necessidade de provisionar capacidade e paga apenas pelo uso real. Auto Scaling ainda requer estimativas e pode não reagir rápido suficiente para picos súbitos.

**[Pergunta](dva_perguntas.md#questão-10)**

---

## Domínio 2: Segurança (26%)

### Questão 11

**Resposta:** B) Implementar cross-account role assumption

**Resumo:** Cross-account role assumption usando STS é a prática recomendada. A função Lambda assume uma role na conta de destino usando temporary credentials, seguindo o princípio de least privilege e eliminando a necessidade de credenciais estáticas.

**[Pergunta](dva_perguntas.md#questão-11)**

---

### Questão 12

**Resposta:** D) Todas as opções podem ser usadas dependendo do cenário

**Resumo:** A escolha depende dos requisitos: IAM para integração com AWS services, Lambda authorizers para lógica custom complexa, Cognito User Pools para aplicações com usuários finais. Frequentemente são usados em combinação.

**[Pergunta](dva_perguntas.md#questão-12)**

---

### Questão 13

**Resposta:** A) User Pools gerencia autenticação, Identity Pools gerencia autorização AWS

**Resumo:** User Pools foca em autenticação de usuários (sign-up, sign-in, password recovery). Identity Pools (Federated Identity) converte tokens de authentication em temporary AWS credentials para autorizar acesso a recursos AWS.

**[Pergunta](dva_perguntas.md#questão-13)**

---

### Questão 14

**Resposta:** D) Todas as opções acima

**Resumo:** Uma estratégia completa de segurança requer múltiplas camadas: client-side encryption para dados ultra-sensíveis, encryption at rest para proteção de storage, e TLS para encryption in transit. Cada camada protege contra diferentes vetores de ataque.

**[Pergunta](dva_perguntas.md#questão-14)**

---

### Questão 15

**Resposta:** A) Usar AWS Secrets Manager com rotação automática

**Resumo:** Secrets Manager foi projetado especificamente para este caso de uso, oferecendo rotação automática com zero-downtime através de versioning. Inclui integração nativa com RDS, Redshift, e DocumentDB.

**[Pergunta](dva_perguntas.md#questão-15)**

---

### Questão 16

**Resposta:** B) Criar custom policies com actions específicas e recursos limitados

**Resumo:** O princípio do menor privilégio requer policies específicas que concedem apenas as permissões mínimas necessárias. Managed policies são muitas vezes muito permissivas, e wildcards violam o princípio de security by design.

**[Pergunta](dva_perguntas.md#questão-16)**

---

### Questão 17

**Resposta:** B) Usar STS para obter temporary credentials

**Resumo:** STS (Security Token Service) fornece temporary credentials com escopo limitado e tempo de vida definido. É a abordagem mais segura para aplicações web, eliminando riscos de credenciais vazadas no client-side code.

**[Pergunta](dva_perguntas.md#questão-17)**

---

### Questão 18

**Resposta:** A) Habilitar CloudTrail em todas as regiões

**Resumo:** CloudTrail é o serviço específico para auditoria de API calls. Deve ser habilitado em todas as regiões onde a aplicação opera e configurado para armazenar logs em S3 com encryption e integrity validation.

**[Pergunta](dva_perguntas.md#questão-18)**

---

### Questão 19

**Resposta:** D) Todas as opções acima

**Resumo:** Proteção contra DDoS requer defesa em profundidade: CloudFront com AWS Shield para absorver ataques de rede, API Gateway throttling para controlar rate per client, e rate limiting granular baseado em padrões de comportamento.

**[Pergunta](dva_perguntas.md#questão-19)**

---

### Questão 20

**Resposta:** D) Todas as opções podem ser apropriadas

**Resumo:** A escolha depende de como a função é invocada: resource-based policies para invocação direta, API Gateway authorizers para APIs públicas, e application-level auth para controle granular de business logic.

**[Pergunta](dva_perguntas.md#questão-20)**

---

## Domínio 3: Implantação (24%)

### Questão 21

**Resposta:** C) Canary deployment com gradual traffic shift

**Resumo:** Canary deployment permite testar a nova versão com uma pequena porcentagem do tráfego primeiro, gradualmente aumentando se não houver problemas. Oferece o melhor balance entre segurança e agilidade para atualizações críticas.

**[Pergunta](dva_perguntas.md#questão-21)**

---

### Questão 22

**Resposta:** A) CodePipeline → CodeBuild → CodeDeploy

**Resumo:** Esta é a sequência padrão AWS para CI/CD: CodePipeline orquestra o pipeline, CodeBuild executa testes e build, CodeDeploy realiza deployment com strategies configuráveis. Integra nativamente com outros serviços AWS.

**[Pergunta](dva_perguntas.md#questão-22)**

---

### Questão 23

**Resposta:** B) SAM tem templates mais simples e abstrações específicas para serverless

**Resumo:** SAM (Serverless Application Model) oferece syntax simplificada para recursos serverless comuns. Um recurso SAM pode gerar múltiplos recursos CloudFormation, reduzindo verbosidade e complexidade dos templates.

**[Pergunta](dva_perguntas.md#questão-23)**

---

### Questão 24

**Resposta:** A) Usar CloudWatch Alarms com CodeDeploy

**Resumo:** CodeDeploy pode monitorar CloudWatch Alarms durante deployment e automaticamente fazer rollback se métricas indicarem problemas. Oferece rollback automatizado baseado em health checks objetivos.

**[Pergunta](dva_perguntas.md#questão-24)**

---

### Questão 25

**Resposta:** A) Usar contas AWS separadas

**Resumo:** Contas separadas oferecem isolamento completo de recursos, billing, e permissões. É a prática recomendada para environments críticos, facilitando governance e security através de account boundaries.

**[Pergunta](dva_perguntas.md#questão-25)**

---

### Questão 26

**Resposta:** A) Usar stages diferentes para deployment

**Resumo:** API Gateway stages permitem deployment zero-downtime ao alternar entre stages após validação. É simpler e mais cost-effective que blue/green deployment com Route 53 para APIs.

**[Pergunta](dva_perguntas.md#questão-26)**

---

### Questão 27

**Resposta:** A) AWS CDK

**Resumo:** AWS CDK permite definir infrastructure usando linguagens familiares (TypeScript, Python, etc.) com type safety, IDE support, e abstrações de alto nível. Compila para CloudFormation templates para deployment.

**[Pergunta](dva_perguntas.md#questão-27)**

---

### Questão 28

**Resposta:** A) CodeBuild → ECR → Lambda deployment

**Resumo:** Esta é a pipeline recomendada para container images: CodeBuild constrói e publica a imagem no ECR, depois atualiza a função Lambda para usar a nova imagem. Oferece versionamento robusto de images.

**[Pergunta](dva_perguntas.md#questão-28)**

---

### Questão 29

**Resposta:** A) Systems Manager Parameter Store com prefixos por ambiente

**Resumo:** Parameter Store com hierarchical naming (e.g., /dev/app/config, /prod/app/config) oferece gerenciamento centralizado, versionamento, e encryption de configurações por ambiente.

**[Pergunta](dva_perguntas.md#questão-29)**

---

### Questão 30

**Resposta:** A) CodePipeline com manual approval actions

**Resumo:** CodePipeline tem manual approval actions nativas que pausam o pipeline aguardando aprovação humana. Integra com SNS para notificações e suporta multiple approvers com diferentes roles.

**[Pergunta](dva_perguntas.md#questão-30)**

---

## Domínio 4: Solução de Problemas e Otimização (18%)

### Questão 31

**Resposta:** D) Todas as opções acima

**Resumo:** Debugging timeouts requer análise completa: CloudWatch Logs para erros específicos, X-Ray para latência distribuída, e verificação de networking/dependencies. Cada ferramenta oferece insights complementares.

**[Pergunta](dva_perguntas.md#questão-31)**

---

### Questão 32

**Resposta:** B) X-Ray service map e trace analysis

**Resumo:** X-Ray é especificamente projetado para distributed tracing, oferecendo service map visual e detailed trace analysis que identifica gargalos, latência, e error rates across microservices.

**[Pergunta](dva_perguntas.md#questão-32)**

---

### Questão 33

**Resposta:** D) Todas as opções devem ser verificadas

**Resumo:** Erros 5XX podem originar em múltiplas camadas. Uma abordagem sistemática verifica API Gateway logs, Lambda errors, throttling limits, e backend health para identificar a root cause.

**[Pergunta](dva_perguntas.md#questão-33)**

---

### Questão 34

**Resposta:** D) Todas as opções acima

**Resumo:** Otimização de RCU envolve múltiplas estratégias: eventually consistent reads reduzem RCU pela metade, projection em GSI minimiza dados transferidos, e pagination reduz o tamanho de cada query.

**[Pergunta](dva_perguntas.md#questão-34)**

---

### Questão 35

**Resposta:** D) Todas as opções acima

**Resumo:** Cold start optimization requer abordagem multi-facetada: análise de métricas para identificar padrões, warmup scheduling para critical functions, e code optimization para reduzir initialization time.

**[Pergunta](dva_perguntas.md#questão-35)**

---

### Questão 36

**Resposta:** D) Combinação de todas as ferramentas

**Resumo:** Monitoramento efetivo de aplicações distribuídas requer múltiplas ferramentas: CloudWatch para métricas e alertas, X-Ray para trace visualization, e Health API para AWS service status.

**[Pergunta](dva_perguntas.md#questão-36)**

---

### Questão 37

**Resposta:** D) Todas as opções são relevantes

**Resumo:** Message backlog pode ter múltiplas causas: verificar queue depth metrics, analisar consumer performance/errors, e validar visibility timeout configuration que pode causar reprocessing.

**[Pergunta](dva_perguntas.md#questão-37)**

---

### Questão 38

**Resposta:** A) CloudWatch Anomaly Detection

**Resumo:** CloudWatch Anomaly Detection usa machine learning para identificar padrões anômalos em métricas, oferecendo alertas proativos baseados em comportamento histórico ao invés de thresholds estáticos.

**[Pergunta](dva_perguntas.md#questão-38)**

---

### Questão 39

**Resposta:** D) Todas as estratégias podem ser aplicadas

**Resumo:** Otimização de custos serverless é multi-dimensional: right-sizing de Lambda memory, Reserved Capacity para DynamoDB com workloads previsíveis, e caching para reduzir compute e database costs.

**[Pergunta](dva_perguntas.md#questão-39)**

---

### Questão 40

**Resposta:** D) Todas as abordagens podem ser necessárias

**Resumo:** Problemas de concorrência podem requerer múltiplas soluções: reserved concurrency para garantir resources, exponential backoff para handles transient errors, e SQS buffering para smooth traffic spikes.

**[Pergunta](dva_perguntas.md#questão-40)**

---

## Questões Adicionais (Casos Complexos)

### Questão 41

**Resposta:** C) Kinesis Data Streams → Lambda → DynamoDB Streams

**Resumo:** Para e-commerce que requer ordem, durabilidade e replay: Kinesis garante order por partition key, durabilidade com retenção configurável, e capacidade de replay. DynamoDB Streams permite propagação de mudanças para downstream processing.

**[Pergunta](dva_perguntas.md#questão-41)**

---

### Questão 42

**Resposta:** D) Direct S3 upload → S3 Event → SQS → Lambda

**Resumo:** Para arquivos grandes: direct S3 upload evita timeouts de API Gateway, S3 events trigger processing, SQS como buffer para handle spikes, e Lambda para processamento assíncrono. Mais cost-effective e scalable.

**[Pergunta](dva_perguntas.md#questão-42)**

---

### Questão 43

**Resposta:** A) CloudFront → API Gateway Cache → ElastiCache → DynamoDB

**Resumo:** Multi-layer caching: CloudFront para edge caching global, API Gateway cache para responses, ElastiCache para application data, e DynamoDB como data store. Cada layer reduz latência e load downstream.

**[Pergunta](dva_perguntas.md#questão-43)**

---

### Questão 44

**Resposta:** A) Step Functions com error handling e compensation

**Resumo:** Step Functions oferece workflow orchestration com error handling nativo, retry logic, e compensation actions. Ideal para implementar saga pattern com visibility e reliability em distributed transactions.

**[Pergunta](dva_perguntas.md#questão-44)**

---

### Questão 45

**Resposta:** D) Combinação de API Gateway + ElastiCache + custom logic

**Resumo:** Rate limiting distribuído requer múltiplas layers: API Gateway para basic throttling, ElastiCache para distributed counters com TTL, e custom logic para business rules complexas e sliding window algorithms.

**[Pergunta](dva_perguntas.md#questão-45)**

---

## Questões de Cenários Reais

### Questão 46

**Resposta:** A) Strangler Fig pattern com API Gateway

**Resumo:** Strangler Fig permite migração gradual interceptando requests com API Gateway e roteando para monolith ou microservices. Reduz risco permitindo rollback fácil e testing incremental de cada microservice.

**[Pergunta](dva_perguntas.md#questão-46)**

---

### Questão 47

**Resposta:** B) Implementar data encryption e right to be forgotten

**Resumo:** GDPR compliance requer: encryption at rest/transit, data minimization, right to deletion/portability, e audit trails. Região é importante mas não suficiente - requires comprehensive data governance.

**[Pergunta](dva_perguntas.md#questão-47)**

---

### Questão 48

**Resposta:** A) DynamoDB Transactions

**Resumo:** Para fintech, DynamoDB Transactions oferece ACID compliance para operações que envolvem múltiplos items/tables, essencial para consistency em operações financeiras críticas.

**[Pergunta](dva_perguntas.md#questão-48)**

---

### Questão 49

**Resposta:** D) Todas as abordagens têm casos de uso válidos

**Resumo:** Multi-tenancy strategy depende de requirements: separate accounts para maximum isolation, shared infrastructure com tenant isolation para cost optimization, ou hybrid approaches baseados em tenant tiers.

**[Pergunta](dva_perguntas.md#questão-49)**

---

### Questão 50

**Resposta:** D) Todas as estratégias são complementares

**Resumo:** DR efetivo combina: multi-region deployment para availability, data replication para consistency, e IaC para rapid recovery. RTO/RPO requirements determinam a combinação apropriada.

**[Pergunta](dva_perguntas.md#questão-50)**

---

## Questões Avançadas de Performance

### Questão 51

**Resposta:** D) Todas as otimizações podem ser necessárias

**Resumo:** Image processing optimization é multi-facetada: container images permitem caching de layers, provisioned concurrency elimina cold starts para critical functions, e bundle optimization reduz initialization time.

**[Pergunta](dva_perguntas.md#questão-51)**

---

### Questão 52

**Resposta:** D) Combinação de strategies dependendo do workload

**Resumo:** Workloads com picos variáveis podem beneficiar de: On-demand para spikes imprevisíveis, Auto-scaling para padrões conhecidos, e scheduled scaling para patterns regulares. Hybrid approach otimiza costs.

**[Pergunta](dva_perguntas.md#questão-52)**

---

### Questão 53

**Resposta:** A) RDS Proxy para connection pooling

**Resumo:** RDS Proxy é projetado especificamente para Lambda, oferecendo connection pooling, failover automático, e IAM authentication. Elimina connection overhead e connection limits do RDS.

**[Pergunta](dva_perguntas.md#questão-53)**

---

### Questão 54

**Resposta:** A) Kinesis Data Analytics com SQL queries

**Resumo:** Para real-time analytics, Kinesis Data Analytics oferece SQL-based stream processing com low latency, built-in windowing functions, e integration com visualization tools.

**[Pergunta](dva_perguntas.md#questão-54)**

---

### Questão 55

**Resposta:** D) Combinação de todas as estratégias de cache

**Resumo:** Para milhões de usuários: CloudFront para global edge caching, API Gateway cache para regional optimization, e ElastiCache para application-level data caching. Layered approach maximiza performance.

**[Pergunta](dva_perguntas.md#questão-55)**

---

## Questões de Debugging e Troubleshooting

### Questão 56

**Resposta:** D) Todas as abordagens são necessárias

**Resumo:** Intermittent timeouts requerem análise completa: CloudWatch Logs para error patterns, X-Ray para latency hotspots, memory usage analysis, e dependency health checks.

**[Pergunta](dva_perguntas.md#questão-56)**

---

### Questão 57

**Resposta:** D) Todas as verificações de networking

**Resumo:** VPC connectivity issues são multi-layered: security groups (instance level), NACLs (subnet level), route tables para traffic routing, e NAT Gateway para internet access.

**[Pergunta](dva_perguntas.md#questão-57)**

---

### Questão 58

**Resposta:** D) Todas as análises de performance

**Resumo:** DynamoDB latency investigation envolve: hot partition identification, query pattern analysis para efficiency, consistency level impact assessment, e overall capacity planning.

**[Pergunta](dva_perguntas.md#questão-58)**

---

### Questão 59

**Resposta:** D) Não há memory leaks em Lambda devido ao stateless nature

**Resumo:** Lambda functions são stateless e containers são reciclados regularmente. Memory "leaks" são geralmente global variables ou connection pooling behavior, não true memory leaks.

**[Pergunta](dva_perguntas.md#questão-59)**

---

### Questão 60

**Resposta:** D) Todas as camadas da arquitetura

**Resumo:** 502 Bad Gateway pode originar em qualquer layer: API Gateway configuration, Lambda execution errors, timeout issues, ou backend service failures. Systematic investigation é necessária.

**[Pergunta](dva_perguntas.md#questão-60)**

---

## Questões de Casos de Uso Específicos

### Questão 61

**Resposta:** C) Kinesis Data Streams → Lambda → CloudWatch Alarms

**Resumo:** Para real-time log processing: Kinesis Data Streams para high-throughput ingestion, Lambda para processing e analysis, CloudWatch Alarms para automated alerting baseado em log patterns.

**[Pergunta](dva_perguntas.md#questão-61)**

---

### Questão 62

**Resposta:** A) API Gateway → Lambda → DynamoDB com conditional writes

**Resumo:** Sistema de votação requer: API Gateway para rate limiting, Lambda para business logic, DynamoDB conditional writes para prevent duplicate votes, garantindo integrity sem race conditions.

**[Pergunta](dva_perguntas.md#questão-62)**

---

### Questão 63

**Resposta:** D) Personalize → API Gateway → CloudFront

**Resumo:** Para recomendações: Amazon Personalize para ML-powered recommendations, API Gateway para serving, CloudFront para global caching de recommendations quasi-static.

**[Pergunta](dva_perguntas.md#questão-63)**

---

### Questão 64

**Resposta:** C) Event-driven architecture com CQRS

**Resumo:** Marketplace complexo beneficia de: event-driven para loose coupling, CQRS para separate read/write optimization, permitindo independent scaling e evolution de cada vendor's capabilities.

**[Pergunta](dva_perguntas.md#questão-64)**

---

### Questão 65

**Resposta:** D) Combinação de automated backups e IaC

**Resumo:** Backup completo de serverless requer: automated backups para data (DynamoDB, RDS), IaC para infrastructure reproducibility, e version control para code/configuration recovery.

**[Pergunta](dva_perguntas.md#questão-65)**

---

© 2025 · Curado por **Kleryton de Souza** · [LinkedIn](https://www.linkedin.com/in/kleryton-souza/)
