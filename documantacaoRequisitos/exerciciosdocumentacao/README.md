# Sistema de gerenciamentos de Reservas de Hotel 

## 1. introdeção

## 2. visão Geral
Este documento especifica os requisitos funcionais e o controle de versões para o módulo de agendamento do SRH, seguindo o padrão.
O SRH permitirá que hóspedes realizem reservas de quartos, com regras dinâmicas de prazos e tarifas baseadas no perfil do usuário e na urgência da reserva.

## 3. Requisitos Especificos

## 3.1 Requisitos Funcionais 

RF-010: Gestão de Período e Prazos de Reserva
**Descrição**: Permitir reservas com antecedência mínima de 24 horas e máxima de 6 meses.
**Versão**: 1.0.0
**Data**: 2026-01-15
**Prioridade**: Alta 
**Rastreabilidade**: NS-001 (Necessidade de Negócio: Operação Padrão)
**Critérios de Aceitação**:

[ ] Bloquear reservas feitas para o mesmo dia (menos de 24h).
[ ] Bloquear seleções no calendário superiores a 6 meses da data atual.

---

## 3.2 

RF-010: Gestão de Período e Prazos de Reserva
**Descrição**: Manter regra padrão. Adição: Clientes com perfil VIP podem reservar com até 1 ano de antecedência.
**Versão**: 1.1.0
**Data**: 2026-02-10
**Motivo da Alteração**: Solicitação do Departamento de Vendas para oferecer benefícios exclusivos e fidelizar clientes VIP.
**Prioridade**: Alta 
**Rastreabilidade**:  NS-012 (Solicitação Vendas: Fidelização)
**Critérios de Aceitação**:

[ ] Validar o status do usuário antes de renderizar o calendário.

[ ] Liberar 12 meses de disponibilidade apenas para usuários autenticados como VIP.


---

RF-010: Gestão de Período e Prazos de Reserva
**Descrição**:O sistema permite reservas com máxima de 6 meses (1 ano para VIPs). Adição: São permitidas reservas de "última hora" (menos de 2 horas de antecedência), desde que seja aplicada uma taxa de urgência de 15% sobre o valor total.
**Versão**: 1.1.0
**Data**: 2026-03-20
**Motivo da Alteração**:Nova política da empresa para maximizar a ocupação e rentabilizar reservas imediatas.
**Prioridade**: Alta 
**Rastreabilidade**:  NS-012 (Solicitação Vendas: Fidelização)
**Critérios de Aceitação**:

[ ] Identificar reservas criadas com delta de tempo < 120 minutos.

[ ] Aplicar multiplicador de $1.15$ no cálculo do checkout.

[ ] Exibir aviso visual da "Taxa de Conveniência" antes da finalização.


## 4. Controle de versão

### 4.1 Historica de versões
Versão|Data      |Autor  |Modificação   |
|------|----------|-------|--------------|
|1.0.0  |2026-01-15 |Sarah| Versão inicial: Janela padrão de 24h a 6 meses.  |
| 1.1.0 |2026-02-10 | Sarah| AImplementada regra de exceção para Clientes VIP (1 ano).|
|1.1.1 |2026-03-20 |Sarah| Inclusão de "Last Minute" com taxa adicional de 15%.

## 5. Conclusão 
A evolução do requisito RF-010 demonstra a adaptabilidade do Sistema de Reservas de Hotel (SRH) às demandas dinâmicas do mercado e às estratégias de fidelização da empresa.
