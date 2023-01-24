# Cenário Saúde

Geração de dados gráficos para o relatório trimestral do Cenário Saúde.

## Funcionamento

O documento `cenario_saude.Rmd` é o responsável pela geração dos dados e dos gráficos do relatório. Ele tem a seguinte composição

-   **Bibliotecas e funções**

-   **Parâmetros fixos**

-   **Parâmetros variáveis** (nesta seção, alteram-se informações referentes a ano, edição, meses incluídos, tamanhos e fontes e cores dos gráficos)

-   **Arquivo** (seção responsável por manter série histórica de outputs para reprodutibilidade posterior)

## Principais fontes de problemas

-   **Formatos de datas do trimestre** (arquivo: `3_analise_financeira.R`)  
    A ANS constantemente muda o formato das datas disponíveis nos arquivos `.csv` no FTP. Embora tenham sidos inclusos os três formatos mais prováveis no código de download de arquivos do FTP, a quebra do código é uma possibilidade.

-   **Janela de análise** (arquivo: `4_adesao_cancelamento.R`)  
    A janela de análise de churn rate é sempre de 12 meses. O código foi feito para se basear no trimestre informado. Para análises além dessa, abrir branch de testes e deletar após a extração de informações.

-   **SIDRA ou IPEADATA fora do ar** (arquivo: `5_dados_var.R`)  
    Quando der erro na obtenção dos dados do modelo de previsão, geralmente isso significa que a API de um dos dois sites está fora do ar. Esperar é a solução.
