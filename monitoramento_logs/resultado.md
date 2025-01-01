<h1>Monitoramento - Análise de Logs</h1>

Esta é a minha solução para o quinto desafio de programação proposto pelo Bootcamp de Segurança Cibernética - Dio IO e Santander.

<h2>Descrição</h2>
Você é responsável por implementar um sistema de monitoramento de segurança para um sistema de acesso. Seu objetivo é analisar registros de log de tentativas de acesso para detectar possíveis invasões. Cada registro contém um identificador de usuário e um status que indica se a tentativa de acesso foi bem-sucedida ou falhou.

A detecção de tentativas de invasão é essencial para a segurança do sistema, e a análise de logs é uma prática comum para identificar comportamentos suspeitos. O sistema deve emitir um alerta se detectar mais de 3 tentativas consecutivas de falha para o mesmo usuário.

+ <b>Entrada</b>

  Uma lista de registros de log no formato <b>id_usuario:status</b>, onde:

    + <b>id_usuario</b> é uma string que representa o identificador do usuário (exemplo: <b>"user1"</b>).

    + <b>status</b> pode ser uma das seguintes strings:
      
   &ndash; <b>"sucesso"</b> – indica que a tentativa de acesso foi bem-sucedida.
 
   &ndash; <b>"falha"</b> – indica que a tentativa de acesso falhou.

   <b>A lista pode conter qualquer número de registros.</b>
  
+ <b>Saída</b>

  O sistema deve retornar:
  
  + O <b>id_usuario</b> que teve mais de 3 tentativas consecutivas de falha.
    
  + Se nenhum usuário tiver mais de 3 tentativas de falha consecutivas, o sistema deve retornar a mensagem <b>"Nenhum invasor detectado"</b>.

<h2>Exemplos</h2>

A tabela abaixo apresenta exemplos com alguns dados de entrada e suas respectivas saídas esperadas. Certifique-se de testar seu programa com esses exemplos e com outros casos possíveis.

<table >
    <tr>
      <td><b>Entrada</b></td>
      <td><b>Saída</b></td>
    </tr>
      <tr>
      <td>user1:falha,<br> 
       user1:falha,<br> 
       user1:falha,<br> 
       user1:sucesso
      </td>
      <td>Nenhum invasor detectado</td>
    </tr>
      <tr>
      <td>user2:falha,<br> 
          user2:falha,<br> 
          user2:falha,<br> 
          user2:falha</td>
      <td>user2</td>
    </tr>
      <tr>
      <td>user3:sucesso,<br>
          user3:falha,<br> 
          user3:falha,<br> 
          user3:falha,<br> 
          user3:falha</td>
      <td>user3</td>
    </tr>
  </table>


<b>Segue o script desenvolvido como resposta, escrito em linguagem Python.</b>


```python
# Função para detectar tentativas de invasão em registros de log
def detectar_invasao(registros):

 # Variáveis para rastrear o ID do usuário atual e suas falhas consecutivas
 usuario_atual = None
 tentativas_consecutivas = 0
 invasor_detectado = None

 # Percorra cada registro de log
 for registro in registros:
     # Separa o ID do usuário e o status do registro (sucesso ou falha)
     id_usuario, status = registro.split(":")
     
     # Verifica se o usuário atual é o mesmo da iteração anterior
     if id_usuario == usuario_atual:
         if status == "falha":
             tentativas_consecutivas += 1
         else:
             tentativas_consecutivas = 0  # Reseta o contador se a tentativa foi bem-sucedida
     else:
         # Se mudar de usuário, verifica se o usuário anterior teve mais de 3 falhas consecutivas
         if tentativas_consecutivas > 3:
             invasor_detectado = usuario_atual
         
         # Atualiza para o novo usuário e reinicie a contagem de tentativas falhas
         usuario_atual = id_usuario
         tentativas_consecutivas = 1 if status == "falha" else 0  # Inicia contagem

 # Após o loop, verifica se o último usuário teve mais de 3 tentativas de falha
 if tentativas_consecutivas > 3:
     invasor_detectado = usuario_atual

 # Retorna o resultado final
 return invasor_detectado if invasor_detectado else "Nenhum invasor detectado"

# Função principal para executar o programa
def main():
 # Solicita ao usuário que insira os registros de log
 entrada = input()
 
 registros = [registro.strip().strip('"') for registro in entrada.split(",")]

 # Chama a função para detectar tentativas de invasão
 resultado = detectar_invasao(registros)

 # Imprime o resultado
 print(resultado)

# Chama a função principal para executar o programa
if __name__ == "__main__":
 main()


  
