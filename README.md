Calculadora Freelance Bolivia + Tipo de Cambio P2P Binance

Este proyecto es una calculadora de presupuestos para freelancers en Bolivia 🇧🇴, con integración en tiempo real del tipo de cambio USDT/BOB desde Binance P2P.

🚀 Funcionalidades principales

Cálculo de tarifa por hora base en USD según metas y costos.

Creación de presupuestos con desglose (margen, IVA, ajustes por cliente).

Conversión de valores a bolivianos (BOB) usando el precio de USDT en Binance P2P.

Detección de variación en tiempo real del tipo de cambio (⬆ sube, ⬇ baja, sin cambios).

Actualización automática cada 60 segundos.

⚙️ Cómo funciona el tipo de cambio

La app realiza una petición POST al endpoint interno de Binance P2P:

https://p2p.binance.com/bapi/c2c/v2/friendly/c2c/adv/search


con el siguiente payload:

{
  "asset": "USDT",
  "fiat": "BOB",
  "tradeType": "BUY",
  "page": 1,
  "rows": 10,
  "payTypes": [],
  "merchantCheck": true
}


De la respuesta se extrae el primer anuncio (data[0].adv.price) como referencia del mercado.

👉 Para evitar problemas de CORS, se usa un proxy abierto:
https://corsproxy.io/?

📂 Archivos

index2_actualizado.html: Calculadora con integración del tipo de cambio.

README.md: Este archivo de documentación.

🖥️ Uso

Clona este repositorio o descarga los archivos.

Abre index2_actualizado.html en cualquier navegador moderno.

La calculadora mostrará el tipo de cambio USDT/BOB P2P actualizado y su variación en tiempo real.

📸 Captura de ejemplo
Cambio USD/BOB: Bs. 6.95 ⬆ +0.02

⚠️ Nota

Binance no ofrece una API pública oficial para P2P, por lo que este método depende de endpoints usados en su propia web. Podrían cambiar en el futuro.

✍️ Proyecto creado para freelancers en Bolivia que necesitan presupuestar en dólares y bolivianos con datos de mercado en tiempo real.
