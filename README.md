# Central de Consultas Brasil

Aplicação web responsiva que reúne consultas úteis em uma única página. O projeto foi desenvolvido com HTML, CSS e JavaScript, sem framework obrigatório, e integra diferentes serviços externos diretamente pelo navegador.

## Funcionalidades

- Consulta de CEP e busca de endereços.
- Previsão do tempo para cidades brasileiras.
- Consulta de dados públicos de CNPJ.
- Consulta da Tabela FIPE por categoria, marca, modelo e ano.
- Busca de unidades de saúde por estado e município.
- Filtros de saúde por tipo de atendimento, funcionamento, nome ou bairro.
- Rotas, telefone, cópia de endereço e verificação no CNES quando disponíveis.
- Consulta de feriados nacionais, calendário, impressão e exportação.
- Consulta de bancos pelo código ou nome.
- Interface responsiva para computador, celular e tablet.

## Tecnologias utilizadas

- HTML5
- CSS3
- JavaScript
- LocalStorage para salvar configurações no navegador
- APIs e serviços externos

## Serviços integrados

O projeto utiliza serviços externos para realizar as consultas:

- ViaCEP
- Open-Meteo
- BrasilAPI
- FIPE API
- Geoapify Places API
- IBGE
- CNES / DATASUS como fonte oficial complementar

A disponibilidade, os limites e a atualização dos resultados dependem dos serviços externos utilizados.

## Estrutura principal

```text
index.html
README.md
manifest.json       # quando configurado como PWA
service-worker.js   # quando configurado como PWA
icons/              # ícones do aplicativo, quando disponíveis
```

Os arquivos adicionais de PWA são opcionais, mas necessários para uma experiência instalável completa.

## Como executar

### Execução simples

1. Baixe ou clone os arquivos do projeto.
2. Abra o arquivo `index.html` em um navegador moderno.
3. Para evitar limitações de segurança do navegador, prefira executar o projeto por um servidor local ou publicá-lo em HTTPS.

### Publicação

O projeto pode ser publicado em serviços de hospedagem de sites estáticos. Ao publicar, preserve os caminhos dos arquivos utilizados pelo `index.html`.

## Configuração da busca de saúde

A seção de saúde utiliza a Geoapify Places API.

1. Acesse o portal MyProjects da Geoapify.
2. Crie uma conta gratuita ou entre em sua conta.
3. Crie um projeto.
4. Abra a seção **API Keys**.
5. Copie a chave gerada.
6. Na seção **Saúde** da aplicação, cole a chave no campo correspondente.
7. Clique em **Salvar chave**.

A chave é armazenada no navegador utilizado. Antes de publicar o projeto, configure as restrições permitidas pelo provedor da API e não distribua uma chave privada diretamente no código-fonte.

Os resultados de saúde são informativos. Confirme telefone, horário, serviços e atendimento pelo SUS diretamente com a unidade ou pela consulta oficial do CNES antes de se deslocar.

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

## Privacidade e segurança

- As consultas dependem de serviços externos.
- A chave da Geoapify é salva localmente no navegador quando o usuário utiliza essa opção.
- Não inclua dados sensíveis ou credenciais privadas diretamente no repositório.
- Confirme os dados importantes nas fontes oficiais correspondentes.

## Licença

Nenhuma licença específica foi definida no arquivo fornecido. Antes de distribuir ou publicar o projeto, inclua uma licença compatível com a finalidade pretendida e verifique as licenças das bibliotecas externas utilizadas.

## Aviso

> Este projeto é uma demonstração educacional desenvolvida para estudos de HTML, CSS e JavaScript. A empresa mencionada é fictícia e qualquer semelhança com empresas reais é mera coincidência.
