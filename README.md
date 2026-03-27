# 💰 Minhas Finanças - Gerenciador Financeiro Pessoal

Um aplicativo web de controle financeiro com design premium (estilo "fintech") construído inteiramente com HTML, CSS e JavaScript puros (Vanilla). Focado em performance, usabilidade *mobile-first* e privacidade.

## ✨ Funcionalidades Principais

* **Dashboard Intuitivo:** Visão clara do Saldo Acumulado, Receitas, Débitos e Créditos do mês atual.
* **Organização em Abas:** Separação visual limpa entre as movimentações da **Conta Corrente** (Débito/Pix/Receitas) e os gastos do **Cartão de Crédito**.
* **Inteligência de Cartão de Crédito:** * Configuração personalizada do **dia de fechamento** da fatura.
  * Lançamento automático de compras para a fatura do mês correto (suporta cartões que fecham tanto no início quanto no final do mês).
  * Botão de **"Pagar Fatura"** que gera uma transação inteligente, debitando o valor total do cartão diretamente do saldo da sua conta corrente.
* **UI/UX Avançada (Livre de visuais nativos):**
  * Formulários com *Segmented Controls* (botões lado a lado) no lugar de caixas de seleção antigas.
  * **Custom DatePicker:** Calendário próprio do aplicativo para seleção de datas, ignorando o calendário padrão feio dos navegadores.
  * Animações suaves e janelas modais deslizantes (*Bottom Sheets*).
  * **Tour de Boas-Vindas:** Um *Onboarding* animado para ensinar atalhos e realizar a primeira configuração.
* **Suporte a Temas:** Alternância instantânea entre os modos **Claro ☀️**, **Médio 🌙** (Slate) e **Escuro ✨** (OLED).
* **Gestão de Dados Completa:** * Edição rápida (puxando os dados antigos para o formulário) e exclusão de transações.
  * **Backup Seguro:** Exportação de todo o histórico financeiro para o Excel no formato `.CSV`.
* **100% Offline e Privado:** Sem bancos de dados em nuvem. Tudo fica salvo de forma persistente no `LocalStorage` do seu próprio dispositivo.

## 🚀 Como Usar (Instalação Zero)

A beleza deste projeto é a ausência de dependências, compiladores ou *build steps*. 

1. Baixe o arquivo `index.html`.
2. Dê um duplo clique para abrir no seu navegador favorito (Chrome, Edge, Safari).
3. **Dica Pro (Mobile):** Abra o arquivo no navegador do seu celular e selecione a opção **"Adicionar à Tela Inicial"**. Ele se comportará como um aplicativo nativo de verdade!

## 🛠 Tecnologias Utilizadas

* **HTML5:** Estrutura e semântica.
* **CSS3:** Estilização com foco em Variáveis Globais (`:root`), Flexbox, CSS Grid e animações (`@keyframes`).
* **JavaScript (ES6+):** Toda a lógica de regras de negócios, paginação de meses, cálculos de fatura e manipulação do DOM.
* **Lucide Icons:** (Via CDN) Biblioteca minimalista para a iconografia do aplicativo.
* **Window.localStorage:** Armazenamento de dados no cliente de forma eficiente e síncrona.

## 💡 A "Mágica" do Fechamento da Fatura

O sistema foi programado com um algoritmo bifurcado para entender o comportamento de diferentes emissores de cartão:
* **Cartões de "Fim de mês" (Ex: fecham dia 25):** Compras feitas a partir do dia 25 são automaticamente calculadas como dívidas da fatura do *mês seguinte*.
* **Cartões de "Início de mês" (Ex: fecham dia 4):** Compras feitas antes do dia 4 são jogadas para a fatura do *mês anterior*, ajustando-se à realidade bancária.

---
