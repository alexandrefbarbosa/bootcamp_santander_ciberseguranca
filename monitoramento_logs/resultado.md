<h1>Monitoramento - Análise de Logs</h1>

Esta é a minha solução para o quinto desafio de programação proposto pelo Bootcamp de Segurança Cibernética - Dio IO e Santander.

<h2>Descrição</h2>
Você é responsável por implementar um sistema de monitoramento de segurança para um sistema de acesso. Seu objetivo é analisar registros de log de tentativas de acesso para detectar possíveis invasões. Cada registro contém um identificador de usuário e um status que indica se a tentativa de acesso foi bem-sucedida ou falhou.

A detecção de tentativas de invasão é essencial para a segurança do sistema, e a análise de logs é uma prática comum para identificar comportamentos suspeitos. O sistema deve emitir um alerta se detectar mais de 3 tentativas consecutivas de falha para o mesmo usuário.

+ <b>Entrada</b>

  Uma lista de registros de log no formato id_usuario:status, onde:

    + id_usuario é uma string que representa o identificador do usuário (exemplo: "user1").

    + status pode ser uma das seguintes strings:
      
   &ndash; "sucesso" – indica que a tentativa de acesso foi bem-sucedida.
 
   &ndash; "falha" – indica que a tentativa de acesso falhou.

   A lista pode conter qualquer número de registros.
  
+ <b>Saída</b>

  O sistema deve retornar:
  
  + O <b>id_usuario</b> que teve mais de 3 tentativas consecutivas de falha.
    
  + Se nenhum usuário tiver mais de 3 tentativas de falha consecutivas, o sistema deve retornar a mensagem "Nenhum invasor detectado".
  
  
