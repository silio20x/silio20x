import cv2
import numpy as np

# Carregue a imagem
imagem = cv2.imread('caminho_para_sua_imagem.jpg')

# Converta a imagem para tons de cinza
imagem_gray = cv2.cvtColor(imagem, cv2.COLOR_BGR2GRAY)

# Aplique uma operação de limiarização para destacar objetos
_, thresh = cv2.threshold(imagem_gray, 150, 255, cv2.THRESH_BINARY)

# Encontre contornos na imagem limiarizada
contornos, _ = cv2.findContours(thresh, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)

# Itere sobre os contornos e desenhe retângulos ao redor dos objetos
for contorno in contornos:
    x, y, w, h = cv2.boundingRect(contorno)
    cv2.rectangle(imagem, (x, y), (x + w, y + h), (0, 255, 0), 2)

# Exiba a imagem com os retângulos desenhados
cv2.imshow('Resultado', imagem)
cv2.waitKey(0)
cv2.destroyAllWindows()
 👋 Hi, I’m @silio20x
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
silio20x/silio20x is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
