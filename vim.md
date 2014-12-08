---
layout: page
title: Resumo Vim
permalink: /Vim/
---

#Resumo dos comandos VIM por masp

Resumo dos Comandos gerais:

|Comando    |Ação no texto selecionado                              |
|-----------|-------------------------------------------------------|
|d	        |Apaga                                                  |
|y	        |Copia                                                  |
|p	        |Cola                                                   |
|c	        |Troca por outro texto                                  |
|r	        |Troca cada letra por um caractere                      |
|J	        |Junta todas as linhas em uma só                        |
|U	        |Converte para maiúsculas                               |
|u	        |Converte para minúsculas                               |
|~	        |Inverte maiúsculas e minúsculas                        |
|gq	        |Reformata as linhas para a largura desejada            |
|!	        |Manda as linhas para um comando externo (!sort)        |
|:	        |Aplica um comando 'ex' nas linhas (:s/isso/aquilo/)    |

##Salvando todos os buffers (arquivos) abertos
`:wa` Salva todos os arquivos

`:xa` Salva todos os arquivos e sai do  VIM


##

##Copia e cola entre VIM e outros aplicativos Windows
[Material de site http://vim.wikia.com/wiki/Copy,_cut_and_paste](http://vim.wikia.com/wiki/Copy,_cut_and_paste)

`Ctrl+Insert` para copiar (copy)

`Shift+Delete` para cortar (cut)to cut

`Shift+Insert` para colar do Windows

##Gravando como UTF-8
`:w ++enc=utf-8`

##Para indentar todo o arquivo:

Ir para o inicio do Texto `gg`, entrar no modo visual, `ctrl-v`, marcar todo o texto, `G`, e digitar `=`, (todo o buffer será indentando)
[How to indent: superuser.com/questions/582894/how-to-re-indent-html-snippets-in-vim](http://superuser.com/questions/582894/how-to-re-indent-html-snippets-in-vim)

**No arquivo rails o RagTag é útil para a marcação do texto erb**
ctrl-x =

##Trabalhando com blocos
[Material tirado de: http://aurelio.net/vim/selecao-vi-sual.html](Material tirado de: http://aurelio.net/vim/selecao-vi-sual.html)

|Comando    |Nome	            |Ação                                   |
|:----------|-------------------|---------------------------------------|
|v	        |-- VISUAL --	    |Seleciona caracteres                   |
|V	        |-- VISUAL LINE --	|Seleciona linhas                       |
|Ctrl+V	    |-- VISUAL BLOCK --	|Seleciona blocos (seleção vertical)    |

Para fazer alteração em várias linha usa-se o `Ctrl+V` e seleciona as linhas onde se fará a inclusão, digita-se I (maiusculo) para o texto entrar antes da seleção ou A (maisuculo) para incluir após a seleção, após concluida a seleção, `ESC` e toda a seleção terá a alteração.


##Movimentação entre janelas
`ctrl-w h` - esquerda
`crtl-w l` - direita

`crtl-w j` - baixo
`crtl-w k` - acima

##Movimentação na janela atual
No modo de comando:
`h` - esquerda
`l` - direita

`j` - baixo
`k` - acima

No modo de comando:

`e` avança pulando palavra por palavra
`b` retorna pulando palavra por palavra

##Para encontrar o par, por exemplo a tag div que fecha a tag atual;
`%` em cima da tag no modo de comando.

##Fechar o Buffer atual
`:bw`

##Abrindo a Shell do sistema em uso
`:shell`

##Listando os buffers abertos
`:ls`

##Navegação
`j` desce
`k` sobre
`h` esquerda
`l` direita

###as mesmas teclas funcionam para navegar entre os buffers

`crtl-j` buffer abaixo
`ctrl-k` bufer acima
`ctrl-h` buffer a esquerda
`ctrl-l` buffer a direita


##Saltando palavras
[retirado do site:vim-anotacoes.blogspot.com.br](http://vim-anotacoes.blogspot.com.br/2009/01/movendo-cada-palavra-no-vim.html)

Saltando para frente parando no início da palavra: `w`
Saltando para trás parando no início da palavra: `b`
Saltando para frente parando no final da palavra: `e`
Saltando para trás parando no final da palavra: `ge`

O que determina o que é uma palavra é a definição da opção `:iskeyword`, a qual define como separadores de palavras, entre eles: ( /_.

Para saltar palavras somente separadas por espaços as respectivas versões maiúsculas :
`W`, `B`, `E`, `gE`.

Esses comandos são mais ágeis para saltar palavras do `h`,`j`,`k`,`l`.
Os comandos suportam contadores:
`3w`

##Substituições

Para fazer uma busca, certifique-se de que está em modo normal, em seguida digite use o comando `:s`, conforme será explicado.
Para substituir "foo" por "bar" na linha atual: `:s/foo/bar`
Para substituir "foo" por "bar" da primeira à décima linha do arquivo: `:1,10 s/foo/bar`
Para substituir "foo" por "bar" da primeira à última linha do arquivo: `:1,$ s/foo/bar`

Ou simplesmente: `:% s/foo/bar`

$ ............. significa para o vim final do arquivo
% ............. representa o arquivo atual
O comando ":s" possui muitas opções que modificam seu comportamento.

###Substituindo newline em arquivos
[http://stackoverflow.com/questions/3983406/delete-newline-in-vim](http://stackoverflow.com/questions/3983406/delete-newline-in-vim)

[http://stackoverflow.com/questions/71323/how-to-replace-a-character-for-a-newline-in-vim](http://stackoverflow.com/questions/71323/how-to-replace-a-character-for-a-newline-in-vim)

[http://stackoverflow.com/questions/71417/why-is-r-a-newline-for-vim](http://stackoverflow.com/questions/71417/why-is-r-a-newline-for-vim)

`:%s/\n\n/\r`

Este comando vai procurar uma sequencia de duas newlines e substituir por uma newline do vim (usa-se \r para "Carriage Return")



---

#Rails#
---

** no modo Insert **


* Press `Ctrl + s and =` afterwards to insert <%= %> block
* Press `Ctrl + s and -` afterwards to insert <% -%> block
* Press `Ctrl + s and #` afterwards to insert <%# %> block

**Se disponivel o plugin RagTag do Tim pope**

---

|Mapping      | Changed to (cursor = ^) ~                           |                           |
|-------------|:---------------------------------------------------:|--------------------------:|
|<C-X>=       | foo<%= ^ %>                                         |*ragtag-CTRL-X_=*          |
|<C-X>+       | <%= foo^ %>                                         |*ragtag-CTRL-X_+*          |
|<C-X>-       | foo<% ^ %>                                          |*ragtag-CTRL-X_-*          |
|<C-X>_       | <% foo^ %>                                          |*ragtag-CTRL-X__*          |
|<C-X>'       | foo<%# ^ %>                                         |*ragtag-CTRL-X_'*          |
|             |(mnemonic: ' is a comment in ASP VBS)                |                           |
|<C-X>"       | <%# foo^ %>                                         |*ragtag-CTRL-X_quote*      |
|<C-X><Space> | <foo>^</foo>                                        |*ragtag-CTRL-X_<Space>*    |
|<C-X><CR>    | <foo>\n^\n</foo>                                    |*ragtag-CTRL-X_<CR>*       |
|<C-X>/       | Last HTML tag closed                                |*ragtag-CTRL-X_/*          |
|<C-X>!       | <!DOCTYPE...>/<?xml ...?> (menu)                    |*ragtag-CTRL-X_!*          |
|<C-X>@       | <link rel="stylesheet" ...>                         |*ragtag-CTRL-X_@*          |
|             |(mnemonic: @ is used for importing in a CSS file)    |                           |
|<C-X>#       | <meta http-equiv="Content-Type" ... />              |*ragtag-CTRL-X_#*          |
|<C-X>$       | <script src="/javascripts/^.js"></script>           |*ragtag-CTRL-X_$*          |
|             |(mnemonic: $ is valid in javascript identifiers)     |                           |

##Para criar um arquivo vazio no DOS:##
[http://stackoverflow.com/questions/1702762/how-to-create-an-empty-file-at-the-command-line](http://stackoverflow.com/questions/1702762/how-to-create-an-empty-file-at-the-command-line)

`cd. > filename`


##Para saltar do buffer atual para o buffer anterior##
`crtl+6`

##Para remover os caracteres BOM (Byte Order Mark) por exemplo: <feff> ##

`:set nobomb`
`:w`

## Contatndo caracteres e outras estatisticas no VIM

[http://superuser.com/questions/149854/how-can-i-get-gvim-to-display-the-character-count-of-the-current-file](http://superuser.com/questions/149854/how-can-i-get-gvim-to-display-the-character-count-of-the-current-file)

`g ctrl+g`

### ou ainda:

`:%s/./&/gn`



## Para incluir caracteres especiais usa-se o "digraphs"

material retirado do site [http://www.alecjacobson.com/weblog/?p=443](http://www.alecjacobson.com/weblog/?p=443)

usa-se os digraphs, para ver a lista completa no proprio VIM:

`:digraphs`

para incluir poe exemplo o μ usa-se o seguinte:

`ctrl+km*` no modo de inserção

##Gravação de Macro

Material retirado de: [http://vim.wikia.com/wiki/Macros](http://vim.wikia.com/wiki/Macros)

Basicamente usa-se da seguinte maneira;

`q (letra de a-z) (comandos) q`

`qd`    inicia gravando o registro d

...     Todos os comandos complexos

`q` 	para a gravação

@d      executa a macro d

@@      executa a macro mais uma vez


#Vim - Janelas
##Trabalhando com Janelas
O Vim trabalha com o conceito de múltiplos buffers de arquivo. Cada buffer é um arquivo carregado para edição. Um buffer pode estar visível ou não, e é possível dividir a tela em janelas, de forma a visualizar mais de um buffer simultaneamente.


##Alternando entre Buffers de arquivo

Ao abrir um documento qualquer no Vim o mesmo fica em um buffer. Caso seja decidido que outro arquivo seja aberto na mesma janela, o documento inicial irá desaparecer da janela atual cedendo lugar ao mais novo, mas permanecerá ativo no buffer para futuras modificações.

Para saber quantos documentos estão abertos no momento utiliza-se o comando `:ls` ou `:buffers`. Esses comandos listam todos os arquivos que estão referenciados no buffer com suas respectivas "chaves" de referencia.

Para trocar a visualização do Buffer atual pode-se usar:

`:buffer#` Altera para o buffer anterior
`:b2`Altera para o buffer cujo a chave é 2


Para os que preferem atalhos para alternar entre os buffers, é possível utilizar `Ctrl-6` que tem o mesmo funcionamento do comando `:b#+`


##Modos de divisão da janela

Como foi dito acima, é possível visualizar mais de um buffer ao mesmo tempo, e isso pode ser feito utilizando `tab` ou `plit`.


##Utilizando abas `tab`

A partir do Vim 7 foi disponibilizada a função de abrir arquivos em abas, portanto é possível ter vários buffers abertos em abas distintas e alternar entre elas facilmente. Os comandos para utilização das abas são:

`:tabnew` Abre uma nova tab
`:tabprevious` Vai para a tab anterior
`:tabnext` Vai para a próxima tab

##Utilizando split horizontal

Enquanto os comandos referentes a `tab` deixam a janela inteira disponível para o texto e apenas cria uma pequena aba na parte superior, o comando `split` literamente divide a tela atual em duas para visualização simultânea dos `buffers` (seja ele o mesmo ou outro diferente).
Esse é o split padrão do Vim mas pode ser alterado facilmente colocando a linha abaixo no seu ~/.vimrc:

% deixei a linha de explicação mais curta para não exceder a largura da página
     :set splitright .... split padrão para vertical

##Utilizando split vertical

O split vertical funciona da mesma maneira que o split horizontal, sendo a unica diferença o modo como a tela é dividida, pois nesse caso a tela é dividida verticalmente.

##Abrindo e fechando janelas

`Ctrl-w-s`  Divide a janela horizontalmente (:split)
`Ctrl-w-v`  Divide a janela verticalmente (:vsplit)
`Ctrl-w-o`  Faz a janela atual ser a única (:only)
`Ctrl-w-n`  Abre nova janela (:new)
`Ctrl-w-q`  Fecha a janela atual (:quit)
`Ctrl-w-c`  Fecha a janela atual (:close)

Lembrando que o Vim considera todos os arquivos como ``buffers'' portanto quando um arquivo é fechado, o que está sendo fechado é a visualização do mesmo, pois ele continua aberto no ``buffer''.


##Salvando e saindo
É possível salvar todas as janelas facilmente, assim como sair tambem:

`:wall` salva todos `write all`
`:qall` fecha todos `quit all`


##Manipulando janelas

`Ctrl-w-w` Alterna entre janelas
`Ctrl-w-j` desce uma janela `j'
`Ctrl-w-k` sobe  uma janela `k'
`Ctrl-w-l` move para a janela da direta `l'
`Ctrl-w-h` move para a janela da direta `h'
`Ctrl-w-r` Rotaciona janelas na tela
`Ctrl-w-+` Aumenta o espaço da janela atual
`Ctrl-w--` Diminui o espaço da janela atual

Pode-se mapear um atalho para redimensionar janelas com as teclas `|+|' e `|-|'.

    :map + <c-w>+
    :map - <c-w>-

###buffers windows
Para abrir o gerenciador de arquivos do Vim use:

:Vex ............ abre o file explorer verticalmente
:Sex ............ abre o file explorer em nova janela
:Tex ............ abre o file explorer em nova aba
:e .............. abre o file explorer na janela atual
após abrir chame a ajuda <F1>

Para abrir o arquivo sob o cursor em nova janela coloque a linha abaixo no seu ~/.vimrc

     let g:netrw_altv = 1

É possível mapear um atalho ``no caso abaixo F2'' para abrir o File Explorer.

map <F2> <Esc>:Vex<cr>


Ao editar um arquivo no qual há referência a um outro arquivo, por exemplo: `/etc/hosts}`, pode-se usar o atalho `Ctrl-w f` para abri-lo em nova janela, ou `gf` para abri-lo na janela atual.
Mas é importante posicionar o cursor sobre o nome do arquivo.  Veja também mapeamentos na seção Mapeamentos página.

