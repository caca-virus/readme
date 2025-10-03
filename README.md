# Caça-Vírus — TestRansom (MVP acadêmico)

**85% de armazenamento usado** — Aproveite 30 GB de armazenamento por **R$ 4,50 → R$ 1 por mês, durante 3 meses**.  

---

## Visão geral
**TestRansom** é um *MVP* (Produto Mínimo Viável) de um **minifiltro (file system filter driver)** para Windows, desenvolvido em ambiente acadêmico e controlado. O propósito deste projeto é **simular** um mecanismo de detecção e bloqueio de comportamentos típicos de ransomware — apenas para fins de estudo, pesquisa e ensino.

> ⚠️ **Aviso importante**  
> Este projeto é **educacional**. **Não** deve ser usado em produção, em computadores pessoais ou em redes de produção. Execute **apenas** em máquinas virtuais ou ambientes de teste isolados.

---

## Estrutura do repositório
- `TestRansom.c` — Código-fonte principal do minifiltro.  
- `TestRansom.inf` — Arquivo de instalação do driver (usado com `pnputil`).  
- `TestRansom.sys` — Binário do driver gerado após compilação.  
- `Makefile` / arquivos de projeto — Auxiliares para compilação.  
- `README.md` — Este guia de instalação e uso.

---

## Pré-requisitos
- Windows 10 ou 11 (64 bits) — ambiente de testes.  
- Visual Studio 2019 (ou superior) com **Windows Driver Kit (WDK)** instalado.  
- Conta com **permissão de administrador** para instalar/carregar drivers.  
- Modo de Teste habilitado no Windows (driver não assinado para produção).

> **Recomendação:** use sempre uma **máquina virtual** (Hyper-V, VirtualBox, VMware) com snapshots para restaurar rapidamente.

---

## Instalação — passo a passo

### 1. Clonar o repositório
```bash
git clone https://github.com/SisteRansom/Ransom_.git
cd Ransom_/TestRansom
