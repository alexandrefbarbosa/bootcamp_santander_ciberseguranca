<h1>Monitoramenro - Análise de Logs</h1>

Esta é a minha solução para o quinto desafio de programação proposto pelo Bootcamp de Segurança Cibernética - Dio IO e Santander.

<h2>Descrição</h2>
Você é responsável por implementar um sistema de monitoramento de segurança para um sistema de acesso. Seu objetivo é analisar registros de log de tentativas de acesso para detectar possíveis invasões. Cada registro contém um identificador de usuário e um status que indica se a tentativa de acesso foi bem-sucedida ou falhou.

A detecção de tentativas de invasão é essencial para a segurança do sistema, e a análise de logs é uma prática comum para identificar comportamentos suspeitos. O sistema deve emitir um alerta se detectar mais de 3 tentativas consecutivas de falha para o mesmo usuário.

+ <b>Entrada</b>

  Uma lista de registros de log no formato id_usuario:status, onde:

id_usuario é uma string que representa o identificador do usuário (exemplo: "user1").

status pode ser uma das seguintes strings:
- "sucesso" – indica que a tentativa de acesso foi bem-sucedida.
- "falha" – indica que a tentativa de acesso falhou.
  
+ <b>Saída</b>

  "Phishing" ou "Seguro" para cada e-mail.
  
  <h2>Exemplos</h2>

  O sistema deve retornar:

O id_usuario que teve mais de 3 tentativas consecutivas de falha.

Se nenhum usuário tiver mais de 3 tentativas de falha consecutivas, o sistema deve retornar a mensagem "Nenhum invasor detectado".
  <table >
    <tr>
      <th><b>Entrada</b></th>
      <th><b>Saída</b></th>
    </tr>

    <tr>
      <td>Ganhe um prêmio incrível hoje!</td>
      <td>Classificação: Phishing</td>
    </tr>

    <tr>
      <td>Não perca esta promoção exclusiva!</td>
      <td>Classificação: Phishing</td>
    </tr>

     <tr>
      <td>Você está convidado para a reunião amanhã!</td>
      <td>Classificação: Seguro</td>
    </tr>

  </table>

  <h2><b>Código em Python</b></h2>
Segue o script desenvolvido como resposta, escrito em linguagem Python.

```python
# Função para verificar se o corpo do e-mail contém palavras suspeitas de phishing
def verificar_phishing(mensagem):

 # Lista de palavras que indicam possíveis e-mails de phishing
 palavras_suspeitas = ["ganhe", "prêmio", "urgente", "desconto", "click", "promoção"]
 
 # Conversão a mensagem para minúsculas para garantir a comparação correta
 mensagem = mensagem.lower()
 
 # Verifica se alguma palavra suspeita está presente no corpo do e-mail
 for palavra in palavras_suspeitas:
     if palavra in mensagem:
         return "Phishing"
 
 return "Seguro"

# Leitura da entrada do usuário
email_usuario = input().strip()

# Chama a função para verificar o e-mail
resultado = verificar_phishing(email_usuario)

# Imprime o resultado
print(f"Classificação: {resultado}")
