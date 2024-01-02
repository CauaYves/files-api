esse é um teste para uma requisição HTTPS de arquivos do tipo multipart/form-data.

multipart/form-data é um tipo de conteúdo (Content-Type) usado em solicitações HTTP para o envio de dados de formulário que podem incluir tanto campos de texto simples quanto arquivos binários. Esse tipo de conteúdo é frequentemente utilizado quando você precisa enviar informações de formulários complexos, especialmente aqueles que envolvem o upload de arquivos.

A razão pela qual é chamado de "multipart" é porque os dados do formulário são divididos em várias partes independentes, cada uma representando um campo do formulário ou um arquivo. Essas partes são delimitadas por um caractere especial chamado de delimitador. O cabeçalho Content-Type informa ao servidor que o corpo da solicitação contém várias partes e especifica o delimitador que é usado para separar essas partes.

Por exemplo, uma solicitação multipart/form-data pode se parecer com isso:


    POST /exemplo/endpoint HTTP/1.1
    Host: exemplo.com
    Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryABC123
    
    ------WebKitFormBoundaryABC123
    Content-Disposition: form-data; name="campoTexto"
    
    Valor do campo de texto
    ------WebKitFormBoundaryABC123
    Content-Disposition: form-data; name="arquivo"; filename="arquivo.txt"
    Content-Type: text/plain
    
    Conteúdo do arquivo de texto
    ------WebKitFormBoundaryABC123--

Neste exemplo, há dois campos no formulário: um campo de texto chamado "campoTexto" e um campo de arquivo chamado "arquivo". Cada parte é delimitada pelo marcador ------WebKitFormBoundaryABC123, e o tipo de conteúdo do arquivo é especificado no cabeçalho da parte correspondente.

O uso de multipart/form-data permite que dados de formulários sejam enviados de forma eficiente, mantendo a estrutura e a integridade dos dados, especialmente quando se trata de envio de arquivos. Este formato é comumente utilizado em formulários HTML que incluem elementos de upload de arquivos.
