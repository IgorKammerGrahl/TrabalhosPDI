# Trabalho 11 - Equalização de histograma

Igor Kammer Grahl | Processamento Digital de Imagens | IFC - Campus Rio do Sul  
Professor: André Alessandro Stein

O arquivo principal é **equalizacao_histograma.ipynb**. Ele já está executado,
com código, gráficos, resultados e análises dos quatro itens.

## Organização

| Caminho | Conteúdo |
|---|---|
| `equalizacao_histograma.ipynb` | Notebook principal, já executado |
| `entrada/` | Quatro TIFFs originais fornecidos na atividade |
| `saida/` | Imagens equalizadas, comparações, histogramas e estatísticas |
| `enunciado/Histograma_Equalizacao.pdf` | Cópia do material recebido |
| `requirements.txt` | Dependências para executar o trabalho |

## Como usar no repositório

Copie a pasta inteira `TrabalhoEqualizacaoHistograma` para a raiz de
`TrabalhosPDI`, ao lado de `TrabalhoHistograma` e `TrabalhoRealceHistograma`.
Mantenha o notebook junto das pastas `entrada/` e `saida/`.

O notebook utiliza NumPy, Matplotlib e Pillow. No ambiente do repositório,
essas bibliotecas podem estar presentes como dependências diretas ou indiretas.
Se necessário, na raiz do repositório gerenciado por uv:

```bash
uv add numpy matplotlib pillow
uv run jupyter lab
```

Para usar a atividade separadamente, com um ambiente virtual:

```bash
python -m venv .venv
.venv/bin/python -m pip install -r requirements.txt
.venv/bin/jupyter lab
```

No Jupyter, abra o notebook e use **Restart Kernel and Run All Cells**.
As saídas são recriadas pelos cálculos. A execução funciona com o diretório
atual na pasta da atividade ou na raiz do repositório.

## Resultados por item

| Item | Entrada | TIFF equalizado |
|:---:|---|---|
| a | `Fig0316(1)(top_left).tif` | `saida/a_equalizada.tif` |
| b | `Fig0316(2)(2nd_from_top).tif` | `saida/b_equalizada.tif` |
| c | `Fig0316(3)(third_from_top).tif` | `saida/c_equalizada.tif` |
| d | `Fig0316(4)(bottom_left).tif` | `saida/d_equalizada.tif` |

Cada item também possui um PNG equalizado, um painel de comparação e um CSV.
O arquivo `saida/resumo_estatistico.csv` reúne as estatísticas de entrada e
saída. `saida/funcoes_transformacao.png` mostra as quatro tabelas de mapeamento.

## Método

É aplicada a fórmula `s(k) = arredondar(255 * CDF(k))`, sem subtrair `CDF_min`,
conforme o material da disciplina. Em valores terminados em 0,5, o
arredondamento é para cima. As entradas são preservadas sem conversão tonal.

Antes de entregar, leia as explicações e confira se o formato de envio exigido
pelo professor é o notebook ou a pasta completa compactada.
