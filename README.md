# C115 - Trabalho de Aprendizado com Mininet
Este repositório contém o trabalho prático desenvolvido na disciplina C115 com foco em simulação de redes utilizando o Mininet. O objetivo é realizar testes de desempenho, largura de banda e conectividade em diferentes topologias de rede.

## Objetivo
O trabalho explora a criação e o teste de topologias de rede no Mininet, configurando hosts e switches para realizar testes de largura de banda e conectividade TCP usando ferramentas como iperf. O objetivo é aplicar conceitos de redes de computadores na prática.

## Topologia Utilizada
A topologia utilizada foi uma topologia em árvore com os seguintes parâmetros:

+ Profundidade: 4
+ Fanout: 2 (cada nó se ramifica em 2 nós filhos)
+ Largura de banda: 25 Mbps
+ Endereços MAC padronizados para os hosts e switches

### Comando para criação da topologia:
```
sudo mn --topo tree,depth=4,fanout=2 --mac --link=tc,bw=25
```
#### Saída obtida:
![Simulação parte 1](simulacao_parte1.png)

## Inspecionando Interfaces, Endereços MAC, IP e Portas
Após a criação da topologia, foi possível inspecionar as interfaces de rede, endereços MAC e IP dos hosts e switches, utilizando os seguintes comandos:

### 1. Listar todos os nós:
![Simulação parte 2](simulacao_parte2.png)

### 2. Exibir interfaces de rede do host h1:
![Simulação parte 3](simulacao_parte3.png)

### 3. Exibir informações das interfaces do switch s1:
![Simulação parte 4](simulacao_parte4.png)
![Simulação parte 5](simulacao_parte5.png)
![Simulação parte 6](simulacao_parte6.png)
![Simulação parte 7](simulacao_parte7.png)
![Simulação parte 8](simulacao_parte8.png)
![Simulação parte 9](simulacao_parte9.png)
![Simulação parte 10](simulacao_parte10.png)

### 4. Verificar as portas e mapeamentos dos hosts e switches:
![Simulação parte 11](simulacao_parte11.png)

## Testes Realizados
Foram realizados os seguintes testes:

### Teste de Ping
Para verificar a conectividade entre diferentes nós na topologia, foram realizados testes de ping entre os hosts:

#### h1 e h2:
![Simulação parte 12](simulacao_parte12.png)

#### h1 e h3:
![Simulação parte 13](simulacao_parte13.png)

#### h2 e h3:
![Simulação parte 14](simulacao_parte14.png)

#### pingall:
![Simulação parte 15](simulacao_parte15.png)

### Teste de Largura de Banda com Iperf
Os testes de largura de banda TCP foram realizados entre o host 1 (servidor) e o host 2 (cliente) usando a ferramenta iperf.

#### Servidor TCP no host 1 (porta 5555):
![Simulação parte 16](simulacao_parte16.png)

#### Cliente TCP no host 2, enviando dados por 10 segundos, com relatórios a cada 1 segundo e largura de banda de 25 Mbps:
![Simulação parte 17](simulacao_parte17.png)

Para uma visualização clara dos resultados de desempenho, foi gerado um gráfico utilizando o Gnuplot, que exibe o throughput (largura de banda) em Mbps a cada segundo durante o teste de 10 segundos.

#### Gráfico de Desempenho do Cliente TCP:
![Simulação parte 18](simulacao_parte18.png)

Este gráfico mostra a variação da largura de banda ao longo do tempo durante o teste, oferecendo uma visão detalhada da performance da comunicação TCP entre os hosts.

## Como Executar
1. Instale o Mininet em sua máquina se ainda não estiver instalado.
2. Execute a topologia fornecida no Mininet.
3. Realize os testes de ping entre os hosts e teste de largura de banda conforme os comandos descritos acima.

## Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um pull request para melhorias e ajustes.

## Licença
Este projeto está licenciado sob a MIT License.
