# ⚙️ Ambiente e Estrutura de Pastas
   A organização clara das pastas é fundamental para a manutenibilidade e escalabilidade do projeto.

1.1 Estrutura Padrão
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

# ✨ Aplicação de Estilo no HTML
Existem três formas principais de aplicar estilo a um documento HTML. A forma recomendada para projetos profissionais é a Folha de Estilo Externa.

2.1 Folha de Estilo Externa (Recomendado)
O estilo é definido em um arquivo .css separado (ex: style.css).

É linkado no <head> do HTML usando a tag <link>.

Vantagem: Limpeza do código HTML, reutilização de estilos em múltiplas páginas e melhor separação de responsabilidades (HTML para estrutura, CSS para apresentação).

HTML

<link rel="stylesheet" href="css/style.css">
2.2 Estilo Interno
O estilo é definido dentro da tag <style> no <head> do documento HTML.

Uso: Estilos específicos para aquela página que não serão usados em outro lugar.

Desvantagem: Não pode ser reutilizado em outras páginas.

HTML

<head>
    <style>
        h1 { color: blue; }
    </style>
</head>
2.3 Estilo Inline
O estilo é aplicado diretamente em um elemento HTML usando o atributo style.

Uso: Apenas em exceções muito raras, para estilos dinâmicos gerados por JS, ou testes rápidos.

Desvantagem: Mistura apresentação com estrutura, dificulta a manutenção e tem a maior especificidade, dificultando a sobrescrita.

HTML

<p style="color: red; font-size: 16px;">Este é um parágrafo.</p>

# 🏷️ Tags Semânticas vs. Não Semânticas

A escolha das tags HTML afeta a acessibilidade, o SEO (Otimização para Mecanismos de Busca) e a clareza do código.

3.1 Tags Semânticas (Recomendado)
Tags que carregam um significado claro sobre o propósito do seu conteúdo para o navegador e para os desenvolvedores.

Exemplos:

<header>: Introdução ou grupo de links de navegação.

<nav>: Contém links de navegação principal.

<main>: Conteúdo principal, único na página.

<section>: Um agrupamento temático de conteúdo.

<article>: Conteúdo autônomo e independente (ex: post de blog).

<footer>: Informações de rodapé, direitos autorais.

Benefício: Ajuda leitores de tela (acessibilidade) e motores de busca (SEO) a entender a hierarquia e o contexto da página.

3.2 Tags Não Semânticas
Tags que não transmitem significado sobre o tipo de conteúdo que contêm, servindo apenas como "caixas" para agrupamento de elementos ou aplicação de estilo.

Exemplos:

<div>: Usada para agrupar elementos e aplicar estilos via CSS. Deve ser evitada quando uma tag semântica for mais apropriada.

<span>: Usada para aplicar estilo a uma pequena parte de um texto (nível inline).

# 🔗 Versionamento e Colaboração (Git e GitHub)Utilizamos Git para controle de versão local e GitHub como plataforma de hospedagem e colaboração.
  Utilizamos Git para controle de versão local e GitHub como plataforma de hospedagem.

4.1 Fluxo de Trabalho com Branches (Git Flow Simplificado)
Adotamos um fluxo de trabalho baseado em branches para garantir que o código principal (main) permaneça estável e funcional.

├── /main (Código de produção. Sempre estável. NUNCA deve ser commitada diretamente.)
├── /develop (Branch de integração. Recebe o merge de todas as features e fixes testados.)
├── /feature/nome-da-feature (Criada a partir de /develop para desenvolver uma nova funcionalidade.)
└── /fix/nome-do-bug (Criada a partir de /develop para corrigir um bug.)

4.2 Padrão de Mensagens de Commit (Conventional Commits)
  Todas as mensagens de commit devem seguir o padrão Tipo: Assunto, que permite gerar changelogs (histórico de mudanças) automáticos e facilita a revisão do código.

  Formato: tipo(escopo opcional): descrição da mudança

  0. Tipo / Descrição / Exemplo
  1. feat / (Nova funcionalidade.) / [feat: create updateCart function]
  2. fix / (Correção de bug.) / [fix: Corrige erro de cálculo no carrinho]
  3. docs / (Mudança apenas na documentação (READMEs, etc.).) / [docs: Atualiza seção de Git no README]
  4. style / (Mudança de estilo (formatação, ponto e vírgula, sem mudança de lógica).) / [style: Adiciona margem nos botões]
  5. refactor / (Refatoração de código que não corrige bugs nem adiciona features.) / [refactor(js): Simplifica o loop de iteração]
  6. test / (Adição ou alteração de testes.) / [test: Adiciona testes unitários para /js/script.js]
  7. chore / (Mudanças de rotina (configurações de build, atualizações de dependências).) / [chore: Atualiza versão do NPM]

4.3 Passos Profissionais para Desenvolvimento
Para ilustrar o fluxo, imagine que você precisa adicionar o arquivo /js/novo-script.js.

  1. Sincronizar develop: Garanta que sua cópia local de /develop esteja atualizada.
    git checkout develop (Troca para a branch develop)
    git pull origin develop (Atualiza os arquivos locais puxando do github)

  2. Criar a Branch de Trabalho: Crie uma nova branch para sua tarefa.
    # Exemplo: Criando uma feature branch
    git checkout -b feature/adicionar-novo-script

  3. Desenvolvimento e Commit: Após criar o arquivo /js/novo-script.js e fazer as alterações necessárias, faça commits atômicos e descritivos.
    # Adicionando a alteração no arquivo index.html e no novo script
    git add index.html /js/novo-script.js

    # Exemplo de commit atômico
    git commit -m "feat: Adiciona novo script para validação de formulário"

  4. Enviar para o Repositório: Envie sua branch para o GitHub.
    git push origin feature/adicionar-novo-script

  5. Revisão (Pull Request): Crie um Pull Request (PR) no GitHub, solicitando que a branch /feature/adicionar-novo-script seja mesclada em /develop.

  6. Merge: Após a revisão e aprovação, o PR é mesclado em /develop. A branch de trabalho pode ser deletada.

# 💡 Conclusão: Princípios Chave
Organização: Mantenha /css e /img separados.

Estilo: Use Folhas de Estilo Externas para manter HTML e CSS separados.

HTML: Priorize tags semânticas (<header>, <nav>, <main>, etc.) em vez de <div> sempre que possível, para construir páginas acessíveis e otimizadas.

Versionamento: Use branches de feature/ e fix/ para isolar seu trabalho e sempre faça o merge via Pull Request para a branch develop.
