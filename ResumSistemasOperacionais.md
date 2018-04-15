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

