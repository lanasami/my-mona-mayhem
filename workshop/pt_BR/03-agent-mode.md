<!-- l10n-sync: source-file="workshop/03-agent-mode.md" -->
# Parte 3: Crie o jogo com fluxos de trabalho agênticos

---

Nesta parte, o Copilot passa de planejador a implementador. Em vez de escrever código linha por linha, você descreve o que quer e deixa o Copilot realizar o trabalho nos arquivos que precisam ser alterados.

## Tarefa 1: Conecte a batalha

<!-- track:vscode:start -->
1. No Copilot Chat, mude para o modo **Agent**.
2. Insira este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Retorne o Copilot CLI ao fluxo normal de programação (ou continue no modo autopilot se quiser que o Copilot prossiga até você pará-lo).
2. Se for útil, mencione o arquivo da página para fornecer mais contexto: `@src/pages/index.astro`
3. Insira este prompt:
<!-- track:cli:end -->

   > Add client-side JavaScript to the battle page that:
   > 1. When the Battle button is clicked, gets both usernames from the inputs
   > 2. Validates both are filled (show error if not)
   > 3. Fetches both users' contribution data in parallel from our API
   > 4. Renders contribution graphs as colored grids — each day is a colored square using GitHub's color palette
   > 5. Shows a VS badge between the two users
   > 6. Displays username, total contributions, and date range for each user
   > 7. Handles loading states and errors
   > 8. Also triggers on Enter key in input fields.
   > 9. Simple UI for now that is already scaffolded.
   >
   > Use TypeScript interfaces for the contribution data structure.

<!-- track:vscode:start -->
3. Deixe o Agent Mode implementar as alterações em vários arquivos de `index.astro`.
4. Antes de aceitar, revise as alterações propostas na visualização de diferenças.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Deixe o Copilot CLI implementar as alterações em `src/pages/index.astro`.
5. Inspecione as alterações geradas com `/diff` e, então, aprove-as.
<!-- track:cli:end -->

## Tarefa 2: Teste a batalha

> **⚠️ Não está vendo as alterações?** Se a página de batalha não tiver sido atualizada, pare o servidor de desenvolvimento (`Ctrl+C`), reinicie com `npm run dev` e atualize o navegador.

1. Insira `octocat` e `torvalds` como os nomes de usuário e clique em **Battle**.
2. Você deverá ver os gráficos de contribuições dos dois usuários lado a lado, em grades coloridas.
3. Teste os casos de erro:
   - Deixe um ou ambos os campos vazios e clique em Battle — deverá aparecer um erro de validação.
   - Insira um nome de usuário inválido — o aplicativo deverá exibir um erro da API.
4. Pressione **Enter** em qualquer um dos campos — a batalha deverá começar, assim como ao clicar no botão.

## Tarefa 3: Itere com o Copilot

Se algo não estiver como deveria, envie comentários diretamente ao Copilot. Por exemplo:

- *"The contribution squares are too large, make them 12x12px"*
- *"Add a hover tooltip showing the date and contribution count"*
- *"The loading state needs a pulse animation"*

<!-- track:vscode:start -->
O Agent Mode lida naturalmente com alterações em vários arquivos e com iterações. Cada comentário de acompanhamento usa o contexto da conversa anterior, permitindo refinar a implementação aos poucos sem recomeçar.
<!-- track:vscode:end -->

<!-- track:cli:start -->
As sessões do Copilot CLI mantêm o histórico, então cada comentário de acompanhamento usa o anterior como contexto. Use `/session` ou `/context` para inspecionar o contexto atual do Copilot e `/review` depois de uma iteração maior para fazer uma revisão adicional de possíveis bugs ou melhorias.
<!-- track:cli:end -->

## Dicas para esta parte

- **Seja específico sobre o que você quer** — requisitos claros ajudam o Copilot a produzir resultados melhores.
- **Divida tarefas grandes em prompts menores** se o Copilot sair do rumo.
- **Revise as alterações antes de aceitá-las** — é mais rápido inspecionar o código gerado do que reescrevê-lo depois.
- **Teste o aplicativo logo após cada etapa de implementação** para manter os problemas localizados.

## ✅ Parte 3 concluída

Você aprendeu a:

- Usar o Copilot para **implementar funcionalidades em vários arquivos**
- **Iterar nos resultados** com comentários de acompanhamento específicos
- Conduzir o **ciclo completo de uma funcionalidade** — implementação, revisão, testes e refinamento
