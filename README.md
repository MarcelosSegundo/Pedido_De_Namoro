 (cd "$(git rev-parse --show-toplevel)" && git apply --3way <<'EOF' 
diff --git a/README.md b/README.md
index 3671193cd9686005b848fd18b369b8f94b562047..7c915ce20aa7ed84955fd26390be98c216a5bdf1 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,64 @@
-# diversao
\ No newline at end of file
+# Pedido de Namoro Interativo
+
+Este projeto é uma página HTML simples e divertida para fazer um pedido de namoro com dois botões: **Sim** e **Não**.
+
+## Como o sistema funciona
+
+A aplicação roda 100% no navegador, em um único arquivo (`index.html`), com três partes principais:
+
+- **HTML**: estrutura da tela (pergunta, botões e modal).
+- **CSS**: estilo visual (cores, centralização, animação do coração).
+- **JavaScript**: comportamento interativo dos botões.
+
+## Fluxo de interação
+
+1. A pessoa vê a pergunta: **"Aceita namorar comigo?"**.
+2. Se clicar em **Sim**:
+   - Um modal é exibido com um coração animado.
+3. Se clicar em **Não**:
+   - O botão "Não" muda para uma posição aleatória na tela.
+   - O botão "Sim" aumenta de tamanho a cada clique no "Não".
+
+Esse efeito cria a brincadeira de "fugir" do botão negativo e incentivar o clique em "Sim".
+
+## Regras da movimentação do botão "Não"
+
+Quando o botão **Não** é clicado, o script:
+
+- calcula os limites da tela;
+- define margens para manter o botão visível;
+- sorteia posições aleatórias;
+- evita sobreposição com o texto da pergunta e com o botão **Sim**;
+- limita as tentativas de reposicionamento para não travar a interface.
+
+Se não encontrar uma posição válida após o número máximo de tentativas, ele usa uma posição de fallback.
+
+## Modal de confirmação
+
+O modal:
+
+- aparece ao clicar em **Sim**;
+- usa `display: flex` para centralizar o conteúdo;
+- mostra um coração com animação de batimento;
+- pode ser fechado pelo botão **Fechar**.
+
+## Como executar
+
+Como é um projeto estático, existem duas formas simples:
+
+1. **Abrir o `index.html` diretamente** no navegador.
+2. **Rodar um servidor local** (opcional), por exemplo:
+
+```bash
+python3 -m http.server 8000
+```
+
+Depois acesse `http://localhost:8000`.
+
+## Estrutura do projeto
+
+```text
+.
+├── index.html
+└── README.md
+```
 
EOF
)
