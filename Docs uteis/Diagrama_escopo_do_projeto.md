
# Diagrama, Escopo e Arquitetura — Resumo Simples

## Objetivo (em 1 frase)
Automatizar a leitura de PDFs de sinistro e transformar cada documento em um registro estruturado que a equipe possa consultar rapidamente.

## O que o sistema faz (resumido)
- Recebe o PDF enviado pelo usuário.
- Extrai o texto e campos importantes automaticamente.
- Normaliza e guarda os dados para consulta e auditoria.

## Arquitetura (explicação simples)
- Usuário envia o PDF → o sistema recebe e processa automaticamente.
- O processamento usa um pequeno "agente" que chama OCR (para ler o documento) e uma inteligência (para organizar o texto em campos).
- O resultado é salvo num banco rápido e consultável (histórico disponível).

## Diagrama (visão de alto nível — para leigos)

```mermaid
flowchart LR
	A[Usuário / Cliente] -->|envia PDF| B[API Gateway / Upload S3]
	B --> C[AWS Lambda (Agente Strands)]
	C --> D[Amazon Textract (OCR)]
	C --> E[Amazon Bedrock (Normalização)]
	D --> C
	E --> C
	C --> F[Amazon DynamoDB (Resultados)]
	C --> G[Amazon CloudWatch (Logs/Métricas)]
```

## Escopo — O que está incluído
- Ingestão de PDFs, extração automática, normalização e persistência de resultados.
- API simples para envio de documentos e endpoint de consulta básico.
- Monitoramento básico (logs e métricas) e retentativas automáticas em falhas.

## Escopo — O que NÃO está incluído (neste MVP)
- Interface web avançada ou dashboard completo (pode ser adicionado depois).
- Validação manual integrada complexa (será opcional em casos críticos).
- Busca semântica e dashboards analíticos (evolução futura).

## Métricas de sucesso (fáceis de medir)
- Tempo médio para processar um PDF (ex.: < 60s)
- Percentual de campos extraídos corretamente (ex.: > 85%)
- Número de documentos processados por hora
- Taxa de erros / retries

## Público-alvo / Quem se beneficia
- Equipes de sinistros, atendimento e análise que precisam transformar documentos em dados rápidos.

---

Se quiser, eu transformo isso em um slide único ou em um README curto para apresentação ao time.
