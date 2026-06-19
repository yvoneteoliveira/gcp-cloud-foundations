# gcp-cloud-foundations
Projeto prático de manipulação do Google Cloud Storage utilizando chamadas de API REST (curl) e autenticação OAuth2 via Cloud Shell.

Este projeto demonstra a automação e interação com o serviço de armazenamento em nuvem do Google (Google Cloud Storage) sem o uso da interface gráfica, utilizando chamadas diretas de API REST através do terminal Cloud Shell.

O laboratório valida competências em autenticação baseada em tokens, gerenciamento de permissões de API e consumo de payloads estruturados em formato JSON.

## 🛠️ Tecnologias e Conceitos Utilizados
* **Google Cloud Platform (GCP):** Cloud Storage e Cloud Shell Terminal.
* **Protocolos e APIs:** HTTP/REST utilizando a ferramenta `curl`.
* **Segurança e Autenticação:** Geração e uso de tokens de acesso OAuth2 (`Bearer Token`).
* **Formatos de Dados:** Leitura e interpretação de respostas em formato `JSON`.

---

## 📈 Arquitetura e Implementação Passo a Passo

### 1. Autenticação e Configuração de Variáveis
O processo foi iniciado no Cloud Shell definindo as variáveis de ambiente necessárias para a requisição, incluindo o caminho do objeto local (`demo-image.png`) e o nome do bucket de destino. A autenticação foi realizada injetando um token OAuth2 dinâmico (`$OAUTH2_TOKEN`) diretamente no cabeçalho da requisição HTTP.

### 2. Upload do Objeto via Terminal (`curl`)
Utilizando o método `POST` e o endpoint nativo do Google APIs (`https://www.googleapis.com/upload/storage/v1/b/...`), o arquivo foi transmitido de forma binária (`--data-binary`). A API retornou um payload JSON confirmando o sucesso da operação, detalhando metadados críticos como ID de geração, hashes de validação (`md5Hash`, `crc32c`) e a URL de mídia gerada.
---

### 3. Validação no Ambiente de Armazenamento
Após a resposta de sucesso da API, a criação do Bucket foi checada e validada na console web do GCP:

Por fim, o repositório de objetos confirmou que o arquivo `demo-image` foi carregado corretamente com o tipo de conteúdo definido (`image/png`) e tamanho exato de 508.1 KB, sincronizando perfeitamente a chamada via API com a infraestrutura em nuvem
---

## 🚀 Aprendizados Adquiridos
* Entendimento profundo de como a interface gráfica do GCP abstrai chamadas de API que podem ser totalmente automatizadas via scripts.
* Validação de integridade de dados na nuvem
