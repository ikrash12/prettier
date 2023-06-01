<!DOCTYPE html>
<html>
<head>
  <title>Keyword Generator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f2f2f2;
    }
    
    h1 {
      color: #333;
      margin-top: 50px;
    }
    
    .container {
      margin-top: 50px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    
    label {
      font-size: 20px;
      margin-bottom: 10px;
    }
    
    input[type="text"] {
      padding: 10px;
      font-size: 16px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    
    button {
      padding: 10px 20px;
      font-size: 16px;
      background-color: #4CAF50;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    
    table {
      margin-top: 20px;
      border-collapse: collapse;
      width: 80%;
    }
    
    th, td {
      padding: 8px;
      text-align: left;
      border-bottom: 1px solid #ddd;
    }
    
    th {
      background-color: #4CAF50;
      color: white;
    }
    
    #keywords {
      margin-top: 20px;
      text-align: left;
    }
  </style>
</head>
<body>
  <h1>Keyword Generator</h1>
  <div class="container">
    <label for="keyword">Enter a keyword:</label>
    <input type="text" id="keyword">
    <button onclick="generateKeywords()">Generate Keywords</button>
    <div id="keywords"></div>
  </div>

  <script>
    function generateKeywords() {
      var keyword = document.getElementById("keyword").value;
      
      // Generate keywords data (dummy data)
      var keywordsData = [
        { keyword: "keyword1", volume: 1000, kd: 30, updated: "2023-05-01" },
        { keyword: "keyword2", volume: 800, kd: 40, updated: "2023-05-02" },
        { keyword: "keyword3", volume: 1200, kd: 25, updated: "2023-05-03" },
        { keyword: "keyword4", volume: 1500, kd: 35, updated: "2023-05-04" },
        { keyword: "keyword5", volume: 900, kd: 20, updated: "2023-05-05" }
      ];
      
      // Display the keywords
      var keywordsElement = document.getElementById("keywords");
      keywordsElement.innerHTML = "";
      
      if (keywordsData.length > 0) {
        var table = document.createElement("table");
        var headerRow = table.insertRow(0);
        
        var keywordHeader = document.createElement("th");
        keywordHeader.textContent = "Keyword";
        headerRow.appendChild(keywordHeader);
        
        var volumeHeader = document.createElement("th");
        volumeHeader.textContent = "Volume";
        headerRow.appendChild(volumeHeader);
        
        var kdHeader = document.createElement("th");
        kdHeader.textContent = "KD";
        headerRow.appendChild(kdHeader);
        
        var updatedHeader = document.createElement("th");
        updatedHeader.textContent = "Updated";
        headerRow.appendChild(updatedHeader);
        
        for (var i = 0; i < keywordsData.length; i++) {
          var keywordData = keywordsData[i];
          var row = table.insertRow(i + 1);
          
          var keywordCell = row.insertCell(0);
          keywordCell.textContent = keywordData.keyword;
          
          var volumeCell = row.insertCell(1);
          volumeCell.textContent = keywordData.volume;
          
          var kdCell = row.insertCell(2);
          kdCell.textContent = keywordData.kd;
          
          var updatedCell = row.insertCell(3);
          updatedCell.textContent = keywordData.updated;
        }
        
        keywordsElement.appendChild(table);
      } else {
        keywordsElement.textContent = "No keywords found.";
      }
    }
  </script>
</body>
</html>
