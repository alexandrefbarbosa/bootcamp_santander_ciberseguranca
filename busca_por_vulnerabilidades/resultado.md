<h1>Busca por Vulnerabilidades</h1>

Esta é a minha solução para o quarto desafio de programação proposto pelo Bootcamp de Segurança Cibernética - Dio IO e Santander.

<h2>Descrição</h2>
Crie uma solução para analisar uma lista de e-mails recebidos, verificando padrões comuns de phishing nas mensagens. Se um e-mail contiver palavras suspeitas como "ganhe", "prêmio", "urgente", "desconto", "click" e "promoção" ele deve ser classificado como "Phishing" e "Seguro".

+ <b>Entrada</b>

  Uma String contendo um conteúdo único representando o corpo do e-mail.
  
+ <b>Saída</b>

  "Phishing" ou "Seguro" para cada e-mail.
  
  <h2>Exemplos</h2>

  A tabela abaixo apresenta exemplos com alguns dados de entrada e suas respectivas saídas esperadas. Certifique-se de testar seu programa com esses exemplos e com outros casos possíveis.

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