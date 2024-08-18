# Classificação do Sport Recife

Neste projeto, vamos usar um script Python para calcular e visualizar a classificação do Sport Recife ao longo das rodadas do Brasileirão - Série B. O objetivo é calcular as estatísticas de cada time e criar um gráfico tipo Bumpy para mostrar a evolução da classificação do Sport Recife.

## Funcionalidades

1. **Cálculo das Estatísticas dos Times**
   - **Pontos**: Total de pontos ganhos pelo time.
   - **Vitórias**: Número de jogos vencidos.
   - **Empates**: Número de jogos empatados.
   - **Derrotas**: Número de jogos perdidos.
   - **Gols Realizados**: Total de gols marcados.
   - **Gols Sofridos**: Total de gols sofridos.

2. **Geração do Gráfico de Classificação**
   - **Gráfico Bumpy**: Visualiza a evolução da posição do Sport Recife ao longo das rodadas.

## Gráfico Bumpy

O gráfico Bumpy é uma ferramenta útil para visualizar como a posição de um time muda ao longo do campeonato:

### Estrutura do Gráfico

- **Eixo X (Horizontal)**: Representa as rodadas do campeonato. Cada ponto ao longo deste eixo mostra a posição do time em uma rodada específica.
- **Eixo Y (Vertical)**: Representa a posição do time na tabela de classificação. A posição é numerada de 1 a 10 (ou outro intervalo dependendo do número de times), onde 1 é a melhor posição e 10 é a pior.

### Linha e Marcadores

- **Linha**: Conecta os pontos e mostra a trajetória da posição do time ao longo das rodadas.
- **Marcadores (ou Pontos)**: Indicam a posição exata do time em cada rodada ao longo da linha.

## Salvando o Gráfico como Imagem

Para salvar o gráfico gerado como uma imagem e garantir que ele possa ser facilmente utilizado em diferentes contextos, como em páginas web ou documento.

buf = io.BytesIO()
fig.savefig(buf, format='png', dpi=150, bbox_inches='tight')
buf.seek(0)
img_str = base64.b64encode(buf.read()).decode('utf-8')
plt.close(fig)

- **`io.BytesIO()`**: Cria um buffer de memória onde o gráfico será salvo temporariamente. Isso evita a necessidade de salvar o gráfico em um arquivo físico no disco.

- **`fig.savefig(buf, format='png', dpi=150, bbox_inches='tight')`**: Salva o gráfico no buffer em formato PNG com uma resolução de 150 dpi. O parâmetro `bbox_inches='tight'` ajusta a caixa delimitadora para incluir apenas o conteúdo do gráfico, eliminando espaços em branco desnecessários ao redor da imagem.

- **`buf.seek(0)`**: Reposiciona o ponteiro do buffer no início para garantir que toda a imagem seja lida corretamente na etapa seguinte.

- **`base64.b64encode(buf.read()).decode('utf-8')`**: Lê o conteúdo do buffer, codifica a imagem em base64 e a decodifica para uma string UTF-8. Isso permite que a imagem seja incorporada diretamente em HTML ou outros formatos que aceitam strings codificadas, facilitando a inclusão do gráfico em páginas web e relatórios sem precisar de arquivos externos.

