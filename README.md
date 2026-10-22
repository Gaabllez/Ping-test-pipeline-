# Ping Test Pipeline

Este repositório contém uma pipeline de integração contínua (CI) desenvolvida com **GitHub Actions**, com o objetivo de automatizar testes básicos de conectividade com o GitHub.

## Objetivo

Demonstrar a criação e execução de uma esteira de automação acionada por eventos do GitHub, utilizando um ambiente Linux para executar comandos e validar a conectividade.

## Tecnologias utilizadas

- Git e GitHub
- GitHub Actions
- Ubuntu Linux
- Bash
- `ping` (ICMP)
- `curl` (HTTP/HTTPS)

## Como funciona a pipeline

A pipeline é executada automaticamente quando ocorre um `push` na branch `main`. Também pode ser iniciada manualmente pela aba Actions do GitHub.

### Etapas de execução

1. **Checkout:** obtém os arquivos do repositório.
2. **Informações da execução:** exibe o repositório, a branch, o commit e o usuário responsável.
3. **Validação da estrutura:** verifica se o arquivo do workflow existe.
4. **Teste de ping:** tenta verificar a conectividade com `github.com`. A ausência de resposta gera um aviso, sem interromper a execução.
5. **Teste HTTPS:** utiliza `curl` para verificar o acesso ao GitHub.
6. **Resumo final:** informa que o fluxo chegou à etapa de encerramento.

## Como executar

1. Acesse o repositório no GitHub.
2. Abra a aba **Actions**.
3. Selecione a workflow **CI - Pipeline de Conectividade**.
4. Para iniciar manualmente, clique em **Run workflow**.

A pipeline também é acionada automaticamente por um `push` na branch `main`.

## Estrutura do projeto

```text
Ping-test-pipeline-/
├── .github/
│   └── workflows/
│       └── ping.yml
└── README.md
```

## Resultados esperados

- **Sucesso:** as etapas obrigatórias são concluídas sem erros.
- **Aviso:** o ping pode não receber respostas caso o tráfego ICMP esteja bloqueado.
- **Falha:** o workflow é marcado como falha se uma etapa obrigatória, como o teste HTTPS, não for concluída.

## Objetivo acadêmico

Este projeto demonstra conceitos básicos de DevOps e integração contínua, incluindo automação de tarefas, execução de comandos em runners Linux, monitoramento de resultados e uso de workflows versionados com Git.

---

Desenvolvido como atividade prática de estudo de GitHub Actions e pipelines de CI.
