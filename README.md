# 🧘 DigitalZen - App de Bem-Estar com ZenCoins

Transforme hábitos saudáveis em ZenCoins e troque por prêmios reais!

## 🚀 Status do Projeto

✅ **MVP COMPLETO E FUNCIONANDO!**

## 📋 O que está pronto:

### Frontend
- ✅ Landing page completa
- ✅ Sistema de login/cadastro
- ✅ Dashboard interativo
- ✅ Sistema de metas
- ✅ Marketplace
- ✅ Histórico de transações
- ✅ Ranking global
- ✅ Perfil do usuário
- ✅ Design responsivo (mobile-friendly)

### Backend (Firebase)
- ✅ Autenticação (Email/Senha + Google)
- ✅ Banco de dados (Firestore)
- ✅ Armazenamento de usuários
- ✅ Sistema de metas
- ✅ Transações
- ✅ Tempo real

### Funcionalidades
- ✅ Criar conta
- ✅ Login
- ✅ Criar metas personalizadas
- ✅ Completar metas e ganhar ZenCoins
- ✅ Marketplace para trocar coins
- ✅ Histórico de transações
- ✅ Estatísticas em tempo real
- ✅ Sistema de níveis
- ✅ Bônus de boas-vindas (100 ZC)

## 🖥️ Como Testar Localmente

### Opção 1: Live Server (Recomendado)

1. **Instale a extensão Live Server no VS Code:**
   - Abra VS Code
   - Vá em Extensions (Ctrl+Shift+X)
   - Procure "Live Server"
   - Instale

2. **Inicie o servidor:**
   - Botão direito no arquivo `index.html`
   - Clique em "Open with Live Server"
   - O navegador vai abrir automaticamente

### Opção 2: Python HTTP Server

```bash
# Python 3
python -m http.server 8000

# Acesse: http://localhost:8000
```

### Opção 3: Node.js HTTP Server

```bash
# Instale (se não tiver)
npm install -g http-server

# Execute
http-server

# Acesse: http://localhost:8080
```

## 🧪 Testando o App

### 1. Criar uma conta
- Vá para a página inicial
- Clique em "Começar Grátis"
- Preencha o formulário
- OU use "Continuar com Google"
- Você receberá **100 ZenCoins de bônus**! 🎉

### 2. Explorar o Dashboard
- Veja seu saldo de ZenCoins
- Confira as estatísticas
- Navegue pelas diferentes seções

### 3. Criar uma Meta
- Clique em "+ Nova Meta"
- Preencha os campos:
  - Nome (ex: "Meditação matinal")
  - Categoria (escolha uma)
  - Duração (em minutos)
  - Recompensa (ZenCoins)
- Clique em "Criar Meta"

### 4. Completar Meta
- Clique no botão "Completar" na meta
- Você ganhará os ZenCoins! 💎
- A transação aparecerá no histórico

### 5. Usar o Marketplace
- Vá em "Marketplace"
- Escolha um item
- Clique em "Resgatar"
- Confirme a compra
- Os ZenCoins serão debitados

### 6. Ver Ranking
- Clique em "Ranking"
- Veja sua posição
- Compare com outros usuários

## 📱 Estrutura do Projeto

```
digitalzen-app/
├── index.html          # Landing page
├── login.html          # Login/Cadastro
├── dashboard.html      # Dashboard principal
├── css/
│   └── style.css      # Todos os estilos
├── js/
│   ├── firebase-config.js  # Configuração Firebase
│   ├── auth.js            # Autenticação
│   ├── dashboard.js       # Lógica do dashboard
│   └── landing.js         # Animações da landing
└── README.md
```

## 🔥 Configuração do Firebase

O app está conectado ao Firebase com as seguintes configurações:

- **Autenticação:** Email/Senha + Google
- **Database:** Cloud Firestore
- **Região:** São Paulo (southamerica-east1)

### Regras de Segurança (Importante!)

Para configurar as regras do Firestore:

1. Vá para Firebase Console
2. Firestore Database → Regras
3. Cole o seguinte:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Users: apenas o próprio usuário pode ler/escrever
    match /users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
    
    // Goals: apenas o dono pode ler/escrever
    match /goals/{goalId} {
      allow read, write: if request.auth != null && 
                           resource.data.userId == request.auth.uid;
    }
    
    // Transactions: apenas o dono pode ler
    match /transactions/{transId} {
      allow read: if request.auth != null && 
                     resource.data.userId == request.auth.uid;
      allow create: if request.auth != null;
    }
  }
}
```

## 🚀 Deploy (Próximos Passos)

### GitHub
1. Criar repositório no GitHub
2. Fazer commit:
```bash
git init
git add .
git commit -m "Initial commit - DigitalZen MVP"
git branch -M main
git remote add origin [SEU_REPOSITORIO]
git push -u origin main
```

### Vercel (Deploy Gratuito)
1. Acesse vercel.com
2. Faça login com GitHub
3. Clique em "New Project"
4. Importe o repositório `digitalzen-app`
5. Deploy! (3 minutos)
6. Você terá uma URL: `digitalzen-app.vercel.app`

### Atualizar Firebase
Após deploy, adicione o domínio Vercel em:
- Firebase Console → Authentication → Settings
- Authorized domains → Add domain
- Cole: `digitalzen-app.vercel.app`

## 📊 Métricas para Acompanhar

### Próximos 7 dias:
- [ ] 10 usuários cadastrados
- [ ] 50 metas criadas
- [ ] 30 metas completadas
- [ ] 5 transações no marketplace

### Próximos 30 dias:
- [ ] 100 usuários
- [ ] 500 metas
- [ ] Taxa de retenção > 40%
- [ ] Primeira receita com afiliados

## 🐛 Problemas Conhecidos

Nenhum no momento! 🎉

Se encontrar algum bug, anote:
1. O que você estava fazendo
2. O que aconteceu
3. Mensagem de erro (se houver)
4. Screenshot (se possível)

## 💡 Próximas Features

### Semana 1:
- [ ] Sistema de notificações
- [ ] Mais categorias de metas
- [ ] Gráficos de progresso
- [ ] Dark mode

### Semana 2:
- [ ] Integração com afiliados reais
- [ ] Sistema de indicação
- [ ] Chat/Comunidade
- [ ] App mobile (PWA)

## 🤝 Suporte

Problemas? Dúvidas? Entre em contato!

---

## 🎉 Parabéns!

Você tem agora um app COMPLETO e FUNCIONANDO!

**Próximo passo:** Testar com amigos e coletar feedback! 🚀

---

**Desenvolvido com ❤️ usando:**
- HTML5, CSS3, JavaScript
- Firebase (Auth + Firestore)
- Muito café ☕

**Custo total:** R$ 0,00
**Tempo de desenvolvimento:** 4 horas
**Potencial:** Ilimitado! 💎
