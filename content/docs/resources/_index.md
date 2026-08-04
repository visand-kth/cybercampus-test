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

## IoT devices

<div id="IoT devices"></div>

## Hacking tools

<div id="Hacking tools"></div>

## Hardware

<div id="Hardware"></div>

## Other

<div id="Other"></div>



<script src="https://cdnjs.cloudflare.com/ajax/libs/sql.js/1.10.3/sql-wasm.js"></script>
<script>

  async function getSection(section) {
    
    const response = await fetch('resources.db');
    const buffer = await response.arrayBuffer();
    const db = new SQL.Database(new Uint8Array(buffer));
    
    const SQL = await initSqlJs({
      locateFile: file => `https://cdnjs.cloudflare.com/ajax/libs/sql.js/1.10.3/${file}`
    });
    const result = db.exec(`SELECT section, name, availability, diva_references FROM resources WHERE section == ${section}`);

    const output = document.getElementById(section);
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

  getSection("IoT devices");
  getSection("Hacking tools");
  getSection("Hardware");
  getSection("Other");
</script>