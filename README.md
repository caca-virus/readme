85% de armazenamento usado … Se você atingir o limite, não será possível criar, editar ou fazer upload de arquivos. Aproveite 30 GB de armazenamento por R$ 4,50 R$ 1 por mês, durante 3 meses.
﻿Este projeto é um **MVP (Minimum Viable Product)** de um driver **minifilter** para Windows, desenvolvido em ambiente acadêmico e controlado, com o objetivo de simular um mecanismo de detecção e bloqueio de comportamentos típicos de ransomware.  


⚠️ **Aviso Importante**:  
Este projeto é **estritamente educacional**. Não deve ser utilizado em produção ou em sistemas pessoais.  


---


## 📂 Estrutura da Pasta


- **TestRansom.c** → Código-fonte principal do driver (minifilter).  
- **TestRansom.inf** → Arquivo de instalação do driver (usado com `pnputil`).  
- **TestRansom.sys** → Binário do driver gerado após a compilação.  
- **Makefile / arquivos de projeto** → Arquivos auxiliares para compilação.  
- **README.md** → Este guia de instalação e uso.  


---


## 🔧 Pré-requisitos


1. **Windows 10 ou 11 (64 bits)** em ambiente de testes.  
2. **Visual Studio (2019 ou superior)** com o pacote **Windows Driver Kit (WDK)** instalado.  
3. Permissão de administrador para instalar e carregar drivers.  
4. **Modo de Teste habilitado** (se não houver certificado digital para assinar o driver).  


---


## 🚀 Passo a Passo de Instalação


### 1. Clonar o repositório
```powershell
git clone https://github.com/SisteRansom/Ransom_.git
cd Ransom_/TestRansom


2. Compilar o driver
Abra o Developer Command Prompt for VS (ou WDK) e execute:
msbuild TestRansom.vcxproj /t:Build /p:Configuration=Release /p:Platform=x64


➡️ Isso irá gerar o arquivo TestRansom.sys na pasta x64\Release\.


3. Instalar o driver
Instale o driver pelo arquivo .inf:
pnputil /add-driver TestRansom.inf /install


✅ Isso registra e instala o driver no Windows.


4. Verificar se o minifilter foi carregado
No Prompt de Comando (Admin):
fltmc filters


Você deverá ver o filtro TestRansom listado na saída.


5. Remover/Desinstalar o driver (quando necessário)
pnputil /delete-driver TestRansom.inf /uninstall /force




📌 Observações
O driver foi feito apenas como prova de conceito para estudo.


Alertas sobre assinatura digital são esperados em drivers não certificados.


Execute sempre em máquina virtual ou ambiente de testes controlado.
