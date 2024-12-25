# site

<!DOCTYPE html>
<html>
<head>

<h1>Thomasson Family Game Collection</h1>

<script src="https://cdn.jsdelivr.net/npm/xlsx/dist/xlsx.full.min.js"></script>

<! Update the HTML to include a file input
<form id="fileForm">
    <input type="file" id="uploadFile" accept=".xlsx, .xls"><br><br>
    <label for="newName">New Name:</label>
    <input type="text" id="newName"><br><br>
    <button type="button" onclick="modifyExcel()">Modify Excel</button>
</form>
<div id="output"></div>

<! javascript to load and modify the file

<script>
    let workbook;

    document.getElementById('uploadFile').addEventListener('change', function(event) {
        const file = event.target.files[0];
        const reader = new FileReader();

        reader.onload = function(e) {
            const data = new Uint8Array(e.target.result);
            workbook = XLSX.read(data, { type: 'array' });
        };

        reader.readAsArrayBuffer(file);
    });

    function modifyExcel() {
        if (!workbook) {
            alert('Please upload an Excel file first.');
            return;
        }

        // Get the first worksheet
        const sheetName = workbook.SheetNames[0];
        const worksheet = workbook.Sheets[sheetName];

        // Convert worksheet to JSON
        let sheetData = XLSX.utils.sheet_to_json(worksheet);

        // Add new data
        const newName = document.getElementById('newName').value;
        sheetData.push({ Name: newName });

        // Convert back to worksheet and update the workbook
        const updatedWorksheet = XLSX.utils.json_to_sheet(sheetData);
        workbook.Sheets[sheetName] = updatedWorksheet;

        // Generate a new downloadable file
        XLSX.writeFile(workbook, 'updated_data.xlsx');
    }
</script>
