
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
     
     
<details>
<summary>Algoritmo parar passar dados de um componente filho para um componente pai</summary>
     
![image](https://github.com/iuryeng/Estudo_Material_Projeto_Professor_FullStack/assets/38250160/d1eb4ac9-ed7c-4c73-8994-6aa71b468840)
     
</details>


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
<summary>Algoritmo parar passar dados de um componente pai para um componente filho</summary>
     
![image](https://github.com/iuryeng/Estudo_Material_Projeto_Professor_FullStack/assets/38250160/f7036b69-b4e2-4f7f-a8aa-2611287b563c)  
     
</details>

## Exercicio de Fixacao

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

As diretivas em Angular são usadas para manipular o DOM (Document Object Model) e podem ser consideradas como instruções especiais que dizem ao template HTML o que fazer. 

Aqui estão algumas das diretivas mais comuns em Angular:

1. **ngFor**: Esta é uma diretiva estrutural que é usada para renderizar uma lista de elementos. Por exemplo, você pode usar ngFor para exibir uma lista de nomes em uma lista HTML.

2. **ngIf**: Esta é outra diretiva estrutural que é usada para adicionar ou remover um elemento do DOM com base em uma condição. Por exemplo, você pode usar ngIf para exibir uma mensagem de erro apenas se um formulário for inválido.

3. **ngClass**: Esta é uma diretiva de atributo que é usada para adicionar ou remover classes CSS de um elemento com base em uma expressão. Por exemplo, você pode usar ngClass para adicionar uma classe de erro a um campo de formulário se ele for inválido.

4. **ngStyle**: Esta é outra diretiva de atributo que é usada para adicionar ou remover estilos CSS de um elemento com base em uma expressão. Por exemplo, você pode usar ngStyle para alterar a cor de fundo de um elemento com base em uma condição.

5. **ngSwitch**: Esta é uma diretiva estrutural que é usada para adicionar ou remover um grupo de elementos do DOM com base em uma expressão. Por exemplo, você pode usar ngSwitch para exibir diferentes elementos com base no valor de uma variável.

#### Exemplos

```ts
<div *ngFor="let nome of nomes">
  <p>{{ nome }}</p>
</div>

<div *ngIf="formInvalido">
  <p>Formulário inválido!</p>
</div>

<div [ngClass]="{'classe-erro': formInvalido}">
  <p>Este campo é obrigatório</p>
</div>

<div [ngStyle]="{'background-color': corDeFundo}">
  <p>Texto com fundo colorido</p>
</div>

<div [ngSwitch]="valor">
  <p *ngSwitchCase="'valor1'">Valor 1</p>
  <p *ngSwitchCase="'valor2'">Valor 2</p>
  <p *ngSwitchDefault>Valor padrão</p>
</div>
```

💡 Lembre-se de que as diretivas estruturais são sempre prefixadas com um asterisco (*), enquanto as diretivas de atributo não são.

## Exercicio de Fixacao


<details>
<summary>Didatica 1</summary>

![image](https://github.com/iuryeng/Estudo_Material_Projeto_Professor_FullStack/assets/38250160/410ebc9d-dd9c-4ae1-bd73-62464ef5f2c1)
     
</details>

<details>
<summary>Didatica 2</summary>
     
![image](https://github.com/iuryeng/Estudo_Material_Projeto_Professor_FullStack/assets/38250160/61a16937-ed69-4f90-949a-5d4f241ba534)
     
</details>

<details>
<summary>Didatica 3</summary>
     
![image](https://github.com/iuryeng/Estudo_Material_Projeto_Professor_FullStack/assets/38250160/b081b3d7-8eac-4ace-b397-ce0ab1695bf0)
     
</details>


# [Pipes Integrados e Personalizados](#pipes-integrados-e-personalizados)
> :bulb: **Nota:** Aqui, discutiremos o conceito de pipes no Angular e como eles podem ser usados para transformar a saída em nossos templates.

Os Pipes no Angular são uma maneira de escrever transformações de exibição que podem ser usadas em templates HTML. Eles são úteis para formatar dados de maneira consistente em toda a sua aplicação.

Existem dois tipos de pipes que você pode usar em Angular:

1. **Pipes Integrados**: Angular vem com um conjunto de pipes integrados que você pode usar diretamente em seus templates. Alguns exemplos de pipes integrados são:

- date: Formata uma data para uma string com base no formato local ou fornecido.
- uppercase: Transforma o texto em letras maiúsculas.
- lowercase: Transforma o texto em letras minúsculas.
- currency: Transforma um número em uma string de moeda.
- percent: Transforma um número em uma string de porcentagem.

Para usar um pipe integrado, você simplesmente adiciona o pipe (|) seguido pelo nome do pipe e quaisquer argumentos necessários em seu template:

     ```html
     <p>A data de hoje é {{ hoje | date }}</p>
     ```


2. **Pipes Personalizados**: Além dos pipes integrados, Angular também permite que você crie seus próprios pipes personalizados. Isso é útil quando você precisa de uma transformação de exibição que não é fornecida pelos pipes integrados. Para criar um pipe personalizado, você precisa criar uma classe que implementa a interface PipeTransform e fornecer uma implementação para o método transform.

Para criar um pipe personalizado, você precisa definir uma classe que implementa a interface PipeTransform e fornece a lógica de transformação no método transform(). Por exemplo, aqui está um pipe personalizado que transforma um texto em uma string invertida:

  ```ts

   import { Pipe, PipeTransform } from '@angular/core';

     @Pipe({name: 'reverseString'})
     export class ReverseStringPipe implements PipeTransform {
          transform(value: string): string {
          return value.split('').reverse().join('');
          }
     }

   ```

Para usar um pipe personalizado, você precisa adicioná-lo aos declarations em seu módulo Angular e, em seguida, você pode usá-lo em seus templates da mesma maneira que os pipes integrados:

   ```html
     <p>{{ 'Olá, mundo!' | reverseString }}</p>
   ```
     
 
## Exercicio de Fixacao
     
<details>
<summary>Processo de criacao de pipes 1</summary>

![image](https://github.com/iuryeng/Estudo_Material_Projeto_Professor_FullStack/assets/38250160/3c1cc84c-b46e-4373-9ef1-61faed443d77)    
     
    
</details>

<details>
<summary>Processo de criacao de pipes 2</summary>
     
 ![image](https://github.com/iuryeng/Estudo_Material_Projeto_Professor_FullStack/assets/38250160/1321ed86-2e83-4520-a737-eeff9b6ff8b3)

</details>

<details>
<summary>Didatica</summary>     
 
![image](https://github.com/iuryeng/Estudo_Material_Projeto_Professor_FullStack/assets/38250160/d718729e-66fc-483a-aa9a-956f666c9a4f)

</details>







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
