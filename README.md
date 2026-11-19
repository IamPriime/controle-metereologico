# Controle Meteorológico

Página para registrar os locais onde são feitas coletas de dados meteorológicos. Cada registro contém o **nome do local**, a **latitude** e a **longitude** e é enviado ao Google Forms.

**[Abrir a página](https://iampriime.github.io/controle-metereologico/)** · **[Ver o código-fonte](https://github.com/IamPriime/controle-metereologico/blob/dev/index.html)**

## Como usar

1. Informe o **nome do local**.
2. Digite a latitude e a longitude em graus decimais ou clique em **Usar minha localização** para preencher os dois campos com as coordenadas do dispositivo.
3. Confira os dados e clique em **Enviar registro**. O Google Forms exibe o resultado do envio.

A digitação aceita vírgula ou ponto como separador decimal. A latitude deve estar entre **−90 e 90** e a longitude entre **−180 e 180**. O preenchimento automático precisa de HTTPS ou localhost e da permissão do navegador. Se a localização estiver indisponível, use os campos manuais.

## Como funciona

A interface responsiva, os estilos e o JavaScript ficam no mesmo arquivo, o `index.html`. O JavaScript valida as coordenadas e converte a vírgula decimal em ponto antes do envio. O formulário faz um `POST` diretamente ao Google Forms. A página é estática e dispensa dependências, etapa de build e backend próprio.

| Campo | Identificador no Google Forms |
| --- | --- |
| Nome do local | `entry.426002888` |
| Latitude | `entry.1760901326` |
| Longitude | `entry.384178347` |

Para usar outro Google Forms, ajuste a URL `formResponse` no atributo `action`, os três atributos `name` e o link para o formulário no rodapé.

## Executar localmente

Com Git e Python 3 instalados, rode:

```bash
git clone --branch dev https://github.com/IamPriime/controle-metereologico.git
cd controle-metereologico
python -m http.server 8000
```

Acesse [http://localhost:8000](http://localhost:8000). Os envios feitos pela cópia local também vão para o formulário configurado no HTML.

## Publicar no GitHub Pages

Em **Settings → Pages**, escolha **Deploy from a branch**, selecione a branch **`dev`**, onde está o `index.html`, e a pasta **`/ (root)`**. Salve a configuração. Consulte o [guia do GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) para mais detalhes.
