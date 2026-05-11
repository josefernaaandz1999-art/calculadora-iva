<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Calculadora de IVA</title>

<style>
    body {
        font-family: Arial, sans-serif;
        background: #f4f4f4;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }

    .calculadora {
        background: white;
        padding: 30px;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0,0,0,0.2);
        width: 320px;
    }

    h1 {
        text-align: center;
    }

    input, select, button {
        width: 100%;
        padding: 10px;
        margin-top: 10px;
        font-size: 16px;
    }

    .resultado {
        margin-top: 20px;
        background: #eef;
        padding: 15px;
        border-radius: 8px;
    }
</style>
</head>

<body>

<div class="calculadora">
    <h1>Calculadora IVA</h1>

    <input type="number" id="precio" placeholder="Introduce el precio">

    <select id="iva">
        <option value="21">21%</option>
        <option value="10">10%</option>
        <option value="4">4%</option>
    </select>

    <button onclick="calcularIVA()">Calcular</button>

    <div class="resultado" id="resultado">
        Resultado aparecerá aquí
    </div>
</div>

<script>
function calcularIVA() {
    let precio = parseFloat(document.getElementById("precio").value);
    let iva = parseFloat(document.getElementById("iva").value);

    if (isNaN(precio)) {
        alert("Introduce un precio válido");
        return;
    }

    let cantidadIVA = precio * iva / 100;
    let total = precio + cantidadIVA;

    document.getElementById("resultado").innerHTML = `
        Precio sin IVA: €${precio.toFixed(2)}<br>
        IVA (${iva}%): €${cantidadIVA.toFixed(2)}<br>
        Total con IVA: €${total.toFixed(2)}
    `;
}
</script>

</body>
</html>
