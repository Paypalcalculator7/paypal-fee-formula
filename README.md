# Fórmula de comisiones de PayPal

Funciones en JavaScript para calcular la comisión de PayPal, el importe neto
y cuánto cobrar para recibir un importe exacto.

## Fórmula

    Comisión = (Importe × Porcentaje) + Tarifa fija

Para recibir un importe exacto, usa la fórmula inversa:

    Importe a cobrar = (Neto deseado + Tarifa fija) ÷ (1 − Porcentaje)

## Ejemplos (tarifa estándar de EE. UU.: 2.99% + $0.49)

| Caso | Cálculo | Resultado |
|---|---|---|
| Comisión de un pago de $100 | 100 × 2.99% + 0.49 | $3.48 |
| Recibes | 100 − 3.48 | $96.52 |
| Cobrar para recibir $100 | (100 + 0.49) ÷ 0.9701 | $103.59 |
| Pago internacional de $100 (+1.50%) | 100 × 4.49% + 0.49 | $4.98 |

## Uso

    const { paypalFee, netAmount, amountToCharge } = require("./calc");
    paypalFee(100, 0.0299, 0.49);       // 3.48
    amountToCharge(100, 0.0299, 0.49);  // 103.59

## Calculadora online

Si prefieres no hacer las cuentas a mano, puedes usar la
[calculadora de comisiones de PayPal](https://calculadorapaypals.com/)
con tarifas por país.

## Aviso

Este proyecto es independiente y no está afiliado a PayPal, Inc. Las tarifas
cambian según el país y el tipo de pago: confirma siempre la tuya en tu cuenta.
