# 📊 Projeto Culturama: Pesquisa de Opinião  
Este projeto é um formulário de pesquisa de opinião completo e acessível, desenvolvido para coletar dados demográficos, hábitos e opiniões de usuários. O foco principal foi a utilização de HTML5 semântico, acessibilidade digital (A11y) e validação de dados nativa.

# 🚀 Funcionalidades do Formulário  
O formulário está dividido em seções lógicas utilizando fieldset e legend para facilitar a navegação e compreensão:

Dados Pessoais: Coleta de nome, idade (com limite de 12 a 100 anos), data de nascimento, e-mail e telefone.

Destaque: Uso de pattern="[0-9]{11}" para validar o formato do telefone e type="file" com accept="image/\*" para upload de fotos.

Perfil: Uso de input type="radio" para gênero e select para estado civil e localização (Estado/Cidade).

Hábitos Sociais e Musicais: \* Uso de checkbox para seleção múltipla de redes sociais.

Implementação de um Datalist para sugestões de estilos musicais, otimizando a digitação do usuário.

Seleção de cor favorita através do input type="color".

Opinião e Feedback: Escala de satisfação e um campo de texto (textarea) para comentários livres.

Conformidade LGPD: Checkbox obrigatório para aceite de participação, garantindo a transparência no tratamento dos dados.

# 🛠️ Tecnologias e Conceitos Aplicados

1 - Estrutura e Semântica
Utilização de tags como main, header, section, fieldset e footer.

Associação rigorosa entre label e input através do atributo id, garantindo que o clique no texto foque o campo correspondente.

2 - Acessibilidade Digital (A11y)
Navegabilidade: O formulário foi pensado para ser operável via teclado.

Leitores de Tela: A estrutura de legend dentro de fieldset fornece contexto imediato para usuários de tecnologias assistivas.

Auditoria: O projeto está preparado para passar por ferramentas de análise como Google Lighthouse e WAVE.

3 - Design e Performance (SEO)
Tipografia: Integração com Google Fonts (fontes Fjalla One e Work Sans).

SEO Técnico: Uso de meta tags de viewport e charset, além de títulos hierárquicos (h1) claros para indexação.

Favicon Personalizado: Identidade visual presente desde a aba do navegador.

# 📂 Estrutura de Pastas  
/  
├── index.html // Estrutura do formulário  
├── sucesso.html // Página de destino após o envio  
├── /css  
│ └── style.css // Estilização e validações visuais  
└── /img  
├── logo-culturama.png // Logo oficial no cabeçalho  
└── culturama-favico.png // Ícone da aba do navegador

# 🧠 Aprendizados Extraídos  
Validação Nativa: Como restringir entradas de dados (como idade mínima e máxima) sem depender exclusivamente de JavaScript.

Usabilidade com Datalist: Oferecer opções ao usuário enquanto permite a liberdade de escrita.

Higiene de Código: A importância de organizar o formulário em blocos lógicos para evitar a sobrecarga cognitiva do usuário.

Feedback Visual: Preparação do CSS para estados de :required, :valid e :invalid.
