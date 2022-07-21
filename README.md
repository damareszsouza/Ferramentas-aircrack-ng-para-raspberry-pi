# Ferramentas-aircrack-ng-para-raspberry-pi
Descrição da aula


 
Moodle - IFRS

Raspberry PI e Aplicações - Turma 2022A
Painel Meus cursos  RPIA2022A 3. Vulnerabilidades de Redes Domésticas  3.4 Vídeo Suíte de ferramentas aircrack-ng
3.4 Vídeo Suíte de ferramentas aircrack-ng
Clique aqui para versão em Libras

 Transcrição do vídeo
Vídeo Suíte de ferramentas aircrack-ng
Até o momento, nesta questão de segurança vista no módulo de segurança, foi visto a configuração do roteador e uso do Macchanger e o uso do UFW para criação de regras de firewall, ou seja, apenas medidas de segurança.
O que vai ser visto agora, são algumas ferramentas para efetivar alguns ataques e para visualizar também informações sobre as nossas redes que ficam disponíveis no ar, por incrível que pareça, para acesso de qualquer intruso que tiver por perto.
Nesta apresentação será feito um overview dando uma visão geral das ferramentas que serão usadas na próxima apresentação na prática.
Então vamos iniciar com o switch de ferramentas que é o AirCrack-NG (https://www.aircrack-ng.org/). 
O AirCrack-NG é um switch completo de ferramentas e utilitários para avaliar a segurança de redes Wifi.
Então ele é composto por uma série de outras ferramentas e utilitários e vamos ver 3 deles nesta apresentação. 
Com o AirCrack-NG é possível monitorar a rede, capturar pacotes e exportar os dados para arquivos de texto. É possível fazer ataques de desautenticação.
É possível fazer testes para verificar a capacidade dos drivers e é possível fazer Cracking que é descobrir as chaves e senhas utilizadas na rede.
Todas as linhas são de linha de comando.
Vamos começar o AiroDump (https://www.aircrack-ng.org/doku.php?id=airtun-ng) que é usado para captura de pacotes. Aqui tenho sobre o uso do AiroDump , opções, interface que será monitorada, documentações, opções de filtro e etc. Agora, o que nos interessa no momento é isso aqui (professor salienta uma parte da página de manual do AiroDump através do link acima), a saída do AiroDump . 
Ao rodar o AiroDump -NG eu tenho esta saída aqui que é uma listagem de todas as redes disponíveis que estão sendo vistas por essa máquina que está rodando o AiroDump -NG. 
Aqui no caso, o site mostra como exemplo, 3 redes sendo visualizadas onde as 3 redes estão no raio de ação da máquina e informações onde cada coluna disponibiliza uma informação sobre aquela rede em particular. Exemplo: nome do ponto de acesso, a autenticação, se usa senha wep, wpa, o canal que está sendo utilizado e uma série de outras informações e aqui em baixo, na documentação, têm todos os campos com as respectivas informações. 
Eu não falei, mas assim como a Wiringpi tem a sua página específica o www.aircrack-ng.org.
Depois dessa primeira listagem dos pontos de acesso no raio de ação tem esta segunda listagem fornecida pelo AiroDump onde para cada ponto de acesso, vamos pegar aqui como exemplo esse o 00:14:6c:7a:41:81 que é o bigbear tem, no momento, nesta listagem aqui uma estação, duas estações, três estações conectadas ao bigbear. Desculpe, existem duas conectadas ao bigbear e uma conectada ao tedy. Este número aqui (professor aponta para o endereço mac do ponto de acesso na lista fornecida pelo programa) é o endereço mac de uma interface de rede. Tem o endereço IP na camada de rede sendo de 32 bits ou 128 bits no IPv6 e tem o endereço mac de 48 bits que é um endereço de camada de enlace sendo a camada abaixo da camada de rede. 
E aí temos outras informações nas colunas sobre cada uma das estações que estão conectadas como número de pacotes trafegados, número de pacotes perdidos e novamente a explicação de cada campo está aqui na documentação.
Então, este é o resultado (professor aponta para a parte no site que mostra um exemplo de saída do AiroDump), a saída do nosso AiroDump que é uma das ferramentas do Crack-NG e que é usada para captura de pacotes. 
Na prática, quando utilizarmos, para não ser invasivo, irei selecionar pelas opções do comando apenas estações ao ponto de acesso que estou usando para preparar o material. 
E para que serve o AiroDump?
Serve para, por exemplo, um endereço MAC de uma estação e fazer um ataque a esta estação para retirá-la da rede.
Depois, uma outra ferramenta do AirCrack é o Airmon-ng (https://www.aircrack-ng.org/doku.php?id=airmon-ng). Este é um script que é usado para habilitar o módulo monitor. Para rodar o AiroDump preciso colocar a interface em modo monitor.
O modo default é management que é gerenciado e aí eu não consigo obter as informações neste modo. Preciso colocar em modo monitor.
Em algumas máquinas não há a necessidade de eu rodar o Airmon. Rodo o AiroDump e ele já sai fornecendo as informações. Em outras máquinas preciso executar este comando “airmon-ng check kill” antes de rodar o AiroDump se não ele não mostra nem uma informação de rede e estações, que é o caso desta máquina na qual estou trabalhando no momento. 
E a terceira ferramenta é o Aireplay (https://www.aircrack-ng.org/doku.php?id=aireplay-ng) que é usada para criar tráfego para posteriormente utilizar para crackear as senhas WPA ou WEP mas ele permite fazer diferentes ataques como, por exemplo, ataque de desautenticação que é o que faremos.
Temos aqui (professor aponta para trecho do manual disponível no site) o uso do Airplay, opções e a interface que será utilizada. Aqui como exemplo, qual o access point será  atacado.
Desculpe, eu tenho feito nos access points utilizando o -a junto ao comando e com o -c para especificar o endereço MAC do cliente que será atacado.
Vamos ver se tem mais alguma informação importante aqui na documentação. 
Tem mais uma informação que eu gostaria de passar que é… aqui, quando se faz um ataque de desautenticação, se coloca dois números logo após o comando onde o primeiro identifica se vai desautenticar todas as estações ou apenas uma e aqui o count é o número de pacotes de desautenticação que serão enviados. Vamos utilizar com o -0 nesta opção aqui (professor aponta para a linha do manual  “--deaulth count : deauthenticate 1 or all stations -0”.
Bom então, uma visão geral do que é o Aircrack-NG que é uma Switch tools para monitorar, atacar, testar e crackear redes wifi e depois uma visão geral de 3 destas ferramentas da switch o Airodump, Airmon que é um script e o Airplay. 
Airodump para visualizar informações da rede, Airplay para efetivar ataques e Airmon que é um script para colocar a interface de rede em modo monitor.
Na sequência, faremos uso destas ferramentas na prática. 
