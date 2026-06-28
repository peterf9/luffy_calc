# 🚀 Quick Start Guide

## ⚡ 5 Minutos para Começar

### 1. Abra a Aplicação

```bash
# Opção A: Versão Melhorada (Recomendado)
https://github.com/peterf9/luffy_calc/blob/main/index-improved.html
# Clique em "Raw" → salve como index.html → abra no navegador

# Opção B: GitHub Pages (mais direto)
https://peterf9.github.io/luffy_calc/index-improved.html
```

### 2. Adicione Seu Pet

O aplicativo se conecta ao Pantry Cloud e espera esta estrutura JSON:

```json
{
  "activePetId": "pet123",
  "pets": {
    "pet123": {
      "petInfo": {
        "name": "Seu Pet Aqui",
        "birthDate": "2024-01-15"
      },
      "schedule": {
        "totalGrams": 500,
        "gramsPerMeal": 100,
        "meals": [
          {
            "id": "meal1",
            "name": "Breakfast",
            "time": "08:00",
            "grams": 100
          },
          {
            "id": "meal2",
            "name": "Lunch",
            "time": "12:00",
            "grams": 100
          },
          {
            "id": "meal3",
            "name": "Dinner",
            "time": "19:00",
            "grams": 100
          }
        ]
      },
      "gamification": {
        "level": 1,
        "xp": 0,
        "patacoins": 0,
        "dailyTasks": {}
      },
      "logs": {}
    }
  }
}
```

### 3. Configure o Pantry Cloud

1. Acesse: https://getpantry.cloud/
2. Clique em "New Pantry"
3. Copie seu `PANTRY_ID`
4. Edite o arquivo `.html`:

```javascript
// Encontre estas linhas:
const PANTRY_ID = "c42cdca2-f5c9-4b78-b7ba-527236418398"; // ← MUDE ISTO
const BASKET_NAME = "bello_app_state";
```

Substitua pelo seu `PANTRY_ID`.

### 4. Use a Aplicação

```
┌─────────────────────────────────────┐
│  Luffy Family 🐾                    │
│  Painel da Família                  │
│  🌟 Lvl 5 | ✨ 1250 XP | 🪙 50     │
├─────────────────────────────────────┤
│ Idade: 5 meses, 14 dias             │
│ Meta Hoje: 500 g (~100g/pote)       │
├─────────────────────────────────────┤
│ 🍖 Refeições                        │
│                                     │
│ Café da Manhã 100g                 │
│ [08:00] ☑️ ✅ 08:15                │
│                                     │
│ Almoço 100g                         │
│ [12:00] [ ] (vazio)                │
│                                     │
│ Jantar 100g                         │
│ [19:00] [ ] (vazio)                │
├─────────────────────────────────────┤
│ 🎯 Missões Diárias                 │
│ 🦮 Passeio          ☑️              │
│ 💧 Água Fresca      [ ]             │
├─────────────────────────────────────┤
│ ⏳ Próxima: Almoço às 12:00        │
│ Sincronizado! 🚀                   │
└─────────────────────────────────────┘
```

### 5. Interações Principais

| Ação | O que faz |
|------|-----------|
| Clique no **checkbox** de refeição | Marca como concluída + registra hora |
| Modifique a **hora** | Muda o horário da refeição |
| Clique em **Passeio** | Marca tarefa diária |
| Aguarde 5 segundos | Dados sincronizam automaticamente ☁️ |

---

## 🎨 Interface Visual

### Estados da Refeição

#### Não Realizada
```
┌─────────────────────────────┐
│ Café da Manhã 100g          │
│ [08:00] ☐                   │ ← Vazio
└─────────────────────────────┘
```

#### Realizada
```
┌─────────────────────────────┐
│ Café da Manhã 100g          │
│ ~~08:00~~ ✅ 08:15          │ ← Concluída
└─────────────────────────────┘
```

### Status Bar (Barra de Status)

| Mensagem | Cor | Significado |
|----------|-----|------------|
| ✅ Rotina concluída! | Verde | Todas as refeições do dia foram registradas |
| 🍖 HORA DE COMER! | Verde | Está na janela de alimentação (±15min) |
| ⏳ Próxima: Almoço às 12:00 | Cinza | Próxima refeição agendada |
| ⚠️ Sem conexão | Vermelho | Sem internet (offline mode) |
| ❌ Erro ao sincronizar | Vermelho | Falha na comunicação com servidor |

---

## 🧪 Executar Testes

1. Abra: `tests.html`
2. Clique em "▶ Executar Todos os Testes"
3. Veja os resultados:

```
✅ 30+ testes passando
📊 Taxa de Sucesso: 100%
⏱️ Tempo de execução: < 1 segundo
```

---

## 🔧 Solução de Problemas

### Problema: "Conectando à nuvem..." fica travado

**Causa**: `PANTRY_ID` incorreto ou sem internet

**Solução**:
```javascript
// Abra Console (F12) e veja logs
// Verifique PANTRY_ID no código
// Tente recarregar a página
```

### Problema: Dados não sincronizam

**Causa**: Conexão lenta ou Pantry Cloud indisponível

**Solução**:
```javascript
// Dados são salvos localmente
// Sincronizarão quando conexão voltar
// Veja "Sincronizado! 🚀" na barra de status
```

### Problema: Refeição marcada desaparece

**Causa**: Outro dispositivo/usuário modificou os dados

**Solução**:
```javascript
// A app puxa os dados do servidor a cada 5 segundos
// Mudanças externas são refletidas automaticamente
// É comportamento esperado em ambiente compartilhado
```

### Problema: Horas mostram errado

**Causa**: Dispositivo com timezone incorreto

**Solução**:
```
Configurações do dispositivo
→ Data e Hora
→ Ajuste seu fuso horário
```

---

## 📱 Mobile Tips

### iOS Safari
- ✅ Funciona perfeitamente
- ✅ Salve como atalho na tela inicial
- ⚠️ Notificações push não disponíveis

### Android Chrome
- ✅ Funciona perfeitamente
- ✅ Instale como Progressive Web App (PWA)
- ✅ Funciona offline com cache

### Orientação
- ✅ Retrato (portrait)
- ✅ Paisagem (landscape)

---

## 🔐 Segurança

### ✅ O que a App Protege
- Validação de datas/horas
- Proteção contra XSS
- Sanitização de nomes de pets
- Timeouts em requisições
- Suporte offline seguro

### ⚠️ Recomendações
- Use em rede confiável
- Não compartilhe `PANTRY_ID`
- Revise dados periodicamente
- Faça backup do JSON

### ❌ O que NÃO protege
- Não substitui backup profissional
- Não criptografa dados em trânsito (use HTTPS)
- Não autentica usuários

---

## 📊 Dados JSON - Estrutura Completa

### Campos Obrigatórios
```json
{
  "activePetId": "string (ID único do pet ativo)",
  "pets": {
    "petId": {
      "petInfo": {
        "name": "string (nome do pet)",
        "birthDate": "YYYY-MM-DD"
      },
      "schedule": {
        "totalGrams": "number (total do dia)",
        "gramsPerMeal": "number (por refeição)",
        "meals": [
          {
            "id": "string (único)",
            "name": "string (Breakfast, Lunch, Dinner)",
            "time": "HH:MM",
            "grams": "number"
          }
        ]
      },
      "gamification": {
        "level": "number (≥1)",
        "xp": "number (≥0)",
        "patacoins": "number (≥0)",
        "dailyTasks": {
          "walk": "boolean",
          "water": "boolean"
        }
      },
      "logs": {
        "YYYY-MM-DD": [
          {
            "id": "string (meal ID)",
            "completedAt": "HH:MM"
          }
        ]
      }
    }
  }
}
```

---

## 🎯 Casos de Uso

### Caso 1: Registrar Refeição Matinal
```
1. Abra a app às 08:00
2. Status bar: "🍖 HORA DE COMER! (08:00)"
3. Clique no checkbox de "Café da Manhã"
4. Hora é registrada automaticamente (08:15)
5. Refeição fica verde ✅
```

### Caso 2: Ajustar Horário da Refeição
```
1. Clique no campo de hora [12:00]
2. Mude para [12:30]
3. Pressione Enter
4. Hora atualizada no cloud
5. Sincronizado! 🚀
```

### Caso 3: Usar Offline
```
1. Feche WiFi
2. Status bar: "⚠️ Sem conexão"
3. Registre refeições normalmente
4. Dados ficam no navegador
5. Reconecte WiFi
6. Sincronização automática
```

---

## 🔄 Sincronização

### Timeline de uma Ação

```
T+0ms   User clica checkbox
        ↓
T+10ms  UI atualiza (feedback imediato)
        ↓
T+100ms debouncedSync() ativado (aguarda 1 seg)
        ↓
T+1000ms sincronizarComBackend() executa
        ↓
T+1100ms Fetch POST → Pantry Cloud
        ↓
T+1500ms Response recebido
        ↓
T+1510ms "✅ Sincronizado!" exibido
        ↓
T+2000ms Próxima poll (carregarDaNuvem) acontece
        ↓
T+2100ms UI refresh com dados confirmados
```

**Total**: ~2 segundos do clique à confirmação

---

## 🌍 Ambientes Suportados

| Navegador | Desktop | Mobile | Status |
|-----------|---------|--------|--------|
| Chrome | ✅ | ✅ | Full support |
| Firefox | ✅ | ✅ | Full support |
| Safari | ✅ | ✅ | Full support |
| Edge | ✅ | - | Full support |
| IE 11 | ❌ | - | Not supported |

---

## 📞 Contato & Suporte

### Reportar Bug
```
Abra uma Issue no GitHub com:
1. O que estava fazendo
2. O que esperava
3. O que aconteceu
4. Logs do Console (F12)
```

### Sugerir Melhoria
```
Abra uma Discussion ou Issue com tag "enhancement"
```

### Documentação Completa
```
Veja: README.md (overview)
      IMPROVEMENTS.md (comparação)
      tests.html (validação)
```

---

## ✅ Checklist de Configuração

- [ ] Baixei `index-improved.html`
- [ ] Criei uma conta em getpantry.cloud
- [ ] Copiei meu `PANTRY_ID`
- [ ] Atualizei o código com meu PANTRY_ID
- [ ] Adicionei meu pet no JSON
- [ ] Testei em desktop
- [ ] Testei em mobile
- [ ] Verificar testes em `tests.html`
- [ ] Bookmarquei a página
- [ ] Compartilhei com a família 🐾

---

## 🎁 Dicas de Ouro

💡 **Tip 1**: Adicione ao homescreen do celular para acesso rápido
```
iOS: Compartilhar → Adicionar à Tela Inicial
Android: Menu → Instalar app
```

💡 **Tip 2**: Use o modo escuro do navegador para noites
```
Safari: Configurações → Aparência → Escuro
Chrome: Configurações → Tema → Escuro
```

💡 **Tip 3**: Revise testes.html regularmente
```
Garante que suas alterações não quebraram nada
Execute antes de fazer grandes mudanças
```

💡 **Tip 4**: Exporte seus dados regularmente
```
F12 → Console → copie fullCloudData
Salve em arquivo de backup
```

---

**Pronto para começar!** 🚀

Abra [index-improved.html](index-improved.html) no seu navegador agora mesmo.

