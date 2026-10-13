Projeto de Portfólio QA Analyst - ServeRest

**Status:** Planejamento inicial. Nenhum caso foi executado contra a aplicação ou a API.

## 1. Objetivo

Demonstrar competências de QA Analyst em análise de requisitos, avaliação de riscos, desenho e execução de testes, registro de defeitos, rastreabilidade e comunicação de resultados usando o ServeRest como sistema sob teste.

O projeto será documentado em português. Evidências e resultados devem corresponder a execuções reais; exemplos simulados serão identificados como "simulação".

## 2. Sistema sob teste e fontes

- Front-end: <https://front.serverest.dev/login>
- Documentação da API: <https://serverest.dev/?lang=pt-BR#/>
- Contrato local consultado: `C:\Users\yuril\OneDrive\Área de Trabalho\QA department\swagger.json`
- Contrato informado: ServeRest 3.2.2, OpenAPI 3.0.0, servidor `https://serverest.dev`.

O Swagger descreve os grupos Login, Usuários, Produtos e Carrinhos.
O front-end é identificado na documentação como beta.

## 3. Escopo inicial

### Incluído

- Interface de login: campos de e-mail e senha, ação Entrar, navegação para cadastro e mensagens de validação/erro.
- API de login: `POST /login`.
- Usuários: listar, cadastrar, buscar por ID, editar e excluir.
- Produtos: listar, cadastrar, buscar por ID, editar e excluir.
- Carrinhos: listar, cadastrar, buscar por ID, concluir compra e cancelar compra.
- Autorização por token e diferença de acesso entre usuário comum e administrador.
- Validação de dados, mensagens de resposta, integridade de estoque e comportamento de carrinho, conforme o contrato e as regras confirmadas.

## 4. Premissas e pontos a confirmar com equipe de desenvolvimento

- O Swagger fornece exemplos, rotas e respostas, mas não define todos os requisitos de negócio nem os limites válidos de campos.
- Valores mínimos/máximos, regras de estoque, política de duplicidade e critérios de aceite precisam ser confirmados ou registrados como hipóteses de teste.
- A API pública pode conter dados compartilhados. Testes que criem, alterem ou excluam registros devem usar uma estratégia de dados aprovada e não devem empregar dados pessoais.
- A instância e o front-end podem mudar; cada execução precisa registrar data, URL, versão disponível, navegador, dados de teste e evidências.

## 5. Riscos iniciais

| ID | Risco | Prioridade inicial | Abordagem |

| R-01 | Usuário sem permissão ou token inválido consegue acessar operações administrativas | Alta | Cobrir ausência, invalidade e uso de token; comparar usuário comum e administrador |
| R-02 | Cadastro ou edição aceita dados inválidos, duplicados ou inconsistentes | Alta | Testar campos obrigatórios, formatos, duplicidade e limites quando confirmados |
| R-03 | Carrinho calcula total incorreto ou altera estoque de forma inconsistente | Alta | Verificar total, quantidades, conclusão e cancelamento com dados controlados |
| R-04 | Testes afetam dados compartilhados da instância pública | Alta | Não executar operações mutáveis até definir ambiente, dados e limpeza |
| R-05 | Requisitos incompletos levam a resultados esperados ambíguos | Média | Manter dúvidas e hipóteses explícitas; validar regras antes de aprovar casos |
| R-06 | Falhas de validação ou feedback na tela de login confundem o usuário | Média | Verificar estados vazio, credencial inválida, navegação e mensagens visíveis |

## 6. Plano de desenvolvimento do portfólio

Premissa de agenda: 4 horas por dia, cinco dias por semana (aproximadamente 20 horas semanais), em uma trilha inicial de seis semanas.

| Semana | Foco | Entregável |
| 1 | Fundamentos CTFL, produto, requisitos e riscos | Brief do projeto, escopo, dúvidas e critérios de qualidade |
| 2 | Revisão estática e análise de requisitos | Checklist de revisão e achados documentados |
| 3 | Análise e desenho de testes | Casos, dados, resultados esperados e rastreabilidade |
| 4 | Execução, evidências, defeitos e retestes | Registro de execução e relatório de defeitos reproduzíveis |
| 5 | Sistema, aceitação, regressão e manutenção | Conjunto de regressão e resumo de teste |
| 6 | Revisão de portfólio e entrevistas | Portfólio organizado e avaliação de progresso |

## 7. Entregáveis previstos

1. Este brief e o registro de escopo.
2. Estratégia/plano de teste e matriz de riscos.
3. Checklist de análise estática e registro de dúvidas de requisitos.
4. Casos de teste com dados, resultado esperado, execução e evidências.
5. Relatório de defeitos com passos de reprodução, esperado/obtido, impacto e reteste.
6. Resumo final com cobertura, resultados, limitações e recomendações.

## 8. Referências de trabalho

- ISTQB CTFL v4.0: fundamentos e atividades de teste.
- ISO/IEC/IEEE 29119-1 e 29119-2: conceitos e processos de teste.
- ISO/IEC/IEEE 29119-3: documentação de teste.
- ISO/IEC/IEEE 29119-4: técnicas de projeto de teste.
- ISO/IEC 25002: orientação para modelos de qualidade.
- ISO/IEC/IEEE 14764: manutenção de software.