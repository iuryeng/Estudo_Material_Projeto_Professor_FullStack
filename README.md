
# Curso de Angular para iniciantes

Bem-vindo ao mundo do Angular, uma poderosa plataforma de desenvolvimento web criada pelo Google. Angular é uma estrutura de JavaScript de código aberto que é usada para construir aplicações web de página única. Com o Angular, você pode criar aplicações web eficientes, sofisticadas e escaláveis.


## Sumário do Curso de Angular

1. [Introdução ao Angular](#introdução-ao-angular)
2. [Por que Angular?](#por-que-angular)
3. [Primeiro Componente Angular](#primeiro-componente-angular)
4. [@Input e @Output](#input-e-output)
5. [Diretivas: ngFor, ngIf, ngClass, ngStyle, ngSwitch](#diretivas-ngfor-ngif-ngclass-ngstyle-ngswitch)
6. [Pipes Integrados e Personalizados](#pipes-integrados-e-personalizados)
7. [@Injectable e Serviços Personalizados](#injectable-e-serviços-personalizados)
8. [Cliente HTTP - GET, POST, PUT, DELETE](#cliente-http---get-post-put-delete)
9. [Pipe Async](#pipe-async)
10. [Construindo Serviços Personalizados](#construindo-serviços-personalizados)
11. [Buscando e Modificando Dados com Serviço Personalizado](#buscando-e-modificando-dados-com-serviço-personalizado)
12. [Conclusão do Curso e Próximos Passos](#conclusão-do-curso-e-próximos-passos)


## [Introdução ao Angular](#introdução-ao-angular)
> :bulb: **Nota:** Nesta seção, faremos uma introdução ao Angular, discutindo o que é e por que é uma escolha popular para o desenvolvimento de aplicações web

O Angular é conhecido por sua capacidade de tornar as aplicações web mais rápidas e eficientes. Ele faz isso através do uso de componentes, que são essencialmente blocos de construção de código que podem ser reutilizados em toda a sua aplicação. Isso não só torna o código mais fácil de manter, mas também permite que você crie uma interface de usuário mais consistente.

Além disso, o Angular também oferece uma série de outras características poderosas, como data binding bidirecional, injeção de dependência, e uma arquitetura modular que torna mais fácil organizar o seu código e adicionar funcionalidades à sua aplicação ao longo do tempo.

Neste curso, vamos começar do básico e trabalhar nosso caminho até os conceitos mais avançados do Angular. Vamos aprender sobre componentes, diretivas, serviços, e muito mais. Então, se você está pronto para mergulhar no mundo do Angular, vamos começar!

## [Por que Angular?](#por-que-angular)
> :bulb: **Nota:** Aqui, exploraremos as razões pelas quais o Angular é uma escolha popular entre os desenvolvedores, incluindo suas características poderosas e flexibilidade.

Angular é uma escolha popular entre os desenvolvedores por várias razões:

1. **Componentes Reutilizáveis**:  Angular é baseado em componentes, o que significa que você pode reutilizar blocos de código em toda a sua aplicação. Isso torna o código mais fácil de manter e permite que você crie uma interface de usuário mais consistente.

2. **Data Binding Bidirecional**: Angular oferece data binding bidirecional, o que significa que as alterações no modelo de dados são automaticamente refletidas na visualização e vice-versa. Isso torna mais fácil manter a sincronização entre a visualização e o modelo de dados.

3. **Injeção de Dependência**: Angular tem um sistema de injeção de dependência integrado que torna mais fácil reutilizar e testar seu código.

4. **Arquitetura Modular**: Angular é construído em torno de uma arquitetura modular, o que significa que você pode organizar seu código em módulos distintos. Isso torna mais fácil adicionar funcionalidades à sua aplicação ao longo do tempo.

5. **Suporte da Comunidade**: Angular é mantido pelo Google, o que significa que você pode esperar atualizações regulares e suporte da comunidade. Além disso, há uma grande quantidade de recursos de aprendizado disponíveis, incluindo documentação, tutoriais e cursos online.

6. **Desempenho**: Angular é conhecido por seu desempenho. Ele usa o Change Detection para minimizar o número de operações DOM, o que pode melhorar significativamente o desempenho de suas aplicações.

7. **Compatibilidade com Plataformas Múltiplas**: Angular permite que você desenvolva aplicações para várias plataformas, incluindo web, mobile e desktop.


## [Primeiro Componente Angular](#primeiro-componente-angular)
> :bulb: **Nota:** Nesta seção, criaremos nosso primeiro componente Angular e discutiremos a importância dos componentes na arquitetura Angular. 


Criar o primeiro componente Angular é um passo fundamental para começar a trabalhar com essa estrutura. Aqui está um exemplo de como você pode fazer isso:

1. **Instale o Angular CLI**: O Angular CLI é uma ferramenta de linha de comando que você pode usar para criar e gerenciar projetos Angular. 
     
    ```bash
    npm install -g @angular/cli
    ```
2. **Crie um novo projeto Angular**: Use o Angular CLI para criar um novo projeto Angular com o seguinte comando:
    ```
    ng new meu-projeto
    ```
3. **Navegue para o diretório do projeto**: Use o comando cd meu-projeto para navegar para o diretório do seu novo projeto Angular.
   ```bash
    cd meu-projeto
   ```

5. Crie um novo componente: Use o Angular CLI para criar um novo componente com o seguinte comando:
    ```bash
    ng generate component meu-componente
    ```
    
    Isso criará um novo diretório chamado meu-componente dentro do diretório src/app do seu projeto.
    
    ```bash
    meu-projeto/
    └── src/
    └── app/
        └── meu-componente/
            ├── meu-componente.component.ts
            ├── meu-componente.component.html
            ├── meu-componente.component.css
            └── meu-componente.component.spec.ts    
    ```
    
    
5. **Atualize o arquivo do componente**: Abra o arquivo `meu-componente.component.ts` e atualize o conteúdo para definir o comportamento do seu componente criando um método chamado exibirMensagem que retorna a mensagem.

   ```ts
    import { Component } from '@angular/core';

     @Component({
          selector: 'app-meu-componente',
          templateUrl: './meu-componente.component.html',
          styleUrls: ['./meu-componente.component.css']
     })
     export class MeuComponenteComponent {
          mensagem: string;

          constructor() {
               this.mensagem = 'Olá, mundo!';
          }

          exibirMensagem() {
               return this.mensagem;
          }
     }
   ```

6. **Atualize o arquivo de template do componente**: Abra o arquivo `meu-componente.component.html` e atualize o conteúdo para definir a visualização do seu componente. Por exemplo, você pode adicionar um botão que, quando clicado, exibe a mensagem definida no arquivo do componente.

   ```ts
     <button (click)="exibirMensagem()">Clique aqui</button>
     <p>{{ mensagem }}</p>
   ```


7. **Inclua o componente na aplicação**: Finalmente, você precisa incluir o seu novo componente na sua aplicação. Para fazer isso, abra o arquivo `src/app/app.component.html` e adicione a tag do seu componente. A tag do seu componente será o nome do componente em kebab-case (ou seja, com hífens entre as palavras e todas as letras minúsculas). Por exemplo, se o nome do seu componente é MeuComponente, a tag do seu componente será `<app-meu-componente></app-meu-componente>`.
   
   ```html
     <app-meu-componente></app-meu-componente>
   ```

## Exercicio de Fixacao
 
<details>
<summary>Didatica</summary>

![fluxo didatico ](https://github.com/iuryeng/Estudo_Material_Projeto_Professor_FullStack/assets/38250160/24c1a8f4-e072-4378-acdc-593dca027d9d)

</details>

<details>
<summary>Algoritimo de criação do primeiro componente Angular,</summary>

![fluxo de criação do primeiro componente Angular,](https://github.com/iuryeng/Estudo_Material_Projeto_Professor_FullStack/assets/38250160/407ab3ef-604f-493c-9178-23684f40e2eb)

</details> 


## [@Input e @Output](#input-e-output)
> :bulb: **Nota:** Aqui, aprenderemos sobre as propriedades @Input e @Output e como elas facilitam a comunicação entre componentes.

No Angular, a comunicação entre componentes é um aspecto fundamental para criar aplicações interativas. Dois dos principais mecanismos para essa comunicação são as propriedades @Input e @Output.

### @Input

A propriedade @Input permite que você passe dados de um componente pai para um componente filho. Por exemplo, se você tem um componente que exibe uma mensagem e você quer que essa mensagem seja personalizável, você pode usar @Input para passar a mensagem do componente pai para o componente filho.

#### Exemplos de como usar @Input

1. **Defina a propriedade @Input no componente filho**: No arquivo do componente filho (por exemplo, filho.component.ts), defina a propriedade @Input. 

     ```ts
     import { Component, Input } from '@angular/core';

     @Component({
          selector: 'app-filho',
          template: `<p>{{ mensagem }}</p>`,
     })
     export class FilhoComponent {
          @Input() mensagem: string;
     }
     ```

2. **Passe dados para a propriedade @Input no template do componente pai**: No template do componente pai (por exemplo, pai.component.html), passe dados para a propriedade @Input do componente filho:

     ```ts
     <app-filho [mensagem]="'Olá, mundo!'"></app-filho>
     ```

### @Output

A propriedade @Output, por outro lado, permite que um componente filho envie dados de volta para um componente pai. Isso é útil quando você tem um componente filho que precisa notificar o componente pai de alguma ação, como um botão sendo clicado. @Output é normalmente usado em conjunto com EventEmitters para emitir eventos personalizados.

#### Exemplos de como usar @Output

1. **Defina o evento @Output no componente filho**: No arquivo do componente filho (por exemplo, filho.component.ts), defina o evento @Output:

     ```ts
     import { Component, Output, EventEmitter } from '@angular/core';

     @Component({
          selector: 'app-filho',
          template: `<button (click)="enviarEvento()">Clique em mim</button>`,
     })
     export class FilhoComponent {
          @Output() evento = new EventEmitter<string>();

          enviarEvento() {
               this.evento.emit('Olá, mundo!');
          }
     }

     ```
     
2. **Escute o evento @Output no template do componente pai**: No template do componente pai (por exemplo, pai.component.html), escute o evento @Output do componente filho:

     ```ts
     <app-filho (evento)="tratarEvento($event)"></app-filho>
     ```

3. **Trate o evento @Output no componente pai**: No arquivo do componente pai (por exemplo, pai.component.ts), trate o evento @Output do componente filho:

      ```ts
      import { Component } from '@angular/core';

     @Component({
          selector: 'app-pai',
          template: `<app-filho (evento)="tratarEvento($event)"></app-filho>`,
     })
     export class PaiComponent {
          tratarEvento(mensagem: string) {
          console.log(mensagem);
        }
     }

 
     ```




<details>
<summary>Didatica 1</summary>
     
![image](https://github.com/iuryeng/Estudo_Material_Projeto_Professor_FullStack/assets/38250160/73a7a8e1-92e5-49f6-a9d2-2f85b1b6852d)
     
</details>


<details>
<summary>Didatica 2</summary>

![image](https://github.com/iuryeng/Estudo_Material_Projeto_Professor_FullStack/assets/38250160/8e578b96-8439-451c-9809-fac606f67e4e)     


</details>







## [Diretivas: ngFor, ngIf, ngClass, ngStyle, ngSwitch](#diretivas-ngfor-ngif-ngclass-ngstyle-ngswitch)
> :bulb: **Nota:** Nesta seção, exploraremos algumas das diretivas mais comuns no Angular e como elas podem ser usadas para manipular o DOM.

## [Pipes Integrados e Personalizados](#pipes-integrados-e-personalizados)
> :bulb: **Nota:** Aqui, discutiremos o conceito de pipes no Angular e como eles podem ser usados para transformar a saída em nossos templates.

## [@Injectable e Serviços Personalizados](#injectable-e-serviços-personalizados)
> :bulb: **Nota:** Nesta seção, aprenderemos sobre a decoração @Injectable e como criar nossos próprios serviços no Angular.

## [Cliente HTTP - GET, POST, PUT, DELETE](#cliente-http---get-post-put-delete)
> :bulb: **Nota:** Aqui, exploraremos o cliente HTTP do Angular e como ele pode ser usado para fazer solicitações GET, POST, PUT e DELETE.

## [Pipe Async](#pipe-async)
> :bulb: **Nota:** Nesta seção, discutiremos o pipe async e como ele pode ser usado para lidar com operações assíncronas no Angular.

## [Construindo Serviços Personalizados](#construindo-serviços-personalizados)
> :bulb: **Nota:** Aqui, aprenderemos como construir nossos próprios serviços no Angular e como eles podem ser usados para encapsular a lógica de negócios.

## [Buscando e Modificando Dados com Serviço Personalizado](#buscando-e-modificando-dados-com-serviço-personalizado)
> :bulb: **Nota:** Nesta seção, discutiremos como podemos usar nossos serviços personalizados para buscar e modificar dados.

## [Conclusão do Curso e Próximos Passos](#conclusão-do-curso-e-próximos-passos)
> :bulb: **Nota:** Finalmente, concluiremos o curso e discutiremos os próximos passos para continuar aprendendo e melhorando suas habilidades no Angular.
