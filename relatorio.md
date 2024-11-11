# Relatório

## Menu Principal

### Descrição
O menu principal do script é a interface inicial exibida ao usuário. Segue o padrão exigido no trabalho e, por conta do uso do comando `tput`, a alteração na data e hora não interfere no alinhamento da interface, garantindo que as informações sejam exibidas de forma clara e organizada.

### Comandos Usados
- `printf`: Exibe a interface do menu principal com informações formatadas.
- `date`: Coleta a data e hora atuais do sistema.
- `tput`: Controla a posição do cursor, organizando visualmente os campos de data e hora.
- `read`: Captura a entrada do usuário para selecionar uma opção de menu.
- `clear`: Limpa o terminal antes de exibir a interface do menu, proporcionando uma experiência visual mais limpa.

---

## Opção 1: Listagem de diretórios

### Descrição
O script consiste em listar arquivos e(ou) diretórios em um caminho dado pelo usuário. O usuário interage com o programa através de um menu que oferece opções para listar apenas arquivos, apenas diretórios, ambos ou sair do programa. O script verifica as preferências do usuário sobre o detalhamento da listagem (detalhado ou simples) e executa as listagens usando comandos de terminal.

### Comandos Usados
- `find`: Realiza buscas em diretórios específicos com filtros de tipo, como arquivos ou diretórios. A opção `-maxdepth` limita a profundidade da busca, enquanto `-mindepth 1` exclui o diretório raiz da busca. É usado para detalhagem simples.
- `ls -lh`: Lista o conteúdo do diretório de forma detalhada (longa) e com tamanhos legíveis.
- `grep`: Filtra o conteúdo do comando `ls` para identificar apenas arquivos (`'^-'`) ou apenas diretórios (`'^d'`). Este filtro é usado apenas quando a listagem detalhada é desejada e serve para separar arquivos de diretórios.
- `read`: Coleta as escolhas do usuário sobre o tipo e detalhamento da listagem.
- `clear`: Limpa a tela antes de exibir o conteúdo do menu ou dos resultados da busca.

### Observações  
- **`! -name '.*'`**: O filtro `! -name '.*'` impede que arquivos e diretórios ocultos sejam incluídos na listagem.
- **Pipe (`|`)**: O pipe é utilizado para direcionar a saída de um comando para a entrada de outro.
- **`-z` e `-d`**:
  - **`-z`**: A opção `-z` é usada no comando `test` ou `[[ ... ]]` para verificar se uma variável está vazia.
  - **`-d`**: O teste `-d` verifica se um caminho corresponde a um diretório.

---

## Opção 2: Copiar um arquivo para um subdiretório

### Descrição
A **Opção 2** do menu permite ao usuário copiar um arquivo do diretório atual para um subdiretório de sua escolha. O script exibe todos os arquivos do diretório atual e permite ao usuário selecionar um arquivo a ser copiado. Em seguida, o script apresenta os subdiretórios disponíveis. Após a escolha, o arquivo é copiado para o diretório de destino, com uma mensagem de confirmação da operação.

### Comandos Usados
- `find`: Usado para localizar arquivos e diretórios no diretório atual. A opção `-maxdepth 1` é usada para listar apenas os arquivos no nível atual, sem entrar em subdiretórios.
- `cp`: Comando utilizado para copiar o arquivo selecionado para o diretório de destino.
- `read`: Captura as entradas do usuário.
- `basename`: Usado para extrair o nome do arquivo ou diretório a partir de seu caminho completo.

---

## Opção 3: Renomear um arquivo

### Descrição
A **Opção 3** permite ao usuário renomear um arquivo do diretório atual. O script permite ao usuário selecionar um arquivo para renomear. O usuário deve fornecer um novo nome para o arquivo. Se o novo nome for diferente do nome atual, o arquivo é renomeado.

### Comandos Usados
- `mv`: O comando `mv` é utilizado para mover ou renomear arquivos e diretórios. Neste caso, é usado para renomear o arquivo selecionado para o novo nome fornecido pelo usuário.
- `read`: Captura a entrada do usuário.
- `basename`: Usado para extrair o nome do arquivo, sem o caminho completo, para exibição na mensagem de confirmação.

---

## Opção 4: Deletar arquivos ou diretórios

### Descrição
Na opção 4, o script exibe uma lista numerada de todos os itens disponíveis no diretório atual, e o usuário escolhe o item pelo número correspondente. O programa verifica se o item é um arquivo ou um diretório e, caso seja um diretório, informa ao usuário que todos os arquivos e subdiretórios internos serão removidos junto com o diretório.
Antes de deletar, o script solicita a confirmação do usuário. Essa confirmação adicional é importante para evitar exclusões acidentais de dados importantes.

### Comandos Usados
- `find`: Utilizado para listar arquivos e diretórios no diretório atual com profundidade máxima e mínima de 1, para que, respectivamente, apenas os itens do diretório atual sejam exibidos e o diretório `.` (atual) não seja exibido.
- `basename`: Exibe apenas o nome do arquivo ou diretório, sem o caminho completo, para facilitar a visualização e seleção pelo usuário.
- `rm` e `rm -r`: `rm` é usado para excluir arquivos, enquanto `rm -r` é usado para remover diretórios recursivamente, incluindo todo o conteúdo interno, caso o usuário tenha confirmado a exclusão.
- `read`: Captura as entradas do usuário.

### Observações
- `-d` e `-f`: Utilizados para verificar se o item selecionado é um diretório (`-d`) ou um arquivo (`-f`).

---

## Referências

- Documentação do comando `tput`: [tput usage documentation](https://man7.org/linux/man-pages/man1/tput.1.html)
- Documentação do comando `find`: [GNU find documentation](https://www.gnu.org/software/findutils/)
- Documentação do comando `test` e `[[ ... ]]`: [Bash test documentation](https://www.gnu.org/software/bash/manual/html_node/Bash-Builtins.html#index-test)
- Documentação do comando `basename`: [GNU basename documentation](https://www.gnu.org/software/coreutils/manual/html_node/basename-invocation.html)
