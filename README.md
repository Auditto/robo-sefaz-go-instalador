# Robô Sefaz GO — Instalador

Instalador do **Robô Sefaz GO** da Auditto, que baixa os XMLs das notas das empresas de Goiás e os entrega à Auditto.

> Este repositório publica **somente o instalador**, para download. Ele não contém código-fonte, credenciais nem a lista de empresas.

## Antes de instalar

Você precisa de:

- Windows 10 ou 11, com o **Google Chrome** instalado
- Acesso à rede da Auditto (API e fila)
- Os dois arquivos que a Auditto envia **separadamente** do instalador:
  - `.env` (configuração e credenciais da sua máquina; **não compartilhe**)
  - `allowlist_solutta_go.txt` (lista oficial de empresas)

## Instalar

1. Baixe `RoboSefazGO-Setup-v….exe` na [página de releases](../../releases) e o arquivo `.sha256` que o acompanha.
2. Confira o arquivo no PowerShell (o resultado deve ser igual ao conteúdo do `.sha256`):
   ```powershell
   Get-FileHash .\RoboSefazGO-Setup-v2026.11.05.exe -Algorithm SHA256
   ```
3. Execute o instalador. Como o programa ainda não é assinado digitalmente, o Windows pode mostrar "O Windows protegeu seu computador". Se o hash conferir, use **Mais informações → Executar assim mesmo**.
4. Quando pedir, escolha o `.env` e o `allowlist_solutta_go.txt`.
5. Abra o robô pelo atalho da área de trabalho. Ele abre **parado**: nada acontece até você iniciar.

## Onde ficam os arquivos

| O quê | Onde |
| --- | --- |
| Programa | `C:\Robo Sefaz GO` |
| Dados do robô (XMLs, controle, logs) | `C:\Users\<seu usuário>\Robo Sefaz GO` |

- O `.env` é cifrado na instalação e só abre neste usuário e neste computador. A cópia aberta deve ser apagada.
- Desinstalar ou reinstalar **não apaga** a pasta de dados.

## Verificar a instalação

Execute `RoboSefazGO.exe --verificar` na pasta do programa. Todos os itens devem aparecer como **OK**. O teste não acessa portal, fila, banco nem API.

## Uso

- **Um robô por vez:** não abra o painel em duas máquinas ao mesmo tempo com a mesma configuração.
- Em alguns pedidos o portal exige um captcha; o robô pausa e pede o clique.

## Suporte

Fale com a equipe da Auditto responsável pelo robô.
