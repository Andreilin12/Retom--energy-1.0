<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Gestión de Consumos</title>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/sweetalert2@11/dist/sweetalert2.min.css">
<script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>

<style>

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #2c3e50;
      color: #333;
    }

    .container {
      max-width: 9000px;
      margin: 40px auto;
      background-color: #2e3c50;
      border-radius: 10px;
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
      padding: 30px;
      overflow: hidden;
    }

    h1 {
      text-align: center;
      color: #2c3e50;
      font-size: 28px;
      margin-bottom: 30px;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 20px;

    }

    table th, table td {
      padding: 12px;
      text-align: center;
      border-radius: 8px;
      border: 1px solid #ddd;
    }

    table th {
      background-color: #2c3e50;
      color: ff9;
      font-weight: bold;
    }

    table td {
      background-color: #f9f9f9;
      font-size: 14px;
      color: #333;
    }

  /* Estilo elegante para el botón de eliminar */
  .deleteButton {
    background-color: #16a086;
    color: white;
    border: none;
    border-radius: 5px;
    padding: 8px 16px;
    font-size: 14px;
    cursor: pointer;
    transition: all 0.3s ease;
  }

  .deleteButton:hover {
    background-color: #c0392b;
    transform: scale(1.05);
  }

  /* Tabla con bordes elegantes */
  table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;
  }

  table th, table td {
    border: 1px solid #ddd;
    padding: 8px;
    text-align: center;
  }

  table th {
    background-color: #f4f4f4;
    font-weight: bold;
  }
</style>
</head>
<body>
<!-- Contenido principal -->
<div id="tarifaDisplay">Tarifa Actual: RD$ 1000.00</div>
<table id="dataTable">
  <thead>
    <tr>
      <th>Apartamento</th>
      <th>Fecha Check-In</th>
      <th>Fecha Check-Out</th>
      <th>Lote Check-Up</th>
      <th>Consumo</th>
      <th>Número de Medidor</th>
      <th>Costo Total</th>
      <th>Acciones</th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

  <script type="module">
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.3/firebase-app.js";
  import { getFirestore, collection, getDocs, deleteDoc, doc, getDoc } from "https://www.gstatic.com/firebasejs/10.12.3/firebase-firestore.js";

  const firebaseConfig = {
    apiKey: "AIzaSyBQZev4QZdClhi4LzdyPlOyJvkyQWRCiKU",
    authDomain: "energycontador-20e7d.firebaseapp.com",
    projectId: "energycontador-20e7d",
    storageBucket: "energycontador-20e7d.appspot.com",
    messagingSenderId: "216700307706",
    appId: "1:216700307706:web:dedc278ff696be60662143"
  };

  const app = initializeApp(firebaseConfig);
  const db = getFirestore(app);

  let tarifa = 1000;

  // Obtener la tarifa actual desde la colección "tarifacheckin"
  async function fetchTarifa() {
    const docRef = doc(db, "tarifacheckin", "tarifa");
    const docSnap = await getDoc(docRef);
    if (docSnap.exists()) {
      tarifa = docSnap.data().valor;
      document.getElementById('tarifaDisplay').textContent = `Tarifa Actual: RD$ ${tarifa.toFixed(2)}`;
    }
  }

  // Cargar datos de la colección "reservas"
  async function loadData() {
    const querySnapshot = await getDocs(collection(db, "reservas"));
    const tableBody = document.querySelector("#dataTable tbody");
    tableBody.innerHTML = "";

    querySnapshot.forEach((docSnap) => {
      const data = docSnap.data();
      const consumoDiario = data.consumos || 0;

      // Calcular el costo total
      const costoTotal = (consumoDiario * tarifa) / 1000;

      const row = document.createElement("tr");

      row.innerHTML = `
        <td>${data.apartmentName}</td>
        <td>${data.checkInDate || ''}</td>
        <td>${data.checkOutDate || ''}</td>
        <td>${data.loteCheckUp || ''}</td>
        <td>${consumoDiario}</td>
        <td>${data.numeroMedidor || ''}</td>
        <td>RD$ ${costoTotal.toFixed(2)}</td>
        <td><button class="deleteButton" data-id="${docSnap.id}">Eliminar</button></td>
      `;
      tableBody.appendChild(row);
    });

    // Agregar eventos para botones de eliminar
    document.querySelectorAll('.deleteButton').forEach(button => {
      button.addEventListener('click', async (e) => {
        const id = e.target.dataset.id;

        Swal.fire({
          title: '¿Estás seguro?',
          text: "¡Esta acción no se puede deshacer!",
          icon: 'warning',
          showCancelButton: true,
          confirmButtonColor: '#3085d6',
          cancelButtonColor: '#d33',
          confirmButtonText: 'Sí, eliminar',
          cancelButtonText: 'Cancelar'
        }).then(async (result) => {
          if (result.isConfirmed) {
            // Eliminar la reserva de Firebase
            await deleteDoc(doc(db, "reservas", id));
            Swal.fire(
              '¡Eliminado!',
              'La reserva ha sido eliminada correctamente.',
              'success'
            );
            loadData();
          }
        });
      });
    });
  }

  // Ejecutar funciones al cargar la página
  fetchTarifa();
  loadData();
</script>
</body>
</html>
