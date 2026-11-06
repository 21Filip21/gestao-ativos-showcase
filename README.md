<div align="center">

# 🖥️ Gestão de Ativos

**Uma aplicação web para saber o que existe, onde está, quem usa e o que aconteceu a cada equipamento informático.**

![React](https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-Express-339933?logo=nodedotjs&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-Base%20de%20dados-CC2927)
![HTTPS](https://img.shields.io/badge/Seguran%C3%A7a-HTTPS%20%2B%20LDAPS-2EA44F)

<br>

<img src="imagens/dashboard.png" alt="Dashboard" width="900">

[O problema](#-o-problema) · [Funcionalidades](#-o-que-faz) · [Visita guiada](#%EF%B8%8F-visita-guiada) · [Arquitetura](#%EF%B8%8F-arquitetura) · [Segurança](#-segurança) · [Tecnologias](#%EF%B8%8F-tecnologias)

</div>

<br>

> [!NOTE]
> Esta página só apresenta o projeto. **O código é privado.** As imagens usam dados de demonstração: os equipamentos, as pessoas e os endereços são inventados.

## 🧩 O problema

Controlar equipamento informático em folhas de Excel partilhadas leva a dados duplicados, versões diferentes e pouca noção do que aconteceu a cada equipamento. Quando alguém pergunta onde está um portátil, quem o usou ou quanto custou repará-lo, a resposta demora.

Esta aplicação junta tudo num só sítio, com pesquisa, histórico e controlo de quem alterou o quê.

## ✨ O que faz

| | |
|---|---|
| 🖥️ **Inventário completo** | Computadores, monitores, impressoras e telefones, com pesquisa, filtros e colunas à escolha |
| 🏷️ **Etiquetas com QR code** | O telemóvel lê a etiqueta e abre logo a ficha do equipamento |
| 📜 **Histórico** | Todas as alterações, com a pessoa e a hora |
| 🔧 **Manutenção** | Avarias, reparações, peças e custos de cada equipamento |
| 🤝 **Empréstimos e reservas** | Com quem está, quando volta e para quando está reservado |
| 🧾 **Aluguer separado** | Equipamento alugado fora do inventário principal, com numeração própria |
| 🔎 **Auditoria por sala** | Confirmação no local do que existe e do que está em falta |
| 📦 **Consumíveis** | Material pequeno por quantidade, com alerta de stock baixo |
| 📊 **Dashboard e relatório** | Estado, localização, antiguidade e garantias |
| ✅ **Qualidade de dados** | Deteta valores inconsistentes e campos por preencher |
| 🔐 **Login integrado** | Conta do Windows, conta do domínio ou conta local |
| 🌙 **Modo escuro** | Tema claro e escuro, adaptado ao telemóvel |

## 🖼️ Visita guiada

### 1. Entrar na app

No computador, basta um clique para entrar com a conta do Windows. No telemóvel, a app pede logo o utilizador e a palavra-passe. Só entra quem estiver autorizado.

<table>
  <tr>
    <th width="72%">No computador</th>
    <th width="28%">No telemóvel</th>
  </tr>
  <tr>
    <td><img src="imagens/login.png" alt="Login no computador"></td>
    <td><img src="imagens/login-telemovel.png" alt="Login no telemóvel"></td>
  </tr>
</table>

### 2. Ver o estado geral

O Dashboard mostra quantos equipamentos estão em uso, em stock ou avariados, onde estão, que idade têm e que garantias estão a acabar. Cada número abre a lista correspondente.

<img src="imagens/dashboard.png" alt="Dashboard">

<p align="center">
  <img src="imagens/escuro.png" alt="Dashboard em modo escuro" width="520"><br>
  <em>Também há modo escuro.</em>
</p>

### 3. Encontrar um equipamento

A lista pesquisa por número de inventário, série, hostname, sala ou pessoa. Dá para filtrar, escolher as colunas, exportar para Excel e mudar vários equipamentos de uma só vez.

<table>
  <tr>
    <th>Todos os equipamentos</th>
    <th>Só os avariados</th>
  </tr>
  <tr>
    <td><img src="imagens/ativos.png" alt="Lista de ativos"></td>
    <td><img src="imagens/ativos-filtro.png" alt="Lista filtrada pelos avariados"></td>
  </tr>
</table>

### 4. Adicionar um equipamento

O formulário está organizado por temas e sugere o próximo número de inventário. Os campos mudam conforme a categoria: num telefone, aparecem só os que interessam.

<table>
  <tr>
    <th>Equipamento normal</th>
    <th>Telefone</th>
  </tr>
  <tr>
    <td><img src="imagens/novo-ativo.png" alt="Formulário normal"></td>
    <td><img src="imagens/novo-telefone.png" alt="Formulário de telefone"></td>
  </tr>
</table>

**A app evita erros antes de acontecerem.** Se uma licença já estiver noutro telefone, não deixa guardar e mostra um link para esse equipamento, que abre noutra aba para não se perder o que foi preenchido.

<img src="imagens/geo-duplicado.png" alt="Aviso de valor repetido">

### 5. A ficha do equipamento

Cada equipamento tem uma ficha com tudo o que lhe diz respeito, organizada em abas.

<img src="imagens/ficha.png" alt="Ficha do equipamento">

<table>
  <tr>
    <th>Manutenção</th>
    <th>Empréstimo</th>
  </tr>
  <tr>
    <td>Cada avaria e reparação, com o custo total.<br><br><img src="imagens/manutencao.png" alt="Manutenção"></td>
    <td>A quem foi emprestado e quando deve voltar.<br><br><img src="imagens/emprestimo.png" alt="Empréstimo"></td>
  </tr>
  <tr>
    <th>Reservas</th>
    <th>Atribuições</th>
  </tr>
  <tr>
    <td>Marcar o equipamento para uma data futura.<br><br><img src="imagens/reservas.png" alt="Reservas"></td>
    <td>Por quem passou o equipamento ao longo do tempo.<br><br><img src="imagens/atribuicoes.png" alt="Atribuições"></td>
  </tr>
</table>

**Histórico do equipamento:** todas as alterações, com a pessoa e a hora. Há ainda uma aba de **Anexos**, para fotos e faturas.

<img src="imagens/ficha-historico.png" alt="Histórico do equipamento">

### 6. Etiqueta e QR code

A etiqueta é gerada logo depois de criar o equipamento, pronta para imprimir numa impressora de etiquetas ou numa normal. Com o telemóvel, basta ler o QR code para abrir a ficha e marcar o equipamento como verificado.

<table>
  <tr>
    <th width="72%">A etiqueta</th>
    <th width="28%">Ao ler o QR code</th>
  </tr>
  <tr>
    <td><img src="imagens/etiqueta.png" alt="Etiqueta com QR code"></td>
    <td><img src="imagens/telemovel.png" alt="Ficha no telemóvel"></td>
  </tr>
</table>

### 7. Equipamento alugado

O que é alugado tem uma secção própria, com numeração própria e o hostname à frente. Não conta para o inventário, para o Excel, para o Dashboard nem para o relatório, por isso uma auditoria não o confunde com equipamento próprio. A pesquisa avisa quando o resultado está na outra lista.

<img src="imagens/aluguer.png" alt="Secção de aluguer">

### 8. Auditoria por sala

Na sala, escolhe-se o local e confirma-se cada equipamento com um leitor, com o telemóvel ou com um clique. No fim, a app mostra o que falta e o que está registado noutro sítio.

<img src="imagens/auditoria.png" alt="Auditoria por sala">

### 9. Consumíveis

Cabos, ratos, teclados e outro material pequeno são contados por quantidade. A linha fica destacada quando o stock desce abaixo do mínimo.

<img src="imagens/consumiveis.png" alt="Consumíveis">

### 10. Relatórios e controlo

O **relatório** resume o parque informático numa página, pronta para imprimir ou guardar em PDF, com pontos de atenção.

<img src="imagens/relatorio.png" alt="Relatório">

<table>
  <tr>
    <th>Histórico geral</th>
    <th>Qualidade de dados</th>
  </tr>
  <tr>
    <td><img src="imagens/historico.png" alt="Histórico geral"></td>
    <td><img src="imagens/qualidade.png" alt="Qualidade de dados"></td>
  </tr>
</table>

### 11. Administração

A parte de administração permite gerir a aplicação sem mexer no código, e só os administradores a veem.

**Utilizadores:** cada pessoa tem a sua conta, para se saber sempre quem fez cada alteração. Daqui dá para criar contas, dar permissões, repor palavras-passe e ver o histórico de cada pessoa.

<img src="imagens/utilizadores.png" alt="Gestão de utilizadores">

**Sistema:** escolher o que aparece no menu, fazer cópias de segurança, importar o Excel e ligar a sincronização com o Active Directory.

<img src="imagens/sistema.png" alt="Administração do sistema">

**Campos e listas:** criar campos novos, mudar nomes e ordem, escolher o que é obrigatório e gerir sites, serviços, categorias e estados, com a sua cor.

<table>
  <tr>
    <th>Campos</th>
    <th>Listas</th>
  </tr>
  <tr>
    <td><img src="imagens/campos.png" alt="Gestão de campos"></td>
    <td><img src="imagens/listas.png" alt="Gestão das listas"></td>
  </tr>
</table>

**Definições:** avisos de garantia e de verificação, impressora e tamanho das etiquetas, e o endereço usado nos códigos QR.

<img src="imagens/definicoes.png" alt="Definições">

**Removidos e possíveis fantasmas:** nada se perde por engano, porque os equipamentos removidos podem ser restaurados. Os possíveis fantasmas ajudam a encontrar registos de equipamentos que já não dão sinal de vida, cruzando o inventário com o Active Directory e a rede.

<table>
  <tr>
    <th>Removidos</th>
    <th>Possíveis fantasmas</th>
  </tr>
  <tr>
    <td><img src="imagens/removidos.png" alt="Equipamentos removidos"></td>
    <td><img src="imagens/fantasmas.png" alt="Possíveis fantasmas"></td>
  </tr>
</table>

## 🏗️ Arquitetura

```mermaid
flowchart LR
    A["🌐 Browser ou telemóvel"] -->|"HTTPS"| B["Node.js + Express<br/>API e ecrã"]
    B --> C[("SQL Server")]
    B -->|"LDAPS"| D["Active Directory"]
    B --> E["Cópias de segurança diárias"]
    F["Scripts de inventário"] -->|"API com token"| B
    B --> G["🖨️ Impressora de etiquetas"]
```

Decisões técnicas principais:

- **Campos dinâmicos:** é possível criar campos novos sem mexer no código.
- **Alterações automáticas à base de dados:** aplicam-se sozinhas no arranque.
- **Atualização com um comando:** faz a cópia de segurança, traz a versão nova, compila e volta a arrancar o serviço.
- **Listas grandes rápidas:** a pesquisa e a ordenação foram otimizadas para listas com muitos registos.
- **Verificação antes de publicar:** um comando confirma a sintaxe, o lint, a compilação, o arranque e as dependências.

## 🔒 Segurança

| Área | Como foi feito |
|---|---|
| **Login** | Windows (SSO), LDAPS ou conta local com bcrypt |
| **Tentativas** | Limite por endereço e bloqueio temporário por utilizador |
| **Acesso** | Só entra quem está autorizado, com permissões de administrador separadas |
| **Base de dados** | Todas as consultas usam SQL parametrizado |
| **Rede** | HTTPS com renovação do certificado sem reiniciar |
| **Dados** | Cópias de segurança automáticas e verificadas |
| **Rastreabilidade** | Histórico de todas as alterações |
| **Segredos** | Definições sensíveis fora do Git |

## 🛠️ Tecnologias

| Área | Tecnologia |
|---|---|
| Frontend | React 19, React Router, Vite |
| Backend | Node.js, Express 5 |
| Base de dados | SQL Server |
| Autenticação | Windows (SSO), LDAPS e contas locais |
| Excel | ExcelJS, para importar e exportar |
| Automação | PowerShell, para recolha de dados de rede |
| Instalação | Serviço do Windows e atualização a partir do Git |

## 💡 O que aprendi

- Levar uma aplicação do zero até à produção, com utilizadores reais.
- Modelar dados que vieram de folhas de cálculo com anos de inconsistências.
- Tratar de autenticação, permissões, HTTPS e cópias de segurança.
- Medir o desempenho e corrigir o que estava lento.
- Ouvir quem usa a aplicação e melhorar com base nisso.
