<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Gestión de Producción</title>
    <style>
        :root {
            --primary-color: #1a1b4b;
            --secondary-color: #292a73;
            --accent-color: #f72585;
            --light-color: #4cc9f0;
            --dark-color: #0f1033;
            --success-color: #4ef037;
            --danger-color: #ff006e;
            --warning-color: #fb8500;
            --text-primary: #ffffff;
            --text-secondary: #b8c7ff;
            --border-color: #292a73;
            --hover-color: #3a3b8c;
            --card-bg: #1a1b4b;
            --input-bg: #292a73;
            --input-border: #3a3b8c;
            --shadow-color: rgba(247, 37, 133, 0.2);
        }

        /* Estilos base */
        body {
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
            background-color: var(--primary-color);
            color: var(--text-primary);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        /* Media query para dispositivos móviles */
        @media screen and (max-width: 430px) {
            body {
                overflow-x: hidden;
            }

            .sidebar {
                position: fixed;
                bottom: 0;
                left: 0;
                width: 100%;
                height: auto;
                flex-direction: row;
                justify-content: space-around;
                padding: 10px;
                z-index: 1000;
                background-color: var(--primary-color);
                box-shadow: 0 -2px 10px var(--shadow-color);
            }

            .sidebar button {
                padding: 10px;
                margin: 0;
                font-size: 0.9em;
                width: auto;
                min-width: 100px;
                height: 40px;
            }

            .home-button {
                margin-bottom: 0 !important;
            }

            .content {
                margin-left: 0 !important;
                padding: 10px;
                padding-bottom: 80px;
                width: 100%;
                box-sizing: border-box;
            }

            .section {
                padding: 15px;
                margin-bottom: 60px;
            }

            .section-header h2 {
                font-size: 1.5em;
                margin-bottom: 15px;
            }

            .section-nav {
                flex-direction: column;
                gap: 10px;
            }

            .section-nav button {
                width: 100%;
                margin: 0;
            }

            .form-group {
                flex-direction: column;
                margin-bottom: 15px;
            }

            .form-group input,
            .form-group select,
            .form-group textarea {
                width: 100%;
                margin: 5px 0;
                font-size: 16px;
                padding: 12px;
            }

            table {
                display: block;
                overflow-x: auto;
                white-space: nowrap;
                font-size: 0.9em;
                margin: 10px 0;
            }

            th, td {
                padding: 10px;
                min-width: 100px;
            }

            .welcome-cards {
                grid-template-columns: 1fr;
                gap: 15px;
                padding: 10px;
            }

            .welcome-card {
                padding: 20px;
            }

            .welcome-stats {
                grid-template-columns: 1fr;
                gap: 15px;
                padding: 10px;
            }

            .stat-card {
                padding: 15px;
            }

            .modal-content {
                width: 95%;
                margin: 10px auto;
                padding: 15px;
                max-height: 90vh;
                overflow-y: auto;
            }

            .notas-container {
                grid-template-columns: 1fr;
                gap: 15px;
            }

            .alert-popup {
                width: 90%;
                left: 50%;
                transform: translateX(-50%);
                font-size: 0.9em;
            }

            .historial-content {
                overflow-x: auto;
            }

            .bins-list {
                grid-template-columns: repeat(auto-fill, minmax(60px, 1fr));
                gap: 5px;
            }

            .bin-item {
                padding: 5px;
                font-size: 0.8em;
            }

            .reloj-analogico {
                width: 120px;
                height: 120px;
            }
        }

        /* Ajustes específicos para iPhone 13 */
        @media screen and (device-width: 390px) and (device-height: 844px) {
            .sidebar button {
                font-size: 0.85em;
                min-width: 90px;
            }

            .content {
                padding-bottom: 70px;
            }

            .form-group input,
            .form-group select,
            .form-group textarea {
                font-size: 16px;
                padding: 10px;
            }
        }

        /* Ajustes para la orientación landscape en móviles */
        @media screen and (orientation: landscape) and (max-height: 500px) {
            .sidebar {
                height: auto;
                padding: 5px;
            }

            .sidebar button {
                height: 35px;
                padding: 5px 10px;
            }

            .content {
                padding-bottom: 50px;
            }

            .welcome-cards,
            .welcome-stats {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        /* Media query para tablets */
        @media screen and (min-width: 431px) and (max-width: 768px) {
            .sidebar {
                width: 60px;
            }

            .sidebar button {
                padding: 10px;
                font-size: 0.9em;
            }

            .main-content {
                margin-left: 60px;
            }

            .grid-container {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        /* Media query para ordenadores */
        @media screen and (min-width: 769px) {
            .sidebar {
                width: 200px;
            }

            .main-content {
                margin-left: 200px;
            }

            .grid-container {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        /* Mejoras de accesibilidad táctil */
        @media (hover: none) {
            button, 
            select, 
            input[type="submit"] {
                min-height: 44px;
                min-width: 44px;
            }

            input, select {
                font-size: 16px;
            }
        }

        /* Ajustes para la orientación del dispositivo */
        @media screen and (orientation: landscape) and (max-width: 930px) {
            .sidebar {
                position: fixed;
                bottom: 0;
                left: 0;
                width: 100%;
                height: 50px;
                flex-direction: row;
                justify-content: space-around;
                padding: 0;
            }

            .main-content {
                margin-left: 0;
                padding-bottom: 60px;
            }
        }

        .sidebar {
            position: fixed;
            top: 0;
            left: 0;
            width: 200px;
            background-color: var(--primary-color);
            color: var(--text-primary);
            padding: 15px;
            height: 100vh;
            box-shadow: 2px 0 5px var(--shadow-color);
            display: flex;
            flex-direction: column;
            gap: 10px;
            z-index: 1000;
        }
        .sidebar button {
            width: 100%;
            padding: 12px;
            margin: 5px 0;
            background-color: var(--secondary-color);
            color: var(--text-primary);
            border: none;
            cursor: pointer;
            border-radius: 6px;
            transition: all 0.3s ease;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .home-button {
            background-color: var(--accent-color) !important;
            margin-bottom: 15px !important;
            font-weight: 600 !important;
        }
        .home-button:hover {
            background-color: var(--light-color) !important;
        }
        .home-icon {
            font-size: 1.2em;
        }
        .sidebar button:hover {
            background-color: var(--accent-color);
            transform: translateY(-2px);
            box-shadow: 0 4px 8px var(--shadow-color);
        }
        .content {
            flex: 1;
            padding: 20px;
            margin-left: 200px;
            box-sizing: border-box;
            width: calc(100% - 200px);
            min-height: 100vh;
        }
        .section {
            background-color: var(--card-bg);
            padding: 25px;
            border-radius: 12px;
            box-shadow: 0 4px 12px var(--shadow-color);
            border: 1px solid var(--border-color);
            margin-bottom: 20px;
        }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--text-primary);
        }
        select, input {
            width: 100%;
            padding: 12px;
            margin-bottom: 10px;
            border: 1px solid var(--input-border);
            border-radius: 6px;
            box-sizing: border-box;
            background-color: var(--input-bg);
            color: var(--text-primary);
            transition: all 0.3s ease;
        }
        select:focus, input:focus {
            outline: none;
            border-color: var(--light-color);
            box-shadow: 0 0 0 2px rgba(233, 69, 96, 0.2);
        }
        .unidad-medida {
            color: var(--light-color);
            font-weight: 500;
            margin-top: 5px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            background-color: var(--card-bg);
            border-radius: 8px;
            overflow: hidden;
        }
        table, th, td {
            border: 1px solid var(--border-color);
        }
        th, td {
            padding: 15px;
            text-align: left;
        }
        th {
            background-color: var(--secondary-color);
            color: var(--text-primary);
            font-weight: 500;
        }
        tr:nth-child(even) {
            background-color: var(--primary-color);
        }
        tr:hover {
            background-color: var(--hover-color);
        }
        .btn {
            padding: 12px 20px;
            background-color: var(--light-color);
            color: var(--text-primary);
            border: none;
            cursor: pointer;
            border-radius: 6px;
            transition: all 0.3s ease;
            font-weight: 500;
        }
        .btn:hover {
            background-color: #d13a4f;
            transform: translateY(-2px);
            box-shadow: 0 4px 8px var(--shadow-color);
        }
        .btn-danger {
            background-color: var(--danger-color);
        }
        .btn-danger:hover {
            background-color: #c0392b;
        }
        .btn-warning {
            background-color: var(--warning-color);
            color: var(--dark-color);
        }
        .btn-warning:hover {
            background-color: #f39c12;
        }
        .alert {
            padding: 15px;
            margin-bottom: 20px;
            border-radius: 8px;
            display: none;
            border-left: 4px solid;
        }
        .alert-success {
            background-color: rgba(46, 204, 113, 0.1);
            color: #2ecc71;
            border-left-color: #2ecc71;
        }
        .alert-error {
            background-color: rgba(231, 76, 60, 0.1);
            color: #e74c3c;
            border-left-color: #e74c3c;
        }
        .alert-warning {
            background-color: rgba(241, 196, 15, 0.1);
            color: #f1c40f;
            border-left-color: #f1c40f;
        }
        .consumo-estimado {
            background-color: var(--secondary-color);
            padding: 15px;
            border-radius: 8px;
            margin-top: 10px;
            border: 1px solid var(--border-color);
        }
        .consumo-estimado ul {
            margin: 0;
            padding-left: 20px;
        }
        .consumo-estimado li {
            margin: 8px 0;
            color: var(--text-secondary);
        }
        .stock-bajo {
            color: var(--danger-color);
            font-weight: 500;
        }
        .stock-medio {
            color: var(--warning-color);
            font-weight: 500;
        }
        .stock-alto {
            color: var(--success-color);
            font-weight: 500;
        }
        .bins-checklist {
            background-color: var(--card-bg);
            padding: 20px;
            border-radius: 12px;
            margin-top: 15px;
            max-height: 400px;
            overflow-y: auto;
            border: 1px solid var(--border-color);
        }
        .bins-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--border-color);
            position: sticky;
            top: 0;
            background-color: var(--card-bg);
            z-index: 1;
        }
        .bins-actions {
            display: flex;
            gap: 10px;
        }
        .bins-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(80px, 1fr));
            gap: 8px;
            padding: 15px;
            background-color: var(--secondary-color);
            border-radius: 8px;
        }
        .bin-item {
            display: flex;
            align-items: center;
            gap: 5px;
            padding: 8px;
            background-color: var(--card-bg);
            border-radius: 6px;
            border: 1px solid var(--border-color);
            cursor: pointer;
            transition: all 0.2s ease;
            font-size: 0.85em;
        }
        .bin-item:hover {
            background-color: var(--hover-color);
            border-color: var(--light-color);
            transform: translateY(-2px);
        }
        .bin-item input[type="checkbox"] {
            margin: 0;
            cursor: pointer;
            width: 16px;
            height: 16px;
        }
        .bin-item label {
            margin: 0;
            font-weight: normal;
            color: var(--text-secondary);
            cursor: pointer;
            flex-grow: 1;
            text-align: center;
        }
        .bin-item.checked {
            background-color: var(--secondary-color);
            border-color: var(--success-color);
        }
        .bin-item.checked label {
            color: var(--success-color);
            font-weight: 500;
        }
        .alert-popup {
            display: none;
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 1000;
            min-width: 300px;
            max-width: 400px;
            padding: 15px 20px;
            border-radius: 8px;
            box-shadow: 0 4px 12px var(--shadow-color);
            animation: slideIn 0.3s ease-out;
            font-size: 0.95em;
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
        }
        .alert-popup.success {
            border-left: 4px solid var(--success-color);
        }
        .alert-popup.error {
            border-left: 4px solid var(--danger-color);
        }
        .alert-popup.warning {
            border-left: 4px solid var(--warning-color);
        }
        .alert-popup .alert-header {
            display: flex;
            align-items: center;
            margin-bottom: 10px;
            font-weight: 500;
            color: var(--text-primary);
        }
        .alert-popup .alert-content {
            margin-bottom: 10px;
            line-height: 1.4;
            color: var(--text-secondary);
        }
        .alert-popup .alert-close {
            position: absolute;
            top: 10px;
            right: 10px;
            cursor: pointer;
            font-size: 1.2em;
            opacity: 0.6;
            transition: opacity 0.2s;
            color: var(--text-secondary);
        }
        .alert-popup .alert-close:hover {
            opacity: 1;
            color: var(--text-primary);
        }
        .historial-container {
            margin-top: 25px;
        }
        .btn-historial {
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px;
            background-color: var(--secondary-color);
            color: var(--text-primary);
            border: none;
            border-radius: 8px;
            cursor: pointer;
            margin-bottom: 15px;
            transition: all 0.3s ease;
            font-weight: 500;
        }
        .btn-historial:hover {
            background-color: var(--accent-color);
            transform: translateY(-2px);
            box-shadow: 0 4px 8px var(--shadow-color);
        }
        .toggle-icon {
            transition: transform 0.3s ease;
            color: var(--text-secondary);
        }
        .toggle-icon.active {
            transform: rotate(180deg);
            color: var(--light-color);
        }
        .historial-content {
            background-color: var(--card-bg);
            border-radius: 8px;
            box-shadow: 0 4px 12px var(--shadow-color);
            overflow: hidden;
            transition: all 0.3s ease;
            border: 1px solid var(--border-color);
        }
        .historial-content table {
            margin: 0;
        }
        h2 {
            color: var(--text-primary);
            margin-bottom: 25px;
            font-size: 1.8em;
            font-weight: 600;
        }
        h3 {
            color: var(--text-primary);
            margin-bottom: 20px;
            font-size: 1.4em;
            font-weight: 500;
        }
        .calendar-controls {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        .calendar-nav {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .calendar-container {
            border: 1px solid #ddd;
            border-radius: 8px;
            overflow: hidden;
            background-color: white;
        }
        .calendar-header {
            display: flex;
            border-bottom: 1px solid #ddd;
        }
        .mes-header {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            background-color: #f8f9fa;
            border-bottom: 1px solid #ddd;
        }
        .mes-dia-header {
            padding: 10px;
            text-align: center;
            font-weight: bold;
            border-right: 1px solid #ddd;
        }
        .mes-dia-header:last-child {
            border-right: none;
        }
        .mes-fila {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            border-bottom: 1px solid #ddd;
        }
        .mes-celda {
            min-height: 100px;
            padding: 5px;
            border-right: 1px solid #ddd;
            position: relative;
            cursor: pointer;
        }
        .mes-celda:last-child {
            border-right: none;
        }
        .mes-celda:hover {
            background-color: #f8f9fa;
        }
        .mes-celda-vacia {
            background-color: #f8f9fa;
            cursor: default;
        }
        .actividad-mes {
            margin: 2px;
            padding: 4px;
            border-radius: 4px;
            font-size: 0.8em;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            cursor: pointer;
        }
        .actividad-mes:hover {
            z-index: 1;
            position: relative;
        }
        .calendar-sidebar {
            width: 100px;
            border-right: 1px solid #ddd;
            background-color: #f8f9fa;
        }
        .hora-header {
            padding: 10px;
            text-align: center;
            font-weight: bold;
            background-color: #f8f9fa;
            border-bottom: 1px solid #ddd;
        }
        .horas {
            display: flex;
            flex-direction: column;
        }
        .hora {
            height: 60px;
            padding: 10px;
            text-align: center;
            border-bottom: 1px solid #ddd;
            font-size: 0.9em;
            color: #666;
        }
        .calendar-grid {
            flex: 1;
            display: flex;
            overflow-x: auto;
        }
        .dia {
            flex: 1;
            min-width: 150px;
            border-right: 1px solid #ddd;
            position: relative;
        }
        .dia-header {
            padding: 10px;
            text-align: center;
            font-weight: bold;
            background-color: #f8f9fa;
            border-bottom: 1px solid #ddd;
            position: sticky;
            top: 0;
            z-index: 1;
        }
        .celda-hora {
            height: 60px;
            border-bottom: 1px solid #ddd;
            position: relative;
            background-color: white;
        }
        .actividad {
            position: absolute;
            left: 2px;
            right: 2px;
            border-radius: 4px;
            font-size: 0.8em;
            cursor: pointer;
            overflow: hidden;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            transition: transform 0.2s, box-shadow 0.2s;
            padding: 4px;
        }
        .actividad:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            z-index: 1;
        }
        .actividad strong {
            display: block;
            margin-bottom: 2px;
        }
        .actividad small {
            display: block;
            opacity: 0.8;
        }
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.5);
            z-index: 1000;
        }
        .modal-content {
            position: relative;
            background-color: var(--card-bg);
            margin: 50px auto;
            padding: 20px;
            width: 90%;
            max-width: 500px;
            border-radius: 8px;
            box-shadow: 0 4px 12px var(--shadow-color);
            border: 1px solid var(--border-color);
        }
        .modal-content h3 {
            color: var(--text-primary);
            margin-bottom: 20px;
            font-size: 1.4em;
            font-weight: 500;
        }
        .modal-content .form-group {
            margin-bottom: 20px;
        }
        .modal-content label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--text-primary);
        }
        .modal-content select, 
        .modal-content input, 
        .modal-content textarea {
            width: 100%;
            padding: 12px;
            margin-bottom: 10px;
            border: 1px solid var(--input-border);
            border-radius: 6px;
            box-sizing: border-box;
            background-color: var(--input-bg);
            color: var(--text-primary);
            transition: all 0.3s ease;
        }
        .modal-content select:focus, 
        .modal-content input:focus, 
        .modal-content textarea:focus {
            outline: none;
            border-color: var(--light-color);
            box-shadow: 0 0 0 2px rgba(74, 138, 199, 0.2);
        }
        .modal-content select option {
            background-color: var(--input-bg);
            color: var(--text-primary);
        }
        .modal-buttons {
            display: flex;
            justify-content: flex-end;
            gap: 10px;
            margin-top: 20px;
        }
        /* Estilos para el Calendario de Programación */
        .calendario-controls {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            background-color: var(--card-bg);
            padding: 15px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
        }
        .calendario-nav {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        .vista-controls {
            display: flex;
            gap: 10px;
        }
        .calendario-container {
            display: flex;
            background-color: var(--card-bg);
            border-radius: 8px;
            border: 1px solid var(--border-color);
            overflow: hidden;
        }
        .calendar-sidebar {
            width: 100px;
            border-right: 1px solid var(--border-color);
            background-color: var(--secondary-color);
        }
        .hora-header {
            padding: 15px;
            text-align: center;
            font-weight: 500;
            background-color: var(--primary-color);
            border-bottom: 1px solid var(--border-color);
        }
        .horas {
            display: flex;
            flex-direction: column;
        }
        .hora {
            height: 60px;
            padding: 10px;
            text-align: center;
            border-bottom: 1px solid var(--border-color);
            font-size: 0.9em;
            color: var(--text-secondary);
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .calendar-grid {
            flex: 1;
            display: flex;
            overflow-x: auto;
        }
        .dia {
            flex: 1;
            min-width: 150px;
            border-right: 1px solid var(--border-color);
            position: relative;
        }
        .dia-header {
            padding: 15px;
            text-align: center;
            font-weight: 500;
            background-color: var(--primary-color);
            border-bottom: 1px solid var(--border-color);
            position: sticky;
            top: 0;
            z-index: 1;
        }
        .celda-hora {
            height: 60px;
            border-bottom: 1px solid var(--border-color);
            position: relative;
            background-color: var(--card-bg);
            cursor: pointer;
            transition: background-color 0.2s;
        }
        .celda-hora:hover {
            background-color: var(--hover-color);
        }
        .actividad {
            position: absolute;
            left: 2px;
            right: 2px;
            border-radius: 4px;
            font-size: 0.8em;
            cursor: pointer;
            overflow: hidden;
            box-shadow: 0 2px 4px var(--shadow-color);
            transition: transform 0.2s, box-shadow 0.2s;
            padding: 4px;
            color: var(--text-primary);
        }
        .actividad:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px var(--shadow-color);
            z-index: 1;
        }
        .actividad strong {
            display: block;
            margin-bottom: 2px;
        }
        .actividad small {
            display: block;
            opacity: 0.8;
        }
        /* Estilos para la vista mensual */
        .mes-header {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            background-color: var(--primary-color);
            border-bottom: 1px solid var(--border-color);
        }
        .mes-dia-header {
            padding: 10px;
            text-align: center;
            font-weight: 500;
            border-right: 1px solid var(--border-color);
        }
        .mes-dia-header:last-child {
            border-right: none;
        }
        .mes-fila {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            border-bottom: 1px solid var(--border-color);
        }
        .mes-celda {
            min-height: 100px;
            padding: 5px;
            border-right: 1px solid var(--border-color);
            position: relative;
            cursor: pointer;
            background-color: var(--card-bg);
        }
        .mes-celda:last-child {
            border-right: none;
        }
        .mes-celda:hover {
            background-color: var(--hover-color);
        }
        .mes-celda-vacia {
            background-color: var(--secondary-color);
            cursor: default;
        }
        .actividad-mes {
            margin: 2px;
            padding: 4px;
            border-radius: 4px;
            font-size: 0.8em;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            cursor: pointer;
            color: var(--text-primary);
        }
        .actividad-mes:hover {
            z-index: 1;
            position: relative;
        }
        /* Estilos para el modal de actividad */
        textarea {
            width: 100%;
            padding: 12px;
            margin-bottom: 10px;
            border: 1px solid var(--input-border);
            border-radius: 6px;
            box-sizing: border-box;
            background-color: var(--input-bg);
            color: var(--text-primary);
            resize: vertical;
        }
        textarea:focus {
            outline: none;
            border-color: var(--light-color);
            box-shadow: 0 0 0 2px rgba(233, 69, 96, 0.2);
        }
        /* Estilos para las cuadrículas */
        .cuadriculas-controls {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            background-color: var(--card-bg);
            padding: 15px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
        }
        .cuadriculas-nav {
            display: flex;
            gap: 10px;
        }
        .contenedor-cuadriculas {
            background-color: var(--card-bg);
            padding: 20px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
            min-height: 400px;
        }
        .cuadricula {
            display: grid;
            gap: 2px;
            background-color: var(--border-color);
            padding: 2px;
            border-radius: 4px;
        }
        .celda-cuadricula {
            background-color: var(--input-bg);
            padding: 8px;
            border-radius: 4px;
            min-height: 60px;
            cursor: pointer;
            transition: all 0.2s ease;
        }
        .celda-cuadricula:hover {
            background-color: var(--hover-color);
        }
        .celda-cuadricula.editing {
            background-color: var(--secondary-color);
        }
        .celda-cuadricula textarea {
            width: 100%;
            height: 100%;
            min-height: 60px;
            background-color: transparent;
            border: none;
            color: var(--text-primary);
            resize: none;
            padding: 8px;
            font-family: inherit;
        }
        .celda-cuadricula textarea:focus {
            outline: none;
        }
        #selectorCuadriculas {
            min-width: 200px;
        }
        /* Estilos para la sección de notas */
        .notas-controls {
            display: flex;
            justify-content: flex-end;
            margin-bottom: 20px;
            background-color: var(--card-bg);
            padding: 15px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
        }
        .notas-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            background-color: var(--card-bg);
            padding: 20px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
            min-height: 400px;
        }
        .nueva-nota, .historial-notas {
            background-color: var(--secondary-color);
            padding: 20px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
        }
        .nueva-nota h3, .historial-notas h3 {
            margin-top: 0;
            margin-bottom: 15px;
            color: var(--text-primary);
            font-size: 1.2em;
        }
        .plantillas-controls {
            margin-bottom: 15px;
        }
        .plantillas-controls select {
            width: 100%;
            padding: 10px;
            background-color: var(--input-bg);
            border: 1px solid var(--input-border);
            border-radius: 6px;
            color: var(--text-primary);
            font-size: 1em;
            cursor: pointer;
        }
        .plantillas-controls select:focus {
            outline: none;
            border-color: var(--light-color);
            box-shadow: 0 0 0 2px rgba(74, 138, 199, 0.2);
        }
        #areaNotas {
            width: 100%;
            height: 200px;
            padding: 15px;
            background-color: var(--input-bg);
            border: 1px solid var(--input-border);
            border-radius: 6px;
            color: var(--text-primary);
            font-family: inherit;
            font-size: 1em;
            line-height: 1.5;
            resize: none;
        }
        .lista-notas {
            max-height: 400px;
            overflow-y: auto;
        }
        .nota-item {
            background-color: var(--input-bg);
            padding: 15px;
            margin-bottom: 10px;
            border-radius: 6px;
            border: 1px solid var(--border-color);
        }
        .nota-item .nota-fecha {
            font-size: 0.8em;
            color: var(--text-secondary);
            margin-bottom: 8px;
        }
        .nota-item .nota-contenido {
            white-space: pre-wrap;
            color: var(--text-primary);
        }
        .nota-item .nota-acciones {
            margin-top: 10px;
            display: flex;
            gap: 10px;
            justify-content: flex-end;
        }
        /* Estilos para la pantalla de bienvenida */
        .welcome-container {
            text-align: center;
            padding: 40px 20px;
        }
        .welcome-container h1 {
            font-size: 2.5em;
            margin-bottom: 40px;
            color: var(--text-primary);
            text-shadow: 2px 2px 4px var(--shadow-color);
        }
        .welcome-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }
        .welcome-card {
            background-color: var(--card-bg);
            padding: 30px;
            border-radius: 12px;
            border: 1px solid var(--border-color);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            cursor: pointer;
        }
        .welcome-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 16px var(--shadow-color);
        }
        .card-icon {
            font-size: 3em;
            margin-bottom: 20px;
        }
        .welcome-card h3 {
            color: var(--text-primary);
            margin-bottom: 10px;
            font-size: 1.4em;
        }
        .welcome-card p {
            color: var(--text-secondary);
            font-size: 1.1em;
            line-height: 1.5;
        }
        .welcome-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }
        .stat-card {
            background-color: var(--card-bg);
            padding: 20px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
            cursor: pointer;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 16px var(--shadow-color);
        }
        .stat-value {
            font-size: 2.5em;
            font-weight: bold;
            color: var(--light-color);
            margin-bottom: 10px;
        }
        .stat-label {
            color: var(--text-secondary);
            font-size: 1.1em;
        }
        .fecha-controls {
            margin-bottom: 15px;
        }
        .fecha-controls label {
            display: block;
            margin-bottom: 8px;
            color: var(--text-primary);
        }
        .fecha-input {
            width: 100%;
            padding: 10px;
            background-color: var(--input-bg);
            border: 1px solid var(--input-border);
            border-radius: 6px;
            color: var(--text-primary);
            font-size: 1em;
        }
        .fecha-input:focus {
            outline: none;
            border-color: var(--light-color);
            box-shadow: 0 0 0 2px rgba(74, 138, 199, 0.2);
        }
        .nota-item .nota-fecha {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 0.8em;
            color: var(--text-secondary);
            margin-bottom: 8px;
        }
        .nota-fecha-programada {
            color: var(--light-color);
            font-weight: 500;
        }
        /* Estilos para el reloj analógico */
        .reloj-analogico {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: var(--card-bg);
            border: 4px solid var(--light-color);
            position: relative;
            margin: 0 auto;
            box-shadow: 0 0 20px rgba(74, 138, 199, 0.3);
        }
        .reloj-centro {
            width: 12px;
            height: 12px;
            background: var(--light-color);
            border-radius: 50%;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 10;
        }
        .reloj-aguja {
            position: absolute;
            bottom: 50%;
            left: 50%;
            transform-origin: bottom;
            background: var(--light-color);
            border-radius: 4px;
        }
        .reloj-hora {
            width: 4px;
            height: 40px;
            margin-left: -2px;
        }
        .reloj-minuto {
            width: 3px;
            height: 50px;
            margin-left: -1.5px;
        }
        .reloj-segundo {
            width: 2px;
            height: 60px;
            margin-left: -1px;
            background: var(--danger-color);
        }
        .reloj-marcas {
            position: absolute;
            width: 100%;
            height: 100%;
        }
        .reloj-marca {
            position: absolute;
            width: 2px;
            height: 10px;
            background: var(--light-color);
            left: 50%;
            transform-origin: 50% 70px;
        }
        .reloj-fecha {
            position: absolute;
            bottom: -30px;
            left: 50%;
            transform: translateX(-50%);
            color: var(--text-secondary);
            font-size: 0.8em;
            white-space: nowrap;
            text-align: center;
        }
        /* Estilos para la sección de Elaboración */
        .section-header {
            margin-bottom: 30px;
        }
        .section-nav {
            display: flex;
            gap: 15px;
            margin-top: 20px;
            flex-wrap: wrap;
        }
        .section-nav .btn {
            flex: 1;
            min-width: 200px;
            text-align: center;
            background-color: var(--secondary-color);
            transition: all 0.3s ease;
        }
        .section-nav .btn:hover {
            background-color: var(--accent-color);
            transform: translateY(-2px);
        }
        #subSectionContent {
            background-color: var(--card-bg);
            padding: 20px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
        }
    </style>
</head>
<body>
    <div class="sidebar">
        <button onclick="showSection('bienvenida')" class="home-button">
            <span class="home-icon">🏠</span> Home
        </button>
        <button onclick="showSection('elaboracion')">
            <span class="section-icon">⚙️</span> Elaboración
        </button>
        <button onclick="showSection('gestionPersonas')">Gestión de Personas</button>
    </div>
    <div class="content">
        <div id="alertContainer"></div>
        
        <!-- Pantalla de Bienvenida -->
        <div id="bienvenida" class="section">
            <div class="welcome-container">
                <h1>Bienvenido al Sistema de Gestión</h1>
                <div class="welcome-cards">
                    <div class="welcome-card" onclick="showSection('elaboracion')">
                        <div class="card-icon">⚙️</div>
                        <h3>Elaboración</h3>
                        <p>Gestiona el inventario, elaboraciones y programación</p>
                    </div>
                    <div class="welcome-card" onclick="showSection('gestionPersonas')">
                        <div class="card-icon">👥</div>
                        <h3>Gestión de Personas</h3>
                        <p>Administra el personal y sus cargos</p>
                    </div>
                </div>
                <div class="welcome-stats">
                    <div class="stat-card">
                        <div class="reloj-analogico">
                            <div class="reloj-marcas"></div>
                            <div class="reloj-aguja reloj-hora"></div>
                            <div class="reloj-aguja reloj-minuto"></div>
                            <div class="reloj-aguja reloj-segundo"></div>
                            <div class="reloj-centro"></div>
                        </div>
                        <div class="reloj-fecha" id="fechaReloj"></div>
                        <div class="stat-label">Hora Actual</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value" id="totalElaboraciones">0</div>
                        <div class="stat-label">Elaboraciones Totales</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value" id="totalNotas">0</div>
                        <div class="stat-label">Notas Guardadas</div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Sección de Elaboración -->
        <div id="elaboracion" class="section">
            <div class="section-header">
                <h2>Elaboración</h2>
                <div class="section-nav">
                    <button class="btn" onclick="showSubSection('gestionElaboraciones')">Gestión de Elaboraciones</button>
                    <button class="btn" onclick="showSubSection('gestionInventario')">Gestión de Inventario</button>
                    <button class="btn" onclick="showSubSection('notas')">Notas y Programación</button>
                </div>
            </div>
            <div id="subSectionContent">
                <!-- El contenido de las subsecciones se cargará aquí -->
            </div>
        </div>
        
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
            
            <div class="historial-container">
                <button class="btn btn-historial" onclick="toggleHistorial('historialInventario')">
                    Historial de Inventario
                    <span class="toggle-icon">▼</span>
                </button>
                <div id="historialInventario" class="historial-content" style="display: none;">
                    <table>
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
            </div>
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
                <input type="number" id="bins" min="1" max="200" placeholder="Ingrese el número de bins">
            </div>
            <div class="form-group">
                <label>Consumo Estimado por <span id="binsValue">1</span> Bins:</label>
                <div id="consumoEstimado" class="consumo-estimado"></div>
            </div>
            <button class="btn" onclick="registrarElaboracion()">Registrar Elaboración</button>
            
            <div class="historial-container">
                <button class="btn btn-historial" onclick="toggleHistorial('historialElaboraciones')">
                    Historial de Elaboraciones
                    <span class="toggle-icon">▼</span>
                </button>
                <div id="historialElaboraciones" class="historial-content" style="display: none;">
                    <div class="historial-actions">
                        <button class="btn btn-danger" onclick="eliminarElaboracionesSeleccionadas()" id="btnEliminarSeleccionados" style="display: none;">
                            Eliminar Seleccionados
                        </button>
                    </div>
                    <table>
                        <thead>
                            <tr>
                                <th><input type="checkbox" id="seleccionarTodos" onchange="seleccionarTodasElaboraciones()"></th>
                                <th>Cliente</th>
                                <th>Referencia</th>
                                <th>Número de Bins</th>
                                <th>Consumo</th>
                                <th>Fecha y Hora</th>
                                <th>Acciones</th>
                            </tr>
                        </thead>
                        <tbody>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>

        <!-- Sección de Notas y Programación -->
        <div id="notas" class="section">
            <h2>Notas y Programación</h2>
            <div class="notas-controls">
                <button class="btn" onclick="guardarNota()">Guardar Nota</button>
            </div>
            <div class="notas-container">
                <div class="nueva-nota">
                    <h3>Nueva Nota</h3>
                    <div class="fecha-controls">
                        <label for="fechaNota">Fecha de la nota:</label>
                        <input type="date" id="fechaNota" class="fecha-input">
                    </div>
                    <div class="form-group">
                        <label for="personaAsignada">Personas Asignadas:</label>
                        <select id="personaAsignada" class="fecha-input" multiple>
                            <option value="">Seleccione una o más personas</option>
                        </select>
                    </div>
                    <textarea id="areaNotas" placeholder="Escriba su nota aquí..."></textarea>
                </div>
                <div class="historial-notas">
                    <h3>Historial de Notas</h3>
                    <div id="listaNotas" class="lista-notas"></div>
                </div>
            </div>
        </div>

        <!-- Sección de Gestión de Personas -->
        <div id="gestionPersonas" class="section">
            <h2>Gestión de Personas</h2>
            <div class="form-group">
                <label for="nombrePersona">Nombre:</label>
                <input type="text" id="nombrePersona" placeholder="Ingrese el nombre completo">
            </div>
            <div class="form-group">
                <label for="cargoPersona">Cargo:</label>
                <input type="text" id="cargoPersona" placeholder="Ingrese el cargo">
            </div>
            <button class="btn" onclick="agregarPersona()">Agregar Persona</button>
            
            <div class="historial-container">
                <button class="btn btn-historial" onclick="toggleHistorial('historialPersonas')">
                    Plantilla Actual
                    <span class="toggle-icon">▼</span>
                </button>
                <div id="historialPersonas" class="historial-content" style="display: none;">
                    <table>
                        <thead>
                            <tr>
                                <th>Nombre</th>
                                <th>Cargo</th>
                                <th>Acciones</th>
                            </tr>
                        </thead>
                        <tbody>
                        </tbody>
                    </table>
                </div>
            </div>
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

        // Configuración de umbrales de stock
        const umbralesStock = {
            'SAL': {
                bajo: 2000,
                medio: 7000,
                alto: 7000
            },
            'HIDRAL-70': {
                bajo: 2000,
                medio: 7000,
                alto: 7000
            },
            'HYDROMAR-4': {
                bajo: 100,
                medio: 500,
                alto: 500
            },
            'ANTIESPUMANTE': {
                bajo: 100,
                medio: 500,
                alto: 500
            }
        };

        // Variables globales para las cuadrículas
        let cuadriculas = JSON.parse(localStorage.getItem('cuadriculas')) || [];
        let cuadriculaActual = null;

        // Variables globales para las notas
        let notas = [];

        // Plantillas predeterminadas
        const plantillas = {
            lunes: `Lunes, [FECHA]

Actividades programadas:
- 

Notas importantes:
- 

Materiales necesarios:
- 

Personal asignado:
- `,
            martes: `Martes, [FECHA]

Actividades programadas:
- 

Notas importantes:
- 

Materiales necesarios:
- 

Personal asignado:
- `,
            miercoles: `Miércoles, [FECHA]

Actividades programadas:
- 

Notas importantes:
- 

Materiales necesarios:
- 

Personal asignado:
- `,
            jueves: `Jueves, [FECHA]

Actividades programadas:
- 

Notas importantes:
- 

Materiales necesarios:
- 

Personal asignado:
- `,
            viernes: `Viernes, [FECHA]

Actividades programadas:
- 

Notas importantes:
- 

Materiales necesarios:
- 

Personal asignado:
- `,
            sabado: `Sábado, [FECHA]

Actividades programadas:
- 

Notas importantes:
- 

Materiales necesarios:
- 

Personal asignado:
- `,
            domingo: `Domingo, [FECHA]

Actividades programadas:
- 

Notas importantes:
- 

Materiales necesarios:
- 

Personal asignado:
- `
        };

        // Función para mostrar una sección y ocultar las demás
        function showSection(sectionId) {
            const sections = document.getElementsByClassName('section');
            for (let section of sections) {
                section.style.display = 'none';
            }
            const sectionToShow = document.getElementById(sectionId);
            if (sectionToShow) {
                sectionToShow.style.display = 'block';
                
                // Si es la sección de elaboración, mostrar la primera subsección por defecto
                if (sectionId === 'elaboracion') {
                    showSubSection('gestionElaboraciones');
                }

                // Actualizar estadísticas cuando se muestra la pantalla de bienvenida
                if (sectionId === 'bienvenida') {
                    actualizarEstadisticas();
                }
            }
        }

        // Función para mostrar una subsección dentro de Elaboración
        function showSubSection(subSectionId) {
            const subSectionContent = document.getElementById('subSectionContent');
            if (!subSectionContent) return;

            // Obtener el contenido de la subsección
            const originalSection = document.getElementById(subSectionId);
            if (!originalSection) return;

            // Limpiar el contenedor de subsección
            subSectionContent.innerHTML = '';
            
            // Clonar el contenido de la subsección
            const content = originalSection.cloneNode(true);
            
            // Añadir el contenido clonado
            subSectionContent.appendChild(content);

            // Inicializar funcionalidades específicas según la subsección
            switch(subSectionId) {
                case 'gestionInventario':
                    mostrarHistorialInventario();
                    break;
                case 'gestionElaboraciones':
                    generarGridBins();
                    setTimeout(calcularConsumoEstimado, 100);
                    mostrarHistorialElaboraciones();
                    break;
                case 'notas':
                    cargarNotas();
                    cargarPersonasEnSelector();
                    break;
            }

            // Mostrar la subsección
            content.style.display = 'block';
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
            const container = document.getElementById('alertContainer');
            const alert = document.createElement('div');
            alert.className = `alert-popup ${tipo}`;
            
            // Configurar el ícono según el tipo
            let icon = '';
            switch(tipo) {
                case 'success':
                    icon = '✓';
                    break;
                case 'error':
                    icon = '✕';
                    break;
                case 'warning':
                    icon = '⚠';
                    break;
            }

            alert.innerHTML = `
                <div class="alert-header">
                    <span class="alert-icon">${icon}</span>
                    ${tipo === 'success' ? 'Éxito' : 
                      tipo === 'error' ? 'Error' : 
                      'Advertencia'}
                </div>
                <div class="alert-content">${mensaje}</div>
                <span class="alert-close" onclick="cerrarAlerta(this)">×</span>
            `;

            container.appendChild(alert);
            alert.style.display = 'block';

            // Cerrar automáticamente después de 5 segundos
            setTimeout(() => {
                cerrarAlerta(alert);
            }, 5000);
        }

        // Función para cerrar alertas
        function cerrarAlerta(elemento) {
            const alert = elemento.closest('.alert-popup');
            if (alert) {
                alert.style.animation = 'slideOut 0.3s ease-out';
                setTimeout(() => {
                    alert.remove();
                }, 300);
            }
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
            actualizarEstadisticas();
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
                actualizarEstadisticas();
                mostrarAlerta('Item eliminado correctamente');
            }
        }

        // Función para obtener el estado del stock
        function obtenerEstadoStock(cantidad, producto) {
            const umbrales = umbralesStock[producto];
            if (!umbrales) return { texto: 'Desconocido', clase: 'stock-desconocido' };

            if (cantidad <= umbrales.bajo) {
                return { texto: 'Bajo', clase: 'stock-bajo' };
            } else if (cantidad <= umbrales.medio) {
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

            // Agrupar por producto para calcular el stock total
            const stockTotal = {};
            inventario.forEach(item => {
                if (!stockTotal[item.producto]) {
                    stockTotal[item.producto] = 0;
                }
                stockTotal[item.producto] += parseFloat(item.cantidad);
            });

            inventario.forEach((item, index) => {
                const row = historialInventario.insertRow();
                const cantidad = parseFloat(item.cantidad);
                const stockTotalProducto = stockTotal[item.producto];
                const estado = obtenerEstadoStock(stockTotalProducto, item.producto);
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
                        ${item.producto === 'ANTIESPUMANTE' ? 
                            `<button class="btn btn-warning" onclick="modificarAntiespumante(${index})">Modificar</button>` : 
                            ''}
                        <button class="btn btn-danger" onclick="eliminarItemInventario(${index})">Eliminar</button>
                    </td>
                `;
            });

            // Mostrar alertas de stock bajo
            mostrarAlertasStockBajo();
        }

        // Función para modificar antiespumante
        function modificarAntiespumante(index) {
            const inventario = JSON.parse(localStorage.getItem('inventario')) || [];
            const item = inventario[index];
            
            if (item.producto !== 'ANTIESPUMANTE') {
                mostrarAlerta('Solo se pueden modificar items de antiespumante', 'error');
                return;
            }

            const nuevaCantidad = prompt('Ingrese la nueva cantidad en litros:', item.cantidad);
            if (nuevaCantidad === null) return;

            const cantidad = parseFloat(nuevaCantidad);
            if (isNaN(cantidad) || cantidad < 0) {
                mostrarAlerta('Por favor, ingrese una cantidad válida', 'error');
                return;
            }

            inventario[index].cantidad = cantidad;
            inventario[index].fechaHora = new Date().toLocaleString();
            
            localStorage.setItem('inventario', JSON.stringify(inventario));
            mostrarHistorialInventario();
            mostrarAlerta('Cantidad de antiespumante actualizada correctamente');
        }

        // Función para verificar stock bajo
        function verificarStockBajo() {
            const inventario = JSON.parse(localStorage.getItem('inventario')) || [];
            const alertas = [];

            // Agrupar por producto para calcular el stock total
            const stockTotal = {};
            inventario.forEach(item => {
                if (!stockTotal[item.producto]) {
                    stockTotal[item.producto] = 0;
                }
                stockTotal[item.producto] += parseFloat(item.cantidad);
            });

            // Verificar cada producto
            Object.entries(stockTotal).forEach(([producto, cantidad]) => {
                const estado = obtenerEstadoStock(cantidad, producto);
                if (estado.texto === 'Bajo') {
                    alertas.push({
                        producto,
                        cantidad: cantidad.toFixed(2),
                        unidad: productosConfig[producto]
                    });
                }
            });

            return alertas;
        }

        // Función para mostrar alertas de stock bajo
        function mostrarAlertasStockBajo() {
            const alertas = verificarStockBajo();
            if (alertas.length > 0) {
                let mensaje = '<div style="margin-bottom: 10px;">⚠️ Alertas de Stock Bajo:</div>';
                alertas.forEach(alerta => {
                    mensaje += `
                        <div style="margin: 5px 0; padding: 5px; background: rgba(255,255,255,0.5); border-radius: 4px;">
                            <strong>${alerta.producto}</strong>: ${alerta.cantidad} ${alerta.unidad}
                        </div>`;
                });
                mostrarAlerta(mensaje, 'warning');
            }
        }

        // Función para calcular el consumo estimado
        function calcularConsumoEstimado() {
            const binsInput = document.getElementById('bins');
            const consumoEstimado = document.getElementById('consumoEstimado');
            const binsValue = document.getElementById('binsValue');
            
            if (!binsInput || !consumoEstimado || !binsValue) {
                console.error('No se encontraron los elementos necesarios para calcular el consumo estimado');
                return;
            }

            const bins = parseInt(binsInput.value) || 1;
            binsValue.textContent = bins;
            
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

            // Procesar cada producto
            for (const [producto, consumoPorBinProducto] of Object.entries(consumoPorBin)) {
                let cantidadNecesaria = consumoPorBinProducto * bins;
                let inventarioProducto = inventario.filter(item => item.producto === producto);
                
                // Ordenar por fecha (FIFO)
                inventarioProducto.sort((a, b) => new Date(a.fechaHora) - new Date(b.fechaHora));

                // Procesar cada lote del producto
                for (let i = 0; i < inventarioProducto.length && cantidadNecesaria > 0; i++) {
                    const item = inventarioProducto[i];
                    const cantidadDisponible = parseFloat(item.cantidad);
                    
                    if (cantidadDisponible <= cantidadNecesaria) {
                        // Consumir todo el lote
                        consumo.push({
                            producto: item.producto,
                            lote: item.lote,
                            cantidad: cantidadDisponible
                        });
                        cantidadNecesaria -= cantidadDisponible;
                        // Eliminar el lote del inventario
                        inventario = inventario.filter(inv => inv.lote !== item.lote);
                    } else {
                        // Consumir parcialmente el lote
                        consumo.push({
                            producto: item.producto,
                            lote: item.lote,
                            cantidad: cantidadNecesaria
                        });
                        // Actualizar la cantidad del lote en el inventario
                        const index = inventario.findIndex(inv => inv.lote === item.lote);
                        if (index !== -1) {
                            inventario[index].cantidad = (cantidadDisponible - cantidadNecesaria).toFixed(2);
                        }
                        cantidadNecesaria = 0;
                    }
                }

                if (cantidadNecesaria > 0) {
                    throw new Error(`No hay suficiente stock de ${producto}`);
                }
            }

            // Actualizar el inventario
            localStorage.setItem('inventario', JSON.stringify(inventario));

            return consumo;
        }

        // Función para generar la lista de bins
        function generarGridBins() {
            const list = document.getElementById('binsList');
            if (!list) return;
            
            list.innerHTML = '';
            
            for (let i = 1; i <= 200; i++) {
                const bin = document.createElement('div');
                bin.className = 'bin-item';
                bin.innerHTML = `
                    <input type="checkbox" id="bin${i}" value="${i}" onchange="actualizarEstadoBin(this)">
                    <label for="bin${i}">${i.toString().padStart(3, '0')}</label>
                `;
                list.appendChild(bin);
            }
        }

        // Función para actualizar el estado visual del bin
        function actualizarEstadoBin(checkbox) {
            const binItem = checkbox.closest('.bin-item');
            if (checkbox.checked) {
                binItem.classList.add('checked');
            } else {
                binItem.classList.remove('checked');
            }
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
                actualizarEstadisticas();
                mostrarAlerta('Elaboración registrada correctamente');

                // Limpiar formulario
                document.getElementById('cliente').value = '';
                document.getElementById('referencia').value = '';
                document.getElementById('bins').value = '1';
            } catch (error) {
                mostrarAlerta(error.message, 'error');
            }
        }

        // Función para mostrar el historial de elaboraciones
        function mostrarHistorialElaboraciones() {
            const historialElaboraciones = document.getElementById('historialElaboraciones').getElementsByTagName('tbody')[0];
            historialElaboraciones.innerHTML = '';

            const elaboraciones = JSON.parse(localStorage.getItem('elaboraciones')) || [];
            
            // Ordenar las elaboraciones por fecha (las más recientes primero)
            elaboraciones.sort((a, b) => new Date(b.fechaHora) - new Date(a.fechaHora));

            elaboraciones.forEach((elaboracion, index) => {
                const row = historialElaboraciones.insertRow();
                const consumoHtml = elaboracion.consumo.map(item => 
                    `${item.producto}: ${item.cantidad} ${productosConfig[item.producto]} (Lote: ${item.lote})`
                ).join('<br>');
                
                row.innerHTML = `
                    <td><input type="checkbox" class="elaboracion-checkbox" value="${index}" onchange="actualizarBotonEliminar()"></td>
                    <td>${elaboracion.cliente}</td>
                    <td>${elaboracion.referencia}</td>
                    <td>${elaboracion.bins}</td>
                    <td>${consumoHtml}</td>
                    <td>${elaboracion.fechaHora}</td>
                    <td>
                        <button class="btn btn-warning" onclick="modificarElaboracion(${index})">Modificar</button>
                        <button class="btn btn-danger" onclick="eliminarElaboracion(${index})">Eliminar</button>
                    </td>
                `;
            });
        }

        // Función para seleccionar todas las elaboraciones
        function seleccionarTodasElaboraciones() {
            const checkboxTodos = document.getElementById('seleccionarTodos');
            const checkboxes = document.getElementsByClassName('elaboracion-checkbox');
            
            for (let checkbox of checkboxes) {
                checkbox.checked = checkboxTodos.checked;
            }
            
            actualizarBotonEliminar();
        }

        // Función para actualizar la visibilidad del botón de eliminar seleccionados
        function actualizarBotonEliminar() {
            const checkboxes = document.getElementsByClassName('elaboracion-checkbox');
            const btnEliminar = document.getElementById('btnEliminarSeleccionados');
            let haySeleccionados = false;
            
            for (let checkbox of checkboxes) {
                if (checkbox.checked) {
                    haySeleccionados = true;
                    break;
                }
            }
            
            btnEliminar.style.display = haySeleccionados ? 'block' : 'none';
        }

        // Función para eliminar las elaboraciones seleccionadas
        function eliminarElaboracionesSeleccionadas() {
            const checkboxes = document.getElementsByClassName('elaboracion-checkbox');
            const indicesSeleccionados = [];
            
            for (let checkbox of checkboxes) {
                if (checkbox.checked) {
                    indicesSeleccionados.push(parseInt(checkbox.value));
                }
            }
            
            if (indicesSeleccionados.length === 0) {
                mostrarAlerta('Por favor, seleccione al menos una elaboración para eliminar', 'error');
                return;
            }
            
            if (confirm(`¿Está seguro de eliminar ${indicesSeleccionados.length} elaboración(es)?`)) {
                const elaboraciones = JSON.parse(localStorage.getItem('elaboraciones')) || [];
                // Eliminar en orden descendente para evitar problemas con los índices
                indicesSeleccionados.sort((a, b) => b - a);
                indicesSeleccionados.forEach(index => {
                    elaboraciones.splice(index, 1);
                });
                
                localStorage.setItem('elaboraciones', JSON.stringify(elaboraciones));
                mostrarHistorialElaboraciones();
                actualizarEstadisticas();
                mostrarAlerta(`${indicesSeleccionados.length} elaboración(es) eliminada(s) correctamente`);
            }
        }

        // Función para modificar una elaboración
        function modificarElaboracion(index) {
            const elaboraciones = JSON.parse(localStorage.getItem('elaboraciones')) || [];
            const elaboracion = elaboraciones[index];
            
            // Crear modal de modificación
            const modal = document.createElement('div');
            modal.className = 'modal';
            modal.id = 'modalModificar';
            modal.innerHTML = `
                <div class="modal-content">
                    <h3>Modificar Elaboración</h3>
                    <div class="form-group">
                        <label for="clienteModificar">Cliente:</label>
                        <select id="clienteModificar">
                            <option value="WOFCO" ${elaboracion.cliente === 'WOFCO' ? 'selected' : ''}>WOFCO</option>
                            <option value="OVERSEA" ${elaboracion.cliente === 'OVERSEA' ? 'selected' : ''}>OVERSEA</option>
                            <option value="SCANFISK" ${elaboracion.cliente === 'SCANFISK' ? 'selected' : ''}>SCANFISK</option>
                            <option value="IBERCONSA" ${elaboracion.cliente === 'IBERCONSA' ? 'selected' : ''}>IBERCONSA</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="referenciaModificar">Referencia:</label>
                        <input type="text" id="referenciaModificar" value="${elaboracion.referencia}">
                    </div>
                    <div class="form-group">
                        <label for="binsModificar">Número de Bins:</label>
                        <input type="number" id="binsModificar" value="${elaboracion.bins}" min="1" max="200">
                    </div>
                    <div class="modal-buttons">
                        <button class="btn btn-warning" onclick="guardarModificacion(${index})">Guardar</button>
                        <button class="btn btn-danger" onclick="cerrarModalModificar()">Cancelar</button>
                    </div>
                </div>
            `;
            
            document.body.appendChild(modal);
            modal.style.display = 'block';
        }

        // Función para guardar las modificaciones de una elaboración
        function guardarModificacion(index) {
            const cliente = document.getElementById('clienteModificar').value;
            const referencia = document.getElementById('referenciaModificar').value;
            const bins = parseInt(document.getElementById('binsModificar').value);

            if (!cliente || !referencia || !bins) {
                mostrarAlerta('Por favor, complete todos los campos', 'error');
                return;
            }

            const elaboraciones = JSON.parse(localStorage.getItem('elaboraciones')) || [];
            
            // Verificar stock disponible para la nueva cantidad de bins
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

            // Actualizar la elaboración
            elaboraciones[index] = {
                ...elaboraciones[index],
                cliente,
                referencia,
                bins,
                fechaHora: new Date().toLocaleString()
            };

            localStorage.setItem('elaboraciones', JSON.stringify(elaboraciones));
            mostrarHistorialElaboraciones();
            cerrarModalModificar();
            mostrarAlerta('Elaboración modificada correctamente');
        }

        // Función para cerrar el modal de modificación
        function cerrarModalModificar() {
            const modal = document.getElementById('modalModificar');
            if (modal) {
                modal.remove();
            }
        }

        // Función para eliminar una elaboración
        function eliminarElaboracion(index) {
            if (confirm('¿Está seguro de eliminar esta elaboración?')) {
                const elaboraciones = JSON.parse(localStorage.getItem('elaboraciones')) || [];
                elaboraciones.splice(index, 1);
                localStorage.setItem('elaboraciones', JSON.stringify(elaboraciones));
                mostrarHistorialElaboraciones();
                actualizarEstadisticas();
                mostrarAlerta('Elaboración eliminada correctamente');
            }
        }

        let vistaActual = 'semana';
        let fechaSeleccionada = new Date();
        let celdaSeleccionada = null;

        // Función para cargar las notas en la interfaz
        function cargarNotas() {
            const listaNotas = document.getElementById('listaNotas');
            if (!listaNotas) return;
            
            listaNotas.innerHTML = '';
            
            // Ordenar notas por fecha programada
            notas.sort((a, b) => new Date(a.fechaProgramada) - new Date(b.fechaProgramada));
            
            notas.forEach((nota, index) => {
                const fechaProgramada = new Date(nota.fechaProgramada);
                const fechaFormateada = fechaProgramada.toLocaleDateString('es-ES', {
                    weekday: 'long',
                    year: 'numeric',
                    month: 'long',
                    day: 'numeric'
                });
                
                const notaElement = document.createElement('div');
                notaElement.className = 'nota-item';
                notaElement.innerHTML = `
                    <div class="nota-fecha">
                        <span>Fecha de creación: ${nota.fechaCreacion}</span>
                        <span class="nota-fecha-programada">Programada para: ${fechaFormateada}</span>
                    </div>
                    ${nota.personasAsignadas && nota.personasAsignadas.length > 0 ? 
                        `<div class="nota-persona">👥 Asignada a: ${nota.personasAsignadas.join(', ')}</div>` : ''}
                    <div class="nota-contenido">${nota.contenido.replace(/\n/g, '<br>')}</div>
                    <div class="nota-acciones">
                        <button class="btn btn-warning" onclick="modificarNota(${index})">Modificar</button>
                        <button class="btn btn-danger" onclick="eliminarNota(${index})">Eliminar</button>
                    </div>
                `;
                listaNotas.appendChild(notaElement);
            });
        }

        // Función para cargar las notas desde localStorage
        function cargarNotasDesdeStorage() {
            const notasGuardadas = localStorage.getItem('notas');
            if (notasGuardadas) {
                try {
                    notas = JSON.parse(notasGuardadas);
                    console.log('Notas cargadas:', notas); // Debug
                } catch (e) {
                    console.error('Error al cargar las notas:', e);
                    notas = [];
                }
            }
        }

        // Función para guardar una nueva nota
        function guardarNota() {
            const areaNotas = document.getElementById('areaNotas');
            const fechaInput = document.getElementById('fechaNota');
            const personaAsignada = document.getElementById('personaAsignada');
            
            if (!areaNotas) return;
            
            const contenido = areaNotas.value.trim();
            const fechaProgramada = fechaInput.value;
            const personas = Array.from(personaAsignada.selectedOptions).map(option => option.value).filter(value => value !== '');
            
            if (!contenido) {
                mostrarAlerta('Por favor, escriba algo antes de guardar', 'error');
                return;
            }

            if (!fechaProgramada) {
                mostrarAlerta('Por favor, seleccione una fecha para la nota', 'error');
                return;
            }

            const nuevaNota = {
                contenido: contenido,
                fechaCreacion: new Date().toLocaleString(),
                fechaProgramada: fechaProgramada,
                personasAsignadas: personas
            };

            // Añadir la nueva nota al array
            notas.push(nuevaNota);
            
            // Ordenar notas por fecha programada
            notas.sort((a, b) => new Date(a.fechaProgramada) - new Date(b.fechaProgramada));
            
            // Guardar en localStorage
            try {
                localStorage.setItem('notas', JSON.stringify(notas));
            } catch (e) {
                console.error('Error al guardar las notas:', e);
                mostrarAlerta('Error al guardar la nota', 'error');
                return;
            }
            
            // Limpiar el área de texto, la fecha y el selector de persona
            areaNotas.value = '';
            fechaInput.value = '';
            personaAsignada.value = '';
            
            // Actualizar la lista de notas
            cargarNotas();
            
            // Actualizar estadísticas
            actualizarEstadisticas();
            
            mostrarAlerta('Nota guardada correctamente');
        }

        // Función para eliminar una nota
        function eliminarNota(index) {
            if (confirm('¿Está seguro de eliminar esta nota?')) {
                notas.splice(index, 1);
                localStorage.setItem('notas', JSON.stringify(notas));
                cargarNotas();
                actualizarEstadisticas();
                mostrarAlerta('Nota eliminada correctamente');
            }
        }

        // Cargar notas al iniciar
        cargarNotasDesdeStorage();

        // Función para actualizar estadísticas
        function actualizarEstadisticas() {
            // Obtener datos de elaboraciones
            const elaboraciones = JSON.parse(localStorage.getItem('elaboraciones')) || [];
            const totalElaboraciones = elaboraciones.length;

            // Obtener datos de notas
            const notas = JSON.parse(localStorage.getItem('notas')) || [];
            const totalNotas = notas.length;

            // Actualizar los valores en la interfaz
            document.getElementById('totalElaboraciones').textContent = totalElaboraciones;
            document.getElementById('totalNotas').textContent = totalNotas;
        }

        // Función para actualizar el reloj
        function actualizarReloj() {
            const ahora = new Date();
            const hora = ahora.getHours() % 12;
            const minutos = ahora.getMinutes();
            const segundos = ahora.getSeconds();
            
            // Calcular ángulos
            const anguloHora = (hora * 30) + (minutos * 0.5); // 30 grados por hora + 0.5 por minuto
            const anguloMinuto = minutos * 6; // 6 grados por minuto
            const anguloSegundo = segundos * 6; // 6 grados por segundo
            
            // Actualizar agujas
            document.querySelector('.reloj-hora').style.transform = `rotate(${anguloHora}deg)`;
            document.querySelector('.reloj-minuto').style.transform = `rotate(${anguloMinuto}deg)`;
            document.querySelector('.reloj-segundo').style.transform = `rotate(${anguloSegundo}deg)`;
            
            // Actualizar fecha
            const fecha = ahora.toLocaleDateString('es-ES', {
                weekday: 'long',
                year: 'numeric',
                month: 'long',
                day: 'numeric'
            });
            document.getElementById('fechaReloj').textContent = fecha;
        }

        // Crear marcas del reloj
        function crearMarcasReloj() {
            const marcas = document.querySelector('.reloj-marcas');
            for (let i = 0; i < 12; i++) {
                const marca = document.createElement('div');
                marca.className = 'reloj-marca';
                marca.style.transform = `rotate(${i * 30}deg)`;
                marcas.appendChild(marca);
            }
        }

        // Inicializar reloj
        crearMarcasReloj();
        actualizarReloj();
        setInterval(actualizarReloj, 1000);

        // Mostrar la pantalla de bienvenida por defecto
        showSection('bienvenida');

        // Cargar datos iniciales
        mostrarHistorialInventario();
        mostrarHistorialElaboraciones();
        mostrarHistorialPersonas();
        cargarNotas();
        actualizarEstadisticas();

        // Agregar evento para actualizar el consumo estimado cuando cambia el número de bins
        const binsInput = document.getElementById('bins');
        if (binsInput) {
            binsInput.addEventListener('input', function() {
                calcularConsumoEstimado();
            });
        }

        // Calcular consumo estimado inicial
        calcularConsumoEstimado();

        // Agregar evento para calcular el consumo estimado cuando se muestra la sección de elaboraciones
        document.getElementById('gestionElaboraciones').addEventListener('show', function() {
            calcularConsumoEstimado();
        });

        // Inicializar localStorage si no existe
        if (!localStorage.getItem('inventario')) {
            localStorage.setItem('inventario', JSON.stringify([]));
        }
        if (!localStorage.getItem('elaboraciones')) {
            localStorage.setItem('elaboraciones', JSON.stringify([]));
        }
        if (!localStorage.getItem('personas')) {
            localStorage.setItem('personas', JSON.stringify([]));
        }
        if (!localStorage.getItem('notas')) {
            localStorage.setItem('notas', JSON.stringify([]));
        }

        // Función para alternar la visibilidad del historial
        function toggleHistorial(historialId) {
            const contenido = document.getElementById(historialId);
            const toggleIcon = contenido.previousElementSibling.querySelector('.toggle-icon');
            
            if (contenido.style.display === 'none') {
                contenido.style.display = 'block';
                toggleIcon.classList.add('active');
            } else {
                contenido.style.display = 'none';
                toggleIcon.classList.remove('active');
            }
        }

        // Función para modificar una nota
        function modificarNota(index) {
            const nota = notas[index];
            
            // Crear modal de modificación
            const modal = document.createElement('div');
            modal.className = 'modal';
            modal.id = 'modalModificarNota';
            modal.innerHTML = `
                <div class="modal-content">
                    <h3>Modificar Nota</h3>
                    <div class="form-group">
                        <label for="fechaNotaModificar">Fecha de la nota:</label>
                        <input type="date" id="fechaNotaModificar" value="${nota.fechaProgramada}" class="fecha-input">
                    </div>
                    <div class="form-group">
                        <label for="personaAsignadaModificar">Personas Asignadas:</label>
                        <select id="personaAsignadaModificar" class="fecha-input" multiple>
                            <option value="">Seleccione una o más personas</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="areaNotasModificar">Contenido:</label>
                        <textarea id="areaNotasModificar" rows="10">${nota.contenido}</textarea>
                    </div>
                    <div class="modal-buttons">
                        <button class="btn btn-warning" onclick="guardarModificacionNota(${index})">Guardar Cambios</button>
                        <button class="btn btn-danger" onclick="cerrarModalModificarNota()">Cancelar</button>
                    </div>
                </div>
            `;
            
            document.body.appendChild(modal);
            modal.style.display = 'block';

            // Cargar personas en el selector del modal
            const selector = document.getElementById('personaAsignadaModificar');
            const personas = JSON.parse(localStorage.getItem('personas')) || [];
            
            personas.forEach(persona => {
                const option = document.createElement('option');
                option.value = persona.nombre;
                option.textContent = `${persona.nombre} - ${persona.cargo}`;
                if (nota.personasAsignadas && nota.personasAsignadas.includes(persona.nombre)) {
                    option.selected = true;
                }
                selector.appendChild(option);
            });
        }

        // Función para guardar las modificaciones de una nota
        function guardarModificacionNota(index) {
            const fechaInput = document.getElementById('fechaNotaModificar');
            const areaNotas = document.getElementById('areaNotasModificar');
            const personaAsignada = document.getElementById('personaAsignadaModificar');
            
            if (!areaNotas) return;
            
            const contenido = areaNotas.value.trim();
            const fechaProgramada = fechaInput.value;
            const personas = Array.from(personaAsignada.selectedOptions).map(option => option.value).filter(value => value !== '');
            
            if (!contenido) {
                mostrarAlerta('Por favor, escriba algo antes de guardar', 'error');
                return;
            }

            if (!fechaProgramada) {
                mostrarAlerta('Por favor, seleccione una fecha para la nota', 'error');
                return;
            }

            // Actualizar la nota
            notas[index] = {
                ...notas[index],
                contenido: contenido,
                fechaProgramada: fechaProgramada,
                personasAsignadas: personas,
                fechaModificacion: new Date().toLocaleString()
            };
            
            // Ordenar notas por fecha programada
            notas.sort((a, b) => new Date(a.fechaProgramada) - new Date(b.fechaProgramada));
            
            // Guardar en localStorage
            try {
                localStorage.setItem('notas', JSON.stringify(notas));
            } catch (e) {
                console.error('Error al guardar las notas:', e);
                mostrarAlerta('Error al guardar la nota', 'error');
                return;
            }
            
            // Cerrar modal y actualizar la vista
            cerrarModalModificarNota();
            cargarNotas();
            actualizarEstadisticas();
            
            mostrarAlerta('Nota modificada correctamente');
        }

        // Función para cerrar el modal de modificación de nota
        function cerrarModalModificarNota() {
            const modal = document.getElementById('modalModificarNota');
            if (modal) {
                modal.remove();
            }
        }

        // Variables globales para la gestión de personas
        let personas = JSON.parse(localStorage.getItem('personas')) || [];

        // Función para mostrar el historial de personas
        function mostrarHistorialPersonas() {
            const historialPersonas = document.getElementById('historialPersonas').getElementsByTagName('tbody')[0];
            historialPersonas.innerHTML = '';

            // Obtener personas del localStorage
            const personas = JSON.parse(localStorage.getItem('personas')) || [];

            personas.forEach((persona, index) => {
                const row = historialPersonas.insertRow();
                row.innerHTML = `
                    <td>${persona.nombre}</td>
                    <td>${persona.cargo}</td>
                    <td>
                        <button class="btn btn-warning" onclick="modificarPersona(${index})">Modificar</button>
                        <button class="btn btn-danger" onclick="eliminarPersona(${index})">Eliminar</button>
                    </td>
                `;
            });

            // Mostrar automáticamente el historial
            document.getElementById('historialPersonas').style.display = 'block';
            document.querySelector('.toggle-icon').classList.add('active');
        }

        // Función para agregar una persona
        function agregarPersona() {
            const nombre = document.getElementById('nombrePersona').value;
            const cargo = document.getElementById('cargoPersona').value;

            if (!nombre || !cargo) {
                mostrarAlerta('Por favor, complete todos los campos', 'error');
                return;
            }

            const nuevaPersona = {
                nombre,
                cargo,
                fechaRegistro: new Date().toLocaleString()
            };

            // Obtener personas existentes
            const personas = JSON.parse(localStorage.getItem('personas')) || [];
            
            // Agregar nueva persona
            personas.push(nuevaPersona);
            
            // Guardar en localStorage
            localStorage.setItem('personas', JSON.stringify(personas));
            
            // Mostrar historial actualizado
            mostrarHistorialPersonas();
            
            // Mostrar mensaje de éxito
            mostrarAlerta('Persona agregada correctamente');

            // Limpiar formulario
            document.getElementById('nombrePersona').value = '';
            document.getElementById('cargoPersona').value = '';
        }

        // Función para modificar una persona
        function modificarPersona(index) {
            const persona = personas[index];
            
            const modal = document.createElement('div');
            modal.className = 'modal';
            modal.id = 'modalModificarPersona';
            modal.innerHTML = `
                <div class="modal-content">
                    <h3>Modificar Persona</h3>
                    <div class="form-group">
                        <label for="nombrePersonaModificar">Nombre:</label>
                        <input type="text" id="nombrePersonaModificar" value="${persona.nombre}">
                    </div>
                    <div class="form-group">
                        <label for="cargoPersonaModificar">Cargo:</label>
                        <input type="text" id="cargoPersonaModificar" value="${persona.cargo}">
                    </div>
                    <div class="modal-buttons">
                        <button class="btn btn-warning" onclick="guardarModificacionPersona(${index})">Guardar</button>
                        <button class="btn btn-danger" onclick="cerrarModalModificarPersona()">Cancelar</button>
                    </div>
                </div>
            `;
            
            document.body.appendChild(modal);
            modal.style.display = 'block';
        }

        // Función para guardar las modificaciones de una persona
        function guardarModificacionPersona(index) {
            const nombre = document.getElementById('nombrePersonaModificar').value;
            const cargo = document.getElementById('cargoPersonaModificar').value;

            if (!nombre || !cargo) {
                mostrarAlerta('Por favor, complete todos los campos', 'error');
                return;
            }

            personas[index] = {
                ...personas[index],
                nombre,
                cargo,
                fechaModificacion: new Date().toLocaleString()
            };

            localStorage.setItem('personas', JSON.stringify(personas));
            mostrarHistorialPersonas();
            cerrarModalModificarPersona();
            mostrarAlerta('Persona modificada correctamente');
        }

        // Función para cerrar el modal de modificación de persona
        function cerrarModalModificarPersona() {
            const modal = document.getElementById('modalModificarPersona');
            if (modal) {
                modal.remove();
            }
        }

        // Función para eliminar una persona
        function eliminarPersona(index) {
            if (confirm('¿Está seguro de eliminar esta persona?')) {
                personas.splice(index, 1);
                localStorage.setItem('personas', JSON.stringify(personas));
                mostrarHistorialPersonas();
                mostrarAlerta('Persona eliminada correctamente');
            }
        }

        // Cargar datos iniciales
        mostrarHistorialInventario();
        mostrarHistorialElaboraciones();
        mostrarHistorialPersonas();
        cargarNotas();
        actualizarEstadisticas();

        // Función para cargar las personas en el selector
        function cargarPersonasEnSelector() {
            const selectores = [
                document.getElementById('personaAsignada'),
                document.getElementById('personaAsignadaModificar')
            ];

            selectores.forEach(selector => {
                if (!selector) return;

                // Obtener personas del localStorage
                const personas = JSON.parse(localStorage.getItem('personas')) || [];
                
                // Limpiar opciones existentes excepto la primera
                selector.innerHTML = '<option value="">Seleccione una o más personas</option>';
                
                // Agregar cada persona como opción
                personas.forEach(persona => {
                    const option = document.createElement('option');
                    option.value = persona.nombre;
                    option.textContent = `${persona.nombre} - ${persona.cargo}`;
                    selector.appendChild(option);
                });
            });
        }
    </script>
</body>
</html> 
