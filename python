import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
from matplotlib.ticker import FuncFormatter

# Definir dados
media_observada = pd.DataFrame({
"Temperatura": [25.02, 24.92, 24.89, 24.83, 24.66, 24.60],
"Ano": [2024, 2023, 2015, 2019, 2016, 1998]
}).sort_values(by='Ano', ascending=True) # Agora ordenado do menor para o maior ano

# Criar o gráfico de barras
plt.figure(figsize=(10,5))
sns.barplot(data=media_observada, orient='v', y='Temperatura', x='Ano', color='#D32F2F')

# Formatar o eixo Y com o sufixo °C
plt.gca().yaxis.set_major_formatter(FuncFormatter(lambda x, _: f"{x:.1f}°C"))
plt.ylim(22, 25.2)

# Remover linhas do topo e do lado direito
sns.despine()

# Definir a média histórica
media = 24.23

# Adicionar texto e setas para cada barra
for i in range(len(media_observada)):
diff = media_observada['Temperatura'].iloc[i] - media

# Adicionar texto com a diferença em cada barra
plt.text(
i, media_observada['Temperatura'].iloc[i] + 0.15,
f'{diff:+.2f}',
color='white', ha='center', weight='bold',
bbox=dict(facecolor='#003b71', edgecolor='#003b71', boxstyle='round,pad=0.3')
)

# Adicionar a seta para cima
plt.text(
i - 0.3, media_observada['Temperatura'].iloc[i] + 0.125,
'↑', ha='center', fontsize=16, color='#030b71', weight='bold', fontfamily='DejaVu Sans'
)

# Adicionar a linha da média histórica
plt.axhline(media, color='#fe904d', linestyle='--', linewidth=2, label=f'Média ({media:.2f}°C)')

# Definir título
plt.title('Média Observada de Temperatura em Relação à Média Histórica', y=1.07, ha='center')

# Ajustar a posição da legenda para o canto superior direito, ainda mais acima
plt.legend(loc='upper right', bbox_to_anchor=(1.2, 1.15))

# Exibir o gráfico
plt.show()
