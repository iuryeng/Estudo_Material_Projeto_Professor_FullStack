### 1. Configuração do Ambiente de Desenvolvimento e Introdução ao Angular (Duração: 15 mins)

  Instale o Angular CLI e crie um novo projeto Angular chamado "3DPrinterStore". Explore a estrutura do projeto e familiarize-se com os principais arquivos e diretórios.

### 2. Por que Angular? Principais Recursos e Vantagens (Duração: 15 mins)

  Discuta as vantagens do Angular e como elas se aplicam ao projeto da loja de impressoras 3D. Por exemplo, a arquitetura baseada em componentes pode ser usada para criar componentes reutilizáveis para a lista de produtos, carrinho de compras, etc.

### 3. Construindo Seu Primeiro Componente Angular (Duração: 15 mins)

  Crie um componente "ProductList" que exibe uma lista de impressoras 3D. Use a diretiva *ngFor para exibir cada produto na lista.

### 4. Entendendo @Input e @Output, Event Emitters (Duração: 15 mins)

  Adicione um botão "Adicionar ao carrinho" a cada produto na lista. Use @Output e EventEmitter para emitir um evento quando o botão é clicado, e @Input para passar os detalhes do produto do componente "ProductList" para um componente "Cart".

### 5. Explorando Diretivas Principais: ngFor, ngIf, ngClass, ngStyle, ngSwitch (Duração: 15 mins)

  Use a diretiva *ngIf para mostrar uma mensagem quando o carrinho está vazio. Use ngClass ou ngStyle para alterar a aparência dos produtos que estão no carrinho. Use ngSwitch em um componente de detalhes do produto para mostrar diferentes informações com base no tipo de impressora 3D.

### 6. Usando Pipes Integrados e Criando Pipes Personalizados (Duração: 15 mins)

  Use o pipe de moeda integrado para formatar os preços dos produtos. Crie um pipe personalizado que converte as descrições dos produtos para letras maiúsculas.

### 7. Introdução a @Injectable e Serviços Personalizados (Duração: 15 mins)

  Crie um serviço "CartService" que gerencia os produtos no carrinho. Use @Injectable para permitir que este serviço seja injetado em outros componentes.

### 8. Cliente HTTP - GET, POST, PUT, DELETE (Duração: 15 mins)

  Adicione um backend à sua aplicação usando o pacote json-server. Use o serviço HttpClient do Angular para obter produtos do servidor e adicionar novos produtos ao carrinho.

### 9. Entendendo o Pipe Async (Duração: 15 mins)

  Use o pipe Async para lidar automaticamente com a subscrição e cancelamento de subscrição de Observables ao obter produtos do servidor.

### 10. Construindo Serviços Personalizados (Duração: 15 mins)

  Crie um serviço "ProductService" que encapsula a lógica para obter produtos do servidor.

### 11. Buscando e Modificando Dados com o Serviço Personalizado (Duração: 15 mins)

  Use o "ProductService" em seu
