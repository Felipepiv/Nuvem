# Parte A: Entendendo a barreira do sistema

quando o processo está executando uma aplicação, ela contem restrições para proteger o sistema. Para que o processo acesse recursos criticos do sistema, ele solicita uma system call que indica o serviço especifico que aquela aplicação requer do kernel. As instruções da system call possuem proteções de memória que as tornam imutáveis ou ílegiveis para programas em modo usuário. Após esse processo das system call, a CPU é reiniciada e retorna ao modo de usuário.

# Parte b: Diagnosticando o Escalonador

O algoritimo FCFS está causando o "congelamento" da interface porque ele processa as requisições estritamente na ordem de chegada, sem interrupções. Se um processo longo ou pesado entra na fila antes de uma requisição simples da interface web, a interface precisa esperar o processo longo terminar para ser atendida.
