
---
# CTF 1 - Web Recon / Content Discovery

#nmap #Whatweb #wpscan #dirb  

---
### 1. Reconhecimento de Rede interna e Alvo

Identificação do ambiente e validação de conectividade com o alvo.

```shell
# Identificar IP da máquina de ataque
ifconfig 
  
# Como não foi entregue de cara o escopo, busquei nos arquivos internos e localizei aqui o escopo do CTF (target.ine.local)            
cat /etc/hosts  
   
# Validar conectividade com o alvo, OK.
ping -c 4 192.215.221.3    
```
---
### 2. Enumeração de Serviços e Tecnologias

Descoberta de portas abertas e análise das tecnologias rodando no servidor.

```shell
# Scan de portas(Porta 80 aberta)
nmap -Pn target.ine.local                    

# Identificar CMS e Versão *(FLAG 2 encontrada)*
whatweb target.ine.local          

# Enumeração detalhada de WordPress(Já tinha ideia, pois as aulas deram indicios)
wpscan --url http://target.ine.local -e vp,u 
```

*Aqui, encontrei a FLAG 2 com o comando ``whatweb target.ine.local``*

---
### 3. Descoberta de Diretórios e Arquivos Sensíveis

Exploração da estrutura de pastas e arquivos de configuração.

```shell
# Verificação de regras de indexação *(FLAG 1 encontrada)*
curl http://target.ine.local/robots.txt     

# Brute-force simples de diretórios padrão
dirb http://target.ine.local                

# Exploração de diretório com listagem ativa
dirb http://target.ine.local/wp-content/uploads/ 
```

*Aqui, encontrei a FLAG 1 com o comando ``curl http://target.ine.local/robots.txt``*

---
### 4. Extração de Conteúdo e Flags

Ações específicas para recuperar arquivos e analisar o código-fonte.

```shell
# Flag 3: Encontrada via exploração de diretório de uploads
curl http://target.ine.local/wp-content/uploads/flag.txt
cat flag.txt
```

*Aqui, encontrei a FLAG 3 com os métodos acima*

--

```shell
# Flag 4: Descoberta de backup de configuração

# Busca por extensões de backup
dirb http://target.ine.local -X .bak,.old      

# Leitura de arquivo sensível (FLAG 4)
curl http://target.ine.local/wp-config.php.bak 
```

*Aqui, encontrei a FLAG 4 com os métodos acima*

--

```shell
# Flag 5: Técnica de Mirroring (Espelhamento)

# Clonagem completa do site para análise offline
wget -m http://target.ine.local  

# Busca recursiva por strings de flags no código
grep -ri "FLAG" ~/target.ine.local/
```

---
---
