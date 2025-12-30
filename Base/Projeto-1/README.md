1. ⚙️ Ambiente e Estrutura de Pastas
   A organização clara das pastas é fundamental para a manutenibilidade e escalabilidade do projeto.

1.1. Estrutura Padrão
Geralmente, adotamos uma estrutura que separa os tipos de arquivos para fácil localização:

/
├── index.html // Arquivo principal de entrada
├── /css
│ ├── style.css // Folha de estilo principal
│ └── reset.css // Estilos para padronização entre navegadores (opcional)
├── /img
│ ├── logo.png // Imagens estáticas (logos, ícones)
│ ├── background.jpg // Imagens de fundo
│ └── icon // Subpasta para ícones (opcional)
└── README.md
/img: Contém todos os recursos visuais do projeto, como imagens, ícones e vetores. A separação ajuda a otimizar o carregamento e a gerenciar caminhos.

/css: Armazena as folhas de estilo (arquivos .css).

index.html: O ponto de entrada principal, que linca todos os recursos das pastas acima.

2. ✨ Aplicação de Estilo no HTML
   Existem três formas principais de aplicar estilo a um documento HTML. A forma recomendada para projetos profissionais é a Folha de Estilo Externa.

2.1. Folha de Estilo Externa (Recomendado)
O estilo é definido em um arquivo .css separado (ex: style.css).

É linkado no <head> do HTML usando a tag <link>.

Vantagem: Limpeza do código HTML, reutilização de estilos em múltiplas páginas e melhor separação de responsabilidades (HTML para estrutura, CSS para apresentação).

HTML

<link rel="stylesheet" href="css/style.css">
2.2. Estilo Interno
O estilo é definido dentro da tag <style> no <head> do documento HTML.

Uso: Estilos específicos para aquela página que não serão usados em outro lugar.

Desvantagem: Não pode ser reutilizado em outras páginas.

HTML

<head>
    <style>
        h1 { color: blue; }
    </style>
</head>
2.3. Estilo Inline
O estilo é aplicado diretamente em um elemento HTML usando o atributo style.

Uso: Apenas em exceções muito raras, para estilos dinâmicos gerados por JS, ou testes rápidos.

Desvantagem: Mistura apresentação com estrutura, dificulta a manutenção e tem a maior especificidade, dificultando a sobrescrita.

HTML

<p style="color: red; font-size: 16px;">Este é um parágrafo.</p>
3. 🏷️ Tags Semânticas vs. Não Semânticas
A escolha das tags HTML afeta a acessibilidade, o SEO (Otimização para Mecanismos de Busca) e a clareza do código.

3.1. Tags Semânticas (Recomendado)
Tags que carregam um significado claro sobre o propósito do seu conteúdo para o navegador e para os desenvolvedores.

Exemplos:

<header>: Introdução ou grupo de links de navegação.

<nav>: Contém links de navegação principal.

<main>: Conteúdo principal, único na página.

<section>: Um agrupamento temático de conteúdo.

<article>: Conteúdo autônomo e independente (ex: post de blog).

<footer>: Informações de rodapé, direitos autorais.

Benefício: Ajuda leitores de tela (acessibilidade) e motores de busca (SEO) a entender a hierarquia e o contexto da página.

3.2. Tags Não Semânticas
Tags que não transmitem significado sobre o tipo de conteúdo que contêm, servindo apenas como "caixas" para agrupamento de elementos ou aplicação de estilo.

Exemplos:

<div>: Usada para agrupar elementos e aplicar estilos via CSS. Deve ser evitada quando uma tag semântica for mais apropriada.

<span>: Usada para aplicar estilo a uma pequena parte de um texto (nível inline).

💡 Conclusão: Princípios Chave
Organização: Mantenha /css e /img separados.

Estilo: Use Folhas de Estilo Externas para manter HTML e CSS separados.

HTML: Priorize tags semânticas (<header>, <nav>, <main>, etc.) em vez de <div> sempre que possível, para construir páginas acessíveis e otimizadas.
