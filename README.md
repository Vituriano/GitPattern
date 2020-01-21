## Getting started
1 - First, you need to init a git project:
```sh
git init
git remote add origin <url>
```
2 - Now, you will install the commitlint and the husky
```sh
yarn add @commitlint/{config-conventional,cli} -D
yarn add husky -D
```
3 - To lint commits before they are created you can use Husky's 'commit-msg' hook:
```json
{
  "husky": {
    "hooks": {
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
    }  
  }
}
```
4 - well, to use a interface for commits, you will use the commitizen. Install with the comand bellow:
```sh
yarn add commitizen -D
yarn commitizen init cz-conventional-changelog --yarn --dev --exact
```
5 - in package.json, add the line bellow in husky -> hooks:
```json
"prepare-commit-msg": "exec < /dev/tty && git cz --hook || true",
```
## Git Rules

1 - A mensagem de commit DEVE ser prefixado com um tipo, que consiste em um substantivo, feat,fix, etc., seguido por um escopo, e OBRIGATÓRIO terminar com dois-pontos e um espaço.

2 - O tipo feat DEVE ser usado quando um commit adiciona um novo recurso ao seu aplicativo ou biblioteca.

3 - O tipo fix DEVE ser usado quando um commit representa a correção de um problema em seu aplicativo ou biblioteca.

4 - O tipo docs DEVE ser usado quando um commit representa modificações apenas na documentação.

5 - O tipo style DEVE ser usado quando um commit não representa modificações no funcionamento do código (white-space, formatação, etc).

6 - O tipo refactor DEVE ser usado quando um commit não representa nem uma correção de bug, nem a adesão de um recurso novo.

7 - O tipo test DEVE ser usado quando um commit representa modificações apenas no que diz respeito a testes.

8 - O tipo revert DEVE ser usado apenas no contexto de reverter um commit.

9 - Um escopo DEVE consistir no nome da branch atual, que descreve uma seção da base de código entre parênteses, por exemplo, fix(navbar):

10 - Uma descrição DEVE existir depois do espaço após o prefixo tipo/escopo. A descrição é um breve resumo das alterações de código, por exemplo, fix: problema na interpretação do array quando uma string tem vários espaços.

11 - Um corpo de mensagem de commit mais longo PODE ser fornecido após a descrição curta, fornecendo informações contextuais adicionais sobre as alterações no código. O corpo DEVE começar depois de uma linha em branco após a descrição.

12 - Um rodapé de uma ou mais linhas PODE ser fornecido depois de uma linha em branco após o corpo. O rodapé DEVE conter informações adicionais sobre o commit, por exemplo, modificações que quebram a compatibilidade, especificidades, com uma informação adicional por linha.

13 - A modificação que quebra a compatibilidade DEVE ser indicadas logo no início da seção do corpo ou no início de uma linha na seção de rodapé. Uma modificação que quebra a compatibilidade DEVE consistir de um texto em maiúsculas BREAKING CHANGE, seguido por dois-pontos e um espaço.

14 - Uma descrição DEVE ser fornecida após o texto “BREAKING CHANGE:“, descrevendo o que mudou na API, por exemplo, BREAKING CHANGE: as variáveis de ambiente agora têm preferência sobre os arquivos de configuração.

15 - Todas as mensagens de commit DEVEM está em inglês.

16 - Todas as mensagnes do commit DEVEM usar snake case como padrão.

## References

- [Conventional Commits](https://www.conventionalcommits.org/pt-br/v1.0.0-beta.4/#especifica%c3%a7%c3%a3o)
- [Commitizen](https://github.com/commitizen/cz-cli)
- [Commit Lint](https://github.com/conventional-changelog/commitlint)
- [cz-customizable](https://github.com/leonardoanalista/cz-customizable)
