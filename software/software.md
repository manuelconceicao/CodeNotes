Estudo software

#  

Índice

[Notas da matéria Software. 2](#_Toc36309163)

[Processo de desenvolvimento de software. 2](#_Toc36309164)

[Q: Quais são algumas considerações a ter no desenvolvimento de software?. 2](#_Toc36309165)

[Q: Quais são os Métodos, modelos e processos para o desenvolvimento de  software?. 4](#_Toc36309166)

[Q: O que é o modelo clássico?. 5](#_Toc36309167)

[Q: O que são os modelos iterativos?. 6](#_Toc36309168)

[DDD - Domain Driven Design. 6](#_Toc36309169)

[Q: Quais são os conceitos básicos de Domain Driven Design (DDD)?. 6](#_Toc36309170)

[Q: O que é uma Entidade / Entity?. 6](#_Toc36309171)

[Q: O que é um Objeto-Valor / Value Object (VO)?. 7](#_Toc36309172)

[Q: O que é um agregado/agregate?. 7](#_Toc36309173)

[Q: O que é um private package e uma class Protected?. 7](#_Toc36309174)

[Q: Como referenciar um objeto de outra classe?. 7](#_Toc36309175)

[Q: O que é um repositório?. 7](#_Toc36309176)

[Bibliografia. 9](#_Toc36309177)

 

 



 

Notas da matéria Software

 

# Processo de desenvolvimento de software 

 

Fonte: ESOFT 2015-2016 Processo de Desenvolvimento de Software (2016-05-23)

 

## *Q: Quais são algumas considerações a ter no desenvolvimento de software?*

Ø Comunicação

o  Cliente por vezes não sabe o que quer do software

o  Dificuldade em criar prioridades

o  Dificuldade em estimar o tempo de desenvolvimento

o  Dificuldade de manutenção

Ø Software é distinto de outros produtos

o  É intangível

o  Flexível

o  Não é estandardizado

o  Eng software não é uma disciplina formal como outras engenharias (civil, mecância, etc) 

o  Grande parte do custo do software está na fase de manutenção

Ø O que faz um bom software? 

o  Correção / Correctness: Grau em que o software adere aos requisitos

o  Portabilidade / Portability: A facilidade com que o software pode ser usado com configurações de diferentes computadores

o  Re-usabilidade / Reusability: A facilidade com que com que cada software pode ser reutilizado no desenvolvimento de outro software

o  Robustez / Reliability: A frequência e gravidade das falhas do software, sendo uma falha um comportamento inaceitável do software dentro das condições de operação estabelecidos

o  Manutibilidade / Maintainability: a facilidade com que se pode realizar alterações ao software para cumprir novos requisitos ou corrigir deficiências

o  Eficiência / Eficiência: grau com que o software cumpre o seu propósito sem desperdiçar recursos.

Ø Alguns dos problemas de desenvolvimento software:

o  Negócio mal entendido

o  Alterações de negócio

o  Taxas de defeito altas

o  Sistema desatualizado 

o  Escalonamento desliza (entrega tardia e custos ultrapassam o orçamentado)

Ø Necessidade de criação engenharia software

o  Introdução de métodos

o  Disciplina na criação de software

o  Desenvolvimento mais efetivo e eficiente

 

**C:** O desenvolvimento de software tem desafios um pouco diferentes das outras engenharias. Devido à natureza digital do software, à sua flexibilidade e intangibilidade, torna-se difícil planear, comunicar e conceber um software que cumpra os requisitos do cliente. 

Um dos desafios no desenvolvimento de software é a comunicação entre o cliente e os desenvolvedores. Muitas vezes o cliente não sabe comunicar o que quer ou não sabe bem o que quer ou não sabe comunicar corretamente o que pretende. Isto acarreta vários problemas, nomeadamente na obtenção dos requisitos. É muito importante entender bem o negócio. 

Para além das falhas de comunicação do negócio, também existem constantes alterações de negócio, ou seja, alterações dos requisitos de negócio para satisfazer as pretensões do cliente. Isto é algo normal no desenvolvimento de software e decorre da natureza da comunicação entre o cliente e a equipa de desenvolvimento. Como foi referido anteriormente, muitas vezes o cliente não sabe bem o que quer e acrescenta, altera ou retira requisitos ao negócio. É necessário o desenvolvimento do software acompanhar a vontade do cliente. É necessário atualizar o sistema. Isto também acontece com a manutenção do software, mesmo após este já ter sido entregue. Por vezes os clientes querem novas features ou querem alterar alguns dos requisitos. 

No desenvolvimento de software as taxas de defeito são muito elevadas. Por esta razão, é necessário realizar testes para certificar que o software é desenvolvido com o mínimo de defeitos possível. Também sucedem muitos deslizes de orçamento e de escalonamento. 

Para obter um bom software – isto é, um software funcional e que vá ao encontro dos requisitos do cliente – é necessário que o software cumpra certos requisitos, entre eles: 

Correção – grau em que o software adere aos requisitos;

Portabilidade – grau em que o software pode ser utilizado em diferentes configurações de computadores; 

Re-usabilidade – grau em que o software pode ser reaproveitado para desenvolver outro software; 

Robustez – grau de confiabilidade do software, ou seja, a frequência e gravidade das falhas que este apresenta dentro das condições de condições de normais de operação estabelecidas; 

Manutibilidade – grau de dificuldade com que se pode fazer alterações ao software, seja por necessidade de adicionar novos requisitos ao software ou por necessidade de corrigir deficiências. 

Eficiência – grau de recursos necessário para o software cumprir a sua função

Estes problemas levaram à criação da disciplina de Eng. Software. Para tornar o desenvolvimento de software mais estandardizado e obter um bom software, cumprindo com os pontos acima. Os custos de manutenção e a fiabilidade do software dependem do grau que se cumpre estes pontos.

 

**
**

 

### Q: Quais são os Métodos, modelos e processos para o desenvolvimento de software?

Ø Nos anos 70:

o  Métodos baseados noutras engenharias

Ø Nos anos 90:

o  Métodos ágeis e iterativos 

Ø Saber uma linguagem de programação não é suficiente para criar um bom software

Ø Fases do processo de desenvolvimento de software:

o  Requisitos: Levantamento de requisitos

o  Análise: Investigação do problema

o  Design: Solução logica

o  Implementação: Código

Ø Outras ferramentas para o desenvolvimento de software:

o  Documentação e partilha de informação (e.g. UML)

o  Testes

§ Unitários

§ Funcionais

§ De integração

§ De aceitação

o  Boas práticas de análise, design…

o  Fator humano

§ Trabalho em equipa (soft skill)

§ Capacidades de comunicação (soft skill)

Ø Foram criadas praticas que sistematizam o desenvolvimento de software e organizam o processo. 

Ø Modelo clássico:

o  Modelo Cascata

o  Processos Sequenciais

o  Processo Preditivo

Ø Modelos Iterativos

o   

**C:** 

 

**
**

 

### Q: O que é o modelo clássico? 

Ø Modelo em cascata é também chamado modelo “Waterfall”

Ø Desenvolvimento de software em que os processos são realizados de forma sequencial.

Ø Nos processos sequencias existe o BRUF: Big Requirements Up-Front (requisites a seguir), Design baseado nos requisites e a implementação baseada no design e é realizada a Integração de módulos.

Ø No Processo Preditivo primeiro desenha-se, depois constrói-se. O projeto segue o plano.

Ø  As vantagens do modelo clássico é que pode ser usado em projetos de qualquer tamanho, Requisitos são claros e concretos, Documentação é produzida em todas as fases.

Ø  As desvantagens do modelo clássico e que não é apropriado para software que não tenha todos o requisitos, feedback do cliente é muito tardio e só ocorre no final do desenvolvimento e não aborda primeiro as situações de risco.

 

**C:** O modelo clássico foi o primeiro modelo de desenvolvimento de software – utilizado de forma informal e baseado em outras engenharias – baseado sobretudo no modelo em cascata (waterfall). Neste modelo de desenvolvimento de software em cascata os processos de desenvolvimento são realizados de forma sequencial. Inicialmente são propostos os requisitos e realizada toda a documentação para o software. Utiliza um processo predativo em que se antecipa todo o desenvolvimento na fase de planeamento. Não existe iteração. Ou seja, primeiro planeia-se o software, depois segue-se o plano. A vantagem deste modelo é que os requisitos, quando possível, são claros e concretos e que se sabe desde a fase inicial como é que o software vai ficar. A desvantagem é que devido à sua rigidez, não se pode realizar modificações a meio do desenvolvimento do software. 

 



 

### Q: O que são os modelos iterativos?

Ø Os modelos iterativos focam-se no prioritário para entregar o trabalho a tempo, os clientes fazem parte do desenvolvimento (dão feedback), testes automatizados para reduzir falhas, têm sprints que demonstrem o trabalho realizado com código funcional, promovem design simples e modular que possa ser refactored, facilmente se pode alterar, substituir e mudar prioridades (alterar o negócio).

Ø Também conhecidos como Incremental, evolutivo, espiral.

Ø Os modelos iterativos tem como objetivo produzir versões do software até este ir ao encontro do pretendido.

Ø As vantagens dos modelos iterativos é que é possível lidar com requisitos evolutivos, que mudem ao longo do processo e obter feedback dos clientes, Permite alterações ao código, Torna-se mais fácil identificar os problemas, Têm uma arquitetura mais robusta pois podem ser avaliados e testados ao longo do processo e facilitam a compreensão do negócio mais cedo (olha-se para a floresta e não apenas para a árvore).

Ø Exemplos de modelos iterativos:

o  Cascata modificado

o  Espiral

o  Unified Process (UP)

o  eXtreme Programming (XP)

o  Scrum

o  Chrystal

o  Lean Development

**C:**

 

 

# DDD - Domain Driven Design 

 

### Q: Quais são os conceitos básicos de Domain Driven Design (DDD)? 

Fonte: software II 03/02/2020

Ø Atribuição de responsabilidades.

Ø Atribuir a responsabilidade a agregados em que uma das classes é root e as outras entity. Para aceder aos agregado é necessário passar pela classe root.

 

**C:** DDD atribui responsabilidades a classes e forma agregados de classes que podem ser root ou entity. Para aceder a uma classe entity de um agreagado é necessário aceder à interface de uma agregado, o root. E.G. :  Agregado Pessoa tem a classe Pessoa como root, ListOfAccounts como entity e Account como entity. Para aceder a ListOfAccounts é necessário aceder à interface do agregado Pessoa, que vai ter acesso a pessoa a por sua vez às classes acopladas a Pessoa, ListOfAccounts e Account. Pessoa tem a responsabilidade.

 

 

### Q: O que é uma Entidade / Entity?

Fonte: software II 03/02/2020

Ø Entidade faz parte de negócio

Ø Tem ciclo de vida (estado)

Ø Não utiliza primitivos nos atributos mas sim objetos-valor

Ø Pertence a um único agregado.

 

**C:** Segundo DDD, uma entidade é um objeto que faz parte do negócio. Uma entidade não pode ter como atributos  primitivos mas sim objetos valor (tipo de classe criado). As entidades tem um ciclo de vida. Uma entidade só pertence a uma agregado de classes. E.G de uma entidade no programa App gestão finanças é  a classe Account.

 

### Q: O que é um Objeto-Valor / Value Object (VO)? 

Fonte: software II 03/02/2020

Ø Imutável

Ø Não tem identidade negócio

Ø Partilhável entre entidades e agregado

Ø Pure Fabrication ??? 

 

**C:** Um value object é uma classe que serve de atributo a uma entidade. Estas classes contém os atributos primitivos. Podem ser partilhadas entre várias entidades e agregação. Um value-object é imutável. 

 

### Q: O que é um agregado/agregate?

 Fonte: software II 03/02/2020

Ø Conjunto de entidades e objetos-valor e as suas relações

Ø Um agregado tem uma classe root que dá o nome ao agregado. É também composto por entidades que são classes que fazem parte do negócio

**C:**

 

### Q: O que é um private package e uma class Protected?

 

### Q: Como referenciar um objeto de outra classe? 

Fonte: software II 03/02/2020

Ø Deixa-se de refeênciar um objecto de uma classe de outro agragado diretamente

Ø Para se referênciar um objecto de uma classe de outro agregado é necessário utilizar a interface disponibilizada pelo agregado na classe root (e.g. Pessoa).

Ø Para identificar o objeto de outra classe é necessário recorrer a Id’s que são VOS (Value-objects)

### Q: O que é um repositório? 

Fonte: software II 03/02/2020

Ø Serve para aceder a objetos

Ø Representa uma lista de objetos de uma raiz (root)

Ø Responsável pela persistência (armazenamento e pesquisa de dados)

Ø Existe um repositório por agragado (e.g. agregado Livro razão tem um repositório livro razão)

Ø Ver Diagrama de classes (Fonte: software II 03/02/2020)

Por terminar!!!!!!!!!!!!!!!

C: Um repositório serve para armazenar e aceder objectos. Cada agragado tem um repositório. Estes servem para encontrar objetos do agregado. 

 

 

 

 

 

 

 

 

 



 

# Bibliografia

Powerpoint: ESOFT 2015-2016 Processo de Desenvolvimento de Software (2016-05-23)

 