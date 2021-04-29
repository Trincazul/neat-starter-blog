---
title: Introdução do escaneamento de porta com a ferramenta Nmap
description: Uma breve intodrução de como faz a instalação da ferramenta e o
  primeiro funcionamento dela, e como fazer sua utilização.
author: Endriw Villa
date: 2021-04-29T16:34:47.629Z
tags:
  - Tags
---
# Nmap

Com início a introdução sobre escaneamento com porta no Nmap, teremos que ter pelo menos um conhecimento básico de como funciona os serviços na ‘internet’ (endereço de IP, e serviços de porta), vamos aprender como funciona o escaneamento e o que está acontecendo.

Nmap é um programa muito conhecido no mundo todo sobre escaneamento de portas e também um programa muito popular entre profissionais de segurança, ele pode fazer uma varredura de dispositivos na rede e também em servidores fora da rede de acesso, fora da barreira de segurança.

## Qual sistema utilizar com Nmap ?

Você pode utilizar o programa normalmente em um sistema Windows, entretanto, geralmente pode funcionar melhor e muito mais rápido em um Linux, e também é a categoria de sistema que eu utilizo o Nmap.

Ter uma experiência em Linux também é muito bom, já que o Linux proporciona uma seleção muito ampla de ferramentas de segurança.

Os exemplos das etapas de instalação nesse tutorial são para sistema baseados em Linux Ubuntu, porem pode ser feita pequenas alterações com outras categorias de Linux, como o Fedora que eu particularmente recomendo muito também.

Caso você não utilize o Linux como seu sistema operacional principal, você pode também fazer uma instalação de uma máquina virtual e instalar um Linux, nele você pode fazer os testes e aprender sobre o Linux.

## Instalação do Nmap no Ubuntu

Na página de download do site oficial do Nmap [https://nmap.org/download.html](https://nmap.org/download.html) você pode obter a versão mais estável ou em desenvolvimento, sugiro que selecione a versão stable('estável'), a versão de desenvolvimento pode ocasionar alguns problemas.

Para obter a última versão pode utilizar o terminal para fazer o download.

Abra o terminal do Linux e digite o seguinte comando:

```bash
wget http://nmap.org/dist/nmap-5.61TEST5.tar.bz2
```

Agora é só esperar ser feito o download do arquivo onde o caminho do terminal se encontra.

Você pode precisar instalar o g ++ para compilar o arquivo. Você também deve instalar o pacote libssl-dev, com ele permitira que os scripts NSE de teste SSL funcionem.

 

```bash
sudo apt-get install g++
```

Agora descompacte o arquivo, compile e instale. Utilize a configuração padrão e utiliza os comandos.

```bash
tar jxvf nmap-5.61TEST5.tar.bz2
cd nmap-5.61TEST5/
./configure
make
make install
```

Execute o comando nmap para mostrar as opções disponíveis do programa, se a instalação foi bem sucedida vai aparecer opções de comandos, como no exemplo a baixo.

```bash
endriw@ubuntu8:/~$nmap

Nmap 5.61TEST5 ( https://nmap.org )
Usage: nmap [Scan Type(s)] [Options] {target specification}
TARGET SPECIFICATION:
  Can pass hostnames, IP addresses, networks, etc.
  Ex: scanme.nmap.org, microsoft.com/24, 192.168.0.1; 10.0.0-255.1-254
  -iL : Input from list of hosts/networks
  -iR : Choose random targets
  --exclude : Exclude hosts/networks
  --excludefile : Exclude list from file
HOST DISCOVERY:
  -sL: List Scan - simply list targets to scan
  -sn: Ping Scan - disable port scan
  -Pn: Treat all hosts as online -- skip host discovery
  -PS/PA/PU/PY[portlist]: TCP SYN/ACK, UDP or SCTP discovery to given ports
  -PE/PP/PM: ICMP echo, timestamp, and netmask request discovery probes
  -PO[protocol list]: IP Protocol Ping
  -n/-R: Never do DNS resolution/Always resolve [default: sometimes]
  --dns-servers : Specify custom DNS servers
  --system-dns: Use OS's DNS resolver
  --traceroute: Trace hop path to each host
SCAN TECHNIQUES:
  -sS/sT/sA/sW/sM: TCP SYN/Connect()/ACK/Window/Maimon scans
  -sU: UDP Scan
  -sN/sF/sX: TCP Null, FIN, and Xmas scans
  --scanflags : Customize TCP scan flags
  -sI : Idle scan
  -sY/sZ: SCTP INIT/COOKIE-ECHO scans
  -sO: IP protocol scan
  -b : FTP bounce scan
PORT SPECIFICATION AND SCAN ORDER:
  -p : Only scan specified ports
    Ex: -p22; -p1-65535; -p U:53,111,137,T:21-25,80,139,8080,S:9
  -F: Fast mode - Scan fewer ports than the default scan
  -r: Scan ports consecutively - don't randomize
  --top-ports : Scan  most common ports
  --port-ratio : Scan ports more common than 
SERVICE/VERSION DETECTION:
  -sV: Probe open ports to determine service/version info
  --version-intensity : Set from 0 (light) to 9 (try all probes)
  --version-light: Limit to most likely probes (intensity 2)
  --version-all: Try every single probe (intensity 9)
  --version-trace: Show detailed version scan activity (for debugging)
SCRIPT SCAN:
  -sC: equivalent to --script=default
  --script=:  is a comma separated list of
           directories, script-files or script-categories
  --script-args=: provide arguments to scripts
  --script-args-file=filename: provide NSE script args in a file
  --script-trace: Show all data sent and received
  --script-updatedb: Update the script database.
  --script-help=: Show help about scripts.
            is a comma separted list of script-files or
           script-categories.
OS DETECTION:
  -O: Enable OS detection
  --osscan-limit: Limit OS detection to promising targets
  --osscan-guess: Guess OS more aggressively
TIMING AND PERFORMANCE:
  Options which take  are in seconds, or append 'ms' (milliseconds),
  's' (seconds), 'm' (minutes), or 'h' (hours) to the value (e.g. 30m).
  -T<0-5>: Set timing template (higher is faster)
  --min-hostgroup/max-hostgroup : Parallel host scan group sizes
  --min-parallelism/max-parallelism : Probe parallelization
  --min-rtt-timeout/max-rtt-timeout/initial-rtt-timeout : Specifies
      probe round trip time.
  --max-retries : Caps number of port scan probe retransmissions.
  --host-timeout : Give up on target after this long
  --scan-delay/--max-scan-delay : Adjust delay between probes
  --min-rate : Send packets no slower than  per second
  --max-rate : Send packets no faster than  per second
FIREWALL/IDS EVASION AND SPOOFING:
  -f; --mtu : fragment packets (optionally w/given MTU)
  -D : Cloak a scan with decoys
  -S : Spoof source address
  -e : Use specified interface
  -g/--source-port : Use given port number
  --data-length : Append random data to sent packets
  --ip-options : Send packets with specified ip options
  --ttl : Set IP time-to-live field
  --spoof-mac : Spoof your MAC address
  --badsum: Send packets with a bogus TCP/UDP/SCTP checksum
OUTPUT:
  -oN/-oX/-oS/-oG : Output scan in normal, XML, s|: Output in the three major formats at once
  -v: Increase verbosity level (use -vv or more for greater effect)
  -d: Increase debugging level (use -dd or more for greater effect)
  --reason: Display the reason a port is in a particular state
  --open: Only show open (or possibly open) ports
  --packet-trace: Show all packets sent and received
  --iflist: Print host interfaces and routes (for debugging)
  --log-errors: Log errors/warnings to the normal-format output file
  --append-output: Append to rather than clobber specified output files
  --resume : Resume an aborted scan
  --stylesheet : XSL stylesheet to transform XML output to HTML
  --webxml: Reference stylesheet from Nmap.Org for more portable XML
  --no-stylesheet: Prevent associating of XSL stylesheet w/XML output
MISC:
  -6: Enable IPv6 scanning
  -A: Enable OS detection, version detection, script scanning, and traceroute
  --datadir : Specify custom Nmap data file location
  --send-eth/--send-ip: Send using raw ethernet frames or IP packets
  --privileged: Assume that the user is fully privileged
  --unprivileged: Assume the user lacks raw socket privileges
  -V: Print version number
  -h: Print this help summary page.
EXAMPLES:
  nmap -v -A scanme.nmap.org
  nmap -v -sn 192.168.0.0/16 10.0.0.0/8
  nmap -v -iR 10000 -Pn -p 80
SEE THE MAN PAGE (https://nmap.org/book/man.html) FOR MORE OPTIONS AND EXAMPLES
```

Agora você tem uma lista de várias opções disponíveis para utilizar. Comece com o básico e passe para o teste de diferentes opções de varredura e scripts NSE. Vamos seguir.

Como você pode perceber, existem muitas variações na varredura de portas que podem ser feitas com o Nmap.

## Começando com comandos no Nmap

Esse é um simples comando para escanear a rede local da sua internet.

```bash
nmap -sV -p 1-65535 192.168.1.1/24
```

Este comando irá varrer todo o seu intervalo de IP local, digamos que você está no intervalo de IP de  192.168.1.0-254, e ira realizar a identificação do serviço -sV vai varrer todas as portas -p 1-65535. Como você está executando isso como um usuário normal, e não como root(administrador), vai ser uma varredura TCP Connect. Se você executar o comando com sudo na frente, ele vai ser executado como uma varredura TCP SYN.

## Open, Closed and Filtered

O Nmap possui uma variedade muito grande de categorias de varreduras, saber como funciona uma varredura SYN padrão é mais comum e é um ótimo lugar para examinar e verificar como a varredura funciona e interpreta os resultados.

## Zenmap, é a versão com interface gráfica do Nmap

Inicie o zenmap pela linha de comando ou pelo menu do sistema. Está é uma opção com interface gráfica GUI do Nmap, eu particularmente já realizei teste na interface gráfica e funciona perfeitamente, porem com a linha de comando você consegue criar scripts, e também ter uma ideia muito boa do que realmente está acontecendo. 

Um recurso interessante do zenmap é o mapa gráfico das redes escaneadas, isso pode ser muito bom para a visualização de todo o processo de mapeamento.

Futuramente meu próximo post vai ser a explicação de protocolo TCP.

Até a próxima.