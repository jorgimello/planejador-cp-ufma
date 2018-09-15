# Planejador CP (UFMA)

## Sobre

Aplicação feita para auxiliar estudantes do curso de Ciência da Computação da UFMA a decidir entre turmas de forma a cumprir a carga horária do curso.

O curso possui uma estrutura específica, onde até o 6º período o estudante possui n cadeiras obrigatórias a cumprir, e a partir daí precisa escolher entre um grupo de disciplinas eletivas de forma a cumprir a carga horária optativa. O sistema [SIGAA](https://sigaa.ufma.br) não descreve em detalhes quantas disciplinas faltam, mostrando apenas a quantidade de horas pendentes, o que pode gerar confusão.

## Motivação

O curso de Ciência da Computação da UFMA tem suas disciplinas divididas entre Obrigatórias, Grupo I (optativas) e Grupo II (também optativas). Todas as disciplinas obrigatórias precisam ser cursadas (2595h), enquanto são exigidas 720h do Grupo I e 225h do Grupo II, totalizando 3540h. O sistema SIGAA é dividido apenas entre carga horária obrigatória e carga horária optativa, não havendo separação entre disciplinas do Grupo I e Grupo II. Dependendo da escolha das disciplinas, o histórico pode informar errado a quantidade de horas pendentes para o aluno. Exemplo:

<p align="center">
    <img src="https://raw.githubusercontent.com/jorgimello/planejador-cp-ufma/master/imgs/horas.png">
</p>

Essa é a tabela que detalha as horas do meu histórico. As horas obrigatórias (cumpridas e pendentes) estão corretas, porém nas colunas de horas optativas e o total existem alguns erros: já cumpri as 225h do Grupo II, e somando todas as disciplinas que fiz, ultrapassei esse valor de horas (somou 255h). Ou seja, tenho 30h a mais que não deveriam ser contabilizadas (não importa se você foi aprovado em todas as disciplinas do Grupo II, apenas 225h serão contabilizadas). O SIGAA considera essas horas no cálculo das horas optativas, informando que devo 210h optativas, o que está errado. No momento de escrita desse README, devo 240h do Grupo I, logo, devo 30h a mais do que é informado (justamente porque o SIGAA considera aquelas 30h que fiz a mais do Grupo II). 

Com isso, essa aplicação foi pensada e desenvolvida pra ajudar os estudantes do curso a planejarem corretamente suas disciplinas, sem fazer horas a mais que não serão contabilizadas ou pensar que possui menos horas pendentes como informado pelo SIGAA. Veja a área de Dicas na aplicação pra ver algumas coisas que você pode fazer pra se graduar mais rápido.

## Tecnologias
- PHP
- SQLite
- Laravel
- [Bulma](https://bulma.io/)
- git (pra fazer clone, commit, push etc e manter suas disciplinas salvas)

## Dependências
- PHP >= 5.6.4
- php-pear php-fpm php-dev php-zip php-curl php-xmlrpc php-gd php-mysql php-mbstring php-xml libapache2-mod-php (pesquise um pouco como instalar esses módulos)
- Composer

## Instalação
Em construção... Porém além de ter o PHP instalado e os módulos acima é certeza que precisa do gerenciador de dependências de PHP [Composer](https://getcomposer.org/). Se estiver interessado pode adiantar a instalação. Existem diversas formas de instalar o composer. No meu caso, rodando no Linux Mint (baseado no Debian), rodei

```
sudo apt install composer
```
e o composer pôde ser utilizado. Já em outros sistemas, pesquise um pouco e descubra. É necessário rodar o comando ```composer install``` dentro da pasta da aplicação, logo, é preciso que o comando esteja disponível na linha de comando.

## Steps de instalação:
- Fork esse repositório (para manter sua base própria de disciplinas)
- ```git clone``` no seu fork
- Rode ```composer install``` dentro da pasta da aplicação
- Renomear .env.example para .env e colocar o caminho completo do arquivo database.sqlite
- Rodar ```php artisan key:generate``` dentro da pasta
- ```php artisan serve``` para rodar a aplicação
- Voilá! Rodando em localhost:8000. Abra em qualquer browser.

## Erros e Pull Requests
Caso encontre algum erro, abra um tópico em [Issues](https://github.com/jorgimello/planejador-cp-ufma/issues) e eu verificarei. 
Sugestões e colaborações são bem vindas. Só abrir um tópico em [Pull requests](https://github.com/jorgimello/planejador-cp-ufma/pulls) e eu verifico a sugestão. Caso seu Pull request tenha sugestões de código, saiba que posso refatorá-lo pra se adequar ao padrão de código que sigo.

## Referências
- [COCOM - Coordenação de Ciência da Computação - UFMA](http://www.deinf.ufma.br/cocom/site/)
- [SIGAA](https://sigaa.ufma.br)
- Uma planilha Cronograma que roda pelos pendrives e emails do curso, que alguns usam pra ver as horas pendentes de cada grupo. Não sei quem foi o autor, se alguém souber é só me falar que dou os devidos créditos. Me ajudou e foi a principal inspiração pra eu desenvolver esse Planejador.
