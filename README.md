# PRD — Safra em Dia

## 1. Identificação
- Responsável: Raymora Katielle de Almeida Silva
- Curso: Bacharelado em Engenharia de Software — UFMT
- Polo: Água Boa
- Produto: Safra em Dia
- Versão: MVP acadêmico 0.1

## 2. Problema
Pequenos e médios produtores de soja e milho podem utilizar
planilhas, anotações e mensagens para acompanhar a colheita.
A dispersão dos registros dificulta consultar a área colhida
no dia e o total acumulado.

Essa necessidade é uma hipótese e deverá ser investigada
com potenciais usuários.

## 3. Público
Contratantes previstos: produtores e gestores de propriedades
de soja e milho de Mato Grosso.

Usuários previstos: gestores, técnicos e monitores de campo.

## 4. Objetivo do MVP
Demonstrar um fluxo funcional de cadastro de uma safra,
registro diário e consulta dos totais de colheita.

## 5. Hipótese crítica
Um fluxo simples de registro e resumo pode facilitar a consulta
da área colhida e da produção acumulada, em comparação com
informações dispersas.

A implementação demonstra o fluxo, mas não comprova a hipótese
sem avaliação com pessoas do público pretendido.

## 6. Escopo
### Incluído
- Cadastro de uma safra por navegador.
- Nome da propriedade, cultura e identificação da safra.
- Área total plantada e área em penhor, em hectares.
- Registro de data, área colhida e produção em toneladas.
- Consulta da área colhida na data selecionada.
- Consulta da área colhida e da produção acumuladas.
- Consulta da área restante e do percentual colhido.
- Listagem e exclusão de registros.
- Persistência local no navegador.
- Exportação dos registros em CSV.
- Exportação e restauração de backup em JSON.

### Fora do escopo
- Login e múltiplos perfis.
- Banco de dados compartilhado.
- Sincronização entre dispositivos.
- Cadastro de várias propriedades simultâneas.
- Controle de CPR e carregamentos.
- Leitura automática de documentos ou vídeos.
- Integração com mapas.
- Cobrança e assinaturas.

## 7. Telas
Uma página responsiva dividida em:
1. Aviso sobre uso acadêmico e armazenamento local.
2. Cadastro da safra.
3. Formulário de registro diário.
4. Resumo dos indicadores.
5. Lista de registros.
6. Exportação e restauração de dados.

## 8. Requisitos funcionais
RF01 — Permitir cadastrar e atualizar os dados da safra.
RF02 — Exigir propriedade, cultura e identificação da safra.
RF03 — Exigir área plantada maior que zero.
RF04 — Impedir área em penhor negativa ou maior que a plantada.
RF05 — Permitir registrar data, hectares colhidos e toneladas.
RF06 — Exigir área colhida maior que zero e toneladas não negativas.
RF07 — Impedir acumulado de colheita maior que a área plantada.
RF08 — Calcular os indicadores com base nos registros salvos.
RF09 — Permitir vários registros na mesma data e somá-los.
RF10 — Permitir excluir um registro mediante confirmação.
RF11 — Preservar dados após recarregar a página, quando o
armazenamento do navegador estiver disponível.
RF12 — Exportar registros em CSV e backup completo em JSON.
RF13 — Validar a estrutura e os valores do backup antes de restaurar.
RF14 — Exigir confirmação antes de substituir dados por um backup.

## 9. Requisitos não funcionais
RNF01 — Interface adaptada para celular e computador.
RNF02 — Campos com rótulos e operação por teclado.
RNF03 — Mensagens textuais de sucesso ou erro.
RNF04 — Não depender exclusivamente de cores para comunicar estados.
RNF05 — Não solicitar dados pessoais de produtores ou funcionários.
RNF06 — Informar que os dados ficam apenas no navegador.
RNF07 — Utilizar dados fictícios na demonstração pública.
RNF08 — Não utilizar serviços pagos para esta demonstração.

## 10. Dados
Safra:
- propriedade: texto
- cultura: soja ou milho
- identificacao: texto
- areaPlantada: número em hectares
- areaPenhor: número em hectares

Registro:
- id: identificador
- data: data no formato AAAA-MM-DD
- hectares: número maior que zero
- toneladas: número maior ou igual a zero

## 11. Regras de negócio
- A área em penhor é uma informação cadastral e não será
  subtraída da área plantada para calcular a área restante.
- Área restante = área plantada menos área colhida acumulada.
- Percentual colhido = área acumulada / área plantada × 100.
- O total do dia soma todos os registros da data selecionada.
- Valores fracionados devem utilizar até duas casas decimais.
- A atualização da área plantada não pode torná-la inferior
  à área já colhida.

## 12. Critérios de aceitação
- Cadastrar safra fictícia com 100 ha e 20 ha em penhor.
- Registrar 10 ha e 30 t em uma data.
- Registrar mais 15 ha e 45 t na mesma data.
- Exibir 25 ha no dia, 25 ha acumulados, 75 t acumuladas,
  75 ha restantes e 25% de avanço.
- Rejeitar registro adicional de 80 ha.
- Manter os dados após recarregar a página.
- Excluir um registro e recalcular os indicadores.
- Exportar CSV e JSON.
- Restaurar o JSON e recuperar os registros.
- Permitir concluir o fluxo pelo celular.

## 13. Avaliação com pessoas
Solicitar a uma pessoa do público pretendido, sem coletar
dados identificáveis, que:
1. Cadastre uma safra fictícia.
2. Registre uma colheita.
3. Consulte a área acumulada.
4. Exporte os dados.

Registrar dificuldades, conclusão das tarefas e sugestões.
Não declarar essa avaliação como realizada antes de executá-la.

## 14. Limitações e riscos
Este MVP utiliza armazenamento local, sem autenticação,
sincronização, auditoria ou backup automático.

A limpeza dos dados do navegador pode apagar os registros.
O link público disponibiliza o aplicativo, não compartilha
automaticamente os dados entre usuários.

Não está pronto para operação institucional ou comercial.

## 15. Publicação
Link público: [INSERIR APÓS PUBLICAR E VERIFICAR]

## 16. Situação dos testes
Implementação inicial elaborada.
Testes de execução e avaliação com usuários: pendentes.
Atualizar esta seção somente após realizar as verificações.
