# 📦 WyncStock — Gestão de Estoque via WhatsApp

<div align="center">

*Controle total do seu inventário direto pelo WhatsApp — sem apps, sem treinamento, sem complicação.*

![N8N](https://img.shields.io/badge/N8N-Automation-EA4B71?style=flat-square&logo=n8n&logoColor=white)
![Airtable](https://img.shields.io/badge/Airtable-Database-18BFFF?style=flat-square&logo=airtable&logoColor=white)
![WhatsApp](https://img.shields.io/badge/WhatsApp-API-25D366?style=flat-square&logo=whatsapp&logoColor=white)
![Python](https://img.shields.io/badge/Python-Scripts-3776AB?style=flat-square&logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Status](https://img.shields.io/badge/Status-MVP%20Estável-brightgreen?style=flat-square)

</div>

---

## 🚀 Sobre o Projeto

O **WyncStock** surgiu de um problema real em pequenas e médias empresas: gestores perdendo tempo em planilhas desatualizadas, erros de entrada manual e falta de visibilidade sobre o estoque em tempo real.

A solução foi radical na sua simplicidade — **usar o WhatsApp, o app que todo mundo já conhece**, como interface de controle. Sem apps novos para instalar, sem treinamento de equipe, sem curva de aprendizado.

> *"Se a equipe já usa WhatsApp, o sistema de estoque também vai."*

---

## ✨ Funcionalidades

| Comando | Descrição |
|---------|-----------|
| `📥 entrada [produto] [qtd]` | Registra entrada de estoque |
| `📤 saída [produto] [qtd]` | Registra saída de estoque |
| `🔍 consulta [produto]` | Consulta quantidade atual |
| `📊 relatório` | Relatório geral do inventário |
| `⚠️ alertas` | Lista produtos com estoque baixo |

---

## 🛠️ Stack Tecnológica

```
Automação
├── N8N              → Orquestração de fluxos (workflow exportado em .json)
└── Python Scripts   → Lógica customizada de processamento

Banco de Dados
└── Airtable         → Armazenamento e gestão do inventário

Comunicação
└── Z-API            → Integração com WhatsApp Business
```

---

## 💡 Como Funciona

```
Gestor envia mensagem no WhatsApp
        ↓
Z-API captura e encaminha para o N8N
        ↓
N8N interpreta o comando
        ↓
Python processa a lógica de negócio
        ↓
Airtable é atualizado em tempo real
        ↓
Confirmação enviada de volta via WhatsApp
```

---

## 📦 Como Usar

### Pré-requisitos

- Conta no [N8N](https://n8n.io) (self-hosted ou cloud)
- Conta no [Airtable](https://airtable.com)
- Conta na [Z-API](https://z-api.io) com número WhatsApp conectado
- Python 3.10+

### Instalação

```bash
# 1. Clone o repositório
git clone https://github.com/Kanashinho/SynckStock.git
cd SynckStock

# 2. Configure as variáveis de ambiente
cp .env.example .env
# Edite o .env com suas credenciais

# 3. Instale as dependências Python
pip install -r requirements.txt

# 4. Importe o fluxo no N8N
# No painel do N8N: Settings → Import workflow → selecione o arquivo .json
```

### Configuração (.env)

```env
# Z-API (WhatsApp)
ZAPI_INSTANCE=sua_instancia
ZAPI_TOKEN=seu_token

# Airtable
AIRTABLE_API_KEY=sua_chave
AIRTABLE_BASE_ID=seu_base_id
AIRTABLE_TABLE_NAME=Estoque

# N8N
N8N_WEBHOOK_URL=http://localhost:5678/webhook/wyncstock
```

---

## 🗂️ Estrutura do Projeto

```
SynckStock/
├── workflows/
│   └── wyncstock_flow.json   # Fluxo N8N (importe aqui)
├── scripts/
│   └── processor.py          # Lógica de processamento Python
├── requirements.txt
├── .env.example
└── .gitignore
```

---

## 🗺️ Roadmap

- [x] MVP funcional com Airtable
- [x] Comandos de entrada, saída e consulta via WhatsApp
- [x] Alertas de estoque baixo
- [ ] **Migração para SQL** (PostgreSQL) — maior performance e controle
- [ ] **Deploy em servidor local** — elimina dependência de serviços cloud, reduz custo de manutenção
- [ ] Relatórios automáticos agendados
- [ ] Suporte a múltiplos almoxarifados
- [ ] Dashboard web complementar

---

## 💰 Casos de Uso Ideais

- Pequenos comércios e lojas
- Restaurantes e estoques de insumos
- Almoxarifados industriais
- Qualquer negócio onde a equipe já usa WhatsApp no dia a dia

---

## 📄 Licença

Este projeto está licenciado sob a **MIT License** — veja o arquivo [LICENSE](LICENSE) para detalhes.

Você pode usar, copiar e modificar livremente, **desde que mantenha os créditos ao autor original**.

---

## 👤 Autor

**Kauã M. S. Winter Moraes**
- LinkedIn: [linkedin.com/in/kaua-winter](https://linkedin.com/in/kaua-winter)
- GitHub: [@Kanashinho](https://github.com/Kanashinho)
- Email: kaua.wintermoraes@gmail.com

---

<div align="center">
<i>Se este projeto foi útil para você, considere deixar uma ⭐</i>
</div>
