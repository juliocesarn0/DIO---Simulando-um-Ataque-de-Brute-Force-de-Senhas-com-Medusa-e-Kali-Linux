# 🔐 Projeto: Simulação de Ataques de Força Bruta com Kali Linux e Medusa

## 📌 Descrição

Este projeto tem como objetivo simular ataques de força bruta em um ambiente controlado utilizando o **Kali Linux** e a ferramenta **Medusa**, explorando serviços vulneráveis em máquinas como o **Metasploitable 2** e aplicações web como o **DVWA (Damn Vulnerable Web Application)**.

A proposta é aplicar conceitos de segurança ofensiva (pentest) e, ao mesmo tempo, compreender medidas de defesa e mitigação.

---

## 🎯 Objetivos de Aprendizagem

* Compreender ataques de força bruta em diferentes serviços (FTP, Web, SMB)
* Utilizar ferramentas como Medusa, Nmap e smbclient
* Criar e utilizar wordlists
* Documentar processos técnicos de forma clara
* Identificar vulnerabilidades e sugerir mitigação

---

## 🧪 Ambiente do Laboratório

### 🖥️ Máquinas Virtuais

* **Kali Linux** (Atacante)
* **Metasploitable 2** (Alvo)
* **DVWA** (Aplicação web vulnerável)

### 🌐 Configuração de Rede

* VirtualBox
* Modo: `Host-Only`
* Comunicação isolada entre as VMs

---

## 🛠️ Ferramentas Utilizadas

* Medusa
* Nmap
* Hydra (opcional)
* smbclient
* Wordlists customizadas

---

## 🔎 Etapas do Projeto

### 1️⃣ Enumeração de Serviços

Utilizando o Nmap para identificar serviços ativos:

```bash
nmap -sV <IP_DO_ALVO>
```

---

### 2️⃣ Ataque de Força Bruta em FTP

```bash
medusa -h <IP> -u <usuario> -P wordlist.txt -M ftp
```

📌 Objetivo:

* Descobrir credenciais válidas via brute force

---

### 3️⃣ Ataque em Aplicação Web (DVWA)

Simulação de tentativas automatizadas de login:

* Uso de listas de usuários e senhas
* Testes em formulários vulneráveis

📌 Possível abordagem:

* Burp Suite ou scripts automatizados
* Ajuste do nível de segurança do DVWA para "low"

---

### 4️⃣ Password Spraying em SMB

#### 🔍 Enumeração de usuários

```bash
enum4linux <IP>
```

#### 🔐 Teste de acesso com Medusa

```bash
medusa -h <IP> -U usuarios.txt -p senha123 -M smbnt
```

📌 Objetivo:

* Testar uma senha comum em múltiplos usuários

---

### 5️⃣ Testando Acesso com smbclient

```bash
smbclient -L //<IP> -U <usuario>
```

---

## 🔑 Criação de Wordlists

Exemplo simples:

**usuarios.txt**

```
admin
user
test
msfadmin
```

**senhas.txt**

```
123456
password
admin
12345
msfadmin
```

---

## 📊 Resultados Obtidos

* Credenciais válidas encontradas em serviços vulneráveis
* Acesso autorizado a serviços como FTP e SMB
* Demonstração prática de falhas de segurança comuns

---

## 🛡️ Medidas de Mitigação

* 🔒 Uso de senhas fortes e complexas
* 🚫 Bloqueio após múltiplas tentativas de login
* 🔐 Implementação de MFA (autenticação multifator)
* 📉 Limitação de taxa (rate limiting)
* 🔍 Monitoramento de logs e alertas
* 🔄 Alteração de portas e hardening de serviços

---

## ⚠️ Aviso Importante

Este projeto foi realizado **exclusivamente em ambiente controlado e autorizado**, com fins educacionais.

🚨 **Nunca execute esses testes em sistemas reais sem permissão!**

---

## 🚀 Conclusão

Este desafio permitiu aplicar conceitos fundamentais de segurança ofensiva e entender na prática como ataques de força bruta funcionam — além de reforçar a importância de boas práticas de segurança.

---

## 📚 Referências

* Documentação do Kali Linux
* Medusa Tool Docs
* DVWA Project
* Nmap Manual
