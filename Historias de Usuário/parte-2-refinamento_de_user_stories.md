# 1 – Pagamento via Carteira Digital/Pix

## Versão Original (gerada pela LLM)

- **História:**  
Enquanto *cliente*, desejo **pagar via Pix de forma integrada**, para **agilizar a finalização do pedido**.

- **Critérios de Aceitação:**
  1. Gerar QR Code após confirmação do pedido.  
  2. Verificar pagamento automaticamente.  
  3. Cancelar pedido em caso de não pagamento.  

- **Regras de Negócio:**  
A transação deve seguir padrões de segurança.

- **Complexidade:** Alta  
- **Estimativa:** 8 story points  

---

## Versão Refinada

- **História:**  
Enquanto *cliente autenticado com um pedido confirmado*, desejo **realizar o pagamento via Pix ou carteira digital integrada**, para **agilizar a finalização do pedido de forma segura e eficiente**.

- **Critérios de Aceitação:**
  1. O sistema deve gerar automaticamente um QR Code e um código “Copia e Cola” após a confirmação do pedido.  
  2. O código “Copia e Cola” deve ser copiado automaticamente para a área de transferência do dispositivo.  
  3. O sistema deve confirmar o pagamento em até 60 segundos após a transação.  
  4. O sistema deve notificar o cliente caso o pagamento não seja identificado dentro do prazo.  
  5. O sistema deve permitir a extensão do prazo de pagamento caso o cliente solicite antes do cancelamento.  
  6. O pedido deve ser cancelado automaticamente caso o pagamento não seja realizado dentro do prazo definido.  

- **Regras de Negócio:**
  - A transação deve seguir os padrões de segurança do Banco Central.  
  - O pagamento deve ser vinculado exclusivamente ao pedido gerado.  

- **Complexidade:** Alta  
- **Estimativa:** 8 story points  

---

 >## Descrição das melhorias realizadas
>- A história foi **tornada mais específica**, incluindo contexto de autenticação e estado do pedido.  
>- Os critérios de aceitação foram **detalhados e tornados testáveis**, com prazos definidos (60 segundos).  
>- Foi adicionada a funcionalidade de **código copia e cola automático**, melhorando usabilidade.  
>- Foram incluídos cenários alternativos como **extensão de prazo de pagamento**.  
>- A linguagem foi padronizada para um formato mais **formal e técnico**.  

---

# 2 – Busca por Categorias

## Versão Original (gerada pela LLM)

- **História:**  
Enquanto *cliente*, desejo **filtrar lojas por categoria**, para **encontrar refeições mais rapidamente**.

- **Critérios de Aceitação:**
  1. Exibir categorias disponíveis.  
  2. Filtrar lojas por categoria.  

- **Regras de Negócio:**  
Categorias devem estar associadas às lojas.

- **Complexidade:** Baixa  
- **Estimativa:** 2 story points  

---

## Versão Refinada

- **História:**  
Enquanto *cliente*, desejo **filtrar as lojas disponíveis por categorias de culinária**, para **restringir os resultados e encontrar minha refeição de forma mais rápida**.

- **Critérios de Aceitação:**
  1. O sistema deve exibir um componente visual (carrossel horizontal) com ícones e nomes das categorias disponíveis.  
  2. Ao selecionar uma categoria, a lista de lojas deve ser atualizada em tempo real.  
  3. O usuário deve conseguir remover o filtro aplicado (clicando novamente ou utilizando um botão “Limpar”).  
  4. Caso não existam lojas abertas na categoria, o sistema deve exibir a mensagem: “Nenhuma loja aberta nesta categoria no momento”.  

- **Regras de Negócio:**
  - Uma loja pode pertencer a no máximo 3 categorias.  
  - Categorias sem lojas cadastradas não devem ser exibidas.  

- **Complexidade:** Baixa  
- **Estimativa:** 2 story points  

---

>## Descrição das melhorias realizadas
>- A história foi **mais detalhada**, incluindo o benefício direto ao usuário.  
>- Os critérios foram **tornados testáveis**, com comportamentos claros da interface.  
>- Foram adicionados fluxos importantes como **remoção de filtro**.  
>- Foram incluídos cenários de erro (categoria sem lojas).  
>- Regras de negócio foram ampliadas para evitar inconsistências.  

---

# 3 – Navegação Integrada GPS

## Versão Original (gerada pela LLM)

- **História:**  
Enquanto *entregador*, desejo **usar GPS para navegar até o cliente**, para **facilitar a entrega**.

- **Critérios de Aceitação:**
  1. Botão de navegação disponível.  
  2. Abrir aplicativo de mapas.  

- **Regras de Negócio:**  
Deve usar localização do cliente.

- **Complexidade:** Baixa  
- **Estimativa:** 2 story points  

---

## Versão Refinada

- **História:**  
Enquanto *entregador autenticado com pedido em andamento*, desejo **iniciar a navegação via aplicativo externo de mapas**, para **otimizar o tempo de entrega**.

- **Critérios de Aceitação:**
  1. O botão “Navegar” deve aparecer apenas para pedidos em status “em entrega”.  
  2. O sistema deve listar aplicativos de navegação disponíveis no dispositivo.  
  3. O sistema deve abrir o app selecionado com rota traçada automaticamente.  
  4. Caso exista apenas um app, ele deve ser aberto automaticamente.  
  5. Caso não exista app, o sistema deve informar indisponibilidade.  

- **Regras de Negócio:**
  - A navegação deve utilizar coordenadas geográficas válidas.  
  - A funcionalidade só pode ser usada em pedidos aceitos.  

- **Complexidade:** Baixa  
- **Estimativa:** 2 story points  

---

>## Descrição das melhorias realizadas
>- A história foi **tornada mais específica**, com contexto e status do pedido.  
>- Critérios ficaram **testáveis**, incluindo cenários alternativos.  
>- Foi incluído tratamento de erro (sem app disponível).  
>- Houve melhoria técnica com uso de **coordenadas geográficas**.  

---

# 4 – Chat com a Loja/Cliente

## Versão Original (gerada pela LLM)

- **História:**  
Enquanto *entregador*, desejo **enviar mensagens rápidas via chat**, para **resolver problemas de localização ou atrasos**.

- **Critérios de Aceitação:**
  1. Chat habilitado apenas enquanto o pedido estiver ativo.  
  2. Opções de frases pré-definidas.  
  3. Histórico apagado após 24h.  

- **Regras de Negócio:**  
Proibida troca de contatos externos.

- **Complexidade:** Alta  
- **Estimativa:** 8 story points  

---

## Versão Refinada

- **História:**  
Enquanto *entregador autenticado em um pedido ativo*, desejo **utilizar um chat integrado com mensagens rápidas e seguras**, para **me comunicar com a loja ou cliente**.

- **Critérios de Aceitação:**
  1. Chat disponível apenas em pedidos ativos.  
  2. Mensagens rápidas em até 2 cliques.  
  3. Permitir mensagens personalizadas (até 200 caracteres).  
  4. Notificações em tempo real.  
  5. Chat desativado após finalização.  
  6. Histórico armazenado por 24h.  
  7. Bloqueio de conteúdos proibidos.  

- **Regras de Negócio:**
  - Apenas usuários do pedido podem acessar.  
  - Proibido envio de contatos externos.  

- **Complexidade:** Alta  
- **Estimativa:** 8 story points  

---

>## Descrição das melhorias realizadas
>- Maior especificidade no contexto.  
>- Critérios mais testáveis.  
>- Inclusão de notificações e mensagens personalizadas.  
>- Melhor definição de regras.  

---

# 5 – Gestão de Disponibilidade de Itens

## Versão Original (gerada pela LLM)

- **História:**  
Enquanto *loja*, desejo **ativar ou desativar itens**, para **evitar pedidos de produtos indisponíveis**.

- **Critérios de Aceitação:**
  1. Listar produtos com botão on/off.  
  2. Atualização instantânea.  

- **Regras de Negócio:**  
Itens desativados não aparecem.

- **Complexidade:** Baixa  
- **Estimativa:** 2 story points  

---

## Versão Refinada

- **História:**  
Enquanto *responsável pela loja*, desejo **gerenciar a disponibilidade dos itens do cardápio em tempo real**, para **garantir que apenas produtos disponíveis sejam exibidos**.

- **Critérios de Aceitação:**
  1. Exibir itens com status (ativo, inativo, esgotado).  
  2. Permitir alteração direta no painel.  
  3. Atualizar status em até 5 segundos.  
  4. Exibir feedback visual.  
  5. Reset automático de “esgotado” às 00:00.  
  6. Itens indisponíveis não aparecem.  

- **Regras de Negócio:**
  - Apenas usuários autorizados podem alterar.  
  - Alterações devem ser registradas em log.  

- **Complexidade:** Baixa  
- **Estimativa:** 2 story points  

---

>## Descrição das melhorias realizadas
>- Persona mais clara.  
>- Estados dos itens melhor definidos.  
>- Critérios mais testáveis (tempo definido).  
- Inclusão de regras importantes (log e permissão).  
- Melhor usabilidade com feedback visual.  
