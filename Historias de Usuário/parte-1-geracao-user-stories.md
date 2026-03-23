# Atividade Historias de Usuário

Como especialista em engenharia de software, elaborei este backlog com 20 histórias de usuário focadas no ecossistema de delivery, garantindo que cada item respeite o padrão **INVEST** e cubra as necessidades das três personas principais: **Cliente**, **Loja** e **Entregador**.

---

### Persona: Cliente

### 1. Cadastro de Endereço via Mapa

- **História:** Enquanto **Cliente**, desejo **selecionar meu endereço de entrega em um mapa interativo**, para **garantir que o entregador receba a localização exata**.
- **Critérios de Aceitação:**
    1. O sistema deve carregar o mapa baseado na posição GPS atual.
    2. O usuário deve conseguir arrastar um "pin" para ajustar o local.
    3. O sistema deve preencher automaticamente o logradouro após a seleção no mapa.
- **Regras de Negócio:** O endereço selecionado deve estar dentro do perímetro de cobertura do aplicativo.
- **Complexidade:** Média.
- **Estimativa:** 5 story points.

### 2. Busca por Categorias

- **História:** Enquanto **Cliente**, desejo **filtrar lojas por categorias (ex: Pizza, Japonesa)**, para **encontrar rapidamente o que desejo comer**.
- **Critérios de Aceitação:**
    1. A tela inicial deve exibir ícones clicáveis para cada categoria.
    2. Ao clicar, apenas lojas que pertencem àquela categoria devem ser listadas.
    3. Se não houver lojas abertas na categoria, exibir mensagem informativa.
- **Regras de Negócio:** Uma loja pode pertencer a até 3 categorias simultâneas.
- **Complexidade:** Baixa.
- **Estimativa:** 2 story points.

### 3. Customização de Itens (Complementos)

- **História:** Enquanto **Cliente**, desejo **adicionar complementos ou observações a um item (ex: sem cebola)**, para **personalizar o pedido conforme meu gosto**.
- **Critérios de Aceitação:**
    1. Exibir lista de complementos (pagos ou gratuitos) vinculados ao item.
    2. Permitir um campo de texto de até 100 caracteres para observações.
    3. O valor total do item deve ser atualizado em tempo real no carrinho.
- **Regras de Negócio:** O lojista define o limite máximo de complementos por item.
- **Complexidade:** Média.
- **Estimativa:** 3 story points.

### 4. Acompanhamento em Tempo Real

- **História:** Enquanto **Cliente**, desejo **visualizar o status do meu pedido (em preparo, saiu para entrega)**, para **reduzir a ansiedade da espera**.
- **Critérios de Aceitação:**
    1. O status deve mudar automaticamente conforme a loja ou entregador atualizam o app.
    2. Deve haver um timestamp para cada mudança de status.
    3. Notificações push devem ser enviadas a cada troca de status crítico.
- **Regras de Negócio:** O status "Saiu para entrega" só pode ser ativado se um entregador já tiver aceito o pedido.
- **Complexidade:** Média.
- **Estimativa:** 5 story points.
- **Relacionado com o(s) requisito(s):** 11, 17.

### 5. Agendamento de Pedidos

- **História:** Enquanto **Cliente**, desejo **escolher um horário futuro para a entrega**, para **planejar minhas refeições com antecedência**.
- **Critérios de Aceitação:**
    1. O usuário deve selecionar data e janelas de horário de 30 minutos.
    2. O sistema deve impedir agendamentos fora do horário de funcionamento da loja.
    3. O pedido agendado deve aparecer em uma seção de "Próximos Pedidos".
- **Regras de Negócio:** Agendamentos só podem ser feitos com no mínimo 2 horas de antecedência.
- **Complexidade:** Alta.
- **Estimativa:** 8 story points.

### 6. Histórico e Recompra

- **História:** Enquanto **Cliente**, desejo **acessar meu histórico de pedidos**, para **repetir uma compra anterior com um clique**.
- **Critérios de Aceitação:**
    1. Listar pedidos dos últimos 6 meses.
    2. Botão "Pedir novamente" que adiciona todos os itens ao carrinho (se disponíveis).
    3. Exibir detalhes de preços e data.
- **Regras de Negócio:** Se um item do pedido antigo estiver indisponível, alertar o usuário antes de fechar o carrinho.
- **Complexidade:** Baixa.
- **Estimativa:** 3 story points.

### 7. Pagamento Via Carteira Digital/Pix

- **História:** Enquanto **Cliente**, desejo **pagar via Pix de forma integrada**, para **agilizar a finalização do pedido**.
- **Critérios de Aceitação:**
    1. Gerar QR Code e código "Copia e Cola" após a confirmação.
    2. O sistema deve verificar o recebimento do pagamento em até 60 segundos.
    3. Cancelar automaticamente o pedido se o pagamento não ocorrer no prazo.
- **Regras de Negócio:** A transação deve seguir os padrões de segurança do Banco Central.
- **Complexidade:** Alta.
- **Estimativa:** 8 story points.

---

### Persona: Loja

### 8. Gestão de Disponibilidade de Itens

- **História:** Enquanto **Loja**, desejo **ativar ou desativar itens do cardápio em tempo real**, para **evitar pedidos de produtos esgotados**.
- **Critérios de Aceitação:**
    1. Dashboard deve listar todos os produtos com um interruptor (on/off).
    2. A alteração deve refletir no app do cliente instantaneamente.
    3. Deve haver uma opção de "Esgotado por hoje" (reset automático no dia seguinte).
- **Regras de Negócio:** Itens desativados não podem aparecer na busca do cliente.
- **Complexidade:** Baixa.
- **Estimativa:** 2 story points.

### 9. Definição de Raio de Entrega

- **História:** Enquanto **Loja**, desejo **configurar a distância máxima e o valor do frete por quilômetro**, para **garantir a rentabilidade da entrega própria**.
- **Critérios de Aceitação:**
    1. Campo para inserir raio em km.
    2. Tabela de preços escalonável por distância.
    3. O sistema deve bloquear pedidos de clientes fora desse raio.
- **Regras de Negócio:** O raio máximo permitido globalmente pelo app é de 20km.
- **Complexidade:** Média.
- **Estimativa:** 3 story points.

### 10. Painel de Pedidos Ativos

- **História:** Enquanto **Loja**, desejo **um painel com alertas sonoros para novos pedidos**, para **minimizar o tempo de resposta e preparo**.
- **Critérios de Aceitação:**
    1. O alerta sonoro deve persistir até que o pedido seja aceito.
    2. Exibir cronômetro regressivo com o tempo de entrega prometido.
    3. Diferenciar pedidos novos, em preparo e prontos por cores.
- **Regras de Negócio:** Pedidos não aceitos em 10 minutos são cancelados automaticamente.
- **Complexidade:** Média.
- **Estimativa:** 5 story points.

### 11. Atribuição de Entregador Parceiro

- **História:** Enquanto **Loja**, desejo **solicitar um entregador da plataforma após o preparo**, para **enviar o pedido sem necessidade de frota própria**.
- **Critérios de Aceitação:**
    1. Botão "Chamar Entregador" fica ativo quando o pedido está "Em Preparo".
    2. O sistema deve notificar o entregador mais próximo disponível.
    3. Exibir nome e placa do entregador que aceitou.
- **Regras de Negócio:** A loja paga uma taxa adicional por este serviço.
- **Complexidade:** Alta.
- **Estimativa:** 8 story points.
- **Relacionado com o(s) requisito(s):** 16.

### 12. Relatório de Vendas Diário

- **História:** Enquanto **Loja**, desejo **visualizar o resumo financeiro do dia**, para **conciliar meu caixa e estoque**.
- **Critérios de Aceitação:**
    1. Exibir total bruto, taxas do app e valor líquido.
    2. Listar métodos de pagamento utilizados (Cartão, Dinheiro, Pix).
    3. Botão para exportar PDF ou CSV.
- **Regras de Negócio:** O fechamento diário ocorre sempre às 00:00.
- **Complexidade:** Baixa.
- **Estimativa:** 3 story points.

### 13. Promoções de "Happy Hour"

- **História:** Enquanto **Loja**, desejo **agendar descontos automáticos para horários específicos**, para **aumentar as vendas em períodos de baixa demanda**.
- **Critérios de Aceitação:**
    1. Definir dia da semana, horário de início e fim.
    2. O desconto pode ser em porcentagem ou valor fixo.
    3. O sistema deve destacar o item com "Preço promocional" no app do cliente.
- **Regras de Negócio:** Descontos não podem ultrapassar 70% do valor original.
- **Complexidade:** Média.
- **Estimativa:** 5 story points.

---

### Persona: Entregador

### 14. Aceite de Rota de Entrega

- **História:** Enquanto **Entregador**, desejo **visualizar o valor do frete e a distância antes de aceitar**, para **decidir se a corrida é vantajosa**.
- **Critérios de Aceitação:**
    1. Notificação deve mostrar origem (Loja) e destino aproximado.
    2. Exibir o valor líquido que o entregador receberá.
    3. Timer de 30 segundos para aceite antes de passar para o próximo.
- **Regras de Negócio:** O entregador deve estar em um raio de 5km da loja para receber a oferta.
- **Complexidade:** Média.
- **Estimativa:** 5 story points.

### 15. Navegação Integrada GPS

- **História:** Enquanto **Entregador**, desejo **abrir a rota no Google Maps ou Waze com um clique**, para **chegar ao destino pelo caminho mais rápido**.
- **Critérios de Aceitação:**
    1. Botão "Navegar" presente na tela de pedido aceito.
    2. Opção de escolher qual app de mapas externo utilizar.
    3. Passar as coordenadas exatas do cliente para o app externo.
- **Regras de Negócio:** O sistema deve registrar o horário de partida para o cálculo de SLA.
- **Complexidade:** Baixa.
- **Estimativa:** 2 story points.
- **Relacionado com o(s) requisito(s):** 1.

### 16. Confirmação de Entrega via Código

- **História:** Enquanto **Entregador**, desejo **solicitar um código de 4 dígitos ao cliente**, para **confirmar que o pedido foi entregue à pessoa correta**.
- **Critérios de Aceitação:**
    1. Campo de input numérico na tela final do entregador.
    2. O sistema deve validar o código em tempo real com o que foi gerado para o cliente.
    3. Só permitir a finalização da corrida após código válido.
- **Regras de Negócio:** O código deve ser enviado ao cliente via Push assim que o entregador chegar ao local.
- **Complexidade:** Média.
- **Estimativa:** 3 story points.

### 17. Gerenciamento de Status de Disponibilidade

- **História:** Enquanto **Entregador**, desejo **ficar "Offline" no aplicativo**, para **parar de receber notificações de pedidos quando terminar meu turno**.
- **Critérios de Aceitação:**
    1. Botão de status visível em todas as telas principais.
    2. Se "Offline", o algoritmo de roteamento deve ignorar o usuário.
    3. Se houver pedido em andamento, o sistema não deve permitir ficar offline.
- **Regras de Negócio:** O sistema deve registrar o tempo total de conexão diária.
- **Complexidade:** Baixa.
- **Estimativa:** 2 story points.

### 18. Extrato de Ganhos Semanais

- **História:** Enquanto **Entregador**, desejo **visualizar o acumulado de ganhos da semana**, para **controlar minhas finanças pessoais**.
- **Critérios de Aceitação:**
    1. Gráfico simples comparando ganhos por dia.
    2. Detalhamento de gorjetas recebidas separadamente do frete.
    3. Indicação da data prevista para o próximo repasse bancário.
- **Regras de Negócio:** Gorjetas são repassadas integralmente ao entregador, sem taxas do app.
- **Complexidade:** Baixa.
- **Estimativa:** 3 story points.

### 19. Chat com a Loja/Cliente

- **História:** Enquanto **Entregador**, desejo **enviar mensagens rápidas via chat**, para **resolver problemas de localização ou atrasos**.
- **Critérios de Aceitação:**
    1. Chat habilitado apenas enquanto o pedido estiver ativo.
    2. Opções de frases pré-definidas (ex: "Cheguei no local", "Estou aguardando o pedido").
    3. O histórico deve ser apagado 24h após a conclusão do pedido por privacidade.
- **Regras de Negócio:** Proibida a troca de links externos ou números de telefone.
- **Complexidade:** Alta.
- **Estimativa:** 8 story points.

### 20. Avaliação do Estabelecimento

- **História:** Enquanto **Entregador**, desejo **avaliar a agilidade da loja na entrega do pacote**, para **que o sistema identifique lojas que causam atrasos aos entregadores**.
- **Critérios de Aceitação:**
    1. Escala de 1 a 5 estrelas após o "Coletado".
    2. Campo opcional para relatar "Pedido não estava pronto".
    3. Os dados devem alimentar um ranking interno de performance de lojas.
- **Regras de Negócio:** Lojas com muitas avaliações negativas de demora podem sofrer penalidades no ranking de busca.
- **Complexidade:** Baixa.
- **Estimativa:** 2 story points.




