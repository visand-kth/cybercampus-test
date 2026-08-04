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

  let db;
  
  async function loadDb() {
    const SQL = await initSqlJs({
      locateFile: file => `https://cdnjs.cloudflare.com/ajax/libs/sql.js/1.10.3/${file}`
    });
    const response = await fetch('resources.db');
    const buffer = await response.arrayBuffer();
    db = new SQL.Database(new Uint8Array(buffer));
  }
  
  function getSection(section, columns) {
  
    const stmt = db.prepare(
      `SELECT ${columns} FROM resources WHERE section = ?`
    );
    stmt.bind([section]);
  
    const output = document.getElementById(section);
    let html = '<table><tr>' + columns.map(c => `<th>${(c.charAt(0).toUpperCase() + c.slice(1).).replace('_',' ')}</th>`).join('') + '</tr>';
    let hasRows = false;
  
    while (stmt.step()) {
      hasRows = true;
      const row = stmt.getAsObject();
      html += '<tr>' + columns.map(c => `<td>${row[c]}</td>`).join('') + '</tr>';
    }
    stmt.free();
  
    html += '</table>';
    output.innerHTML = hasRows ? html : '<p>No results found.</p>';
  }
  
  async function main() {
    await loadDb();
    getSection("IoT devices", ["section", "category", "name", "availability", "diva_references"]);
    getSection("Hacking tools", ["section", "category", "name", "quantity", "availability"]);
    getSection("Hardware", ["section", "category", "name", "quantity", "availability"]);
    getSection("Other", ["section", "category", "name", "quantity", "availability"]);
  }
  
  main();

</script>