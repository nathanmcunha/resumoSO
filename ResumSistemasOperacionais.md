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
 
