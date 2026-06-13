# Resumo Simples: SDK, CLI e Deploy Automatizado na AWS (AWS4)

## Visao Geral
Para desenvolver e operar aplicacoes na AWS, tres pilares sao muito usados:

- **AWS SDK** para integrar servicos AWS no codigo da aplicacao.
- **AWS CLI** para executar comandos AWS via terminal.
- **Deploy automatizado** para publicar mudancas com padrao, velocidade e seguranca.

## AWS SDK para linguagens de programacao
O **AWS SDK (Software Development Kit)** e o conjunto de bibliotecas oficiais para acessar servicos AWS por codigo.

Existem SDKs para varias linguagens, como:
- Java;
- JavaScript/TypeScript;
- Python;
- .NET (C#);
- Go;
- PHP;
- Ruby.

Com o SDK, a aplicacao pode:
- enviar arquivos para S3;
- publicar mensagens no SNS/SQS;
- ler dados do DynamoDB;
- acionar Lambda;
- gerenciar varios recursos da AWS por API.

### Exemplo importante: Java SDK
No contexto Java, usamos o **AWS SDK for Java** (muitas vezes chamado de forma informal de "AWS Java SDK").

Beneficios:
- integracao direta com projetos Java;
- autenticacao com credenciais e roles IAM;
- chamadas para servicos AWS de forma programatica e segura.

## AWS CLI
O **AWS CLI (Command Line Interface)** permite controlar a AWS pelo terminal, sem acessar o console web.

Comandos comuns:
- listar buckets no S3;
- consultar instancias EC2;
- criar e atualizar recursos;
- executar scripts de automacao.

Vantagens:
- rapidez para operacoes repetitivas;
- padronizacao de processos;
- integracao com pipelines de CI/CD.

## Terraform na AWS (Infraestrutura como Codigo)
O **Terraform** e uma ferramenta de **Infrastructure as Code (IaC)** que permite criar e gerenciar recursos AWS por arquivos de configuracao.

Conceitos principais:
- **codigo declarativo**: voce descreve o estado desejado da infraestrutura;
- **provider AWS**: conecta o Terraform com os servicos da AWS;
- **plan**: mostra o que sera criado, alterado ou removido;
- **apply**: executa as mudancas planejadas.

Beneficios:
- padronizacao de ambientes;
- controle de versao da infraestrutura;
- reproducao rapida de cenarios (dev, teste e producao);
- reducao de erros manuais em criacao de recursos.

Uso junto com deploy automatizado:
- pipeline pode executar Terraform para preparar infraestrutura;
- depois, a aplicacao e implantada com CodeDeploy/ECS/Lambda;
- isso cria um fluxo completo de entrega: infraestrutura + aplicacao.

## Deploy automatizado na AWS
Deploy automatizado e o processo de publicar aplicacoes sem etapas manuais repetitivas.

Objetivos:
- reduzir erros humanos;
- acelerar entregas;
- garantir consistencia entre ambientes (dev, homologacao, producao).

Ferramentas e servicos usados:
- **CodePipeline**: orquestra o fluxo de entrega;
- **CodeBuild**: compila e testa o projeto;
- **CodeDeploy**: faz a implantacao automatizada;
- **CloudFormation/Terraform**: automatizam infraestrutura como codigo;
- **GitHub Actions/GitLab CI/Jenkins**: podem integrar com servicos AWS.

## Fluxo teorico de automacao
1. Desenvolvedor envia codigo para o repositorio.
2. Pipeline inicia build e testes.
3. Se aprovado, ocorre deploy automatico no ambiente alvo.
4. Monitoramento acompanha logs, metricas e possiveis falhas.
5. Em caso de problema, pode haver rollback controlado.

## Boas praticas
- usar IAM com menor privilegio para pipelines e servicos;
- separar ambientes (dev, teste, prod) com regras claras;
- automatizar testes antes do deploy;
- monitorar aplicacao apos publicacao (CloudWatch e alarmes);
- manter versoes e estrategia de rollback.

## Resumo Final
- **AWS SDK** conecta seu codigo aos servicos AWS em varias linguagens.
- **AWS CLI** automatiza operacoes via linha de comando.
- **Terraform** automatiza infraestrutura como codigo com padrao e rastreabilidade.
- **Deploy automatizado** melhora qualidade, velocidade e seguranca nas entregas.

### Aluno: Luiz Gustavo Dacome Damas