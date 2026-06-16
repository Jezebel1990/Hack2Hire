# Cloud Document Flow: IDP para Sinistros e Empréstimos

Descrição breve: Solução serverless de Intelligent Document Processing (IDP) que automatiza a classificação, extração e estruturação de dados de documentos de crédito e sinistros usando AWS e Amazon Bedrock.

## Sobre o Projeto
A solução resolve um problema real de negócios: o processamento manual de pacotes de documentos em propostas de empréstimo imobiliário e sinistros de seguros. Documentos como identidade, comprovantes de renda, boletins de ocorrência, laudos e notas fiscais são analisados manualmente, o que aumenta custo, tempo de resposta e risco de erros.

Com a nossa solução, documentos são recebidos em lote, classificados automaticamente, extraídos e transformados em um JSON padronizado. Isso reduz o retrabalho, melhora a velocidade de atendimento e permite que equipes de crédito e sinistros tomem decisões mais rápidas com dados confiáveis.

## Contexto do Hack2Hire
O Hack2Hire é um evento de inovação focado em mostrar como equipes podem resolver desafios reais em tempo acelerado. Nesta edição, o projeto foi construído no contexto de dois desafios complementares de IDP: um para uma fintech de crédito imobiliário e outro para uma seguradora de sinistros.

Esse hackathon destaca a capacidade de entrega em equipe, o uso de tecnologias AWS de ponta e a mentalidade de produção rápida. O projeto foi desenvolvido com foco em resultados reais, usabilidade e sustentabilidade técnica.

## Sobre a Escola da Nuvem
A Escola da Nuvem forma profissionais para o mercado de nuvem com práticas hands-on, orientação de mentores e foco em transformação social. O programa conecta participantes com o universo AWS, prepara para hackathons e promove aprendizado prático em arquitetura serverless, IA generativa e automação.

## Nossa Solução
Nossa implementação combina dois pilares:

- **Extração Inteligente de Documentos (IDP)**: usa Amazon Bedrock Data Automation (BDA) para classificar e extrair dados de documentos complexos.
- **Estruturação e Normalização**: usa Amazon Nova para transformar texto extraído em JSON padronizado e confiável.

### Funcionalidades principais
- Recebe pacotes de documentos em PDF e imagens
- Classifica automaticamente o tipo de cada documento
- Extrai campos relevantes como data, valor, nome, endereço e tipo de sinistro
- Normaliza formatos de data, valores e campos obrigatórios
- Gera JSON estruturado para integração com processos downstream
- Armazena resultados e metadados em AWS S3 e DynamoDB
- Suporta orquestração serverless com Lambda e Step Functions

## Diferenciais
- **Foco em AWS IDP**: a solução não depende de OCR próprio ou parsing manual, respeitando as regras do Hackathon.
- **Pipeline ponta a ponta**: do upload do arquivo à entrega do JSON final.
- **Uso de Amazon Nova para tool-calling**: garante estruturação de saída mais confiável e padronizada.
- **Arquitetura serverless**: alta escalabilidade e menor custo de manutenção.
- **Visão de produto**: pensada tanto para crédito quanto para seguros, com potencial para evolução em agente conversacional e RAG.

## Tecnologias Utilizadas
- AWS Lambda
- Amazon S3
- Amazon Bedrock Data Automation (BDA)
- Amazon Nova (Bedrock)
- AWS Step Functions
- Amazon DynamoDB
- AWS IAM
- Python com boto3
- (Opcional) Amazon Textract e Amazon Comprehend, conforme evolução do produto

## Arquitetura da Solução
A arquitetura adotada é simples e modular:

1. **Upload do documento** em um bucket S3
2. **Disparo de evento** AWS Lambda ou Step Functions
3. **Classificação e extração** pelo Amazon Bedrock Data Automation
4. **Estruturação** do resultado via Amazon Nova tool-calling
5. **Persistência** em S3 ou DynamoDB
6. **Retorno** do JSON padronizado para consumo de sistemas downstream

## Demonstração
> Inserir GIFs, capturas de tela e links de vídeo aqui assim que estiverem disponíveis.

- Demo: _[link do vídeo ou apresentação]_ (a ser preenchido)
- Gif de fluxo: _[link ou caminho do arquivo]_ (a ser preenchido)

## Como Executar o Projeto
1. Configure uma conta AWS com acesso a Bedrock e us-east-1.
2. Crie ou reutilize um bucket S3 para upload de documentos.
3. Configure roles IAM com permissões para Lambda, S3, Bedrock, Step Functions e DynamoDB.
4. Faça o deploy das funções Lambda e da state machine do Step Functions.
5. Envie documentos via API ou upload direto e acompanhe o processamento.

> Observação: instruções de deploy detalhadas, scripts e parâmetros devem ser adicionados quando o código estiver disponível no repositório.

## Integrantes da Equipe
- **[Nome do Integrante 1]** – Desenvolvimento e arquitetura servidorless
- **[Nome do Integrante 2]** – Integração com AWS Bedrock e IDP
- **[Nome do Integrante 3]** – Documentação, qualidade e apresentação

> Atualizar com nomes reais e links para LinkedIn/GitHub.

## Aprendizados e Desafios
Durante o Hack2Hire, o time enfrentou desafios como:
- alinhar o processamento de documentos legados com a padronização de saída;
- escolher entre múltiplas opções de AI da AWS sem sacrificar o foco no escopo;
- manter o fluxo serverless resiliente e testável em tempo reduzido.

Os principais aprendizados foram:
- uso prático de Amazon Bedrock Data Automation para IDP;
- definição de um schema JSON desde o início;
- valor da orquestração com AWS Lambda e Step Functions;
- importância de um fluxo de trabalho colaborativo em hackathons.

## Próximos Passos
A evolução natural para o projeto inclui:
- adicionar agente conversacional para perguntas sobre documentos;
- ampliar o suporte a novos tipos de documento;
- criar uma interface web para upload e visualização;
- implementar revisão humana assistida (A2I) para baixa confiança;
- gerar dashboards de métricas e performance.

## Agradecimentos
Agradecemos ao Hack2Hire, à Escola da Nuvem, aos mentores e à organização pelo espaço de aprendizado e colaboração. Este projeto reflete a dedicação do time em construir uma solução prática, alinhada às melhores práticas AWS e à realidade de mercado.

---

### Observações pendentes
- Inserir nomes reais e perfis dos integrantes
- Adicionar badges de CI/CD, licença e AWS stack quando o reposítorio estiver configurado
- Incluir links de demonstração e provas de conceito assim que disponíveis
- Completar instruções de execução com scripts e caminhos reais do código
