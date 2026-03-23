# DIAGNÓSTICO TÉCNICO E FUNCIONAL - PAINEL CREDPLUS 1.0

Este documento apresenta o diagnóstico detalhado de todas as funcionalidades, arquitetura e regras de negócio do sistema **PAINEL CREDPLUS 1.0**.

## 1. ARQUITETURA DO SISTEMA
- **Tecnologias**: HTML5, CSS3 (Vanilla), JavaScript (ES6+).
- **Interface**: Design responsivo com estética *Clean Green* (Dark Mode e Glassmorphism).
- **Persistência**: Armazenamento via `localStorage` (os dados ficam salvos no seu navegador).
- **Dependências**: Biblioteca **Lucide Icons** para os ícones e fontes do **Google Fonts** (Inter e Outfit).

---

## 2. HIERARQUIA DE NAVEGAÇÃO E ACESSO (4 NÍVEIS)
O sistema foi estruturado para garantir que a gestão seja descentralizada e auditável:

1.  **VISÃO GERAL (ADM)**: O painel mestre. Consolida 100% dos dados de todos os colaboradores e sub-dashboards em tempo real.
2.  **GRUPO ESPECIAL**: Painel exclusivo de **LELLYS FLÁVIO**, no topo da prioridade de visualização.
3.  **GRUPO A**: Gerencia os portfólios de **Jailton, Ricardo, Mangu e Matheus Tuk**.
4.  **GRUPO B**: Gerencia os portfólios de **Sanny, Marcos e Jean**.

---

## 3. IDENTIDADES VISUAIS (PALETA EXCLUSIVA)
Cada gestor possui uma cor identificadora única para evitar confusão no Dashboard Geral:
- **Lellys Flávio**: Verde Emerald (`#10b981`)
- **Jailton**: Branco (`#ffffff`)
- **Ricardo**: Laranja (`#f97316`)
- **Mangu**: Azul Royal (`#1d4ed8`)
- **Matheus Tuk**: Roxo (`#a855f7`)
- **Sanny**: Rosa (`#ec4899`)
- **Marcos**: Azul Sky (`#0ea5e9`)
- **Jean**: Amarelo (`#fbbf24`)

---

## 4. FUNCIONALIDADES FINANCEIRAS AVANÇADAS

### 📊 Painel de Estatísticas
- **Carteira em Aberto**: Valor total de capital emprestado (exclui contratos marcados como 'PAGO').
- **Juros à Receber**: Valor consolidado de juros mensais baseados no capital pendente.
- **Clientes Ativos**: Contagem real de registros conforme o filtro atual da tela.
- **Comissão (Grupo B)**: Card estatístico que exibe o ganho individual de Sanny, Jean e Marcos conforme a porcentagem individual definida pelo ADM.

### 📅 Controle de Datas e Rastreabilidade
- **Data do Empréstimo**: Registro oficial de quando o capital saiu.
- **Data Pagamento Juros**: Data de vencimento que rege as cores de status.

### 🔴 Semáforo Financeiro (Status Dinâmico)
O sistema utiliza as seguintes cores baseadas na **Data de Pagamento dos Juros**:
- 🛑 **Vermelho**: Contrato Vencido.
- 🟡 **Amarelo**: Faltando 1 dia para o vencimento (Atenção).
- 🔵 **Azul**: Vencendo hoje ou contrato em dia.
- 🟢 **Verde**: Contrato liquidado (PAGO).

### 📐 Cálculos Individualizados
- **Juros Mensais**: Calculados individualmente por contrato (padrão 8%, ajustável pelo ADM).
- **Comissões**: Porcentagem definida individualmente pelo ADM no formulário do Grupo B.

---

## 5. REGRAS DE SINCRONIZAÇÃO
- **Consolidação Automática**: Todo lançamento feito em um dashboard individual ou de grupo é instantaneamente somado à **Visão Geral**.
- **Segurança de Dados**: O sistema utiliza filtros blindados que impedem que cruzamentos de dados indevidos entre colaboradores (cada um enxerga apenas sua carteira ou grupo).
- **Formatação Monetária**: O padrão visual é rigorosamente o da moeda brasileira (R$ 0.000,00).

---

**Diagnóstico finalizado e validado na Versão 15.0.**
