<h1>Verificação da Integridade de Arquivo</h1>

Esta é a minha solução para o desafio inicial de programação proposto pelo Bootcamp de Segurança Cibernética -Dio IO e Santander.

<h2>Objetivo</h2>

Você foi encarregado de criar um sistema simples que verifica a integridade de arquivos, comparando o hash fornecido pelo usuário com o hash real do arquivo. Na função verificar_hashes que irá receber uma lista de hashes e compará-los com os valores esperados para cada arquivo. Seu objetivo é verificar se o hash calculado é igual ao hash esperado.

<h2>Estruturação</h2>

+ <b>Entrada</b>
  
  Uma lista de pares de hashes (hash calculado e hash esperado), separados por vírgulas, e cada par separado por ponto e vírgula.

+ <b>Saída</b>
  
  Para cada par de hashes fornecido, o código imprime o resultado "Correto" ou "Inválido".

  <h2>Exemplos</h2>

  A tabela abaixo apresenta exemplos com alguns dados de entrada e suas respectivas saídas esperadas. Certifique-se de testar seu programa com esses exemplos e com outros casos possíveis.

  <table text-align: center>
    <tr>
      <td ><b>Entrada</b></td>
      <td ><b>Saída</b></td>
    </tr>

    <tr>
      <td>abc123, abc123</td>
      <td>Correto</td>
    </tr>

    <tr>
      <td>def456, def789</td>
      <td>Inválido</td>
    </tr>

     <tr>
      <td>123abc, 123abc; 456def,456def</td>
      <td>Correto</td>
    </tr>

  </table>
