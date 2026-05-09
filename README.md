# Experential-learning-2
<html>
<html lang="en">
<h1>Angad Bhende</h1>
<h2>USN - CS25068</h2>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>City Central Library</title>

    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">

  <style>
    body {
      background-color: #f4f6f9;
      font-family: Arial, sans-serif;
    }

    .library-container {
      margin-top: 50px;
      background: white;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }

    h1 {
      text-align: center;
      margin-bottom: 25px;
      color: #2c3e50;
      font-weight: bold;
    }

    #searchInput {
      margin-bottom: 20px;
      border-radius: 8px;
      border: 1px solid #ccc;
      padding: 10px;
    }

    table {
      border-radius: 10px;
      overflow: hidden;
    }

    thead {
      background-color: #34495e;
      color: white;
    }

    tbody tr:hover {
      background-color: #f1f1f1;
      transition: 0.3s;
    }

    .available {
      color: green;
      font-weight: bold;
    }

    .unavailable {
      color: red;
      font-weight: bold;
    }
  </style>
</head>

<body>

  <div class="container">
    <div class="library-container">

      <h1>City Central Library</h1>

            <input type="text" id="searchInput" class="form-control" placeholder="Search books by title or author...">

            <table class="table table-bordered table-striped text-center">
        <thead>
          <tr>
            <th>Title</th>
            <th>Author</th>
            <th>ISBN</th>
            <th>Availability</th>
          </tr>
        </thead>

        <tbody id="bookTable">
          <tr>
            <td>The Great Gatsby</td>
            <td>F. Scott Fitzgerald</td>
            <td>9780743273565</td>
            <td class="available">Available</td>
          </tr>

          <tr>
            <td>Harry Potter</td>
            <td>J.K. Rowling</td>
            <td>9780439708180</td>
            <td class="unavailable">Not Available</td>
          </tr>

          <tr>
            <td>To Kill a Mockingbird</td>
            <td>Harper Lee</td>
            <td>9780061120084</td>
            <td class="available">Available</td>
          </tr>

          <tr>
            <td>The Alchemist</td>
            <td>Paulo Coelho</td>
            <td>9780062315007</td>
            <td class="available">Available</td>
          </tr>

          <tr>
            <td>Rich Dad Poor Dad</td>
            <td>Robert Kiyosaki</td>
            <td>9781612680194</td>
            <td class="unavailable">Not Available</td>
          </tr>
        </tbody>
      </table>

    </div>
  </div>

    <script>
    const searchInput = document.getElementById("searchInput");
    const tableRows = document.querySelectorAll("#bookTable tr");

    searchInput.addEventListener("keyup", function () {
      const searchText = searchInput.value.toLowerCase();

      tableRows.forEach(row => {
        const title = row.cells[0].textContent.toLowerCase();
        const author = row.cells[1].textContent.toLowerCase();

        if (title.includes(searchText) || author.includes(searchText)) {
          row.style.display = "";
        } else {
          row.style.display = "none";
        }
      });
    });
  </script>

</body>
</html>
