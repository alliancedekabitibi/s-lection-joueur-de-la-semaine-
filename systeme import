<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Joueurs de la semaine — Dek Hockey</title>
<style>
  * { box-sizing: border-box; }
  body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, sans-serif;
    margin: 0;
    padding: 20px;
    background: #f5f5f4;
    color: #1a1a1a;
    line-height: 1.5;
  }
  .container {
    max-width: 1100px;
    margin: 0 auto;
    background: #ffffff;
    border-radius: 12px;
    padding: 24px;
    box-shadow: 0 1px 3px rgba(0,0,0,0.08);
  }
  h1 { margin: 0 0 4px; font-size: 24px; font-weight: 600; }
  h3 { margin: 0; font-size: 16px; font-weight: 600; }
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 12px;
    margin-bottom: 20px;
    padding-bottom: 16px;
    border-bottom: 1px solid #e7e5e4;
  }
  .status { font-size: 13px; color: #78716c; margin: 0; }
  .week-control { display: flex; gap: 8px; align-items: center; }
  .week-control label { font-size: 13px; color: #78716c; }
  select, input[type="text"], textarea, button {
    font-family: inherit;
    font-size: 14px;
    padding: 8px 12px;
    border: 1px solid #d6d3d1;
    border-radius: 6px;
    background: #fff;
    color: #1a1a1a;
  }
  select:focus, input[type="text"]:focus, textarea:focus {
    outline: none;
    border-color: #2563eb;
    box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
  }
  button {
    cursor: pointer;
    background: #fafaf9;
    transition: all 0.15s;
  }
  button:hover { background: #f5f5f4; border-color: #a8a29e; }
  button.primary {
    background: #2563eb;
    color: #fff;
    border-color: #2563eb;
  }
  button.primary:hover { background: #1d4ed8; border-color: #1d4ed8; }
  button.icon-btn {
    padding: 6px 10px;
    background: transparent;
    border: 1px solid transparent;
    color: #78716c;
  }
  button.icon-btn:hover { color: #dc2626; background: #fef2f2; }
  .tabs {
    display: flex;
    gap: 4px;
    margin-bottom: 20px;
    border-bottom: 1px solid #e7e5e4;
    flex-wrap: wrap;
  }
  .tab-btn {
    border: none;
    border-bottom: 2px solid transparent;
    border-radius: 0;
    padding: 10px 16px;
    background: transparent;
    color: #78716c;
    font-size: 14px;
    cursor: pointer;
    transition: all 0.15s;
  }
  .tab-btn:hover { color: #1a1a1a; background: transparent; }
  .tab-btn.active {
    color: #1a1a1a;
    border-bottom-color: #1a1a1a;
    font-weight: 500;
  }
  .form-row {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 12px;
    margin-bottom: 16px;
  }
  .form-row label {
    font-size: 12px;
    color: #78716c;
    display: block;
    margin-bottom: 4px;
  }
  .form-row select, .form-row input { width: 100%; }
  .two-teams {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 16px;
  }
  @media (max-width: 760px) {
    .two-teams { grid-template-columns: 1fr; }
  }
  .team-box {
    background: #fafaf9;
    border: 1px solid #e7e5e4;
    border-radius: 8px;
    padding: 14px;
  }
  .team-box.team1 { border-left: 4px solid #2563eb; }
  .team-box.team2 { border-left: 4px solid #dc2626; }
  .team-box h4 {
    margin: 0 0 10px;
    font-size: 13px;
    font-weight: 600;
    color: #1a1a1a;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }
  .team-box label {
    font-size: 12px;
    color: #78716c;
    display: block;
    margin-bottom: 4px;
    margin-top: 8px;
  }
  .team-box select { width: 100%; margin-bottom: 8px; }
  .team-box textarea {
    width: 100%;
    min-height: 140px;
    font-family: 'Courier New', monospace;
    font-size: 12px;
    resize: vertical;
  }
  .detect-badge {
    display: inline-block;
    margin-top: 6px;
    padding: 2px 8px;
    background: #dcfce7;
    color: #166534;
    border-radius: 4px;
    font-size: 11px;
  }
  .detect-badge.empty { background: #f5f5f4; color: #78716c; }
  .button-row {
    display: flex;
    gap: 8px;
    margin-top: 12px;
    flex-wrap: wrap;
  }
  .alert {
    padding: 12px 16px;
    border-radius: 8px;
    font-size: 13px;
    margin-top: 14px;
  }
  .alert-success { background: #dcfce7; color: #166534; }
  .alert-danger { background: #fee2e2; color: #991b1b; }
  .stats-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 13px;
    margin-top: 12px;
  }
  .stats-table th, .stats-table td {
    padding: 8px 10px;
    text-align: left;
    border-bottom: 1px solid #e7e5e4;
  }
  .stats-table th {
    font-weight: 500;
    color: #57534e;
    font-size: 12px;
    background: #fafaf9;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }
  .stats-table tr.top1 td { background: #fef3c7; }
  .stats-table tr.top2 td { background: #f5f5f4; }
  .stats-table tr.top3 td { background: #fed7aa; }
  .table-wrap {
    overflow-x: auto;
    margin-top: 12px;
    border: 1px solid #e7e5e4;
    border-radius: 8px;
  }
  .top-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 16px;
  }
  .top-card {
    background: #fff;
    border: 1px solid #e7e5e4;
    border-radius: 12px;
    padding: 16px 20px;
  }
  .card-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 12px;
    flex-wrap: wrap;
    gap: 8px;
  }
  .winner-badge {
    font-size: 12px;
    padding: 4px 12px;
    background: #dbeafe;
    color: #1e40af;
    border-radius: 6px;
    font-weight: 500;
  }
  .medal {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 24px;
    height: 24px;
    border-radius: 50%;
    font-size: 12px;
    font-weight: 600;
    flex-shrink: 0;
  }
  .medal-1 { background: #fde68a; color: #92400e; }
  .medal-2 { background: #e7e5e4; color: #57534e; }
  .medal-3 { background: #fed7aa; color: #9a3412; }
  .pick-row {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 10px;
    border-radius: 8px;
    cursor: pointer;
    margin-bottom: 6px;
    background: #fafaf9;
    transition: background 0.1s;
  }
  .pick-row:hover { background: #f5f5f4; }
  .pick-row.selected { background: #dbeafe; }
  .pick-row .name {
    flex: 1;
    min-width: 0;
    font-size: 14px;
    font-weight: 500;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }
  .pick-row .team {
    font-size: 11px;
    color: #78716c;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }
  .pick-row .stats {
    font-size: 11px;
    color: #78716c;
    text-align: right;
    white-space: nowrap;
  }
  .pick-row .stats strong {
    color: #1a1a1a;
    font-size: 14px;
    display: block;
  }
  .game-card {
    background: #fff;
    border: 1px solid #e7e5e4;
    border-radius: 8px;
    padding: 12px 16px;
    margin-bottom: 8px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;
  }
  .cat-pill {
    display: inline-block;
    padding: 3px 10px;
    border-radius: 6px;
    font-size: 11px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }
  .cat-H2 { background: #dbeafe; color: #1e40af; }
  .cat-H3 { background: #ede9fe; color: #5b21b6; }
  .cat-F2 { background: #fce7f3; color: #9d174d; }
  .cat-F3 { background: #d1fae5; color: #065f46; }
  .empty-state {
    font-size: 14px;
    color: #78716c;
    padding: 32px;
    text-align: center;
    background: #fafaf9;
    border-radius: 8px;
  }
  .history-card {
    background: #fff;
    border: 1px solid #e7e5e4;
    border-radius: 12px;
    padding: 16px 20px;
    margin-bottom: 12px;
  }
  .history-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 10px;
    margin-top: 8px;
  }
  .history-cell {
    padding: 10px 12px;
    background: #fafaf9;
    border-radius: 8px;
  }
  @media (max-width: 600px) {
    body { padding: 10px; }
    .container { padding: 16px; }
    h1 { font-size: 20px; }
  }
</style>
</head>
<body>

<div class="container">
  <div class="header">
    <div>
      <h1>🏒 Joueurs de la semaine</h1>
      <p class="status" id="status-line">Chargement…</p>
    </div>
    <div class="week-control">
      <label>Semaine</label>
      <select id="week-select" style="min-width: 90px;"></select>
      <button id="new-week-btn" title="Nouvelle semaine">+ Nouvelle</button>
    </div>
  </div>

  <div class="tabs">
    <button class="tab-btn active" data-tab="add">➕ Ajouter une partie</button>
    <button class="tab-btn" data-tab="games">📋 Parties</button>
    <button class="tab-btn" data-tab="totals">📊 Totaux</button>
    <button class="tab-btn" data-tab="selection">🏆 Sélections</button>
    <button class="tab-btn" data-tab="history">🕒 Historique</button>
  </div>

  <div id="tab-add" class="tab-content">
    <div class="form-row">
      <div>
        <label>Division</label>
        <select id="g-cat"></select>
      </div>
    </div>

    <div class="two-teams">
      <div class="team-box team1">
        <h4>🔵 Équipe 1</h4>
        <label>Nom de l'équipe</label>
        <select id="team1-select"></select>
        <label>Coller les stats (format SportNinja)</label>
        <textarea id="team1-paste" placeholder="9&#10;Alexis Fournier&#10;1  2  2  4  2  0&#10;..."></textarea>
        <div id="team1-status" class="detect-badge empty">0 joueur</div>
      </div>

      <div class="team-box team2">
        <h4>🔴 Équipe 2</h4>
        <label>Nom de l'équipe</label>
        <select id="team2-select"></select>
        <label>Coller les stats (format SportNinja)</label>
        <textarea id="team2-paste" placeholder="11&#10;Joueur Adverse&#10;1  1  2  3  0  0&#10;..."></textarea>
        <div id="team2-status" class="detect-badge empty">0 joueur</div>
      </div>
    </div>

    <div class="button-row">
      <button id="save-game-btn" class="primary">💾 Enregistrer la partie</button>
      <button id="clear-form-btn">🗑 Vider le formulaire</button>
    </div>
    <div id="save-result"></div>
  </div>

  <div id="tab-games" class="tab-content" style="display:none;">
    <div id="games-list"></div>
  </div>

  <div id="tab-totals" class="tab-content" style="display:none;">
    <div style="display: flex; gap: 12px; align-items: center; flex-wrap: wrap;">
      <label style="font-size: 13px; color: #78716c;">Division</label>
      <select id="t-cat"></select>
      <span style="flex:1;"></span>
      <span id="t-count" style="font-size: 12px; color: #a8a29e;"></span>
    </div>
    <div id="totals-table-wrap"></div>
  </div>

  <div id="tab-selection" class="tab-content" style="display:none;">
    <p style="font-size: 13px; color: #78716c; margin: 0 0 16px;">Top 3 par division selon les totaux de la semaine. Clique sur un joueur pour le couronner.</p>
    <div id="selection-grid" class="top-grid"></div>
  </div>

  <div id="tab-history" class="tab-content" style="display:none;">
    <div id="history-list"></div>
  </div>
</div>

<script>
(function() {
  const DIVISIONS = [
    { code: 'H2', name: 'Thibault Amos', teams: ['Hyundai Amos', 'Bar chez Frid', 'Hamel Arpentage', 'Pikogan Maikan', 'McDo'] },
    { code: 'H3', name: 'McMines', teams: ['Kirk Hockey Club', 'Nortech solutions', 'comz', 'La Brosse', 'Rihnolining', 'Les supers amis', 'Deshaies', 'Roteux', 'Le Moose', 'Flamingos', 'LMS Industrie', 'Black Knights'] },
    { code: 'F2', name: 'St-Hubert', teams: ['Centre Visuel des Eskers', 'Washaw Sibi Falcons', 'Baho Média', 'La Relève', 'Pikogan nighthawks', 'Pikogan Spartans'] },
    { code: 'F3', name: 'McDo Abitibi', teams: ['Hardy Construction', 'Athena', 'Les Starlettes', 'Mes dentistes', "Mass'eau'Cryolipo", 'Thunder', 'Les Crinquées'] },
  ];
  const CATS = DIVISIONS.map(d => d.code);
  const TEAMS_BY_CAT = Object.fromEntries(DIVISIONS.map(d => [d.code, d.teams]));
  const DIV_NAME = Object.fromEntries(DIVISIONS.map(d => [d.code, d.name]));
  const STORAGE_KEY = 'dek-joueurs-semaine-v2';

  let state = { currentWeek: 2, weeks: {} };
  let activeTab = 'add';

  function save() {
    try {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(state));
      updateStatus();
    } catch(e) { document.getElementById('status-line').textContent = 'Erreur de sauvegarde'; }
  }
  function load() {
    try {
      const raw = localStorage.getItem(STORAGE_KEY);
      if (raw) state = JSON.parse(raw);
    } catch(e) {}
    if (!state.weeks[state.currentWeek]) state.weeks[state.currentWeek] = { games: [], selections: {} };
  }
  function getWeek(w) {
    if (!state.weeks[w]) state.weeks[w] = { games: [], selections: {} };
    if (!state.weeks[w].games) state.weeks[w].games = [];
    if (!state.weeks[w].selections) state.weeks[w].selections = {};
    return state.weeks[w];
  }
  function updateStatus() {
    const wd = getWeek(state.currentWeek);
    document.getElementById('status-line').textContent = `Semaine ${state.currentWeek} · ${wd.games.length} partie(s) enregistrée(s)`;
  }
  function uid() { return 'g_' + Date.now() + '_' + Math.random().toString(36).slice(2, 6); }
  function escapeHtml(s) {
    return String(s||'').replace(/[&<>"']/g, c => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'})[c]);
  }
  function playerKey(p) { return (p.name || '').trim().toLowerCase(); }

  function populateCatSelects() {
    const opts = DIVISIONS.map(d => `<option value="${d.code}">${d.code} — ${escapeHtml(d.name)}</option>`).join('');
    ['g-cat', 't-cat'].forEach(id => {
      const el = document.getElementById(id);
      if (el) el.innerHTML = opts;
    });
  }
  function populateTeamSelects() {
    const cat = document.getElementById('g-cat').value;
    const teams = TEAMS_BY_CAT[cat] || [];
    const opts = '<option value="">— Choisir —</option>' + teams.map(t => `<option value="${escapeHtml(t)}">${escapeHtml(t)}</option>`).join('');
    document.getElementById('team1-select').innerHTML = opts;
    document.getElementById('team2-select').innerHTML = opts;
  }

  function parseGame(raw) {
    if (!raw || !raw.trim()) return [];
    const lines = raw.split(/\r?\n/).map(l => l.trim()).filter(Boolean);
    const headerKeys = ['player','team','gp','pts','pim','ppg','goals','assists','#'];
    let start = 0;
    for (let i = 0; i < Math.min(lines.length, 10); i++) {
      const low = lines[i].toLowerCase();
      if (headerKeys.some(k => low === k || low.startsWith(k + ' '))) start = i + 1;
    }
    const useLines = lines.slice(start);
    const tokens = [];
    useLines.forEach(l => {
      const parts = l.split(/[\s\t]+/).filter(Boolean);
      parts.forEach(p => tokens.push({ text: p, isNum: /^-?\d+(\.\d+)?$/.test(p) }));
    });

    const players = [];
    let i = 0;
    while (i < tokens.length) {
      let runStart = -1;
      for (let j = i; j <= tokens.length - 6; j++) {
        let allNum = true;
        for (let k = 0; k < 6; k++) {
          if (!tokens[j+k].isNum) { allNum = false; break; }
        }
        if (allNum) { runStart = j; break; }
      }
      if (runStart === -1) break;
      const preTokens = tokens.slice(i, runStart);
      if (preTokens.length === 0) { i = runStart + 6; continue; }
      let jersey = '';
      let nameTokens = preTokens.slice();
      if (nameTokens.length > 0 && nameTokens[0].isNum) {
        jersey = nameTokens[0].text;
        nameTokens = nameTokens.slice(1);
      }
      nameTokens = nameTokens.filter(t => {
        if (/^#/.test(t.text)) { jersey = t.text.replace(/^#/, ''); return false; }
        return true;
      });
      const name = nameTokens.map(t => t.text).join(' ').trim();
      const [gp, g, a, pts, pim, ppg] = tokens.slice(runStart, runStart + 6).map(t => parseFloat(t.text));
      if (name && name.length > 1) {
        players.push({ jersey, name, gp: gp||0, g: g||0, a: a||0, pts: pts||0, pim: pim||0, ppg: ppg||0 });
      }
      i = runStart + 6;
    }
    return players;
  }

  function updateDetectBadge(num) {
    const textarea = document.getElementById(`team${num}-paste`);
    const badge = document.getElementById(`team${num}-status`);
    const players = parseGame(textarea.value);
    if (players.length === 0) {
      badge.textContent = '0 joueur';
      badge.className = 'detect-badge empty';
    } else {
      badge.textContent = `✓ ${players.length} joueur(s) détecté(s)`;
      badge.className = 'detect-badge';
    }
  }

  function renderGames() {
    const wrap = document.getElementById('games-list');
    const wd = getWeek(state.currentWeek);
    if (wd.games.length === 0) {
      wrap.innerHTML = `<div class="empty-state">Aucune partie enregistrée pour la semaine ${state.currentWeek}.</div>`;
      return;
    }
    let html = '';
    CATS.forEach(cat => {
      const cgames = wd.games.filter(g => g.cat === cat);
      if (cgames.length === 0) return;
      html += `<h3 style="margin: 16px 0 8px; font-size: 14px;"><span class="cat-pill cat-${cat}">${cat}</span> ${escapeHtml(DIV_NAME[cat])} <span style="color:#78716c; font-weight:400; font-size:12px;">— ${cgames.length} partie(s)</span></h3>`;
      cgames.forEach(g => {
        const totalPlayers = (g.team1Players || []).length + (g.team2Players || []).length;
        html += `<div class="game-card"><div style="flex:1; min-width:0;"><div style="font-size:14px; font-weight:500;">${escapeHtml(g.team1)} <span style="color:#78716c; font-weight:400;">vs</span> ${escapeHtml(g.team2)}</div><div style="font-size:11px; color:#a8a29e; margin-top:2px;">${totalPlayers} joueurs au total</div></div><button class="icon-btn" data-del-game="${g.id}" title="Supprimer">🗑</button></div>`;
      });
    });
    wrap.innerHTML = html;
    wrap.querySelectorAll('[data-del-game]').forEach(btn => {
      btn.addEventListener('click', () => {
        if (confirm('Supprimer cette partie?')) {
          wd.games = wd.games.filter(g => g.id !== btn.dataset.delGame);
          save();
          render();
        }
      });
    });
  }

  function aggregateForCat(weekNum, cat) {
    const wd = getWeek(weekNum);
    const cgames = wd.games.filter(g => g.cat === cat);
    const map = {};
    function addPlayers(players, teamName) {
      players.forEach(p => {
        const k = playerKey(p);
        if (!map[k]) map[k] = { key: k, name: p.name, teams: new Set(), jerseys: new Set(), gp:0, g:0, a:0, pts:0, pim:0, ppg:0 };
        if (teamName) map[k].teams.add(teamName);
        if (p.jersey) map[k].jerseys.add(p.jersey);
        map[k].gp += p.gp;
        map[k].g += p.g;
        map[k].a += p.a;
        map[k].pts += p.pts;
        map[k].pim += p.pim;
        map[k].ppg += p.ppg;
      });
    }
    cgames.forEach(game => {
      addPlayers(game.team1Players || [], game.team1);
      addPlayers(game.team2Players || [], game.team2);
    });
    return Object.values(map).map(x => ({
      ...x,
      teams: Array.from(x.teams).join(', '),
      jerseys: Array.from(x.jerseys).join('/')
    })).sort((a,b) => b.pts - a.pts || b.g - a.g || b.a - a.a);
  }

  function renderTotals() {
    const cat = document.getElementById('t-cat').value;
    const wrap = document.getElementById('totals-table-wrap');
    const players = aggregateForCat(state.currentWeek, cat);
    document.getElementById('t-count').textContent = `${players.length} joueurs en ${cat}`;
    if (players.length === 0) {
      wrap.innerHTML = `<div class="empty-state">Aucune partie ${cat} enregistrée cette semaine.</div>`;
      return;
    }
    let html = '<div class="table-wrap"><table class="stats-table"><thead><tr><th>#</th><th>Joueur</th><th>Équipe</th><th style="text-align:right;">PJ</th><th style="text-align:right;">B</th><th style="text-align:right;">A</th><th style="text-align:right;">PTS</th><th style="text-align:right;">PUN</th></tr></thead><tbody>';
    players.forEach((p, idx) => {
      const cls = idx < 3 ? `class="top${idx+1}"` : '';
      html += `<tr ${cls}><td style="color:#78716c;">${idx+1}</td><td>${escapeHtml(p.name)}${p.jerseys ? ` <span style="color:#a8a29e; font-size:11px;">#${escapeHtml(p.jerseys)}</span>` : ''}</td><td style="color:#78716c; font-size:12px;">${escapeHtml(p.teams)}</td><td style="text-align:right;">${p.gp}</td><td style="text-align:right;">${p.g}</td><td style="text-align:right;">${p.a}</td><td style="text-align:right; font-weight:500;">${p.pts}</td><td style="text-align:right;">${p.pim}</td></tr>`;
    });
    html += '</tbody></table></div>';
    wrap.innerHTML = html;
  }

  function renderSelection() {
    const grid = document.getElementById('selection-grid');
    const wd = getWeek(state.currentWeek);
    let html = '';
    CATS.forEach(cat => {
      const players = aggregateForCat(state.currentWeek, cat);
      const top3 = players.slice(0, 3);
      const selKey = wd.selections[cat];
      const selected = selKey ? players.find(p => p.key === selKey) : null;
      html += `<div class="top-card"><div class="card-header"><h3><span class="cat-pill cat-${cat}">${cat}</span> <span style="font-weight:400; font-size:13px; color:#78716c;">${escapeHtml(DIV_NAME[cat])}</span></h3>`;
      if (selected) html += `<span class="winner-badge">🏆 ${escapeHtml(selected.name)}</span>`;
      html += `</div>`;
      if (top3.length === 0) {
        html += `<p style="font-size:13px; color:#78716c; margin:0;">Aucune donnée.</p>`;
      } else {
        top3.forEach((p, i) => {
          const isSel = selKey === p.key;
          html += `<div class="pick-row ${isSel ? 'selected' : ''}" data-cat="${cat}" data-key="${escapeHtml(p.key)}">`;
          html += `<span class="medal medal-${i+1}">${i+1}</span>`;
          html += `<div style="flex:1; min-width:0;"><div class="name">${escapeHtml(p.name)}</div>`;
          if (p.teams) html += `<div class="team">${escapeHtml(p.teams)}</div>`;
          html += `</div><div class="stats">${p.g}B · ${p.a}A<strong>${p.pts} pts</strong></div></div>`;
        });
        if (selected) html += `<button data-clear="${cat}" style="margin-top:10px; font-size:12px; width:100%;">Annuler la sélection</button>`;
      }
      html += `</div>`;
    });
    grid.innerHTML = html;
    grid.querySelectorAll('.pick-row').forEach(el => {
      el.addEventListener('click', () => {
        wd.selections[el.dataset.cat] = el.dataset.key;
        save();
        renderSelection();
      });
    });
    grid.querySelectorAll('[data-clear]').forEach(btn => {
      btn.addEventListener('click', () => {
        delete wd.selections[btn.dataset.clear];
        save();
        renderSelection();
      });
    });
  }

  function renderHistory() {
    const wrap = document.getElementById('history-list');
    const weeks = Object.keys(state.weeks).map(Number).sort((a,b) => b-a);
    let html = '';
    weeks.forEach(w => {
      const wd = state.weeks[w];
      html += `<div class="history-card"><div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:8px;"><strong style="font-size:15px;">Semaine ${w}</strong><span style="font-size:11px; color:#a8a29e;">${(wd.games||[]).length} parties</span></div><div class="history-grid">`;
      CATS.forEach(cat => {
        const key = (wd.selections||{})[cat];
        const players = aggregateForCat(w, cat);
        const p = key ? players.find(x => x.key === key) : null;
        html += `<div class="history-cell"><span class="cat-pill cat-${cat}">${cat}</span>`;
        if (p) {
          html += `<div style="font-size:13px; font-weight:500; margin-top:6px;">${escapeHtml(p.name)}</div><div style="font-size:11px; color:#78716c;">${p.g}B · ${p.a}A · ${p.pts} pts</div>`;
        } else {
          html += `<div style="font-size:13px; color:#a8a29e; margin-top:6px;">—</div>`;
        }
        html += `</div>`;
      });
      html += '</div><div style="margin-top:12px; display:flex; justify-content:flex-end;"><button class="icon-btn" data-del-week="' + w + '">🗑 Supprimer la semaine</button></div></div>';
    });
    wrap.innerHTML = html || '<div class="empty-state">Aucune semaine enregistrée.</div>';
    wrap.querySelectorAll('[data-del-week]').forEach(btn => {
      btn.addEventListener('click', () => {
        const w = btn.dataset.delWeek;
        if (confirm(`Supprimer toute la semaine ${w}?`)) {
          delete state.weeks[w];
          if (parseInt(w) === state.currentWeek) {
            const rem = Object.keys(state.weeks).map(Number).sort((a,b)=>a-b);
            state.currentWeek = rem[0] || 2;
            if (!state.weeks[state.currentWeek]) state.weeks[state.currentWeek] = { games:[], selections:{} };
          }
          save();
          render();
        }
      });
    });
  }

  function renderWeekSelect() {
    const sel = document.getElementById('week-select');
    const weeks = Object.keys(state.weeks).map(Number).sort((a,b) => a-b);
    if (weeks.length === 0) weeks.push(2);
    sel.innerHTML = weeks.map(w => `<option value="${w}" ${w === state.currentWeek ? 'selected' : ''}>S ${w}</option>`).join('');
  }

  function clearForm() {
    document.getElementById('team1-select').value = '';
    document.getElementById('team2-select').value = '';
    document.getElementById('team1-paste').value = '';
    document.getElementById('team2-paste').value = '';
    updateDetectBadge(1);
    updateDetectBadge(2);
  }

  function render() {
    renderWeekSelect();
    updateStatus();
    if (activeTab === 'games') renderGames();
    else if (activeTab === 'totals') renderTotals();
    else if (activeTab === 'selection') renderSelection();
    else if (activeTab === 'history') renderHistory();
  }

  function bind() {
    document.querySelectorAll('.tab-btn').forEach(btn => {
      btn.addEventListener('click', () => {
        document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
        btn.classList.add('active');
        document.querySelectorAll('.tab-content').forEach(c => c.style.display = 'none');
        activeTab = btn.dataset.tab;
        document.getElementById('tab-' + activeTab).style.display = 'block';
        render();
      });
    });

    document.getElementById('week-select').addEventListener('change', (e) => {
      state.currentWeek = parseInt(e.target.value, 10);
      getWeek(state.currentWeek);
      save();
      render();
    });

    document.getElementById('new-week-btn').addEventListener('click', () => {
      const weeks = Object.keys(state.weeks).map(Number);
      const next = weeks.length ? Math.max(...weeks) + 1 : 2;
      state.weeks[next] = { games: [], selections: {} };
      state.currentWeek = next;
      save();
      render();
    });

    document.getElementById('g-cat').addEventListener('change', populateTeamSelects);

    document.getElementById('team1-paste').addEventListener('input', () => updateDetectBadge(1));
    document.getElementById('team2-paste').addEventListener('input', () => updateDetectBadge(2));

    document.getElementById('save-game-btn').addEventListener('click', () => {
      const cat = document.getElementById('g-cat').value;
      const team1 = document.getElementById('team1-select').value;
      const team2 = document.getElementById('team2-select').value;
      const team1Players = parseGame(document.getElementById('team1-paste').value);
      const team2Players = parseGame(document.getElementById('team2-paste').value);
      const resultDiv = document.getElementById('save-result');

      const errors = [];
      if (!team1) errors.push("Choisis l'équipe 1");
      if (!team2) errors.push("Choisis l'équipe 2");
      if (team1 && team2 && team1 === team2) errors.push("Les 2 équipes doivent être différentes");
      if (team1Players.length === 0 && team2Players.length === 0) errors.push("Colle les stats d'au moins une équipe");

      if (errors.length > 0) {
        resultDiv.innerHTML = `<div class="alert alert-danger">⚠ ${errors.join(' · ')}</div>`;
        return;
      }

      const wd = getWeek(state.currentWeek);
      wd.games.push({
        id: uid(),
        cat,
        team1, team2,
        team1Players, team2Players,
        ts: Date.now()
      });
      save();
      const total = team1Players.length + team2Players.length;
      resultDiv.innerHTML = `<div class="alert alert-success">✓ Partie enregistrée : ${escapeHtml(team1)} vs ${escapeHtml(team2)} en ${cat} (${total} joueurs au total). Tu peux en saisir une autre.</div>`;
      clearForm();
      updateStatus();
    });

    document.getElementById('clear-form-btn').addEventListener('click', () => {
      clearForm();
      document.getElementById('save-result').innerHTML = '';
    });

    document.getElementById('t-cat').addEventListener('change', renderTotals);
  }

  load();
  populateCatSelects();
  populateTeamSelects();
  bind();
  render();
})();
</script>

</body>
</html>
