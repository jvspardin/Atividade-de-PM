># Trabalho de PM
>Nome: João Vítor, Felipe Miranda, Pablo Refundini - ADS

**✈️ Trajeto do Avião para determinados Pontos**

O algoritmo se baseia onde o avião possui um trajeto entre pontos e percorre cada ponto da tragetória mais rápida.

---      

### Algoritmo
``` python
import numpy as np
import plotly.graph_objects as go
from PIL import Image
import math


texture_filename = "BlackMarble_2016_gray_tn.jpg"  # use o nome do arquivo que você subiu
texture = np.array(Image.open(texture_filename).convert("RGB"))


estados = {
    "SP": (-23.55, -46.63),
    "RJ": (-22.90, -43.20),
    "MG": (-19.92, -43.94),
    "ES": (-20.32, -40.34),
    "PR": (-25.42, -49.27),
    "SC": (-27.59, -48.55),
    "RS": (-30.03, -51.23)
}

def latlon_to_xyz(lat, lon, R=1.0):
    lat = math.radians(lat)
    lon = math.radians(lon)
    x = R * math.cos(lat) * math.cos(lon)
    y = R * math.cos(lat) * math.sin(lon)
    z = R * math.sin(lat)
    return x, y, z


def great_circle(lat1, lon1, lat2, lon2, n=40):
    lat1, lon1, lat2, lon2 = map(math.radians, [lat1, lon1, lat2, lon2])
    d = 2 * math.asin(
        math.sqrt(
            math.sin((lat2-lat1)/2)**2 +
            math.cos(lat1)math.cos(lat2)*math.sin((lon2-lon1)/2)*2
        )
    )
    if abs(d) < 1e-6:
        return np.zeros(n), np.zeros(n), np.zeros(n)
    f = np.linspace(0, 1, n)
    A = np.sin((1 - f)*d) / math.sin(d)
    B = np.sin(f*d) / math.sin(d)
    x = A*np.cos(lat1)*math.cos(lon1) + B*np.cos(lat2)*math.cos(lon2)
    y = A*np.cos(lat1)*math.sin(lon1) + B*np.cos(lat2)*math.sin(lon2)
    z = A*np.sin(lat1) + B*np.sin(lat2)
    norm = np.sqrt(x*x + y*y + z*z)
    return x/norm, y/norm, z/norm


h, w, _ = texture.shape
u = np.linspace(0, 2*np.pi, w)
v = np.linspace(-np.pi/2, np.pi/2, h)
U, V = np.meshgrid(u, v)
X = np.cos(V)*np.cos(U)
Y = np.cos(V)*np.sin(U)
Z = np.sin(V)

fig = go.Figure()

fig.add_trace(go.Surface(
    x=X, y=Y, z=Z,
    surfacecolor=np.flipud(texture[:,:,0]),
    colorscale="Gray",
    showscale=False
))


for nome, (lat, lon) in estados.items():
    x, y, z = latlon_to_xyz(lat, lon)
    fig.add_trace(go.Scatter3d(
        x=[x], y=[y], z=[z],
        mode='markers+text',
        marker=dict(size=5, color='red'),
        text=[nome],
        textposition='bottom center'
    ))


names = list(estados.keys())
for i in range(len(names)):
    for j in range(i+1, len(names)):
        a, b = names[i], names[j]
        gx, gy, gz = great_circle(estados[a][0], estados[a][1],
                                   estados[b][0], estados[b][1], n=40)
        fig.add_trace(go.Scatter3d(
            x=gx, y=gy, z=gz,
            mode='lines',
            line=dict(color='yellow', width=1),
            opacity=0.6
        ))


fig.update_layout(
    title="Globo Terra + Rotas Sul-Sudeste (Bhargava)",
    width=800, height=800,
    scene=dict(
        xaxis=dict(visible=False),
        yaxis=dict(visible=False),
        zaxis=dict(visible=False),
        aspectmode="data"
    )
)

fig.show()
[16:54, 08/12/2025] Pablo Refundini: def great_circle(lat1, lon1, lat2, lon2, n=40):
    lat1, lon1, lat2, lon2 = map(math.radians, [lat1, lon1, lat2, lon2])
    d = 2 * math.asin(
        math.sqrt(
            math.sin((lat2-lat1)/2)**2 +
            math.cos(lat1)math.cos(lat2)*math.sin((lon2-lon1)/2)*2
```
### Imagem da Trajetória
<img width="720" height="480" alt="image" src="https://github.com/user-attachments/assets/fc7fc458-ecf9-4f15-8370-dd7742662e77" />

blob:https://web.whatsapp.com/ff2bee43-b2ed-4a4a-8f0c-8c037bc08643

