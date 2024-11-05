DomainScan


Descrição

**DomainScan** é um script em Bash para coleta de informações de rede, voltado para reconhecimento e auditoria de segurança em domínios. Ele realiza a coleta de informações de DNS, força bruta de subdomínios e verificação de portas, além de fornecer detalhes do sistema operacional dos alvos encontrados.

Este script é útil para analistas de segurança e entusiastas de redes que precisam identificar rapidamente a infraestrutura de um domínio e possíveis subdomínios ativos.


## Funcionalidades

- **Consulta de Registros DNS**: Obtém registros A, NS, MX, e TXT do domínio.
- **Força Bruta de Subdomínios**: Verifica subdomínios comuns e registra os encontrados.
- **Verificação de Portas e Sistema Operacional**: Realiza uma varredura nas portas mais comuns (22, 80, 443, 3306, 8080) e tenta identificar o sistema operacional.

## Pré-requisitos

Para usar o script, você precisará das seguintes ferramentas:

- `dig` – para consultas de DNS.
- `nmap` – para verificação de portas e identificação de sistema operacional.


Certifique-se de que esses pacotes estão instalados em sua máquina. Caso não estejam, você pode instalá-los com os seguintes comandos:

```bash
sudo apt-get install dnsutils
sudo apt-get install nmap
```

Uso


Clone o repositório ou faça o download do script.


Dê permissão de execução ao script:

chmod +x DomainScan.sh


Execute o script fornecido o domínio alvo como argumento:

./DomainScan.sh exemplo.com


Estrutura do Relatório


Os resultados serão salvos em um arquivo chamado relatorio_dominio.txtno diretório onde o script for executado. Esse arquivo inclui:

Subdomínios identificados com força bruta.

Registros DNS (A, NS, MX, TXT).

Informações sobre portas abertas e possíveis sistemas operacionais.



Exemplo de Saída

Iniciando coleta para o domínio: exemplo.com

Relatório será salvo em relatorio_dominio.txt


[Registro A]

192.0.2.1

[Registro MX]

10 mail.exemplo.com


sub.exemplo.com - [ENCONTRADO]


[Alvo: sub.exemplo.com]


PORT   STATE SERVICE

22/tcp open  ssh

OS details: Linux 2.6.X


Notas e Considerações

O script foi projetado para ser utilizado em redes autorizadas. Não execute o script em redes ou domínios sem permissão.

Esse script realiza diversas requisições e pode gerar tráfego de rede significativo, dependendo do número de subdomínios selecionados.
