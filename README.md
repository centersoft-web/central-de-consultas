# Central de Consultas Brasil

Aplicação web demonstrativa que reúne consultas úteis sobre **CEP, clima, CNPJ, veículos pela Tabela FIPE, feriados nacionais e bancos** em uma única interface responsiva.

O projeto foi desenvolvido com HTML, CSS e JavaScript puro e consome serviços públicos diretamente pelo navegador.

## Funcionalidades

- Consulta de endereço por CEP.
- Busca de possíveis CEPs por UF, cidade e logradouro.
- Consulta das condições atuais do clima e da previsão para sete dias.
- Consulta de dados cadastrais públicos de CNPJ.
- Pesquisa de veículos e preços de referência pela Tabela FIPE.
- Consulta de feriados nacionais com calendário anual.
- Exportação de feriados nos formatos CSV e ICS.
- Impressão da relação de feriados.
- Consulta de instituições bancárias por código ou nome.
- Interface responsiva para computador, celular e tablet.

## Tecnologias utilizadas

- HTML5
- CSS3
- JavaScript
- Fetch API
- APIs externas públicas

## Serviços externos

O projeto utiliza os seguintes serviços:

- [ViaCEP](https://viacep.com.br/) para consultas de CEP e endereço.
- [Open-Meteo](https://open-meteo.com/) para geocodificação e previsão do tempo.
- [BrasilAPI](https://brasilapi.com.br/) para consultas de CNPJ, feriados e bancos.
- [FIPE API](https://fipe.api.br/) para consultas de veículos e valores de referência.

A disponibilidade, o formato e a atualização dos dados dependem desses serviços externos.

## Estrutura básica do projeto

```text
.
├── index.html
├── icon.ico
├── manifest.json
└── service-worker.js
```

> `manifest.json` e `service-worker.js` são necessários para oferecer os recursos completos de uma PWA. Caso ainda não existam no projeto, será preciso criá-los e vinculá-los ao `index.html`.

## Como executar

### Execução local simples

1. Baixe ou clone os arquivos do projeto.
2. Mantenha os arquivos na mesma pasta.
3. Inicie um servidor HTTP local.
4. Abra o endereço fornecido pelo servidor no navegador.

Exemplo com Python:

```bash
python -m http.server 8000
```

Depois, acesse `http://localhost:8000` no navegador.

> Abrir o `index.html` diretamente pode permitir a visualização da página, mas não garante o funcionamento completo de recursos de PWA, service worker ou de integrações sujeitas às políticas de segurança do navegador.

## Instalação no computador

### No Google Chrome ou Microsoft Edge:

1. Abra o endereço publicado do projeto.
2. Aguarde o carregamento completo da página.
3. Clique no ícone de instalação exibido na barra de endereço ou abra o menu do navegador.
4. Selecione **Instalar aplicativo** ou **Instalar este site como aplicativo**.
5. Confirme a instalação.

Depois disso, o aplicativo poderá ser aberto pelo menu Iniciar, pela área de trabalho ou pelo gerenciador de aplicativos do sistema.

## Instalação no celular ou tablet

### Em navegadores compatíveis:

1. Abra o endereço do projeto.
2. Acesse o menu do navegador.
3. Selecione **Instalar aplicativo** ou **Adicionar à tela inicial**.
4. Confirme o nome e a instalação.

O ícone será adicionado à tela inicial do dispositivo.

## Observações

- A disponibilidade e o nome da opção de instalação podem variar conforme o navegador e o sistema operacional.
- Abrir somente o arquivo `index.html` pelo computador não garante a instalação como PWA.
- O projeto deve ser publicado em HTTPS para utilizar os recursos completos de instalação e service worker.
- O funcionamento offline depende da configuração do `service-worker.js` e dos arquivos adicionados ao cache.
- Atualizações no projeto podem exigir a atualização da versão do cache do service worker.
- O código fornecido em `index.html` não apresenta, por si só, a referência a um manifesto nem o registro de um service worker. Esses componentes devem ser adicionados para habilitar a instalação completa como PWA.

## Licença

Nenhuma licença específica foi definida no arquivo fornecido. Antes de distribuir ou publicar o projeto, inclua uma licença compatível com a finalidade pretendida e verifique as licenças das bibliotecas externas utilizadas.

## Aviso

> Este projeto é uma demonstração educacional desenvolvida para estudos de HTML, CSS e JavaScript. A empresa mencionada é fictícia e qualquer semelhança com empresas reais é mera coincidência.
