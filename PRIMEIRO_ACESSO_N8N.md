# Guia de Primeiro Acesso ao N8N

## 🎯 O que fazer após o deploy

### 1. Acesse o N8N
- **URL:** `https://n8n.hallsync.com.br` (ou a URL que o Coolify gerou)
- Aguarde alguns minutos após o deploy para o N8N inicializar completamente

### 2. Primeiro Acesso - Criação de Conta
Quando acessar pela primeira vez, o N8N vai pedir para você criar uma conta de administrador:

1. **Nome:** Seu nome completo
2. **Email:** Seu email (será usado para login)
3. **Senha:** Crie uma senha forte
4. Clique em **"Create account"**

### 3. Configurações Iniciais Recomendadas

Após criar a conta, configure:

#### Settings → Settings
- **Timezone:** America/Sao_Paulo (já deve estar configurado)
- **Save execution progress:** Ativado (recomendado)
- **Save execution data:** Ativado (para debug)

#### Settings → Community Nodes
- Ative se quiser usar nodes da comunidade

### 4. Testar Conexão com Evolution API

1. Vá em **Credentials** → **Add Credential**
2. Procure por **HTTP Request** ou **REST API**
3. Configure:
   - **URL Base:** `https://evolution.hallsync.com.br`
   - **Authentication:** Header
   - **Header Name:** `apikey`
   - **Header Value:** `EAKestaeraiRo` (sua chave de API)

### 5. Verificar Status dos Serviços

No Coolify, verifique:
- ✅ **Redis:** Deve estar Healthy
- ✅ **PostgreSQL:** Deve estar Healthy  
- ⚠️ **N8N:** Pode mostrar Degraded até você fazer o primeiro login
- ⚠️ **Evolution:** Pode mostrar Degraded até configurar uma instância

## 🔧 Sobre o Status "Degraded"

O status "Degraded" pode aparecer por alguns motivos:

1. **N8N não foi acessado ainda** - Após o primeiro login, o status deve melhorar
2. **Evolution não tem instâncias** - Normal até você criar uma instância do WhatsApp
3. **Healthchecks ainda verificando** - Aguarde alguns minutos

## ✅ Como verificar se está tudo funcionando

1. **N8N:**
   - Acesse a URL do N8N
   - Deve carregar a tela de login/criação de conta
   - Se carregar = ✅ Funcionando

2. **Evolution API:**
   - Acesse: `https://evolution.hallsync.com.br`
   - Deve mostrar a documentação da API
   - Se mostrar = ✅ Funcionando

3. **PostgreSQL:**
   - Verifique no Coolify se está "Healthy"
   - Se estiver = ✅ Funcionando

4. **Redis:**
   - Verifique no Coolify se está "Healthy"
   - Se estiver = ✅ Funcionando

## 🚨 Problemas Comuns

### N8N não carrega
- Aguarde 2-3 minutos após o deploy
- Verifique os logs no Coolify
- Verifique se o PostgreSQL está Healthy

### Evolution não responde
- Verifique se o Redis está Healthy
- Verifique os logs no Coolify
- Aguarde alguns minutos para inicializar

### Status continua Degraded
- Faça o primeiro login no N8N
- Aguarde 5-10 minutos após o primeiro acesso
- Verifique os logs de cada serviço no Coolify

## 📝 Próximos Passos

Após configurar o N8N:
1. Criar workflows de automação
2. Conectar com Evolution API
3. Configurar webhooks
4. Testar automações

