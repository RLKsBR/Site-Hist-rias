# Painel local do Arquivo Vermelho

Este painel é uma ferramenta privada para manutenção do site. Ele roda no seu navegador e grava arquivos diretamente na pasta local do repositório.

## Como usar

1. Abra `admin-local/index.html` no Chrome ou Edge.
2. Clique em `Selecionar pasta do site`.
3. Escolha a pasta raiz do repositório, onde ficam `index.html`, `assets`, `capitulos`, `downloads` e `obras`.
4. Escolha a obra, informe número, título e selecione o PDF.
5. Clique em `Gerar prévia`.
6. Clique em `Aplicar no repositório`.
7. Revise o site local.
8. Faça commit e push.

Se o navegador bloquear o acesso à pasta ao abrir direto pelo arquivo, rode um servidor local na raiz do repositório:

```powershell
python -m http.server 8080
```

Depois abra:

```text
http://localhost:8080/admin-local/
```

## O que ele atualiza ao adicionar PDF

- Copia o PDF para `downloads/...`.
- Cria uma página HTML em `capitulos/...`.
- Atualiza a página oficial da obra.
- Atualiza a seção `Últimas atualizações` da home.
- Atualiza a barra lateral desktop em `assets/js/main.js`.
- Atualiza `sitemap.xml`.
- Tenta liberar o botão `Próximo capítulo` no capítulo anterior.

## Substituir PDF

Use a ação `Substituir PDF existente` e informe o caminho relativo exato do arquivo, por exemplo:

```text
downloads/a-hora-vermelha/capitulo-05-me-destranca.pdf
```

O painel troca apenas o arquivo PDF. Ele não altera páginas HTML nessa ação.

## Observações

- O painel não publica no GitHub sozinho.
- O painel não usa login.
- O painel não expõe token.
- Se o navegador bloquear acesso a arquivos ao abrir direto pelo `file://`, rode um servidor local e abra pelo `localhost`.
