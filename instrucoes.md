# Prova do terceiro trimestre para os segundos anos:
Os alunos ao longo do trimestre trabalharam no projeto de uma Landing Page para o jogo criado nas disciplinas dos professores Sílvio Romero e Ju Caldas. Neste ponto do projeto é esperado que a aplicação possua as páginas "Home", "Galeria" e "Sobre a equipe", bem como ter implementada uma classe para os Assinantes ou PessoasInscritas para receber notícias sobre o projeto. Caso este não seja o caso para sua aplicação, consulte o projeto base no link: https://github.com/VicCAlq/basePagina

Para os alunos que não completaram o projeto, será disponibilizada uma base onde poderão trabalhar em cima, mas neste caso a nota máxima para o aluno será seis (6), enquanto que para os alunos que usaram o próprio projeto, estes podem chegar a nota dez (10). Alternativamente, podem utilizar seu próprio projeto e tentar implementar as partes que faltaram se baseando no projeto base (o basePagina do link acima).

A prova consistirá em atividades de desenvolvimento de funcionalidades para a aplicação, sendo uma (1) delas obrigatória, valendo metade da nota, e mais duas atividades a escolha do aluno dentre quatro opções. Seguem as regras abaixo quanto as atividades:

1. Uma atividade ***obrigatória*** valendo cinco (5) pontos. Esta atividade tem duas partes "bônus", que são chance para ponto extra: meio (0,5) ponto cada.
2. Quatro (4) atividades, das quais o aluno poderá escolher duas (2) para realizar
3. Cada uma das atividades opcionais vale dois e meio (2,5) pontos.
4. A nota máxima do aluno para as atividades opcionais é de cinco (5) pontos, ***independente*** de quantas o aluno fizer. Ex: Se o aluno fizer três (3) questões opcionais, a nota máxima possível para estas questões é de cinco (5) pontos.

## Lista de atividades
### Obrigatória (5 pontos) (3 pontos para quem usar projeto disponibilizado pelo professor)

No momento, a implementação das mensagens a serem enviadas para os assinantes foi implementada como uma lista de objetos, onde cada objeto tem o formato `{ mensagem: string, data: Date }`. Apesar de eficaz, gera _muita_ duplicação: Nós provavelmente queremos enviar as mesmas mensagens para todo mundo.

Para solucionar isso, crie um arquivo para a classe "Email", em formato TypeScript (arquivo terminado em .ts). Ela deve receber em seu constructor os seguintes argumentos:

- remetente: `string`. É o email de nosso projeto, podem usar algo como "nome_do_meu_jogo@nave.org.br", obviamente substituindo "nome_do_meu_jogo" pelo nome de seu jogo, usando underlines ( _ ) para separar palavras. O jogo pode ser inventado.
- destinatarios: Lista de strings (declarado como `string[]` ou `Array<string>`). Lista com os emails dos assinantes que receberão a mensagem.
- conteudo: `string`. É o conteúdo em texto da mensagem.
- assinatura: `string`. Vai ser a assinatura presente em todas as mensagens.
- dataEnvio: `Date`. É a data para quando o email estará agendado.

Esta classe também precisará de quatro métodos:

1. adicionarDestinatario(destinatario: string). Recebe um email (argumento destinatario) e adiciona este email na lista de destinarários.
2. removerDestintario(destinatario: string). Recebe um email, e o email da lista this.destinatarios que for igual ao email recebido pelo método deve ser removido da lista.
3. alterarConteudo(novoConteudo: string). Recebe um texto com o novo conteúdo e modifica o valor de this.conteudo para o novo valor.
4. alterarData(novaData: Date). Recebe nova data e modifica o valor de this.dataEnvio para o novo valor.


Para criarmos os objetos utilizando a classe que vocês fizerem acima, usaremos a classe da forma abaixo:
```javascript
const meuEmail = new Email(
    "meu_jogo@nave.org.br",
    ["primeiro@gmail.com"], // Pode começar como uma lista vazia: []
    "Bem-vindo/a! Obrigado por assinar as notícias de nosso jogo!",
    "<p>Fique atento para mais!</p> <p>Equipe JogoMassa</p>", // Podemos usar HTML nos textos
    new Date("2026-01-10")
) // Ordem dos argumentos: remetente, destinatarios, conteudo, assinatura, dataEnvio
```

(bônus) Ponto extra para quem estiver com o código organizado com boa indentação (o espaçamento de código antes de cada linha, para indicar se algum código é parte interna de outra coisa).

Consultem exemplos de indentação no material de apoio, em especial no arquivo "js_7_classes_em_typescript"

### Livre-escolha (2,5 pontos cada) (1,5 pontos para quem usar projeto disponibilizado pelo professor)

1. (Foco em OOP) Modificar a função "adicionarDestinatário" para também poder receber uma lista de emails:
    - Se ela receber uma única string, adiciona essa string a lista this.destinatarios
    - Se ela receber uma lista de strings, percorre essa lista em um loop e adiciona cada item a lista this.destinatarios

2. (Foco em OOP) Modificar a função "removerDestinatario" para também poder receber uma lista de emails:
    - Se ela receber uma única string, mantém o funcionamento inicial
    - Se ela receber uma lista de strings, percorre a lista this.destinatarios, e para cada destinatário existente verifica se o destinatário existente é igual a algum dos destinatários da lista a serem removidos, e caso seja igual, remove.

3. (Foco em HTML) Criar um componente representando uma página de "Como jogar", onde deve ser descrito como o jogo funciona.

4. (Foco em HTML) Criar um componente representando um rodapé na página, sendo exibido independente do conteúdo a mostra no site (ou seja, fica visível na página Home, Galeria, Sobre, etc). Este rodapé deve conter os nomes de sua equipe (a que fez o jogo, não o site), e estes nomes devem ser links (uma tag "âncora", ou `<a>`) para o email de seu jogo (se não tiver um email, pode inventar, exemplo: "detona.na.lona@nave.org.br").

# Instruções de envio

1. Se tiver uma pasta chamada node_modules no projeto, apague.
2. Compacte a pasta contendo seu código
3. Envie o arquivo compactado no classroom

# Boa sorte

