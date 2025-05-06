# 🔐 Aplicação Web Segura com Criptografia AES e Proteção CSRF

## 📌 Descrição

Esta aplicação web demonstra como proteger formulários HTML com **criptografia simétrica (AES)** e **tokens CSRF**. O objetivo é garantir confidencialidade e integridade dos dados enviados.

> Desenvolvido com Flask e PyCryptodome.

---

## 🚀 Como Executar

### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/secure-chat-app.git
cd secure-chat-app/app
```

### 2. Instale as dependências

```bash
pip install -r requirements.txt
```

### 3. Execute a aplicação

```bash
python main.py
```

Acesse no navegador:

```
http://127.0.0.1:5000
```

---

## 💡 Funcionalidades

- 🔒 Criptografia simétrica com AES (modo EAX)
- ✅ Proteção contra CSRF com token de sessão
- 📤 Envio seguro de mensagens via formulário
- 🔍 Visualização da mensagem criptografada e original

---

## 🛡️ Testes de Segurança

### 1. Teste CSRF

Simule envio de requisição com token inválido:

```bash
curl -X POST -d "message=teste&csrf_token=token_invalido" http://127.0.0.1:5000/
```

**Resultado esperado:** `CSRF Detectado!` com status `403`.

---

### 2. Teste de Criptografia

Envie uma mensagem no formulário.

**Observe:**
- A versão criptografada (em base64)
- A mensagem original restaurada (após descriptografia)

---

## 📘 Diferenças entre Criptografia Simétrica e Assimétrica

| Criptografia Simétrica | Criptografia Assimétrica     |
|------------------------|------------------------------|
| Uma única chave secreta | Usa duas chaves: pública e privada |
| Mais rápida             | Mais lenta                  |
| Exemplo: AES            | Exemplo: RSA                |
| Boa para dados em tempo real | Boa para troca de chaves   |

---

## ⚠️ Três Ataques Comuns em Aplicações Web

1. **CSRF (Cross-Site Request Forgery)**  
   - Envio de requisições maliciosas autenticadas.
   - ✅ Mitigação: tokens CSRF por sessão (**implementado**).

2. **XSS (Cross-Site Scripting)**  
   - Injeção de scripts via entrada do usuário.
   - ✅ Mitigação: escapar HTML, validar entradas.

3. **SQL Injection**  
   - Inserção de SQL malicioso.
   - ✅ Mitigação: usar ORM ou parâmetros preparados.

---

## 📁 Estrutura de Diretórios

```bash
/app
├── static/                  # Arquivos estáticos (CSS, JS, imagens)
├── templates/
│   └── index.html           # Interface do formulário
├── main.py                  # Aplicação principal (Flask)
├── requirements.txt         # Dependências Python
└── README.md                # Documentação do projeto
```
