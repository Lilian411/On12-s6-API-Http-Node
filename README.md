# On12-TodasEmTech-s6-Introducao-Node
Turma Online 12 - Todas em Tech | Back-end | 2021 | Introdução à API:
HTTP e NodeJS

## Para o lar
Abra o PullRequest Respondendo as seguintes questões:

1) Qual a relação entre os métodos HTTP e o CRUD?

O protocolo HTTP define um conjunto de métodos de requisição responsáveis por indicar a ação a ser executada para um dado recurso. Também chamados de Verbos HTTP, são:

Get: Requisições que utilizam esse método retornam apenas dados.

Head: Este método solicita uma resposta de forma idêntica ao método GET, porém sem conter o corpo da resposta.

Post: Este método submete uma entidade a um recurso específico, causando uma mudança no estado do recurso ou efeitos colaterais no servidor.

Put: Este verbo substitui todas as atuais representações do recurso de destino pela carga de dados da requisição.

Delete: Verbo que remove um recurso específico.

Connect: O método que estabelece um túnel para o servidor identificado pelo recurso de destino.

Options: Este verbo é usado para descrever as opções de comunicação com o recurso de destino.

Trace: Método que executa um teste de chamada loop-back junto com o caminho para o recurso de destino.

Patch: Este método é utilizado para aplicar modificações parciais em um recurso.

​ Enquanto o HTTP trafega ente o Frontend e o Backend, o CRUD trafega entre o Backend e o Banco de dados. 
CRUD é um acrónimo na língua inglesa (Create, Read, Updata, Delete), que são as quatro operações básicas relacionada a base de dados.

Create - Criação, relaciona-se ao método Post do HTTP;

Read - Consulta, relaciona-se ao verbo Get do HTTP;

Updata - Atualização, relaciona-se aos verbos PUT e Patch do HTTP;

Delete - Destruição, relaciona-se ao método Delete do HTTP.


2) Comente, com exemplos, a diferença entre o PUT e o PATCH.

Tanto o Put, quanto o Patch promovem atualização no conteúdo.
 Enquanto o Put substitui toda a informação do recurso pela informação da requisição,
 o Patch realiza a alteração parcial do recurso, atualiza apenas a modificação.

3) Assim como na aula, apresente os dados dos JSONs no console 
    - No colors-rgb.js apresente o nome da cor e o codigo RGB como no exemplo: "gainsboro - rgb(220, 220, 220, 1)"
    - No estados-cidade.js apresente o nome do Estado, a sigla e todas as cidadades, sem arrays aparentes no console
    - No filmes.js apresente titulo, plot, generos e lingua. Genero e lingua devem ser apresentados em arrays no console.

4) Defina o conceito de idempotência e como uma API pode ser idempotente

conceito de idempotência:
Propriedade que algumas operações têm de poderem ser aplicadas várias vezes sem que o valor do resultado seja alterado após a aplicação inicial.
A idempotência tem esse significado na matemática e na ciência da computação.

Quando falamos em idempotência em API’s REST, podemos concluir que os seguintes os verbos:
GET, PUT, DELETE, HEAD e OPTIONS são idempotentes.
POST não é idempotente.

No contexto das APIs REST, quando fazer várias solicitações idênticas tem o mesmo efeito que fazer uma única solicitação - essa API REST é chamada de idempotente .

Ao projetar APIs REST, você deve perceber que os consumidores de API podem cometer erros. Os usuários podem escrever o código do cliente de forma que possa haver solicitações duplicadas chegando à API.

Essas solicitações duplicadas podem ser não intencionais, bem como intencionais em algum momento (por exemplo, devido a tempo limite ou problemas de rede). Você deve projetar APIs tolerantes a falhas de forma que as solicitações duplicadas não deixem o sistema instável.

Um método HTTP idempotente é um método HTTP que pode ser chamado muitas vezes sem resultados diferentes. Não importaria se o método fosse chamado apenas uma ou dez vezes. O resultado deve ser o mesmo.
Idempotência significa essencialmente que o resultado de uma solicitação executada com sucesso é independente do número de vezes que ela é executada. Por exemplo, em aritmética, adicionar zero a um número é uma operação idempotente.

Idempotência com métodos HTTP
Se você seguir os princípios REST ao projetar API, terá APIs REST idempotentes para métodos GET, PUT, DELETE, HEAD, OPTIONS e TRACE HTTP. Apenas POSTAPIs não serão idempotentes.

POST NÃO é idempotente.
GET, PUT, DELETE, HEAD, OPTIONSE TRACEsão idempotent.
Vamos analisar como os métodos HTTP acima acabam sendo idempotentes - e por que o POST não é.

HTTP POST
Geralmente - não necessariamente - as POSTAPIs são usadas para criar um novo recurso no servidor. Portanto, ao invocar a mesma solicitação POST N vezes, você terá N novos recursos no servidor. Portanto, o POST não é idempotente .

HTTP GET, HEAD, OPTIONS e TRACE
GET, HEAD, OPTIONSE TRACEmétodos NUNCA alterar o estado dos recursos no servidor. Eles são puramente para recuperar a representação do recurso ou metadados naquele ponto do tempo. Portanto, invocar várias solicitações não terá nenhuma operação de gravação no servidor, portanto , GET, HEAD, OPTIONS e TRACE são idempotentes .

HTTP PUT
Geralmente - não necessariamente - as PUTAPIs são usadas para atualizar o estado do recurso. Se você invocar uma PUTAPI N vezes, a primeira solicitação atualizará o recurso; em seguida, as solicitações N-1 restantes apenas sobrescreverão o mesmo estado de recurso repetidas vezes - efetivamente sem alterar nada. Portanto, PUT é idempotente .

HTTP DELETE
Ao invocar N DELETEsolicitações semelhantes , a primeira solicitação excluirá o recurso e a resposta será 200 (OK)ou 204 (No Content). Outras solicitações N-1 retornarão 404 (Not Found). Claramente, a resposta é diferente da primeira solicitação, mas não há mudança de estado para nenhum recurso no lado do servidor porque o recurso original já foi excluído. Portanto, DELETE é idempotente .

Lembre-se de que alguns sistemas podem ter DELETE APIs como esta:

DELETE / item / last
No caso acima, chamar a operação N vezes excluirá N recursos - portanto, DELETEnão é idempotente neste caso. Nesse caso, uma boa sugestão pode ser alterar a API acima para POST - porque POST não é idempotente.

POST / item / último
Agora, isso está mais próximo da especificação HTTP - portanto, mais compatível com REST.





5) Cite alguns diferentes padrões de projetos de software



Criacionais: padrões que propõem soluções flexíveis para criação de objetos. São eles: Abstract Factory , Factory Method, Singleton , Builder  e Prototype.

Estruturais: padrões que propõem soluções flexíveis para composição de classes e objetos. São eles: Proxy , Adapter , Facade , Decorator , Bridge, Composite e Flyweight.

Comportamentais: padrões que propõem soluções flexíveis para interação e divisão de responsabilidades entre classes e objetos. São eles: Strategy (6.8), Observer , Template Method , Visitor , Chain of Responsibility, Command, Interpreter, Iterator , Mediator, Memento e State.