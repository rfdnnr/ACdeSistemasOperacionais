## Menu Principal
### Descrição
O menu principal do script é a interface inicial exibida ao usuário. Segue o padrão exigido no trabalho e, por conta do uso do comando `tput`, a alteração na data e hora não interfere no alinhamento da interface, garantindo que as informações sejam exibidas de forma clara e organizada.

### Comandos Usados
- `printf`: Exibe a interface do menu principal com informações formatadas.
- `date`: Coleta a data e hora atuais do sistema.
- `tput`: Controla a posição do cursor, organizando visualmente os campos de data e hora.
- `read`: Captura a entrada do usuário para selecionar uma opção de menu.
- `clear`: Limpa o terminal antes de exibir a interface do menu, proporcionando uma experiência visual mais limpa.

### Referências
- Documentação do comando `printf`: [GNU printf documentation](https://www.gnu.org/software/bash/manual/html_node/Bash-Builtins.html#index-printf)
- Documentação do comando `date`: [GNU date documentation](https://www.gnu.org/software/coreutils/manual/html_node/date-invocation.html)
- Documentação do comando `tput`: [tput usage documentation](https://man7.org/linux/man-pages/man1/tput.1.html)
- Documentação do comando `read`: [Bash read documentation](https://www.gnu.org/software/bash/manual/html_node/Bash-Builtins.html#index-read)

## Listagem de diretórios
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

### Referências
- Documentação do comando `find`: [GNU find documentation](https://www.gnu.org/software/findutils/)
- Documentação do comando `ls`: [GNU ls documentation](https://www.gnu.org/software/coreutils/manual/html_node/ls-invocation.html)
- Documentação do comando `grep`: [GNU grep documentation](https://www.gnu.org/software/grep/manual/grep.html)
- Documentação do comando `test` e `[[ ... ]]`: [Bash test documentation](https://www.gnu.org/software/bash/manual/html_node/Bash-Builtins.html#index-test)
- Documentação do comando `read`: [Bash read documentation](https://www.gnu.org/software/bash/manual/html_node/Bash-Builtins.html#index-read)

## Opção 2
### Descrição

### Comandos Usados

### Referências

## Opção 3
### Descrição

### Comandos Usados

### Referências

## Opção 4
### Descrição

### Comandos Usados

### Referências
