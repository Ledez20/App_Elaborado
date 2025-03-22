<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gestión de Inventario y Elaboraciones</title>
    <style>
        :root {
            --primary-color: #1e3d59;
            --secondary-color: #17a2b8;
            --accent-color: #00b4d8;
            --light-color: #e8f4f8;
            --dark-color: #2c3e50;
            --success-color: #28a745;
            --danger-color: #dc3545;
            --warning-color: #ffc107;
        }
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            background-color: var(--light-color);
        }
        .sidebar {
            width: 200px;
            background-color: var(--primary-color);
            color: #fff;
            padding: 15px;
            height: 100vh;
            position: fixed;
        }
        .sidebar button {
            width: 100%;
            padding: 12px;
            margin: 5px 0;
            background-color: var(--secondary-color);
            color: #fff;
            border: none;
            cursor: pointer;
            border-radius: 4px;
            transition: background-color 0.3s;
        }
        .sidebar button:hover {
            background-color: var(--accent-color);
        }
        .content {
            flex-grow: 1;
            padding: 20px;
            margin-left: 200px;
        }
        .section {
            display: none;
            background-color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        .form-group {
            margin-bottom: 15px;
        }
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
            color: var(--primary-color);
        }
        select, input {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            box-sizing: border-box;
        }
        .unidad-medida {
            color: var(--secondary-color);
            font-weight: bold;
            margin-top: 5px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            background-color: white;
        }
        table, th, td {
            border: 1px solid #ddd;
        }
        th, td {
            padding: 12px;
            text-align: left;
        }
        th {
            background-color: var(--light-color);
            color: var(--primary-color);
        }
        tr:nth-child(even) {
            background-color: var(--light-color);
        }
        .btn {
            padding: 10px 15px;
            background-color: var(--success-color);
            color: #fff;
            border: none;
            cursor: pointer;
            border-radius: 4px;
            transition: background-color 0.3s;
        }
        .btn:hover {
            background-color: #218838;
        }
        .btn-danger {
            background-color: var(--danger-color);
        }
        .btn-danger:hover {
            background-color: #c82333;
        }
        .alert {
            padding: 10px;
            margin-bottom: 15px;
            border-radius: 4px;
            display: none;
        }
        .alert-success {
            background-color: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }
        .alert-error {
            background-color: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }
        .alert-warning {
            background-color: #fff3cd;
            color: #856404;
            border: 1px solid #ffeeba;
        }
        .consumo-estimado {
            background-color: var(--light-color);
            padding: 10px;
            border-radius: 4px;
            margin-top: 5px;
        }
        .consumo-estimado ul {
            margin: 0;
            padding-left: 20px;
        }
        .consumo-estimado li {
            margin: 5px 0;
        }
        .stock-bajo {
            color: var(--danger-color);
            font-weight: bold;
        }
        .stock-medio {
            color: var(--warning-color);
            font-weight: bold;
        }
        .stock-alto {
            color: var(--success-color);
        }
    </style>
</head>
<body>
    <div class="sidebar">
        <button onclick="showSection('gestionInventario')">Gestión de Inventario</button>
        <button onclick="showSection('gestionElaboraciones')">Gestión de Elaboraciones</button>
    </div>
    <div class="content">
        <div id="alert" class="alert"></div>
        
        <!-- Sección de Gestión de Inventario -->
        <div id="gestionInventario" class="section">
            <h2>Gestión de Inventario</h2>
            <div class="form-group">
                <label for="producto">Producto:</label>
                <select id="producto" onchange="actualizarUnidadMedida()">
                    <option value="">Seleccione un producto</option>
                    <option value="SAL">SAL</option>
                    <option value="HIDRAL-70">HIDRAL-70</option>
                    <option value="HYDROMAR-4">HYDROMAR-4</option>
                    <option value="ANTIESPUMANTE">ANTIESPUMANTE</option>
                </select>
                <div id="unidadMedida" class="unidad-medida"></div>
            </div>
            <div class="form-group">
                <label for="lote">Lote:</label>
                <input type="text" id="lote" placeholder="Ingrese el número de lote">
            </div>
            <div class="form-group">
                <label for="cantidad">Cantidad:</label>
                <input type="number" id="cantidad" min="0" step="0.01" placeholder="Ingrese la cantidad">
            </div>
            <button class="btn" onclick="agregarProducto()">Agregar Producto</button>
            <h3>Historial de Inventario</h3>
            <table id="historialInventario">
                <thead>
                    <tr>
                        <th>Producto</th>
                        <th>Lote</th>
                        <th>Cantidad</th>
                        <th>Unidad</th>
                        <th>Equivalencia en Bins</th>
                        <th>Estado</th>
                        <th>Fecha y Hora</th>
                        <th>Acciones</th>
                    </tr>
                </thead>
                <tbody>
                </tbody>
            </table>
        </div>

        <!-- Sección de Gestión de Elaboraciones -->
        <div id="gestionElaboraciones" class="section">
            <h2>Gestión de Elaboraciones</h2>
            <div class="form-group">
                <label for="cliente">Cliente:</label>
                <select id="cliente">
                    <option value="">Seleccione un cliente</option>
                    <option value="WOFCO">WOFCO</option>
                    <option value="OVERSEA">OVERSEA</option>
                    <option value="SCANFISK">SCANFISK</option>
                    <option value="IBERCONSA">IBERCONSA</option>
                </select>
            </div>
            <div class="form-group">
                <label for="referencia">Referencia de Elaboración:</label>
                <input type="text" id="referencia" placeholder="Ingrese la referencia">
            </div>
            <div class="form-group">
                <label for="bins">Número de Bins:</label>
                <input type="number" id="bins" min="1" placeholder="Ingrese el número de bins">
            </div>
            <div class="form-group">
                <label>Consumo Estimado por <span id="binsValue">1</span> Bins:</label>
                <div id="consumoEstimado" class="consumo-estimado"></div>
            </div>
            <button class="btn" onclick="registrarElaboracion()">Registrar Elaboración</button>
            <h3>Historial de Elaboraciones</h3>
            <table id="historialElaboraciones">
                <thead>
                    <tr>
                        <th>Cliente</th>
                        <th>Referencia</th>
                        <th>Número de Bins</th>
                        <th>Consumo</th>
                        <th>Fecha y Hora</th>
                    </tr>
                </thead>
                <tbody>
                </tbody>
            </table>
        </div>
    </div>

    <script>
        // Configuración de productos y sus unidades de medida
        const productosConfig = {
            'SAL': 'KG',
            'HIDRAL-70': 'KG',
            'HYDROMAR-4': 'L',
            'ANTIESPUMANTE': 'L'
        };

        // Configuración de consumo por bin
        const consumoPorBin = {
            'SAL': 12.5,
            'HIDRAL-70': 6,
            'HYDROMAR-4': 1,
            'ANTIESPUMANTE': 0.5
        };

        // Umbral para alertas de stock bajo (20%)
        const umbralStockBajo = 0.2;

        // Función para mostrar una sección y ocultar las demás
        function showSection(sectionId) {
            const sections = document.getElementsByClassName('section');
            for (let section of sections) {
                section.style.display = 'none';
            }
            document.getElementById(sectionId).style.display = 'block';
        }

        // Función para actualizar la unidad de medida según el producto seleccionado
        function actualizarUnidadMedida() {
            const producto = document.getElementById('producto').value;
            const unidadMedida = document.getElementById('unidadMedida');
            if (producto && productosConfig[producto]) {
                unidadMedida.textContent = `Unidad de medida: ${productosConfig[producto]}`;
            } else {
                unidadMedida.textContent = '';
            }
        }

        // Función para mostrar alertas
        function mostrarAlerta(mensaje, tipo = 'success') {
            const alert = document.getElementById('alert');
            alert.textContent = mensaje;
            alert.className = `alert alert-${tipo}`;
            alert.style.display = 'block';
            setTimeout(() => {
                alert.style.display = 'none';
            }, 3000);
        }

        // Función para agregar un producto al inventario
        function agregarProducto() {
            const producto = document.getElementById('producto').value;
            const lote = document.getElementById('lote').value;
            const cantidad = document.getElementById('cantidad').value;

            if (!producto || !lote || !cantidad) {
                mostrarAlerta('Por favor, complete todos los campos', 'error');
                return;
            }

            if (cantidad <= 0) {
                mostrarAlerta('La cantidad debe ser mayor a 0', 'error');
                return;
            }

            const inventario = JSON.parse(localStorage.getItem('inventario')) || [];
            inventario.push({
                producto,
                lote,
                cantidad: parseFloat(cantidad),
                unidad: productosConfig[producto],
                fechaHora: new Date().toLocaleString()
            });

            localStorage.setItem('inventario', JSON.stringify(inventario));
            mostrarHistorialInventario();
            mostrarAlerta('Producto agregado correctamente');

            // Limpiar formulario
            document.getElementById('producto').value = '';
            document.getElementById('lote').value = '';
            document.getElementById('cantidad').value = '';
            document.getElementById('unidadMedida').textContent = '';
        }

        // Función para eliminar un item del inventario
        function eliminarItemInventario(index) {
            if (confirm('¿Está seguro de eliminar este item?')) {
                const inventario = JSON.parse(localStorage.getItem('inventario')) || [];
                inventario.splice(index, 1);
                localStorage.setItem('inventario', JSON.stringify(inventario));
                mostrarHistorialInventario();
                mostrarAlerta('Item eliminado correctamente');
            }
        }

        // Función para obtener el estado del stock
        function obtenerEstadoStock(cantidad, producto) {
            const consumoEstimado = consumoPorBin[producto] * 5; // 5 bins como referencia
            const porcentaje = cantidad / consumoEstimado;

            if (porcentaje <= umbralStockBajo) {
                return { texto: 'Bajo', clase: 'stock-bajo' };
            } else if (porcentaje <= 0.5) {
                return { texto: 'Medio', clase: 'stock-medio' };
            } else {
                return { texto: 'Alto', clase: 'stock-alto' };
            }
        }

        // Función para calcular la equivalencia en bins
        function calcularEquivalenciaBins(cantidad, producto) {
            if (!consumoPorBin[producto]) return { bins: 0, porcentaje: 0 };
            const bins = cantidad / consumoPorBin[producto];
            return {
                bins: bins.toFixed(1),
                porcentaje: ((bins / 5) * 100).toFixed(1) // Porcentaje basado en 5 bins
            };
        }

        // Función para mostrar el historial de inventario
        function mostrarHistorialInventario() {
            const historialInventario = document.getElementById('historialInventario').getElementsByTagName('tbody')[0];
            historialInventario.innerHTML = '';

            const inventario = JSON.parse(localStorage.getItem('inventario')) || [];

            // Ordenar por fecha (los más antiguos primero)
            inventario.sort((a, b) => new Date(a.fechaHora) - new Date(b.fechaHora));

            inventario.forEach((item, index) => {
                const row = historialInventario.insertRow();
                const cantidad = parseFloat(item.cantidad);
                const estado = obtenerEstadoStock(cantidad, item.producto);
                const equivalencia = calcularEquivalenciaBins(cantidad, item.producto);
                
                row.innerHTML = `
                    <td>${item.producto}</td>
                    <td>${item.lote}</td>
                    <td class="${estado.clase}">${item.cantidad}</td>
                    <td>${item.unidad}</td>
                    <td class="${estado.clase}">
                        ${equivalencia.bins} bins
                        <br>
                        <small>(${equivalencia.porcentaje}% de 5 bins)</small>
                    </td>
                    <td class="${estado.clase}">${estado.texto}</td>
                    <td>${item.fechaHora}</td>
                    <td>
                        <button class="btn btn-danger" onclick="eliminarItemInventario(${index})">Eliminar</button>
                    </td>
                `;
            });

            // Mostrar alertas de stock bajo
            mostrarAlertasStockBajo();
        }

        // Función para verificar stock bajo
        function verificarStockBajo() {
            const inventario = JSON.parse(localStorage.getItem('inventario')) || [];
            const alertas = [];

            inventario.forEach(item => {
                const cantidad = parseFloat(item.cantidad);
                const estado = obtenerEstadoStock(cantidad, item.producto);
                
                if (estado.texto === 'Bajo') {
                    alertas.push({
                        producto: item.producto,
                        lote: item.lote,
                        cantidad: cantidad,
                        unidad: item.unidad
                    });
                }
            });

            return alertas;
        }

        // Función para mostrar alertas de stock bajo
        function mostrarAlertasStockBajo() {
            const alertas = verificarStockBajo();
            if (alertas.length > 0) {
                let mensaje = '⚠️ Alertas de Stock Bajo:\n\n';
                alertas.forEach(alerta => {
                    mensaje += `${alerta.producto} (Lote: ${alerta.lote}): ${alerta.cantidad} ${alerta.unidad}\n`;
                });
                mostrarAlerta(mensaje, 'warning');
            }
        }

        // Función para calcular el consumo estimado
        function calcularConsumoEstimado() {
            const bins = parseInt(document.getElementById('bins').value) || 1;
            const consumoEstimado = document.getElementById('consumoEstimado');
            document.getElementById('binsValue').textContent = bins;
            
            let html = '<ul>';
            for (const [producto, cantidad] of Object.entries(consumoPorBin)) {
                const total = cantidad * bins;
                const stockActual = obtenerStockActual(producto);
                const equivalencia = calcularEquivalenciaBins(stockActual, producto);
                const estado = obtenerEstadoStock(stockActual, producto);
                
                html += `
                    <li>
                        ${producto}: ${total} ${productosConfig[producto]}
                        <br>
                        <small>
                            Stock disponible: ${stockActual} ${productosConfig[producto]} 
                            (${equivalencia.bins} bins)
                            <span class="${estado.clase}">${estado.texto}</span>
                        </small>
                    </li>`;
            }
            html += '</ul>';
            
            consumoEstimado.innerHTML = html;
        }

        // Función para obtener el stock actual de un producto
        function obtenerStockActual(producto) {
            const inventario = JSON.parse(localStorage.getItem('inventario')) || [];
            return inventario
                .filter(item => item.producto === producto)
                .reduce((total, item) => total + parseFloat(item.cantidad), 0);
        }

        // Función para verificar stock disponible
        function verificarStockDisponible(bins) {
            const inventario = JSON.parse(localStorage.getItem('inventario')) || [];
            const resultados = [];

            for (const [producto, consumo] of Object.entries(consumoPorBin)) {
                const cantidadNecesaria = consumo * bins;
                const stockDisponible = obtenerStockActual(producto);
                const disponible = stockDisponible >= cantidadNecesaria;

                resultados.push({
                    producto,
                    disponible,
                    cantidadNecesaria,
                    stockDisponible
                });
            }

            return resultados;
        }

        // Función para descontar del inventario
        function descontarDelInventario(bins) {
            let inventario = JSON.parse(localStorage.getItem('inventario')) || [];
            const consumo = [];

            for (const [producto, consumoPorBin] of Object.entries(consumoPorBin)) {
                let cantidadNecesaria = consumoPorBin * bins;
                let inventarioProducto = inventario.filter(item => item.producto === producto);
                
                // Ordenar por fecha (FIFO)
                inventarioProducto.sort((a, b) => new Date(a.fechaHora) - new Date(b.fechaHora));

                while (cantidadNecesaria > 0 && inventarioProducto.length > 0) {
                    const item = inventarioProducto[0];
                    const cantidadDisponible = parseFloat(item.cantidad);
                    
                    if (cantidadDisponible <= cantidadNecesaria) {
                        // Consumir todo el lote
                        consumo.push({
                            producto: item.producto,
                            lote: item.lote,
                            cantidad: cantidadDisponible
                        });
                        cantidadNecesaria -= cantidadDisponible;
                        inventarioProducto.shift();
                    } else {
                        // Consumir parcialmente el lote
                        consumo.push({
                            producto: item.producto,
                            lote: item.lote,
                            cantidad: cantidadNecesaria
                        });
                        item.cantidad = (cantidadDisponible - cantidadNecesaria).toFixed(2);
                        cantidadNecesaria = 0;
                    }
                }

                if (cantidadNecesaria > 0) {
                    throw new Error(`No hay suficiente stock de ${producto}`);
                }
            }

            // Actualizar el inventario principal
            inventario = inventarioProducto;
            localStorage.setItem('inventario', JSON.stringify(inventario));

            return consumo;
        }

        // Función para registrar una elaboración
        function registrarElaboracion() {
            const cliente = document.getElementById('cliente').value;
            const referencia = document.getElementById('referencia').value;
            const bins = parseInt(document.getElementById('bins').value);

            if (!cliente || !referencia || !bins) {
                mostrarAlerta('Por favor, complete todos los campos', 'error');
                return;
            }

            try {
                // Verificar stock disponible
                const verificacionStock = verificarStockDisponible(bins);
                const stockInsuficiente = verificacionStock.find(item => !item.disponible);

                if (stockInsuficiente) {
                    mostrarAlerta(
                        `Stock insuficiente de ${stockInsuficiente.producto}. ` +
                        `Necesario: ${stockInsuficiente.cantidadNecesaria} ${productosConfig[stockInsuficiente.producto]}, ` +
                        `Disponible: ${stockInsuficiente.stockDisponible} ${productosConfig[stockInsuficiente.producto]}`,
                        'error'
                    );
                    return;
                }

                // Descontar del inventario
                const consumo = descontarDelInventario(bins);

                // Registrar la elaboración
                const elaboraciones = JSON.parse(localStorage.getItem('elaboraciones')) || [];
                elaboraciones.push({
                    cliente,
                    referencia,
                    bins,
                    consumo,
                    fechaHora: new Date().toLocaleString()
                });

                localStorage.setItem('elaboraciones', JSON.stringify(elaboraciones));
                mostrarHistorialElaboraciones();
                mostrarHistorialInventario();
                mostrarAlerta('Elaboración registrada correctamente');

                // Limpiar formulario
                document.getElementById('cliente').value = '';
                document.getElementById('referencia').value = '';
                document.getElementById('bins').value = '1';
                calcularConsumoEstimado();
            } catch (error) {
                mostrarAlerta(error.message, 'error');
            }
        }

        // Función para mostrar el historial de elaboraciones
        function mostrarHistorialElaboraciones() {
            const historialElaboraciones = document.getElementById('historialElaboraciones').getElementsByTagName('tbody')[0];
            historialElaboraciones.innerHTML = '';

            const elaboraciones = JSON.parse(localStorage.getItem('elaboraciones')) || [];

            elaboraciones.forEach(elaboracion => {
                const row = historialElaboraciones.insertRow();
                const consumoHtml = elaboracion.consumo.map(item => 
                    `${item.producto}: ${item.cantidad} ${productosConfig[item.producto]} (Lote: ${item.lote})`
                ).join('<br>');

                row.innerHTML = `
                    <td>${elaboracion.cliente}</td>
                    <td>${elaboracion.referencia}</td>
                    <td>${elaboracion.bins}</td>
                    <td>${consumoHtml}</td>
                    <td>${elaboracion.fechaHora}</td>
                `;
            });
        }

        // Agregar evento para actualizar consumo estimado
        document.getElementById('bins').addEventListener('input', calcularConsumoEstimado);

        // Mostrar la sección de Gestión de Inventario por defecto
        showSection('gestionInventario');

        // Cargar datos iniciales
        mostrarHistorialInventario();
        mostrarHistorialElaboraciones();
        calcularConsumoEstimado();
    </script>
</body>
</html>
