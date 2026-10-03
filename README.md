# Parte A: Entendendo a barreira do sistema

O processo vai solicitar a leitura dos dados por meio de uma chamada de sistema. Como as aplicações executam em um espaço protegido e não têm permissão para acessar o hardaware diretamente, eles precisam pedir formalmente que o sistema operacional realize a operação de leitura no disco seu nome.

No momento que a chamada de sistema é invocada, ocorre um mecanismo detalhado:

. Modo Usuário: O processo "Geração de relatórios" vai rodar inicialmente nesse modo, onde possue alguns privilegio limitados e a interação do hardware é bloqueada

. Troca de modo: após a execução da chamada de sistema, o processo vai interromper o software(chamada de trap).

. Modo Kernel: Nesse modo, o código do sistema operacional assume o controle, valida a requisição, localiza os dadps no disco e inicia a leitura física no hardware.

. Bloqueio do Processo: O sistema operacional ira mover o processo batch do estado de execução para o estado bloqueado/espera, pois o acesso do disco é extremamente lenta

. Retorno: Assim que o sistema operacional termina de ler os dados, o processo reverte o nível de privilégio de volta para o modo usuário.

# Parte b: Diagnosticando o Escalonador

O algoritimo FCFS está causando o "congelamento" da interface porque ele processa as requisições estritamente na ordem de chegada, sem interrupções. Se um processo longo ou pesado entra na fila antes de uma requisição simples da interface web, a interface precisa esperar o processo longo terminar para ser atendida.
