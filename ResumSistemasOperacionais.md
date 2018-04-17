# Resumo de Sistemas Operacionais 

### Interrupções e Exceções 
 * Salvamento de registradores e pilha de controle(stackflow control)	
 * A uma estrutura é onde foca o endereçõ da rotina de tratamento  
 * Exceções estão no software e interrupções no hardware  
 * Processador precisar saber onde está o programa de tratamento 
 * Interrupções e exceçoes são diferentes e depende do tipo de evento ocorrido  
 * Interrupções são geradas por algum evento externo ao programa 

### Modos de acesso do sistemas operacional 
* Garantir integridade do sistema 
* Garantir que as aplicações tenha somente acesso a certas instruções  
* Modos Usuário e Modo Kernel 
	* Modo usuário: aplicação só executa instruções não privilegiadas 
	* Modo Kernel: aplicação tem acesso total as instruções do processador 
	* Intruções privileggiadas não podem ser utilizadas de maneira indiscriminada 
 
### System Calls ou APIs 
  * Funções x System Call 
       
### Processos  
  * PC - Guarda o endereço da proxima instrução a ser executada  
  * Sistemas Multiusuáio cada usuário tem seu programa associado a um process o
  * Partes de um processo
	* Desenho estrutura de um processo 
		<Inserir desenho> 
	* Contexto de hardware 
		* Armazenamento do conteudo dos registradores e os especificos  PC(program counter) , Stack Pointer e registrador de status 
		* Fudamental para implementação de sistemas multiprogramaveis , ondes os processos se alternam a utilização da CPU(UCP), 
		podendo se interrompidos e depois restaurados. O SO gerencia as trocas de contexto , base para implementação de concorrencia 
	* Contexto de software 
		* É onde são impostos os limites e caracteristiscas dos recursos que podem ser alocados , numero maximo  de arquivos que podem ser 
		  abertos  simultaneamente, prioridade de execução  e tamanho do buffer para E/S 
		* Composição do contexto de software: 
			* Identificação-> Cada processo criado recebe um PID, atraves dele  o SO e outros processo podem referenciar e consultar contexto e 
			  alterar caracteristicas.O processso recebe um dono indetificado atravas do UID, atraves do UID é que é implementado modelos de segurança.  
			* Quotas-> Limites que cada recurso pode alocar. Se  uma quota não seja suficiente , o processo e executado lentamente,interrompido durante 
			  durante seu processamento.
				* Numero max de arquivos  
				* Tamanho max de memoria principal e secundaria que o processo pode alocar  
				* Número max de operações pendendetes de E/S				
				* Tamanho max do buffer para operações  de E/S
				* Número max de processos de subprocessos e threads que podem ser criado.
			* Privilegios -> Define as açoes que um processo pode fazer em relação  a ele mesmo e os outros processos  e o SO.
	* Espaço de enderaçamento -> É a área de memória que pertence ao processo onde as instruções e os dados do programa são armazenados.
		
	* Bloco de Controle  de Processo, o famigerado PCB  
		<Inserir Desenho do PCB>												
	* Sinais -> Sinais permite notificar processos de eventos gerados pelo SO ou por outros processos, além de sincronizar e permitir a comunicação entre eles.
	 	* RETOMAR LEITURA 

### Threads 
	* Ambiente MonoThread -> Um processo só suporta apenas um programa no seu espaço de endereçamento, 
		* Aplicações concorrentes nesse tipo de ambiente somente com processos independentes e subprocessos.
		* Como cada processo possui seu proprio espaço de endereçamento , isso dificulta a comunicaçao e se torna muito lenta, pois utiliza-se 
		  pipes, sinais e semaforos e memoria compartilhada ou troca de mensagens.
	* Ambiente MultiThread 
		* Programas associados a threads 
		* Espaço de endereçamento compartilhado com outras threads 
		* Vantagens de multithread é minimizar a alocação de recursos do sistema , além de diminuir o overhead na criação,troca e eliminação de 
		  processos.
		* Dentro de hm mesmo processo as Threads compartilham o mesmo contexto de software e espaço de endereçamento, mas cada thread possui seu proprio  
		   contexto de hardware,e algumas outras informações como estado,prioridade e bits de estado.
		* Grande diferença entre os ambientes monothread é o espaço de endereçamento,essa caracteristica permite que o compartilhamento de dados entre threads
		  de um mesmo processo seja mais simples e rápido se comparado com ambientes monothread.
		* Como threads compartilham o mesmo espaço de endereçamento, não existe proteção no acesso a memoria, ou seja threads do mesmo processo podem alterar
		  dados de outros. 
		* Para que não se tenha problemas e as threads trabalhem de forma cooperativa , é fundamental que seja implementado na aplicação os  
		  mecanismos de comunicação e sincronizção, com a finalidade de garantir acesso seguro aos dados e sua integridade.
		* Facilidade na hora de compartilhar outros recursos.
		* Threds em ambientes cliente servidor-> 
		* Thread modo usuario (TMU)-> 
			* Implementados pela aplicação ou seja o SO não sabe que a aplicação é multithread. 
			* Necessita de uma biblioteca para implementação de sincronização, escalonamento e comunicação entre threads.
			* Pode ser utilizado em sistemas que não suportam multithread.
			* São mais rapidos e eficientes pois não precisam fazer a mudança de modo de acesso, no caso modo-kernel.
			* Desvantagens , caso uma threads esteja esperando um recurso e vai pro estado de wait todo o processo fica travado, mesmo 
			  que tenham threads no estado de pronto.Para contornar esse problema a biblioteca deve possuir rotinas que que substituiam as  	
			  rotinas bloqueantes. 
		* Thread modo kernel (TMK)->
			* São Implementados diretamente pelo kernel do SO , através de chamadas das rotinas do sistema  que oferecem todas as funcoes de  
				gerenciamento e sincronização. O SO sabe da existencia de todas as threads e pode escalona-los de forma individual. 
			* O grande problemas das TMK são seu baixo desempenho , threads TMK fazem as chamadas a rotinas do sistema, consequentemente ocorrem  
			  várias mudanças de acesso 
		* Thread modo hibrido->
			* 
