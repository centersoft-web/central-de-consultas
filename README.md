CENTRAL DE CONSULTAS BRASIL

Aplicação web demonstrativa que reúne consultas úteis sobre CEP, clima,
CNPJ, veículos pela Tabela FIPE, feriados nacionais, bancos, DDD, ISBN,
câmbio, taxas econômicas e PIX em uma única interface responsiva.

O projeto foi desenvolvido com HTML, CSS e JavaScript puro e consome
serviços públicos diretamente pelo navegador, sem backend e sem chave
de API.


FUNCIONALIDADES

Consultas gerais
- Consulta de endereço por CEP (ViaCEP).
- Busca de possíveis CEPs por UF, cidade e logradouro.
- Consulta das condições atuais do clima e da previsão para sete dias
  (Open-Meteo).
- Consulta de dados cadastrais públicos de CNPJ (BrasilAPI).
- Pesquisa de veículos e preços de referência pela Tabela FIPE, com
  busca por nome/ano e consulta detalhada (FIPE API).
- Consulta de feriados nacionais com calendário anual, dias restantes
  e possíveis emendas.
- Exportação de feriados nos formatos CSV e ICS.
- Impressão da relação de feriados.
- Consulta de instituições bancárias por código ou nome (BrasilAPI).

Novas consultas
- DDD: informe o código de Discagem Direta à Distância e obtenha o
  estado e a lista de cidades atendidas.
- ISBN: pesquise metadados de livros (título, autores, editora, ano,
  idioma, páginas e capa) pelo ISBN-10 ou ISBN-13.
- Câmbio: cotação oficial de moedas estrangeiras em relação ao Real
  (PTAX/Banco Central), com seleção de moeda e data opcional.
- Taxas econômicas: valores atuais da Selic, CDI e IPCA em % ao ano.
- PIX: lista das instituições autorizadas a operar com PIX no Brasil,
  com ISPB, nome, modalidade e tipo de participação.

Interface
- Abas de navegação com rolagem horizontal em telas pequenas.
- Layout responsivo para computador, celular e tablet.
- Mensagens de status, validação de campos e estados de carregamento
  em todas as consultas.
- Estilos de impressão que ocultam controles e exibem apenas o
  resultado da consulta ativa.


TECNOLOGIAS UTILIZADAS

- HTML5
- CSS3
- JavaScript (ES2020+, sem frameworks)
- Fetch API
- APIs externas públicas


SERVIÇOS EXTERNOS

- ViaCEP (https://viacep.com.br/) para consultas de CEP e endereço.
- Open-Meteo (https://open-meteo.com/) para geocodificação e previsão
  do tempo.
- BrasilAPI (https://brasilapi.com.br/) para consultas de CNPJ,
  feriados, bancos, DDD, ISBN, câmbio, taxas e participantes do PIX.
- FIPE API (https://fipe.parallelum.com.br/) para consultas de
  veículos e valores de referência.

A disponibilidade, o formato e a atualização dos dados dependem
desses serviços externos.

Observação sobre a consulta de câmbio
A BrasilAPI aplica uma política de cache que impede a consulta da
cotação do dia atual (e, eventualmente, do dia seguinte). Por isso,
a interface:
- Pré-preenche o campo de data com o último dia útil anterior a hoje.
- Limita o seletor de data para não permitir hoje ou datas futuras.
- Se a API recusar a data informada (cache, feriado ou ausência de
  cotação), tenta automaticamente o dia útil anterior e atualiza o
  campo com a data efetivamente usada.


ESTRUTURA BÁSICA DO PROJETO

.
├── index.html
├── icon.ico
├── manifest.json
└── service-worker.js

manifest.json e service-worker.js são necessários para oferecer os
recursos completos de uma PWA. Caso ainda não existam no projeto,
será preciso criá-los e vinculá-los ao index.html (via
link rel="manifest" e registro do service worker).


COMO EXECUTAR

Execução local simples
1. Baixe ou clone os arquivos do projeto.
2. Mantenha os arquivos na mesma pasta.
3. Inicie um servidor HTTP local.
4. Abra o endereço fornecido pelo servidor no navegador.

Exemplo com Python:

python -m http.server 8000

Depois, acesse http://localhost:8000 no navegador.

Abrir o index.html diretamente pode permitir a visualização da
página, mas não garante o funcionamento completo de recursos de PWA,
service worker ou de integrações sujeitas às políticas de segurança
do navegador.


INSTALAÇÃO NO COMPUTADOR

No Google Chrome ou Microsoft Edge:
1. Abra o endereço publicado do projeto.
2. Aguarde o carregamento completo da página.
3. Clique no ícone de instalação exibido na barra de endereço ou
   abra o menu do navegador.
4. Selecione "Instalar aplicativo" ou "Instalar este site como
   aplicativo".
5. Confirme a instalação.

Depois disso, o aplicativo poderá ser aberto pelo menu Iniciar, pela
área de trabalho ou pelo gerenciador de aplicativos do sistema.


INSTALAÇÃO NO CELULAR OU TABLET

Em navegadores compatíveis:
1. Abra o endereço do projeto.
2. Acesse o menu do navegador.
3. Selecione "Instalar aplicativo" ou "Adicionar à tela inicial".
4. Confirme o nome e a instalação.

O ícone será adicionado à tela inicial do dispositivo.


OBSERVAÇÕES

- A disponibilidade e o nome da opção de instalação podem variar
  conforme o navegador e o sistema operacional.
- Abrir somente o arquivo index.html pelo computador não garante a
  instalação como PWA.
- O projeto deve ser publicado em HTTPS para utilizar os recursos
  completos de instalação e service worker.
- O funcionamento offline depende da configuração do
  service-worker.js e dos arquivos adicionados ao cache.
- Atualizações no projeto podem exigir a atualização da versão do
  cache do service worker.
- O index.html atual não inclui, por si só, a referência a um
  manifesto nem o registro de um service worker. Esses componentes
  devem ser adicionados para habilitar a instalação completa como
  PWA.
- A consulta de câmbio exige conexão com a internet e respeita a
  política de cache da BrasilAPI (veja a seção acima).


LIMITAÇÕES CONHECIDAS

- A busca ampla da Tabela FIPE percorre marcas e modelos e pode gerar
  muitas requisições; a opção "Todas as categorias" é especialmente
  custosa.
- A cotação de câmbio do dia atual não está disponível por política
  de cache da BrasilAPI.
- A lista de participantes do PIX e a lista de taxas são carregadas
  sob demanda (botão), não automaticamente ao abrir a aba.
- O projeto depende inteiramente de serviços externos e não possui
  fallback local em caso de indisponibilidade.


LICENÇA

Nenhuma licença específica foi definida no arquivo fornecido. Antes
de distribuir ou publicar o projeto, inclua uma licença compatível
com a finalidade pretendida e verifique as licenças das bibliotecas
externas utilizadas.


AVISO

Este projeto é uma demonstração educacional desenvolvida para
estudos de HTML, CSS e JavaScript. A empresa mencionada é fictícia
e qualquer semelhança com empresas reais é mera coincidência.
