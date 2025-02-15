# azure-ai-search
desafio azure ai search
![Captura de tela 2025-02-15 085632](https://github.com/user-attachments/assets/15815a64-ef5a-4097-acf1-1be41eb87d62)
![Captura de tela 2025-02-15 085505](https://github.com/user-attachments/assets/5ba68dc7-3f98-4660-9ac6-5b95d733e8d5)
![Captura de tela 2025-02-15 085356](https://github.com/user-attachments/assets/63e51bec-561b-44a1-a0cb-8c85ecbc6464)
![Captura de tela 2025-02-15 085208](https://github.com/user-attachments/assets/51b97e88-4b9c-47a3-abf2-9f4db0fbb91c)
![Captura de tela 2025-02-15 083936](https://github.com/user-attachments/assets/d8f77e50-de31-4da3-9343-bb3c577dc3de)
![Captura de tela 2025-02-15 083304](https://github.com/user-attachments/assets/232402d8-d084-48ca-96a3-eb1ca1ec126b)
![Captura de tela 2025-02-15 081747](https://github.com/user-attachments/assets/05709625-69a3-4d83-a19e-353971bb8226)
![Captura de tela 2025-02-15 081555](https://github.com/user-attachments/assets/533f7518-25c6-4a51-abac-2d1638e915a7)

Crie o recurso Azure AI Search:
• Acesse o portal Azure, clique em “+ Create a resource”, procure por Azure AI Search e configure os parâmetros (assinatura, grupo de recursos, nome único, região e camada de preço – geralmente Basic).

Crie o recurso Azure AI Services:
• No mesmo grupo de recursos e região, crie um recurso de Azure AI Services que fornecerá as habilidades cognitivas para enriquecer os dados extraídos.

Configure uma Conta de Armazenamento e o Container:
• Crie uma Storage Account (padrão, LRS) e, em seguida, configure um container (ex.: “coffee-reviews”) com acesso público para que os documentos possam ser lidos e indexados.

Faça o Upload dos Documentos:
• Carregue os arquivos (como reviews de clientes) no container criado, garantindo que os dados estejam prontos para a indexação.

Importe os Dados para o Azure AI Search:
• No recurso de Azure AI Search, utilize o assistente “Import data” para conectar ao Azure Blob Storage.
• Configure o data source (definindo a pasta e a conexão com a Storage Account) e adicione uma descrição apropriada.

Configure o Enriquecimento Cognitivo:
• Adicione as habilidades cognitivas através do Azure AI Services, criando um skillset (ex.: “coffee-skillset”) que inclua OCR, extração de entidades, key phrases, análise de sentimento, geração de tags e legendas para imagens.
• Configure o skillset para combinar e salvar os resultados na Knowledge Store, definindo containers e parâmetros de granularidade (por exemplo, em chunks de 5000 caracteres).

Personalize o Índice:
• Defina um índice de destino (ex.: “coffee-index”), configurando o campo-chave (por exemplo, metadata_storage_path) e marcando os campos importantes (como content, locations, keyphrases, sentiment, etc.) como “filterable”.

Crie e Execute o Indexer:
• Configure um indexer (ex.: “coffee-indexer”) para mapear os dados extraídos para o índice, definindo a frequência de execução (por exemplo, “Once”) e ativando opções avançadas, como a codificação em Base-64 para chaves.
• Submeta a configuração e aguarde o processamento até que o status do indexador indique sucesso.

Teste e Consulte o Índice:
• Use a ferramenta Search Explorer do Azure para escrever e testar consultas (ex.: pesquisa global com “search”: "*" e filtros específicos como "locations:'Chicago'" ou "sentiment:'negative'").
• Verifique a contagem e a relevância dos resultados retornados.

Revise a Knowledge Store:
• Acesse a Knowledge Store na Storage Account para examinar os dados enriquecidos, visualizar os metadados dos documentos, imagens e tabelas geradas (como as extrações de key phrases) que facilitam a análise relacional dos dados.
