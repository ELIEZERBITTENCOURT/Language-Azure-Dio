# Análise de Sentimentos com Language Studio no Azure AI

Este projeto visa realizar análise de sentimentos em textos utilizando o Language Studio no Azure AI.

## Passo a Passo para Utilizar o Language Studio no Azure AI

1. **Criação de Recurso no Azure:**
    - Primeiramente, você precisará de uma conta no Azure. Se você não tiver uma, crie uma em [azure.com](https://azure.com).
    - Após criar a conta, acesse o portal do Azure e crie um recurso de Language Studio. Para isso, vá para o painel de controle, clique em "Criar um recurso" e procure por "Language Studio". Siga as instruções para configurar o recurso.

2. **Configuração do Ambiente de Desenvolvimento:**
    - Instale o SDK do Azure para Python utilizando o seguinte comando:

        ```bash
        pip install azure-ai-textanalytics
        ```

3. **Utilizando o Código Python:**
    - Utilize o seguinte código Python para realizar a análise de sentimentos em seus textos:

    ```python
    from azure.core.credentials import AzureKeyCredential
    from azure.ai.textanalytics import TextAnalyticsClient

    endpoint = "SEU_ENDPOINT_DO_LANGUAGE_STUDIO"
    key = "SUA_CHAVE_DO_LANGUAGE_STUDIO"

    def analyze_sentiments(text):
        credentials = AzureKeyCredential(key)
        client = TextAnalyticsClient(endpoint=endpoint, credential=credentials)
        result = client.analyze_sentiment([text])
        sentiment = result[0].sentiment
        return sentiment

    text = "Texto que deseja analisar."
    sentiment = analyze_sentiments(text)
    print("Sentimento detectado:", sentiment)
    ```

4. **Execução do Código:**
    - Substitua `"SEU_ENDPOINT_DO_LANGUAGE_STUDIO"` pelo endpoint do seu recurso do Language Studio no Azure e `"SUA_CHAVE_DO_LANGUAGE_STUDIO"` pela chave do seu recurso.
    - Modifique o texto que deseja analisar, passando-o como argumento para a função `analyze_sentiments()`.
    - Execute o código e veja o resultado da análise de sentimentos para o texto fornecido.
