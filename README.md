# Relatório de Prontidão Técnica: Onboarding SecOps & Soberania Técnica

**Engenheiro:** Vinicius de Oliveira Santos

**Data:** 20/03/2026

Este relatório consolida a execução da Fase 1 do onboarding, atestando o estabelecimento da infraestrutura base individual e da esteira de segurança (Security Gate) em conformidade com o Domínio 8 do CISSP.

## Evidência de Ambiente (Isolamento e Determinismo)
O ambiente foi configurado garantindo o isolamento via Poetry (`virtualenvs.in-project true`) e o uso da versão estável e obrigatória do Python.

**Log de comprovação (`poetry env info`):**
```text
Virtualenv
Python:         3.12.0
Implementation: CPython
Path:           C:\Users\vinic\desktop\faculdade\unb\eps\.venv
Executable:     C:\Users\vinic\desktop\faculdade\unb\eps\.venv\Scripts\python.exe
Valid:          True

Base
Platform:   win32
OS:         nt
Python:     3.12.0
````

## Evidência de Segurança (Auditoria Estática)

A análise estática de segurança (SAST) foi executada localmente utilizando o Bandit, não identificando nenhuma vulnerabilidade lógica no código inicial, atendendo ao critério de zero issues.

**Log de comprovação (`poetry run bandit -c pyproject.toml -r .`):**

```text
[main]  INFO    running on Python 3.12.0
Run started:2026-03-20 15:02:39.767309+00:00

Test results:
        No issues identified.
Code scanned:
        Total lines of code: 0
        Total lines skipped (#nosec): 0

Run metrics:
        Total issues (by severity):
                Undefined: 0
                Low: 0
                Medium: 0
                High: 0
```

*(Nota: Os testes complementares de Linter com Ruff e SCA com Safety também foram executados e retornaram sucesso, garantindo a ausência de CVEs conhecidas. Para verificá-los, consultar a pasta Log)*

## Evidência de CI (Esteira DevSecOps)

A esteira automatizada no GitHub Actions foi configurada e executada com sucesso, validando a integridade da aplicação a cada novo push.

[![DevSecOps Security Gate](https://github.com/ViniciussdeOliveira/pcdf-secops/actions/workflows/devsecops.yml/badge.svg?branch=main)](https://github.com/ViniciussdeOliveira/pcdf-secops/actions/workflows/devsecops.yml)

## Declaração de Prontidão

Declaro que a fundação de DevSecOps e o setup mandatório localhost estão concluídos. O código contido neste repositório está testado, auditado e **pronto para migração via Git Remote (`upstream`) para a organização oficial `rmchaimalm`**.
