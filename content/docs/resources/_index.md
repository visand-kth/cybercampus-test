---
title: Resources
description: List of our IoT devices, Hacking tools and other resources along with availability status.
weight: 3
bookFlatSection: true
---

# Resources

If you have a thesis topic and a supervisor, then you can apply for borrowing our devices. 
Find our IoT devices along with hacking tools below.
Select your devices and then fill out the form [here](apply-resource).

## Inventory

<div id="output"></div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/sql.js/1.10.3/sql-wasm.js"></script>
<script>
  async function main() {
    const SQL = await initSqlJs({
      locateFile: file => `https://cdnjs.cloudflare.com/ajax/libs/sql.js/1.10.3/${file}`
    });

    const response = await fetch('resources.db');
    const buffer = await response.arrayBuffer();
    const db = new SQL.Database(new Uint8Array(buffer));

    const result = db.exec('SELECT * FROM resources LIMIT 10');

    const output = document.getElementById('output');
    if (result.length > 0) {
      const { columns, values } = result[0];
      let html = '<table><tr>' + columns.map(c => `<th>${c}</th>`).join('') + '</tr>';
      values.forEach(row => {
        html += '<tr>' + row.map(v => `<td>${v}</td>`).join('') + '</tr>';
      });
      html += '</table>';
      output.innerHTML = html;
    }
  }

  main();
</script>