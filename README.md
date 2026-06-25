<!DOCTYPE html>
<html lang="yo">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
<title>ÀTÚPALẸ̀ — Yorùbá Word Formation</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif:ital,wght@0,500;0,600;0,700;1,500&family=Noto+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#f3ead4;--ink:#2a2014;--ink-soft:#5c5341;
  --indigo:#1c2a47;--indigo-soft:#324677;
  --terra:#c1602c;--terra-deep:#a14d22;
  --gold:#c9941a;--gray:#8a8170;
  --green:#2d6a2d;--green-bg:#e8f5e8;
  --red:#8b2020;--red-bg:#fde8e8;
  --card:#fffcf4;--edge:#ddcd9f;
  --shadow:0 3px 14px rgba(28,42,71,0.14);
  --r:14px;
  --fd:'Noto Serif',Georgia,serif;
  --fb:'Noto Sans',-apple-system,sans-serif;
}
*{box-sizing:border-box;margin:0;padding:0;}
body{background:var(--bg);font-family:var(--fb);color:var(--ink);-webkit-font-smoothing:antialiased;}
.app{max-width:520px;margin:0 auto;padding:18px 14px 60px;}

/* HEADER */
.hdr{text-align:center;padding:6px 0 16px;}
.tone-row{font-size:13px;letter-spacing:7px;color:var(--ink-soft);opacity:.5;margin-bottom:4px;}
.tone-row b{color:var(--gold);} .tone-row i{color:var(--indigo);font-style:normal;}
.hdr h1{font-family:var(--fd);font-weight:700;font-style:italic;font-size:34px;color:var(--indigo);}
.hdr p{font-size:12.5px;color:var(--ink-soft);margin-top:4px;}

/* TABS */
.tabs{display:flex;gap:6px;margin:16px 0 14px;border-bottom:1px solid var(--edge);}
.tab{flex:1;background:none;border:none;padding:10px 2px 12px;font-family:var(--fb);font-weight:600;font-size:13px;color:var(--ink-soft);cursor:pointer;position:relative;-webkit-tap-highlight-color:transparent;}
.tab small{display:block;font-weight:400;font-size:10px;opacity:.7;margin-top:1px;}
.tab.on{color:var(--indigo);}
.tab.on::after{content:"";position:absolute;left:12%;right:12%;bottom:-1px;height:3px;background:var(--terra);border-radius:3px 3px 0 0;}
.panel{display:none;animation:fadeIn .2s ease;}
.panel.on{display:block;}
@keyframes fadeIn{from{opacity:0;transform:translateY(4px);}to{opacity:1;transform:none;}}

/* CARDS */
.card{background:var(--card);border:1px solid var(--edge);border-radius:var(--r);box-shadow:var(--shadow);}

/* === SYLLABLES === */
.flash{padding:34px 20px 26px;text-align:center;cursor:pointer;min-height:190px;
  display:flex;flex-direction:column;align-items:center;justify-content:center;user-select:none;position:relative;}
.tone-chip{position:absolute;top:14px;left:50%;transform:translateX(-50%);
  font-size:11px;font-weight:700;letter-spacing:1px;padding:3px 10px;border-radius:20px;display:flex;align-items:center;gap:5px;}
.flash-word{font-family:var(--fd);font-weight:700;font-size:52px;color:var(--indigo);margin:8px 0 14px;}
.flash-meaning{font-size:17px;color:var(--terra-deep);font-weight:600;max-width:320px;line-height:1.4;min-height:24px;}
.flash-meaning.hide{visibility:hidden;}
.flash-hint{font-size:11.5px;color:var(--gray);margin-top:16px;}
.stats{text-align:center;font-size:12.5px;color:var(--ink-soft);margin-top:12px;}
.stats b{color:var(--terra-deep);}

/* === PREFIXES === */
.pf-sec{margin-bottom:20px;}
.pf-sec-title{font-family:var(--fd);font-weight:600;font-size:15px;color:var(--indigo);margin-bottom:4px;}
.pf-sec-note{font-size:12px;color:var(--ink-soft);line-height:1.5;margin-bottom:8px;}
.pfc{border:1px solid var(--edge);border-radius:12px;margin-bottom:7px;background:var(--card);box-shadow:var(--shadow);overflow:hidden;}
.pfc-head{display:flex;align-items:center;gap:12px;padding:12px 14px;cursor:pointer;}
.pfc-sym{font-family:var(--fd);font-weight:700;font-size:18px;color:var(--terra-deep);min-width:62px;}
.pfc-label{font-size:12.5px;color:var(--ink);flex:1;line-height:1.35;}
.pfc-caret{color:var(--gray);font-size:11px;transition:transform .2s;flex-shrink:0;}
.pfc.open .pfc-caret{transform:rotate(90deg);}
.pfc-body{display:none;padding:0 14px 12px;}
.pfc.open .pfc-body{display:block;}
.pfc-row{display:flex;justify-content:space-between;font-size:12.5px;padding:5px 0;border-top:1px dashed var(--edge);color:var(--ink-soft);}
.pfc-row:first-child{border-top:none;}
.pfc-row-word{font-family:var(--fd);font-weight:600;color:var(--indigo);}

/* === WORD LAB === */
.lab-intro{font-size:12.5px;color:var(--ink-soft);line-height:1.5;margin-bottom:12px;}
.input-row{display:flex;gap:8px;margin-bottom:14px;}
.txt{flex:1;padding:11px 13px;border:1.5px solid var(--edge);border-radius:10px;
  font-size:16px;font-family:var(--fd);color:var(--indigo);background:var(--card);}
.txt:focus{outline:none;border-color:var(--terra);}
.btn{background:var(--indigo);color:#fdf6e3;border:none;padding:0 18px;border-radius:10px;
  font-weight:600;font-size:13.5px;cursor:pointer;font-family:var(--fb);}
.btn:active{opacity:.85;}
.btn.ghost{background:transparent;color:var(--terra-deep);border:1.5px solid var(--terra);}
.btn.sm{padding:8px 13px;font-size:12px;}
.btn.gold{background:var(--gold);color:#fff;}
.btn:disabled{opacity:.4;cursor:default;}

.bk-card{background:var(--card);border:1px solid var(--edge);border-radius:var(--r);box-shadow:var(--shadow);padding:16px;margin-bottom:14px;}
.bk-word{font-family:var(--fd);font-weight:700;font-size:26px;color:var(--indigo);margin-bottom:10px;}
.mrow{display:flex;align-items:flex-start;gap:10px;padding:7px 0;border-top:1px dashed var(--edge);}
.mrow:first-child{border-top:none;}
.mtag{min-width:50px;font-size:10px;font-weight:700;letter-spacing:.5px;padding:3px 7px;border-radius:20px;text-align:center;flex-shrink:0;margin-top:1px;}
.mtext{font-family:var(--fd);font-weight:700;font-size:17px;color:var(--indigo);min-width:54px;}
.mmean{font-size:13.5px;color:var(--ink-soft);line-height:1.4;flex:1;}
.mmean.unk{color:var(--gray);font-style:italic;}

.ai-section{margin-top:14px;padding-top:12px;border-top:2px dashed var(--edge);}
.ai-label{font-size:11px;font-weight:700;color:var(--terra-deep);letter-spacing:.4px;text-transform:uppercase;margin-bottom:4px;display:flex;align-items:center;gap:6px;}
.ai-badge{background:var(--gold);color:#fff;font-size:9px;padding:2px 6px;border-radius:10px;font-weight:700;letter-spacing:.5px;}
.ai-text{font-size:14px;color:var(--ink);line-height:1.5;padding:9px 11px;background:#fffef9;border:1.5px solid var(--edge);border-radius:8px;min-height:38px;}
.ai-text.loading{color:var(--gray);font-style:italic;}

.field-wrap{margin-top:10px;}
.field-label{font-size:11px;font-weight:700;color:var(--terra-deep);letter-spacing:.4px;text-transform:uppercase;margin-bottom:4px;}
.field-ta{width:100%;padding:9px 11px;border:1.5px solid var(--edge);border-radius:8px;
  font-size:14px;font-family:var(--fb);color:var(--ink);background:#fffef9;resize:vertical;min-height:40px;}
.field-ta:focus{outline:none;border-color:var(--terra);}

.lab-actions{display:flex;gap:8px;margin-top:14px;flex-wrap:wrap;}
.save-status{font-size:11.5px;margin-top:6px;line-height:1.4;min-height:14px;}

/* FINAL WORD RESULT */
.result-banner{margin-top:14px;padding:12px 14px;border-radius:10px;background:linear-gradient(135deg,#1c2a47,#324677);color:#fdf6e3;}
.result-banner .rb-label{font-size:10px;font-weight:700;letter-spacing:1px;text-transform:uppercase;opacity:.7;margin-bottom:4px;}
.result-banner .rb-formula{font-size:12px;opacity:.8;font-family:var(--fd);margin-bottom:6px;}
.result-banner .rb-word{font-family:var(--fd);font-size:28px;font-weight:700;font-style:italic;}
.result-banner .rb-literal{font-size:13px;opacity:.85;margin-top:3px;}

/* SAVED */
.saved-title{font-family:var(--fd);font-weight:600;font-size:15px;color:var(--indigo);margin:20px 0 8px;}
.s-item{background:var(--card);border:1px solid var(--edge);border-radius:10px;padding:11px 13px;
  display:flex;align-items:center;gap:10px;margin-bottom:7px;cursor:pointer;box-shadow:var(--shadow);}
.s-item-main{flex:1;min-width:0;}
.s-item-word{font-family:var(--fd);font-weight:700;color:var(--indigo);font-size:15px;}
.s-item-sub{font-size:12px;color:var(--ink-soft);white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
.s-del{background:none;border:none;color:var(--gray);font-size:16px;cursor:pointer;padding:4px 6px;flex-shrink:0;}
.empty{font-size:12.5px;color:var(--gray);font-style:italic;text-align:center;padding:10px 0;}

/* === PUZZLE === */
.puzzle-hdr{display:flex;justify-content:space-between;align-items:center;margin-bottom:14px;}
.puzzle-hdr h2{font-family:var(--fd);font-weight:700;font-size:18px;color:var(--indigo);}
.level-badge{background:var(--gold);color:#fff;font-size:11px;font-weight:700;padding:4px 10px;border-radius:20px;}
.score-bar{display:flex;gap:8px;align-items:center;margin-bottom:14px;font-size:12.5px;color:var(--ink-soft);}
.score-pips{display:flex;gap:4px;}
.pip{width:12px;height:12px;border-radius:50%;background:var(--edge);}
.pip.done{background:var(--green);}
.puz-word-box{text-align:center;padding:20px;background:var(--card);border:2px solid var(--indigo);border-radius:var(--r);margin-bottom:16px;box-shadow:var(--shadow);}
.puz-word{font-family:var(--fd);font-weight:700;font-size:44px;color:var(--indigo);}
.puz-word-hint{font-size:12px;color:var(--gray);margin-top:6px;}
.puz-question{font-size:14px;color:var(--ink);margin-bottom:10px;font-weight:600;}
.puz-drop-row{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:14px;min-height:46px;padding:8px;border:2px dashed var(--edge);border-radius:10px;align-items:center;}
.puz-drop-row.accept{border-color:var(--terra);background:#fdf3ee;}
.puz-tile{background:var(--indigo);color:#fdf6e3;border:none;padding:9px 14px;border-radius:8px;
  font-family:var(--fd);font-weight:700;font-size:16px;cursor:pointer;transition:transform .1s;user-select:none;}
.puz-tile:active{transform:scale(.95);}
.puz-tile.placed{background:var(--terra);}
.puz-tile.correct{background:var(--green);}
.puz-tile.wrong{background:var(--red);}
.tiles-pool{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:16px;}
.puz-feedback{text-align:center;padding:12px;border-radius:10px;font-size:14px;font-weight:600;margin-bottom:12px;display:none;}
.puz-feedback.show{display:block;}
.puz-feedback.ok{background:var(--green-bg);color:var(--green);}
.puz-feedback.err{background:var(--red-bg);color:var(--red);}
.puz-actions{display:flex;gap:8px;justify-content:center;}

/* EMBED SECTION */
.embed-sec{margin-top:24px;padding-top:16px;border-top:2px solid var(--edge);}
.embed-title{font-family:var(--fd);font-weight:700;font-size:16px;color:var(--indigo);margin-bottom:6px;}
.embed-note{font-size:12.5px;color:var(--ink-soft);line-height:1.5;margin-bottom:12px;}
.embed-plan{display:flex;gap:10px;margin-bottom:12px;flex-wrap:wrap;}
.eplan-card{flex:1;min-width:140px;background:var(--card);border:1px solid var(--edge);border-radius:10px;padding:12px;box-shadow:var(--shadow);}
.eplan-card h4{font-size:13px;font-weight:700;color:var(--indigo);margin-bottom:4px;}
.eplan-card p{font-size:11.5px;color:var(--ink-soft);line-height:1.4;}
.eplan-card .price{font-size:16px;font-weight:700;color:var(--gold);margin-top:6px;}
.code-block{background:#1c2a47;color:#fdf6e3;border-radius:10px;padding:14px;font-size:11.5px;font-family:monospace;white-space:pre-wrap;word-break:break-all;position:relative;margin-bottom:10px;}
.copy-btn{position:absolute;top:8px;right:8px;background:var(--terra);color:#fff;border:none;padding:4px 10px;border-radius:6px;font-size:11px;cursor:pointer;font-family:var(--fb);}
.copy-btn:active{opacity:.8;}

/* === LANGUAGE TAB === */
.lang-sec{margin-bottom:6px;}
.lang-acc{background:var(--card);border:1px solid var(--edge);border-radius:12px;overflow:hidden;box-shadow:var(--shadow);margin-bottom:8px;}
.lang-acc-head{display:flex;align-items:center;gap:12px;padding:13px 15px;cursor:pointer;-webkit-tap-highlight-color:transparent;}
.lang-acc-icon{font-size:22px;flex-shrink:0;}
.lang-acc-titles{flex:1;}
.lang-acc-title{font-family:var(--fd);font-weight:700;font-size:15px;color:var(--indigo);}
.lang-acc-sub{font-size:11px;color:var(--gray);margin-top:1px;}
.lang-acc-caret{color:var(--gray);font-size:11px;transition:transform .2s;flex-shrink:0;}
.lang-acc.open .lang-acc-caret{transform:rotate(90deg);}
.lang-acc-body{display:none;padding:0 15px 15px;}
.lang-acc.open .lang-acc-body{display:block;}

/* alphabet grid */
.alpha-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:6px;margin-bottom:10px;}
.alpha-cell{background:var(--bg);border:1px solid var(--edge);border-radius:8px;padding:8px 4px;text-align:center;cursor:pointer;transition:background .15s;}
.alpha-cell:active{background:var(--edge);}
.alpha-cell .ac-letter{font-family:var(--fd);font-weight:700;font-size:20px;color:var(--indigo);}
.alpha-cell .ac-name{font-size:9px;color:var(--gray);margin-top:2px;}
.alpha-cell .ac-sound{font-size:9px;color:var(--terra-deep);font-style:italic;}
.alpha-detail{background:var(--indigo);color:#fdf6e3;border-radius:10px;padding:12px 14px;margin-top:8px;display:none;}
.alpha-detail.show{display:block;}
.alpha-detail .ad-letter{font-family:var(--fd);font-size:36px;font-weight:700;}
.alpha-detail .ad-name{font-size:13px;opacity:.8;margin-top:2px;}
.alpha-detail .ad-sound{font-size:12px;color:var(--gold);margin-top:4px;}
.alpha-detail .ad-example{font-size:12px;opacity:.75;margin-top:4px;font-style:italic;}

/* consonant rows */
.con-table{width:100%;border-collapse:collapse;font-size:13px;}
.con-table th{font-size:10px;font-weight:700;color:var(--gray);text-transform:uppercase;letter-spacing:.4px;padding:5px 6px;border-bottom:1px solid var(--edge);text-align:left;}
.con-table td{padding:7px 6px;border-bottom:1px dashed var(--edge);color:var(--ink-soft);line-height:1.35;}
.con-table td:first-child{font-family:var(--fd);font-weight:700;font-size:17px;color:var(--indigo);}
.con-table tr:last-child td{border-bottom:none;}
.con-special{background:#f0ebd8;border-radius:4px;}

/* tone display */
.tone-demo-row{display:flex;gap:8px;margin-bottom:12px;}
.tone-card{flex:1;border-radius:10px;padding:12px 8px;text-align:center;}
.tone-card .tc-mark{font-size:22px;font-weight:700;font-family:var(--fd);}
.tone-card .tc-name{font-size:11px;font-weight:700;letter-spacing:.5px;margin-top:4px;text-transform:uppercase;}
.tone-card .tc-desc{font-size:11px;margin-top:4px;line-height:1.3;opacity:.85;}
.tone-card .tc-ex{font-size:13px;font-family:var(--fd);font-weight:600;margin-top:6px;}
.tone-pair-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-top:10px;}
.tone-pair{background:var(--bg);border:1px solid var(--edge);border-radius:8px;padding:9px 10px;}
.tone-pair .tp-words{font-family:var(--fd);font-weight:700;font-size:15px;color:var(--indigo);}
.tone-pair .tp-means{font-size:11.5px;color:var(--ink-soft);margin-top:3px;line-height:1.3;}

/* vowels */
.vowel-row{display:flex;gap:6px;margin-bottom:10px;flex-wrap:wrap;}
.vowel-chip{background:var(--bg);border:1.5px solid var(--edge);border-radius:8px;padding:6px 10px;text-align:center;min-width:52px;}
.vowel-chip .vc-v{font-family:var(--fd);font-weight:700;font-size:20px;color:var(--indigo);}
.vowel-chip .vc-s{font-size:10px;color:var(--terra-deep);margin-top:1px;}
.vowel-section-label{font-size:11px;font-weight:700;color:var(--gray);letter-spacing:.5px;text-transform:uppercase;margin:10px 0 6px;}
.harmony-box{background:linear-gradient(135deg,#1c2a47,#324677);color:#fdf6e3;border-radius:10px;padding:12px 14px;margin-top:10px;}
.harmony-box h4{font-size:13px;font-weight:700;margin-bottom:6px;color:var(--gold);}
.harmony-box p{font-size:12px;line-height:1.5;opacity:.88;}
.harmony-box .hb-pair{display:flex;gap:8px;margin-top:8px;flex-wrap:wrap;}
.harmony-box .hb-item{background:rgba(255,255,255,.1);border-radius:6px;padding:5px 9px;font-size:12px;font-family:var(--fd);}

/* numbers */
.num-intro{font-size:12.5px;color:var(--ink-soft);line-height:1.6;margin-bottom:10px;}
.num-row{display:flex;align-items:center;gap:10px;padding:8px 0;border-top:1px dashed var(--edge);}
.num-row:first-child{border-top:none;}
.num-digit{font-family:var(--fd);font-weight:700;font-size:22px;color:var(--indigo);min-width:36px;}
.num-word{font-family:var(--fd);font-weight:600;font-size:15px;color:var(--terra-deep);min-width:90px;}
.num-note{font-size:12px;color:var(--ink-soft);flex:1;line-height:1.35;}
.num-system-box{background:var(--bg);border:1px solid var(--edge);border-radius:10px;padding:12px;margin-top:12px;}
.num-system-box h4{font-size:13px;font-weight:700;color:var(--indigo);margin-bottom:8px;}

/* SOURCE CODE VIEW */
.src-intro{font-size:12.5px;color:var(--ink-soft);margin-bottom:12px;line-height:1.5;}
.src-block{background:#1c2a47;color:#a8d0a8;border-radius:10px;padding:14px;font-size:11px;font-family:monospace;max-height:320px;overflow-y:auto;white-space:pre-wrap;word-break:break-all;position:relative;margin-bottom:10px;}
.src-block .kw{color:#f0c674;} .src-block .str{color:#b5d5f5;} .src-block .cm{color:#7a9a7a;}
</style>
<!-- Pi Network SDK -->
<script src="https://sdk.minepi.com/pi-sdk.js"></script>
</head>
<body>
<div class="app">

<header class="hdr">
  <div class="tone-row"><b>▲</b> – <i>▼</i></div>
  <h1>ÀTÚPALẸ̀</h1>
  <p>Yorùbá syllables · prefixes · word formation</p>
</header>

<div id="pi-bar" style="display:none;background:linear-gradient(135deg,#6b3fa0,#1c2a47);color:#fdf6e3;border-radius:10px;padding:10px 14px;margin-bottom:14px;font-size:13px;display:flex;align-items:center;gap:10px;">
  <span style="font-size:18px;">π</span>
  <div style="flex:1;">
    <div id="pi-username" style="font-weight:700;font-size:14px;">Connecting to Pi...</div>
    <div id="pi-status" style="font-size:11px;opacity:.8;margin-top:1px;">Loading Pi Network</div>
  </div>
  <button id="pi-pay-puzzle" class="btn sm" style="background:var(--gold);color:#fff;display:none;padding:7px 12px;font-size:12px;">
    Play Puzzle (1π)
  </button>
</div>

<nav class="tabs">
  <button class="tab on" data-tab="syl">Syllables<small>Ôrò ipilẹ̀</small></button>
  <button class="tab" data-tab="pre">Prefixes<small>Àfikún</small></button>
  <button class="tab" data-tab="lab">Word Lab<small>Àtúpalẹ̀</small></button>
  <button class="tab" data-tab="puz">Puzzle<small>Eré ìdánwò</small></button>
  <button class="tab" data-tab="src">Code<small>Ìtẹjáde</small></button>
  <button class="tab" data-tab="lang">Language<small>Èdè Yorùbá</small></button>
</nav>

<!-- SYLLABLES -->
<section class="panel on" id="p-syl">
  <div class="flash card" id="flashcard">
    <div class="tone-chip" id="tc"></div>
    <div class="flash-word" id="fw">—</div>
    <div class="flash-meaning hide" id="fm"></div>
    <div class="flash-hint" id="fh">Tap to reveal meaning</div>
  </div>
  <div class="stats">Explored: <b id="exp">0</b> syllables</div>
</section>

<!-- PREFIXES -->
<section class="panel" id="p-pre">
  <div id="pref-out"></div>
</section>

<!-- WORD LAB -->
<section class="panel" id="p-lab">
  <div class="lab-intro">Type any Yorùbá compound word — the app will break it into morphemes and use AI to auto-fill its meaning.</div>
  <div class="input-row">
    <input type="text" id="ci" class="txt" placeholder="e.g. Ilé, Àpajẹ, Iwájú">
    <button class="btn" id="db">Break down</button>
  </div>
  <div id="lab-out"></div>
  <div class="saved-title">My Compound Words</div>
  <div id="saved-list"></div>
</section>

<!-- PUZZLE -->
<section class="panel" id="p-puz">
  <div class="puzzle-hdr">
    <h2>Word Decoder</h2>
    <div class="level-badge" id="lv-badge">Level 1</div>
  </div>
  <div class="score-bar">
    <span>Progress:</span>
    <div class="score-pips" id="pips"></div>
    <span id="score-txt">0 / 3 correct</span>
  </div>
  <div class="puz-word-box">
    <div class="puz-word" id="puz-word">—</div>
    <div class="puz-word-hint" id="puz-hint">Arrange the syllable tiles below in the correct order</div>
  </div>
  <div class="puz-question" id="puz-q">Tap tiles in order: PREFIX → ROOT → SUFFIX</div>
  <div style="font-size:12px;color:var(--gray);margin-bottom:8px;">Your answer:</div>
  <div class="puz-drop-row" id="puz-answer"></div>
  <div style="font-size:12px;color:var(--gray);margin-bottom:8px;">Available tiles:</div>
  <div class="tiles-pool" id="puz-pool"></div>
  <div class="puz-feedback" id="puz-fb"></div>
  <div class="puz-actions">
    <button class="btn ghost sm" id="puz-clear">Clear</button>
    <button class="btn sm" id="puz-check">Check Answer</button>
    <button class="btn ghost sm" id="puz-skip">Skip</button>
  </div>

  <div class="embed-sec">
    <div class="embed-title">🔗 Embed This Puzzle</div>
    <div class="embed-note">Any website or Pi app can embed the Yorùbá Word Puzzle. Embed requests require a Pi payment that goes directly to you (the app owner). Choose your plan:</div>
    <div class="embed-plan">
      <div class="eplan-card">
        <h4>Trial</h4>
        <p>7 days access, up to 100 plays/day</p>
        <div class="price">1 π</div>
      </div>
      <div class="eplan-card">
        <h4>Standard</h4>
        <p>30 days, unlimited plays, leaderboard</p>
        <div class="price">5 π</div>
      </div>
      <div class="eplan-card">
        <h4>Lifetime</h4>
        <p>Permanent embed, custom branding</p>
        <div class="price">20 π</div>
      </div>
    </div>
    <div style="font-size:12px;color:var(--ink-soft);margin-bottom:8px;">Copy this iframe code and paste into any site:</div>
    <div class="code-block" id="embed-code-block">
&lt;iframe
  src="YOUR_HOSTED_URL?embed=1&amp;level=1"
  width="100%"
  height="560"
  style="border:none;border-radius:14px;"
  allow="clipboard-write"
  title="ÀTÚPALẸ̀ Yorùbá Word Puzzle"
&gt;&lt;/iframe&gt;<button class="copy-btn" onclick="copyCode('embed-code-block')">Copy</button></div>
    <div style="font-size:11px;color:var(--gray);line-height:1.5;">To register your site as an authorized embedder and enable Pi payment, contact via the Pi Fireside Forum or Pi Browser app. Unauthorized embeds will show a watermark only.</div>
  </div>
</section>

<!-- SOURCE CODE -->
<section class="panel" id="p-src">
  <div class="src-intro">This is the full source code of the Àtúpalẹ̀ app — built with Claude (AI vibe coding). Copy it to submit to Pi App Studio or share with vibe coder communities as a demonstration.</div>
  <div style="display:flex;gap:8px;margin-bottom:12px;">
    <button class="btn sm" onclick="copyFullSource()">Copy Full Source</button>
    <button class="btn ghost sm" onclick="downloadSource()">Download .html</button>
  </div>
  <div class="src-block" id="src-display">Loading source...</div>
  <div style="font-size:11.5px;color:var(--ink-soft);margin-top:8px;line-height:1.5;">
    <b>For Pi Network raffle (deadline June 28, 2026):</b><br>
    Share this app in vibe coder communities (Reddit, X, Facebook dev groups) as an example of an AI-built app ready for Pi App Studio. Then submit your post link via the <b>"Vibe Coder" button</b> in your Pi mining app.
  </div>
</section>
<!-- LANGUAGE -->
<section class="panel" id="p-lang">
  <div id="lang-out"></div>
</section>



</div>

<script>
const MONO = [{"word":"Bá","register":"Upper","meaning":"Meet / Hit"},{"word":"Ba","register":"Middle","meaning":"Lay / Ambush / Precede / Govern"},{"word":"Bà","register":"Lower","meaning":"Descend / Settle"},{"word":"Bé","register":"Upper","meaning":"Rise"},{"word":"Be","register":"Middle","meaning":"Rose"},{"word":"Bè","register":"Lower","meaning":"Beg / Bow / Send"},{"word":"Bẹ́","register":"Upper","meaning":"Cut / Jump / Divide"},{"word":"Bẹ","register":"Middle","meaning":"Slice"},{"word":"Bí","register":"Upper","meaning":"Born / As"},{"word":"Bi","register":"Middle","meaning":"Ask"},{"word":"Bì","register":"Lower","meaning":"Vomit / Push | Knock over"},{"word":"Bó","register":"Upper","meaning":"Bleach"},{"word":"Bo","register":"Middle","meaning":"Worship"},{"word":"Bọ̀","register":"Lower","meaning":"Perboil / Return"},{"word":"Bọ́","register":"Upper","meaning":"Feed / Escape"},{"word":"Bọ","register":"Lower","meaning":"Covering"},{"word":"Bú","register":"Upper","meaning":"Breaks / Hurt"},{"word":"Bu","register":"Middle","meaning":"Mouldy / Dirty"},{"word":"Bù","register":"Lower","meaning":"Scoop / Remove"},{"word":"Dá","register":"Upper","meaning":"Break / Win / Cause | Perform"},{"word":"Da","register":"Middle","meaning":"Become / Transform"},{"word":"Dà","register":"Lower","meaning":"Pour / Vomit / Betray"},{"word":"Dé","register":"Upper","meaning":"Cover / Put On / Return"},{"word":"De","register":"Middle","meaning":"Hunt / Trap"},{"word":"Dè","register":"Lower","meaning":"Tie | Bind / Note down"},{"word":"Dẹ́","register":"Lower","meaning":"Loose / Soft | soften"},{"word":"Dí","register":"Upper","meaning":"Block / Close / Replace / Fill Up"},{"word":"Di","register":"Middle","meaning":"Lock"},{"word":"Dì","register":"Lower","meaning":"Tuck in / Freeze / Fold / Tie (loads or wounds) / Become"},{"word":"Dọ́","register":"Upper","meaning":"Penetrate / Dig / Reside / Firm"},{"word":"Dọ̀","register":"Lower","meaning":"Dip / Downward"},{"word":"Dú","register":"Upper","meaning":"Separate | Differentiate / Slaughter"},{"word":"Du","register":"Middle","meaning":"Pull"},{"word":"Dù","register":"Lower","meaning":"Compete / Contest / Drag"},{"word":"Fá","register":"Upper","meaning":"Scrap"},{"word":"Fa","register":"Middle","meaning":"Smoked / Drew"},{"word":"Fà","register":"Lower","meaning":"Drag / Extend / Draw / Smoke"},{"word":"Fè","register":"Lower","meaning":"Blowing"},{"word":"Fẹ́","register":"Upper","meaning":"Marry / Desire / Blow"},{"word":"Fẹ","register":"Upper","meaning":"Rise"},{"word":"Fẹ","register":"Lower","meaning":"Widening / Expanding"},{"word":"Fí","register":"Middle","meaning":"Use"},{"word":"Fì","register":"Lower","meaning":"Rolling / Staggering"},{"word":"Fó","register":"Upper","meaning":"Flew"},{"word":"Fo","register":"Middle","meaning":"Spoke"},{"word":"Fọ́","register":"Upper","meaning":"Break"},{"word":"Fọ","register":"Middle","meaning":"Washing / Speaking"},{"word":"Fù","register":"Lower","meaning":"Raising"},{"word":"Fú","register":"Upper","meaning":"Raise"},{"word":"Fu","register":"Middle","meaning":"Raising"},{"word":"Gá","register":"Upper","meaning":"Shit"},{"word":"Ga","register":"Middle","meaning":"Tall"},{"word":"Gà","register":"Lower","meaning":"Set | Open / Trick"},{"word":"Gé","register":"Upper","meaning":"Cut"},{"word":"Ge","register":"Middle","meaning":"Cut up"},{"word":"Gè","register":"Lower","meaning":"Cutting"},{"word":"Gẹ́","register":"Upper","meaning":"Shaping / Pampering"},{"word":"Gí","register":"Upper","meaning":"Firm"},{"word":"Gi","register":"Middle","meaning":"Rigid / Firmed"},{"word":"Gì","register":"Lower","meaning":"Firming / Thickening"},{"word":"Gó","register":"Upper","meaning":"High"},{"word":"Go","register":"Middle","meaning":"Long / Continuous"},{"word":"Gò","register":"Lower","meaning":"Hollow / Enclosing"},{"word":"Gọ́","register":"Upper","meaning":"Lift"},{"word":"Gọ","register":"Middle","meaning":"Hide"},{"word":"Gọ̀","register":"Lower","meaning":"Half done / Foolish | Curving"},{"word":"Gú","register":"Upper","meaning":"Roast / Bloat / Raise"},{"word":"Gu","register":"Middle","meaning":"Rush"},{"word":"Gù","register":"Lower","meaning":"Rushing / Raising"},{"word":"Gbá","register":"Upper","meaning":"Hit / Dupe / Play"},{"word":"Gba","register":"Middle","meaning":"Pass through"},{"word":"Gbà","register":"Lower","meaning":"Take / Collect / Seize / Grab"},{"word":"Gbẹ́","register":"Upper","meaning":"Carry / Doom"},{"word":"Gbe","register":"Middle","meaning":"Supported"},{"word":"Gbè","register":"Lower","meaning":"Support"},{"word":"Gbẹ́","register":"Upper","meaning":"Dig / Carve"},{"word":"Gbẹ","register":"Middle","meaning":"Dried"},{"word":"Gbẹ̀","register":"Lower","meaning":"Compressing / Stiring"},{"word":"Gbi","register":"Middle","meaning":"Took"},{"word":"Gbó","register":"Upper","meaning":"Old / Bark"},{"word":"Gbo","register":"Middle","meaning":"Squeeze"},{"word":"Gbò","register":"Lower","meaning":"Missing"},{"word":"Gbọ́","register":"Upper","meaning":"Hear / Encounter"},{"word":"Gbù","register":"Lower","meaning":"Suddenly"},{"word":"Há","register":"Upper","meaning":"Hang / Struggle | Pant"},{"word":"He","register":"Middle","meaning":"Pick"},{"word":"Họ́","register":"Upper","meaning":"Tiny"},{"word":"Hu","register":"Middle","meaning":"Screamed"},{"word":"Já","register":"Upper","meaning":"Cut loose / Escape"},{"word":"Jà","register":"Lower","meaning":"Fight"},{"word":"Jé","register":"Upper","meaning":"Let"},{"word":"Jè","register":"Lower","meaning":"Making"},{"word":"Jẹ́","register":"Upper","meaning":"Allow / Calm"},{"word":"Jẹ","register":"Middle","meaning":"Eat / Become / Impact / Toured"},{"word":"Jẹ̀","register":"Lower","meaning":"Touring"},{"word":"Jí","register":"Upper","meaning":"Wake"},{"word":"Jì","register":"Lower","meaning":"Give / Free"},{"word":"Jó","register":"Upper","meaning":"Burn / Dance"},{"word":"Jo","register":"Middle","meaning":"Resemble / Complete"},{"word":"Jò","register":"Lower","meaning":"Shrink / Reduce"},{"word":"Jọ́","register":"Upper","meaning":"Reduce"},{"word":"Jọ","register":"Lower","meaning":"Sieve / Separate"},{"word":"Ju","register":"Middle","meaning":"Spoil"},{"word":"Jù","register":"Lower","meaning":"Late / Throw"},{"word":"Ká","register":"Upper","meaning":"Pluck"},{"word":"Ka","register":"Middle","meaning":"At"},{"word":"Kà","register":"Lower","meaning":"Count / Confess"},{"word":"Ké","register":"Upper","meaning":"Shout / Cut"},{"word":"Kẹ́","register":"Upper","meaning":"Care | Pamper"},{"word":"Kẹ̀","register":"Lower","meaning":"Widen"},{"word":"Kí","register":"Upper","meaning":"Greet / Reference"},{"word":"Ki","register":"Middle","meaning":"Pasty"},{"word":"Kì","register":"Lower","meaning":"Praise / Compress"},{"word":"Kó","register":"Upper","meaning":"Gather (in units) / Unripe / Celebrate"},{"word":"Ko","register":"Middle","meaning":"Encounter"},{"word":"Kò","register":"Lower","meaning":"Join / Unite / Conclude"},{"word":"Kọ́","register":"Upper","meaning":"Join | Couple"},{"word":"Kọ","register":"Middle","meaning":"Sing / Alert | Call"},{"word":"Kọ̀","register":"Lower","meaning":"Refuse"},{"word":"Kú","register":"Upper","meaning":"Die"},{"word":"Ku","register":"Middle","meaning":"Approach"},{"word":"Kù","register":"Lower","meaning":"Vibrate | Shake / Sieve"},{"word":"Lá","register":"Upper","meaning":"Lick"},{"word":"La","register":"Middle","meaning":"Pass"},{"word":"Là","register":"Lower","meaning":"Clear / Divide"},{"word":"Lé","register":"Upper","meaning":"Add / Plus / Chase"},{"word":"Le","register":"Middle","meaning":"Hard | Thick"},{"word":"Lẹ́","register":"Upper","meaning":"Light"},{"word":"Lẹ","register":"Middle","meaning":"Lazy / Mended / Joined"},{"word":"Lẹ̀","register":"Lower","meaning":"Mend"},{"word":"Lí","register":"Upper","meaning":"Have"},{"word":"Lo","register":"Middle","meaning":"Used"},{"word":"Ló","register":"Upper","meaning":"Twindle"},{"word":"Lọ","register":"Middle","meaning":"Go / Went"},{"word":"Lọ̀","register":"Lower","meaning":"Announce / Report"},{"word":"Lú","register":"Upper","meaning":"Breakthrough"},{"word":"Lù","register":"Lower","meaning":"Beat"},{"word":"Pá","register":"Upper","meaning":"Flattened / Smoothened"},{"word":"Pa","register":"Middle","meaning":"Kill / Make | Create / Win / Switch off"},{"word":"Pẹ́","register":"Upper","meaning":"Complete"},{"word":"Pẹ","register":"Middle","meaning":"Called"},{"word":"Pẹ̀","register":"Lower","meaning":"Call"},{"word":"Pẹ́","register":"Upper","meaning":"Late / Off time / Long"},{"word":"Pẹ","register":"Middle","meaning":"Stance / Create"},{"word":"Pẹ̀","register":"Lower","meaning":"Begging"},{"word":"Pó","register":"Upper","meaning":"Shrink"},{"word":"Po","register":"Middle","meaning":"Shrinker"},{"word":"Pò","register":"Lower","meaning":"Mix / Argue"},{"word":"Pọ́","register":"Upper","meaning":"Manage / Aerate"},{"word":"Pọ̀","register":"Lower","meaning":"Many / Vomit"},{"word":"Pú","register":"Upper","meaning":"Make"},{"word":"Rá","register":"Upper","meaning":"Disappear / Vanish / Evaporate / Absorb / Ascend / Crawl"},{"word":"Ra","register":"Middle","meaning":"Dissolve"},{"word":"Rà","register":"Lower","meaning":"Decay"},{"word":"Ré","register":"Upper","meaning":"Over | Through"},{"word":"Re","register":"Middle","meaning":"Gather / Harvest"},{"word":"Rè","register":"Lower","meaning":"To"},{"word":"Rẹ́","register":"Upper","meaning":"Cut through / Slaughter"},{"word":"Rẹ","register":"Middle","meaning":"Gather / Multiplied"},{"word":"Rẹ̀","register":"Lower","meaning":"Fall"},{"word":"Rí","register":"Upper","meaning":"See"},{"word":"Ri","register":"Middle","meaning":"Vibrate"},{"word":"Rì","register":"Lower","meaning":"Sinking / Reducing"},{"word":"Ró","register":"Upper","meaning":"Fortify / Empower / Support"},{"word":"Ro","register":"Middle","meaning":"Straight"},{"word":"Rò","register":"Lower","meaning":"Stir / Meditate"},{"word":"Rọ́","register":"Upper","meaning":"Strain"},{"word":"Rọ","register":"Middle","meaning":"Tither"},{"word":"Rọ̀","register":"Lower","meaning":"Soft / Implore"},{"word":"Rú","register":"Upper","meaning":"Dirty / Distort / Fuss"},{"word":"Ru","register":"Middle","meaning":"Overflow / Rise"},{"word":"Rù","register":"Lower","meaning":"Carry / Bear"},{"word":"Ṣá","register":"Upper","meaning":"Escape | Flee / Fade"},{"word":"Ṣà","register":"Lower","meaning":"Praise"},{"word":"Ṣé","register":"Upper","meaning":"Blocked / Closed"},{"word":"Ṣè","register":"Lower","meaning":"Offend"},{"word":"Ṣí","register":"Lower","meaning":"Dull"},{"word":"Ṣó","register":"Upper","meaning":"Mess / Unfriendly"},{"word":"Ṣọ","register":"Middle","meaning":"Knot"},{"word":"Ṣò","register":"Lower","meaning":"Loosen"},{"word":"Ṣá","register":"Upper","meaning":"Day"},{"word":"Ṣá","register":"Upper","meaning":"Pick | select (in quantities)"},{"word":"Ṣe","register":"Middle","meaning":"Do | Make"},{"word":"Ṣẹ̀","register":"Lower","meaning":"Cook"},{"word":"Ṣẹ́","register":"Upper","meaning":"Break / Pour"},{"word":"Ṣẹ̀","register":"Lower","meaning":"Drop | Release / Offend"},{"word":"Ṣí","register":"Upper","meaning":"Open"},{"word":"Ṣí","register":"Lower","meaning":"Miss"},{"word":"Ṣó","register":"Upper","meaning":"Fart"},{"word":"Ṣo","register":"Middle","meaning":"Tie"},{"word":"Ṣọ̀","register":"Upper","meaning":"Observe"},{"word":"Ṣú","register":"Upper","meaning":"Form / Tire"},{"word":"Ṣú","register":"Middle","meaning":"Develop"},{"word":"Ṣù","register":"Lower","meaning":"Murmur | Drop"},{"word":"TÁ","register":"Upper","meaning":"Hesitate | Withdraw"},{"word":"Ta","register":"Middle","meaning":"Play / Roast / Pepperish / Bet"},{"word":"Tà","register":"Lower","meaning":"Spread / Wander"},{"word":"TÉ","register":"Upper","meaning":"On top"},{"word":"Te","register":"Middle","meaning":"Ahead"},{"word":"Tè","register":"Lower","meaning":"Forward"},{"word":"TẸ́","register":"Upper","meaning":"Loose respect / Tasteless"},{"word":"Tẹ","register":"Lower","meaning":"Trample / Stay"},{"word":"TÍ","register":"Upper","meaning":"That"},{"word":"Ti","register":"Middle","meaning":"Of / Has"},{"word":"Tì","register":"Lower","meaning":"Close"},{"word":"TÓ","register":"Upper","meaning":"Enough"},{"word":"To","register":"Middle","meaning":"Arranged"},{"word":"Tò","register":"Lower","meaning":"Arranging / Aligning"},{"word":"TỌ́","register":"Upper","meaning":"Straight"},{"word":"Tọ","register":"Middle","meaning":"Pass through"},{"word":"Tọ̀","register":"Lower","meaning":"Follow / Piss"},{"word":"TÚ","register":"Upper","meaning":"Loose / Gush"},{"word":"Tu","register":"Middle","meaning":"Spit"},{"word":"Tù","register":"Lower","meaning":"Appease / Relieve"},{"word":"WÁ","register":"Upper","meaning":"Come"},{"word":"Wa","register":"Middle","meaning":"We"},{"word":"WÀ","register":"Lower","meaning":"Mine"},{"word":"WÉ","register":"Upper","meaning":"Wrap / Compare"},{"word":"WÈ","register":"Lower","meaning":"Moving"},{"word":"WẸ́","register":"Upper","meaning":"Grate / Little"},{"word":"WẸ","register":"Middle","meaning":"Piece"},{"word":"Wí","register":"Upper","meaning":"Say"},{"word":"Wì","register":"Lower","meaning":"Burn"},{"word":"WÓ","register":"Upper","meaning":"Fall"},{"word":"Wo","register":"Middle","meaning":"Keep / Pause"},{"word":"Wò","register":"Lower","meaning":"Speechless / Close / Caring for"},{"word":"WỌ́","register":"Upper","meaning":"Bend"},{"word":"Wọ̀","register":"Lower","meaning":"Wear / Enter"},{"word":"WÚ","register":"Upper","meaning":"Boost"},{"word":"Wù","register":"Lower","meaning":"Desire"},{"word":"YÁ","register":"Upper","meaning":"Borrow"},{"word":"Ya","register":"Middle","meaning":"Tear / Overflow"},{"word":"Yà","register":"Lower","meaning":"Turn / Draw"},{"word":"YÉ","register":"Upper","meaning":"Understand"},{"word":"Ye","register":"Middle","meaning":"Worthy"},{"word":"Yè","register":"Lower","meaning":"Survive"},{"word":"YẸ́","register":"Upper","meaning":"Accord"},{"word":"YẸ","register":"Middle","meaning":"Befit"},{"word":"YẸ̀","register":"Lower","meaning":"Postponed / Dodge"},{"word":"YÍ","register":"Upper","meaning":"Turn"},{"word":"Yi","register":"Middle","meaning":"Strong"},{"word":"YÓ","register":"Upper","meaning":"Satisfied"},{"word":"Yo","register":"Middle","meaning":"Reduce"},{"word":"Yò","register":"Lower","meaning":"Melt"},{"word":"Jú","register":"Upper","meaning":"Ahead"},{"word":"N","register":"Mid","meaning":"Nasal syllable / Belonging to"},{"word":"M","register":"Mid","meaning":"Nasal syllable / To hold / Take"},{"word":"Ni","register":"Mid","meaning":"At / Have / Is"},{"word":"Ní","register":"Upper","meaning":"At / Have / Possess"},{"word":"Ǹ","register":"Lower","meaning":"I (first person, nasal)"},{"word":"Mú","register":"Upper","meaning":"Take / Hold / Carry"},{"word":"Mu","register":"Mid","meaning":"Drink"},{"word":"Mù","register":"Lower","meaning":"Become blunt / Dull"},{"word":"Bùn","register":"Lower","meaning":"Give freely"},{"word":"Fín","register":"Upper","meaning":"Fanned / Blown air / Apply"},{"word":"Fìn","register":"Lower","meaning":"Deep"},{"word":"Fọ́n","register":"Upper","meaning":"Spray"},{"word":"Fọn","register":"Middle","meaning":"Blow (trumpet) / Honk"},{"word":"Fàn","register":"Lower","meaning":"Carry / Light"},{"word":"Fún","register":"Upper","meaning":"Tight / Tiny"},{"word":"Fun","register":"Middle","meaning":"Cleared / Bright / Hollow / Elongated"},{"word":"Gán","register":"Upper","meaning":"Sting / Managed"},{"word":"Gan","register":"Middle","meaning":"Sticked / Electrocuted / Stagnant"},{"word":"Gàn","register":"Lower","meaning":"Mock"},{"word":"Gbin","register":"Middle","meaning":"Moan"},{"word":"Gbìn","register":"Lower","meaning":"Plant / Bury"},{"word":"Gbọ́n","register":"Upper","meaning":"Wise"},{"word":"Gbọ̀n","register":"Lower","meaning":"Vibrate / Shake"},{"word":"Gbún","register":"Upper","meaning":"Hit"},{"word":"Hán","register":"Upper","meaning":"Catch"},{"word":"Han","register":"Middle","meaning":"Scream"},{"word":"Hàn","register":"Lower","meaning":"Visible"},{"word":"Jìn","register":"Lower","meaning":"Steep / Deep"},{"word":"Kán","register":"Upper","meaning":"Break"},{"word":"Kan","register":"Middle","meaning":"Sour"},{"word":"Kàn","register":"Lower","meaning":"Hit / Build"},{"word":"Kín","register":"Upper","meaning":"Support"},{"word":"Kún","register":"Upper","meaning":"Full"},{"word":"Kun","register":"Middle","meaning":"Occupied / Filled"},{"word":"Kùn","register":"Lower","meaning":"Murmur"},{"word":"Mìn","register":"Lower","meaning":"Swallow"},{"word":"Mún","register":"Upper","meaning":"Sharp"},{"word":"Mun","register":"Middle","meaning":"Occupied"},{"word":"Mùn","register":"Lower","meaning":"Occupying"},{"word":"Nun","register":"Middle","meaning":"Fed"},{"word":"Nùn","register":"Lower","meaning":"Feed"},{"word":"Pín","register":"Upper","meaning":"Share"},{"word":"Pin","register":"Middle","meaning":"End"},{"word":"Pọ́n","register":"Upper","meaning":"Reddish / Climb"},{"word":"Pọn","register":"Middle","meaning":"Fetch"},{"word":"Pọ̀n","register":"Lower","meaning":"Backed"},{"word":"Rán","register":"Upper","meaning":"Send / Sew"},{"word":"Ràn","register":"Lower","meaning":"Expand"},{"word":"Rin","register":"Middle","meaning":"Spills"},{"word":"Rìn","register":"Lower","meaning":"Walk"},{"word":"Sán","register":"Upper","meaning":"Crack"},{"word":"San","register":"Middle","meaning":"Paid"},{"word":"Sàn","register":"Lower","meaning":"Watery / Preferable"},{"word":"Sín","register":"Upper","meaning":"Sneeze"},{"word":"Sin","register":"Middle","meaning":"Escort / Accompany"},{"word":"Sìn","register":"Lower","meaning":"Serve"},{"word":"Sún","register":"Upper","meaning":"Progress"},{"word":"Sun","register":"Middle","meaning":"Roast"},{"word":"Sùn","register":"Lower","meaning":"Target / Sleep"},{"word":"Tán","register":"Upper","meaning":"Finish"},{"word":"Tan","register":"Middle","meaning":"Lighted / Received"},{"word":"Tàn","register":"Lower","meaning":"Deceive / Light up / Brighten"},{"word":"Tún","register":"Upper","meaning":"Again"},{"word":"Tun","register":"Middle","meaning":"Fresh / And"},{"word":"Wín","register":"Upper","meaning":"Lend"},{"word":"Wọ́n","register":"Upper","meaning":"Scarce"},{"word":"Wọn","register":"Middle","meaning":"Theirs"},{"word":"Wọ̀n","register":"Lower","meaning":"Measure"},{"word":"Yán","register":"Upper","meaning":"Flip"},{"word":"Yan","register":"Middle","meaning":"Fried"},{"word":"Yàn","register":"Lower","meaning":"Choose"},{"word":"Yín","register":"Upper","meaning":"Screep"},{"word":"Yin","register":"Middle","meaning":"Praised"},{"word":"Yìn","register":"Lower","meaning":"Praise"}];
const PREFIXES = {"base":[{"symbol":"A","label":"General Existential Entity","examples":[{"word":"Apá","translation":"Hand"},{"word":"Adé","translation":"Crown"},{"word":"Ajá","translation":"Dog"},{"word":"Awo","translation":"Initiate/Secrecy"},{"word":"Akọ","translation":"Male"}]},{"symbol":"E","label":"Natural Force Entity","examples":[{"word":"Ewé","translation":"Leaf"},{"word":"Ejò","translation":"Snake"},{"word":"Eji","translation":"Dew"},{"word":"Ebi","translation":"Hunger"},{"word":"Eré","translation":"Play"}]},{"symbol":"Ẹ","label":"Existential Participant / Pronoun","examples":[{"word":"Ẹni","translation":"Person"},{"word":"Ẹyin","translation":"Egg"},{"word":"Ẹmu","translation":"Palm Wine"},{"word":"Ẹlẹ́dẹ̀","translation":"Pig"}]},{"symbol":"I","label":"Structural Entity (natural/artificial creation, objects, parts, shapes)","examples":[{"word":"Ilé","translation":"House"},{"word":"Igi","translation":"Tree"},{"word":"Ipin","translation":""},{"word":"Ike","translation":"Plastic"},{"word":"Iwe","translation":"Gizzard"}]},{"symbol":"O","label":"Functional Entity (animate/inanimate)","examples":[{"word":"Oko","translation":"Farm"},{"word":"Owó","translation":"Money"},{"word":"Omi","translation":"Water"},{"word":"Orí","translation":"Head/Destiny"},{"word":"Oge","translation":"Fashion"}]},{"symbol":"Ọ","label":"Authority / Impact-bearing Entity (animate/inanimate/abstract)","examples":[{"word":"Ọkọ","translation":"Husband"},{"word":"Ọsán","translation":"Bow’s rope"},{"word":"Ọmọ","translation":"Child"},{"word":"Ọrẹ","translation":"Offering"},{"word":"Ọmú","translation":"Breast"},{"word":"Ọpẹ́","translation":"Appreciation"}]},{"symbol":"U","label":"Structural Entity (same as “I”, dialectal difference)","examples":[{"word":"Uṣu","translation":"Yam"},{"word":"Ulé","translation":"House"},{"word":"Ugi","translation":"Tree"},{"word":"Ulẹ̀","translation":"Land/Ground"},{"word":"Umú","translation":"Nose"}]}],"state":[{"symbol":"À","label":"State of existential entity","examples":[{"word":"Àgbẹ̀","translation":"Farmer"}]},{"symbol":"È","label":"State of natural force entity","examples":[{"word":"Èdè","translation":"Language"}]},{"symbol":"Ẹ̀","label":"State of existential participant or pronoun","examples":[{"word":"Ẹ̀dá","translation":"Creature"}]},{"symbol":"Ì","label":"State of structural entity","examples":[{"word":"Ìjà","translation":"Fighting"}]},{"symbol":"Ò","label":"State of functional entity","examples":[{"word":"Òjò","translation":"Rainfall"}]},{"symbol":"Ọ̀","label":"State of authority or impact-bearing entity","examples":[{"word":"Ọ̀bẹ","translation":"Knife"}]},{"symbol":"Ù","label":"State of dialectal structural entity","examples":[{"word":"Ùgbà","translation":"Time/Season"}]}],"stateNote":"A vowel marked with the grave tone indicates the “state of” or “process of” an entity — functioning like an adjective or qualifier built on the base prefix vowels above.","intense":[{"symbol":"Òò / Àà / Èè","label":"Intense Functional Entity (extremity / continuous / grossly / intense)","examples":[{"word":"Òòrùn","translation":"Sun"},{"word":"Ààwẹ̀","translation":"Fasting"},{"word":"Èèdì","translation":"Spell/Enchantment"}]},{"symbol":"Èé / Ẹ̀ẹ́ / Àá","label":"Intense Continuity Entity","examples":[{"word":"Èérí","translation":"Dirt"},{"word":"Èéfín","translation":"Smoke"},{"word":"Èémí","translation":"Breathing"},{"word":"Ẹ̀ẹ́dẹ́","translation":"Minus 100"},{"word":"Àádọ́","translation":"Minus 10"}]}],"negation":[{"symbol":"Àì / Éè","label":"Negation (“Not”) Entity","examples":[{"word":"Àìkú","translation":"Immortality i.e not mortal"},{"word":"Àìmọ́","translation":"Uncleanliness i.e not clean"},{"word":"Éè-kú","translation":"Not dead"},{"word":"Éè-wí","translation":"Not speaking"}]}],"ownership":{"label":"Possessive / Ownership Entity","forms":["Oní","Olí","Oló","Ọlọ́","Ẹlẹ́"],"note":"The prefix changes form through vowel harmony to match the noun root it attaches to.","examples":[{"word":"Onílù","translation":"Drummer","formula":"Oní + ílù"},{"word":"Ọlọ́pàá","translation":"Police","formula":"Oní + ọ̀pá (oní → olí → ọlọ́)"},{"word":"Ẹlẹ́ja","translation":"Fish monger","formula":"Oní + ẹja (oní → ẹlẹ́)"}]}};
const PUZZLES = [{"word":"Ilé","parts":["I","Lé"],"labels":["Structural Entity","Add / Chase"],"contextual":"A structure where people live and multiply","literal":"House","level":1},{"word":"Iwájú","parts":["I","Wá","Jú"],"labels":["Structural Entity","Come","Ahead"],"contextual":"The part of something that faces forward","literal":"Front / Future","level":1},{"word":"Àpajẹ","parts":["À","Pa","Jẹ"],"labels":["State of existential entity","Kill","Eat"],"contextual":"The act of killing to eat","literal":"Bush Meat","level":2},{"word":"Òjò","parts":["Ò","Jò"],"labels":["State of functional entity","Shrink / Reduce"],"contextual":"Water that descends and spreads from the sky","literal":"Rain","level":1},{"word":"Àìkú","parts":["Àì","Kú"],"labels":["Negation (Not) entity","Die"],"contextual":"The state of not dying; immortality","literal":"Immortality","level":2},{"word":"Àgbẹ̀","parts":["À","Gbẹ̀"],"labels":["State of existential entity","Compress / Smoothen (soil)"],"contextual":"One who works and smoothens the earth","literal":"Farmer","level":1},{"word":"Onílù","parts":["Oní","Ì","Lù"],"labels":["Possessive entity","Structural entity","Beat"],"contextual":"The one who possesses and beats a drum","literal":"Drummer","level":2},{"word":"Ẹ̀dá","parts":["Ẹ̀","Dá"],"labels":["State of existential participant","Break / Cause / Perform"],"contextual":"That which was caused to exist; a created being","literal":"Creature","level":2},{"word":"Ìjà","parts":["Ì","Já"],"labels":["State of structural entity","Cut loose / Escape"],"contextual":"A struggle where each tries to break free of the other","literal":"Fight / Conflict","level":1},{"word":"Àìfọkànsìn","parts":["Àì","Fọ","Kàn","Sì","N"],"labels":["Negation","Wash","Touch","And","Mind"],"contextual":"The state of not washing or touching the mind — distrust","literal":"Lack of Trust / Unfaithfulness","level":3},{"word":"Ọlọ́pàá","parts":["Ọlọ́","Pà","Á"],"labels":["Ownership entity","Create / Make","High tone marker"],"contextual":"The authority that maintains order and safety","literal":"Police","level":3},{"word":"Ẹlẹ́ja","parts":["Ẹlẹ́","Ja"],"labels":["Possessive entity","Fight / Struggle (with fish)"],"contextual":"The one who handles and sells fish","literal":"Fish Monger","level":2},{"word":"Àsà","parts":["À","Sà"],"labels":["State of existential entity","Pick / Select"],"contextual":"That which has been selected and established over time","literal":"Culture / Tradition","level":1},{"word":"Ọkàn","parts":["Ọ","Kàn"],"labels":["Functional entity","Touch / Reach"],"contextual":"The inner entity that reaches and responds to all things","literal":"Heart / Mind / Soul","level":2},{"word":"Ìtàfù","parts":["Ì","Tà","Fù"],"labels":["State of structural entity","Spread / Lay flat","Raising"],"contextual":"A raised flat surface used for placing things on","literal":"That which is raised flat to hold things","level":2}];

/* ── UTILS ── */
function toneInfo(r){
  if(r==='Upper') return {tri:'▲',color:'#c9941a',bg:'#f8eccb',label:'HIGH'};
  if(r==='Lower') return {tri:'▼',color:'#1c2a47',bg:'#dde2ee',label:'LOW'};
  return {tri:'–',color:'#8a8170',bg:'#ece7da',label:'MID'};
}
function cap(s){return s?s.charAt(0).toUpperCase()+s.slice(1):s;}
function gr(s){
  s=s.normalize('NFC');
  if(typeof Intl!=='undefined'&&Intl.Segmenter)
    return Array.from(new Intl.Segmenter('en',{granularity:'grapheme'}).segment(s),x=>x.segment);
  return Array.from(s);
}
function stor(op,...a){try{return window.storage[op](...a);}catch(e){return Promise.reject(e);}}

/* ── TABS ── */
let prefDone=false,savedDone=false;
document.querySelectorAll('.tab').forEach(b=>{
  b.addEventListener('click',()=>{
    document.querySelectorAll('.tab').forEach(x=>x.classList.remove('on'));
    document.querySelectorAll('.panel').forEach(x=>x.classList.remove('on'));
    b.classList.add('on');
    document.getElementById('p-'+b.dataset.tab).classList.add('on');
    if(b.dataset.tab==='pre'&&!prefDone) buildPrefixes();
    if(b.dataset.tab==='lab'&&!savedDone) loadSaved();
    if(b.dataset.tab==='puz') initPuzzle();
    if(b.dataset.tab==='src') loadSource();
    if(b.dataset.tab==='lang'&&!langDone) buildLang();
  });
});

/* ══════════ SYLLABLES ══════════ */
let deck=[],deckPos=0,revealed=false,explored=0;
function shuffle(a){let b=a.slice();for(let i=b.length-1;i>0;i--){let j=Math.floor(Math.random()*(i+1));[b[i],b[j]]=[b[j],b[i]];}return b;}
function newDeck(){deck=shuffle(MONO);deckPos=0;}
function showCard(){
  const it=deck[deckPos],t=toneInfo(it.register);
  const tc=document.getElementById('tc');
  tc.innerHTML=t.tri+' '+t.label;tc.style.color=t.color;tc.style.background=t.bg;
  document.getElementById('fw').textContent=cap(it.word);
  const fm=document.getElementById('fm');fm.textContent=it.meaning;fm.classList.add('hide');
  revealed=false;document.getElementById('fh').textContent='Tap to reveal meaning';
}
document.getElementById('flashcard').addEventListener('click',()=>{
  if(!revealed){
    document.getElementById('fm').classList.remove('hide');
    document.getElementById('fh').textContent='Tap for next syllable';
    revealed=true;explored++;
    document.getElementById('exp').textContent=explored;
    stor('set','progress:explored',String(explored),false).catch(()=>{});
  } else {
    deckPos++;if(deckPos>=deck.length)newDeck();
    showCard();
  }
});
stor('get','progress:explored',false).then(r=>{if(r&&r.value){explored=parseInt(r.value)||0;document.getElementById('exp').textContent=explored;}}).catch(()=>{});
newDeck();showCard();

/* ══════════ PREFIXES ══════════ */
function buildPrefixes(){
  prefDone=true;
  function exRows(arr){return arr.map(e=>'<div class="pfc-row"><span class="pfc-row-word">'+e.word+'</span><span>'+(e.translation||'')+'</span></div>').join('');}
  function pfCard(sym,label,body){
    return '<div class="pfc"><div class="pfc-head" onclick="this.parentElement.classList.toggle(\'open\')"><div class="pfc-sym">'+sym+'</div><div class="pfc-label">'+label+'</div><div class="pfc-caret">&#9656;</div></div><div class="pfc-body">'+body+'</div></div>';
  }
  let h='';
  h+='<div class="pf-sec"><div class="pf-sec-title">Base Prefixes</div><div class="pf-sec-note">The seven core entity-vowels every Yorùbá noun root builds from.</div>';
  PREFIXES.base.forEach(p=>h+=pfCard(p.symbol,p.label,exRows(p.examples)));
  h+='</div><div class="pf-sec"><div class="pf-sec-title">State / Process Prefixes</div><div class="pf-sec-note">'+PREFIXES.stateNote+'</div>';
  PREFIXES.state.forEach(p=>h+=pfCard(p.symbol,p.label,exRows(p.examples)));
  h+='</div><div class="pf-sec"><div class="pf-sec-title">Intensity Prefixes</div>';
  PREFIXES.intense.forEach(p=>h+=pfCard(p.symbol,p.label,exRows(p.examples)));
  h+='</div><div class="pf-sec"><div class="pf-sec-title">Negation Prefix</div>';
  PREFIXES.negation.forEach(p=>h+=pfCard(p.symbol,p.label,exRows(p.examples)));
  const own=PREFIXES.ownership;
  h+='</div><div class="pf-sec"><div class="pf-sec-title">Ownership Prefix</div><div class="pf-sec-note">'+own.note+'</div>';
  h+=pfCard(own.forms.join(' / '),own.label,own.examples.map(e=>'<div class="pfc-row"><span><span class="pfc-row-word">'+e.word+'</span><div style="font-size:11px;color:var(--gray)">'+e.formula+'</div></span><span>'+e.translation+'</span></div>').join(''));
  h+='</div>';
  document.getElementById('pref-out').innerHTML=h;
}

/* ══════════ WORD LAB — DECOMPOSER ══════════ */
const OWN=['oní','olí','oló','ọlọ́','ẹlẹ́'];
const NEG=['àì','éè'];
const INT=['òò','àà','èè','èé','ẹ̀ẹ́','àá'];
const STATE={'à':'State of existential entity','è':'State of natural force entity','ẹ̀':'State of existential participant or pronoun','ì':'State of structural entity','ò':'State of functional entity','ọ̀':'State of authority or impact-bearing entity','ù':'State of dialectal structural entity'};
const BASE={'a':'General Existential Entity','e':'Natural Force Entity','ẹ':'Existential Participant / Pronoun','i':'Structural Entity (creation / object / part / shape)','o':'Functional Entity (animate/inanimate)','ọ':'Authority / Impact-bearing Entity','u':'Structural Entity (dialectal variant of I)'};

const DICT={};
MONO.forEach(r=>{
  const k=r.word.normalize('NFC').toLowerCase();
  if(!DICT[k])DICT[k]=[];
  DICT[k].push(r);
});

function decompose(raw){
  let w=raw.trim().normalize('NFC');
  const layers=[];
  for(const p of OWN){if(w.toLowerCase().startsWith(p)){layers.push({kind:'PREFIX',text:w.slice(0,p.length),label:'Possessive / Ownership Entity'});w=w.slice(p.length);break;}}
  let took=false;
  for(const p of NEG){if(w.toLowerCase().startsWith(p)){layers.push({kind:'PREFIX',text:w.slice(0,p.length),label:'Negation ("Not") Entity'});w=w.slice(p.length);took=true;break;}}
  if(!took)for(const p of INT){if(w.toLowerCase().startsWith(p)){layers.push({kind:'PREFIX',text:w.slice(0,p.length),label:['òò','àà','èè'].includes(p)?'Intense Functional Entity':'Intense Continuity Entity'});w=w.slice(p.length);break;}}
  if(w.length>0){const g0=gr(w)[0],k=g0.toLowerCase();if(STATE[k]){layers.push({kind:'PREFIX',text:g0,label:STATE[k]});w=w.slice(g0.length);}else if(BASE[k]){layers.push({kind:'PREFIX',text:g0,label:BASE[k]});w=w.slice(g0.length);}}
  const gs=gr(w);const morphs=[];let idx=0;
  while(idx<gs.length){
    let found=false;
    for(let len=3;len>=1;len--){
      if(idx+len<=gs.length){const chunk=gs.slice(idx,idx+len).join('');const hit=DICT[chunk.toLowerCase()];if(hit){morphs.push({text:chunk,meaning:hit.map(h=>h.meaning).join(' / '),register:hit[0].register});idx+=len;found=true;break;}}
    }
    if(!found){morphs.push({text:gs[idx],meaning:null,register:null});idx++;}
  }
  return {layers,morphs};
}

function morphLabel(l){
  if(l.layers.length===0)return 'ROOT';
  const count=l.layers.length;
  if(count===l.layers.length&&l.morphs.length>0)return 'ROOT';
  return 'SUFFIX';
}

function buildBreakdownHTML(word,bd,saved){
  let h='<div class="bk-card"><div class="bk-word">'+word+'</div>';
  const allParts=[];
  bd.layers.forEach(l=>{
    allParts.push({type:'PREFIX',text:l.text,meaning:l.label});
    h+='<div class="mrow"><div class="mtag" style="color:#a14d22;background:#f3e3d6;">PREFIX</div><div class="mtext">'+cap(l.text)+'</div><div class="mmean">'+l.label+'</div></div>';
  });
  let morphIdx=0;
  bd.morphs.forEach((m,i)=>{
    const isLast=i===bd.morphs.length-1&&bd.morphs.length>1&&bd.layers.length>0;
    const role=isLast?'SUFFIX':'ROOT';
    if(m.meaning){
      const t=toneInfo(m.register);
      allParts.push({type:role,text:m.text,meaning:m.meaning});
      h+='<div class="mrow"><div class="mtag" style="color:'+t.color+';background:'+t.bg+';">'+t.tri+' '+t.label+'</div><div class="mtext">'+cap(m.text)+'</div><div class="mmean">'+m.meaning+'</div></div>';
    }else{
      allParts.push({type:'?',text:m.text,meaning:null});
      h+='<div class="mrow"><div class="mtag" style="color:#8a8170;background:#ece7da;">?</div><div class="mtext">'+cap(m.text)+'</div><div class="mmean unk">Not in dictionary yet</div></div>';
    }
  });

  // Formula for result banner
  const formula=allParts.filter(p=>p.text).map(p=>cap(p.text)).join(' + ');

  // AI section
  const savedCtx=saved?saved.contextual:'';
  const savedLit=saved?saved.literal:'';
  const savedFinal=saved?saved.finalWord:'';

  h+='<div class="ai-section">';
  h+='<div class="ai-label">Contextual Meaning <span class="ai-badge">AI</span></div>';
  h+='<div class="ai-text" id="ai-ctx">'+(savedCtx||'<span class="loading" id="ctx-loading">Generating...</span>')+'</div>';
  h+='<div class="field-wrap"><div class="ai-label">Literal Meaning <span class="ai-badge">AI</span></div>';
  h+='<div class="ai-text" id="ai-lit">'+(savedLit||'<span class="loading" id="lit-loading">Generating...</span>')+'</div>';
  h+='<div class="ai-label" style="margin-top:12px;">Final Word (Literal Translation)</div>';
  h+='<input type="text" id="ai-final" class="txt" style="margin-top:4px;font-family:var(--fd);font-size:15px;" placeholder="e.g. Bush Meat, House, Police..." value="'+(savedFinal||'')+'"></div>';
  h+='</div>';

  h+='<div class="lab-actions"><button class="btn" id="sav-btn">Save to my dictionary</button></div>';
  h+='<div class="save-status" id="sav-st"></div>';

  // Result banner (shown after save or if already saved)
  if(saved&&saved.finalWord){
    h+=buildBanner(formula,word,saved.literal,saved.finalWord);
  } else {
    h+='<div id="result-banner-slot"></div>';
  }

  h+='</div>';
  return {html:h,allParts,formula};
}

function buildBanner(formula,word,literal,finalWord){
  return '<div class="result-banner" id="res-banner"><div class="rb-label">Word Formation Result</div>'
    +'<div class="rb-formula">'+formula+' →</div>'
    +'<div class="rb-word">'+word+'</div>'
    +'<div class="rb-literal">'+(literal||'')+' · '+finalWord+'</div></div>';
}

let curKey=null;
const SEEDS={
  'ilé':{word:'Ilé',contextual:'A structure where people live, grow, and multiply',literal:'An erected dwelling place',finalWord:'House'},
  'iwájú':{word:'Iwájú',contextual:'The part of something that faces forward or is yet to come',literal:'That which we come ahead to',finalWord:'Front / Future'},
  'àpajẹ':{word:'Àpajẹ',contextual:'The act of killing animals to eat',literal:'What we kill to eat',finalWord:'Bush Meat'},
  'ìtàfù':{word:'Ìtàfù',contextual:'A raised structural surface used for placing and working with items',literal:'That which is raised (flat) to place things on',finalWord:'Table'},
};

async function runDecompose(){
  const raw=document.getElementById('ci').value.trim();
  if(!raw)return;
  const bd=decompose(raw);
  const normKey=raw.normalize('NFC').toLowerCase();
  curKey='compound:'+normKey;
  let saved=SEEDS[normKey]||null;
  try{const r=await stor('get',curKey,false);if(r&&r.value)saved=JSON.parse(r.value);}catch(e){}
  const {html,allParts,formula}=buildBreakdownHTML(raw,bd,saved);
  document.getElementById('lab-out').innerHTML=html;
  document.getElementById('sav-btn').addEventListener('click',()=>doSave(raw,formula));

  if(!saved){
    runAI(raw,allParts);
  }
}

async function runAI(word,allParts){
  const morphDesc=allParts.filter(p=>p.meaning).map(p=>p.text+'='+p.meaning).join(', ');
  const prompt=`You are a Yorùbá language expert. Given this Yorùbá word breakdown:\nWord: ${word}\nMorphemes: ${morphDesc}\n\nRespond ONLY with valid JSON, no markdown, no extra text:\n{"contextual":"one sentence describing the natural cultural/usage meaning in Yorùbá","literal":"a short phrase giving the word-for-word morpheme translation","finalWord":"the English translation of this Yorùbá word in 1-4 words"}`;

  const setFields=(ctx,lit,fin)=>{
    const ctxEl=document.getElementById('ai-ctx');
    const litEl=document.getElementById('ai-lit');
    const finEl=document.getElementById('ai-final');
    if(ctxEl)ctxEl.textContent=ctx||'';
    if(litEl)litEl.textContent=lit||'';
    if(finEl&&fin&&!finEl.value)finEl.value=fin;
  };

  try{
    const res=await fetch('https://api.anthropic.com/v1/messages',{
      method:'POST',
      headers:{
        'Content-Type':'application/json',
        'anthropic-dangerous-direct-browser-access':'true'
      },
      body:JSON.stringify({model:'claude-sonnet-4-6',max_tokens:512,messages:[{role:'user',content:prompt}]})
    });
    if(!res.ok){
      const err=await res.text();
      console.error('AI API error',res.status,err);
      throw new Error('API '+res.status);
    }
    const data=await res.json();
    if(data.error){throw new Error(data.error.message||'API error');}
    const txt=data.content.map(c=>c.text||'').join('').replace(/```json[\s\S]*?```|```/g,'').trim();
    let parsed;
    try{parsed=JSON.parse(txt);}
    catch(je){
      // try to extract JSON object from response
      const m=txt.match(/\{[\s\S]*\}/);
      if(m)parsed=JSON.parse(m[0]);
      else throw je;
    }
    setFields(parsed.contextual,parsed.literal,parsed.finalWord);
  }catch(e){
    console.error('runAI failed:',e);
    setFields(
      'Could not auto-generate — enter the contextual meaning above.',
      'Could not auto-generate — enter the literal meaning above.',
      ''
    );
  }
}

async function doSave(word,formula){
  const ctx=document.getElementById('ai-ctx')?.textContent?.trim()||'';
  const lit=document.getElementById('ai-lit')?.textContent?.trim()||'';
  const fin=document.getElementById('ai-final')?.value?.trim()||'';
  const entry={word,contextual:ctx,literal:lit,finalWord:fin,savedAt:Date.now()};
  const st=document.getElementById('sav-st');
  try{
    await stor('set',curKey,JSON.stringify(entry),false);
    if(st){st.textContent='Saved ✓';st.style.color='var(--green)';}
    const slot=document.getElementById('result-banner-slot');
    if(slot)slot.outerHTML=buildBanner(formula,word,lit,fin);
    loadSaved();
  }catch(e){
    SEEDS[word.normalize('NFC').toLowerCase()]=entry;
    if(st){st.textContent='Saved for this session (persistent storage unavailable)';st.style.color='var(--terra)';}
    loadSaved();
  }
}

document.getElementById('db').addEventListener('click',runDecompose);
document.getElementById('ci').addEventListener('keydown',e=>{if(e.key==='Enter')runDecompose();});

/* saved list */
async function loadSaved(){
  savedDone=true;
  const el=document.getElementById('saved-list');
  const byKey={};
  Object.keys(SEEDS).forEach(k=>{byKey[k]=SEEDS[k];});
  try{
    const r=await stor('list','compound:',false);
    const keys=(r&&r.keys)?r.keys:[];
    for(const k of keys){try{const v=await stor('get',k,false);if(v&&v.value)byKey[k.replace('compound:','')]=JSON.parse(v.value);}catch(e){}}
  }catch(e){}
  const entries=Object.values(byKey).sort((a,b)=>(a.word||'').localeCompare(b.word||''));
  if(!entries.length){el.innerHTML='<div class="empty">No saved words yet.</div>';return;}
  el.innerHTML=entries.map(en=>'<div class="s-item" data-w="'+en.word.replace(/"/g,'&quot;')+'"><div class="s-item-main"><div class="s-item-word">'+en.word+'</div><div class="s-item-sub">'+(en.finalWord||en.literal||'')+'</div></div><button class="s-del" data-d="'+en.word.replace(/"/g,'&quot;')+'">✕</button></div>').join('');
  el.querySelectorAll('.s-item').forEach(el2=>{
    el2.addEventListener('click',ev=>{if(ev.target.closest('.s-del'))return;document.getElementById('ci').value=el2.dataset.w;runDecompose();});
  });
  el.querySelectorAll('.s-del').forEach(b=>{
    b.addEventListener('click',async ev=>{ev.stopPropagation();const w=b.dataset.d;delete SEEDS[w.normalize('NFC').toLowerCase()];try{await stor('delete','compound:'+w.normalize('NFC').toLowerCase(),false);}catch(e){}loadSaved();});
  });
}

/* ══════════ PUZZLE ══════════ */
let puzLevel=1,puzScore=0,puzTarget=3,puzCurrent=null,puzAnswer=[],puzPool=[];

function initPuzzle(){
  puzScore=0;puzLevel=1;renderPip();loadPuzzleWord();
}

function renderPip(){
  let h='';for(let i=0;i<puzTarget;i++)h+='<div class="pip'+(i<puzScore?' done':'')+'"></div>';
  document.getElementById('pips').innerHTML=h;
  document.getElementById('score-txt').textContent=puzScore+' / '+puzTarget+' correct';
  document.getElementById('lv-badge').textContent='Level '+puzLevel;
}

function loadPuzzleWord(){
  const levelWords=PUZZLES.filter(p=>p.level===puzLevel);
  if(!levelWords.length){levelWords.push(...PUZZLES);}
  puzCurrent=levelWords[Math.floor(Math.random()*levelWords.length)];
  puzAnswer=[];
  puzPool=[...puzCurrent.parts].sort(()=>Math.random()-.5);
  document.getElementById('puz-word').textContent=puzCurrent.word;
  document.getElementById('puz-hint').textContent='Break it into '+puzCurrent.parts.length+' parts: '+puzCurrent.parts.map((_,i)=>i===0?'PREFIX':i===puzCurrent.parts.length-1&&puzCurrent.parts.length>2?'SUFFIX':'ROOT').join(' + ');
  document.getElementById('puz-q').textContent='Tap tiles in order → Prefix first, then root, then suffix (if any)';
  const fb=document.getElementById('puz-fb');fb.className='puz-feedback';fb.textContent='';
  renderPuzTiles();
}

function renderPuzTiles(){
  const pool=document.getElementById('puz-pool');
  const ans=document.getElementById('puz-answer');
  pool.innerHTML=puzPool.map((t,i)=>'<button class="puz-tile" data-i="'+i+'" onclick="moveTile('+i+')">'+t+'</button>').join('');
  ans.innerHTML=puzAnswer.map((t,i)=>'<button class="puz-tile placed" onclick="returnTile('+i+')">'+t+'</button>').join('');
}

function moveTile(i){
  const t=puzPool.splice(i,1)[0];
  puzAnswer.push(t);
  renderPuzTiles();
}
function returnTile(i){
  const t=puzAnswer.splice(i,1)[0];
  puzPool.push(t);
  renderPuzTiles();
}

document.getElementById('puz-clear').addEventListener('click',()=>{
  puzPool=[...puzCurrent.parts].sort(()=>Math.random()-.5);
  puzAnswer=[];renderPuzTiles();
  const fb=document.getElementById('puz-fb');fb.className='puz-feedback';
});

document.getElementById('puz-check').addEventListener('click',()=>{
  if(puzAnswer.length!==puzCurrent.parts.length){
    const fb=document.getElementById('puz-fb');fb.className='puz-feedback err show';
    fb.textContent='Place all '+puzCurrent.parts.length+' tiles first.';return;
  }
  const correct=puzCurrent.parts.every((p,i)=>p.toLowerCase()===puzAnswer[i].toLowerCase());
  const fb=document.getElementById('puz-fb');fb.className='puz-feedback show '+(correct?'ok':'err');
  if(correct){
    fb.innerHTML='✓ Correct! <b>'+puzCurrent.word+'</b> = '+puzCurrent.parts.map((p,i)=>'<b>'+p+'</b> ('+puzCurrent.labels[i]+')').join(' + ')+'<br><i>'+puzCurrent.contextual+'</i> → <b>'+puzCurrent.literal+'</b>';
    puzScore++;renderPip();
    if(puzScore>=puzTarget){
      setTimeout(()=>{
        puzScore=0;puzLevel=Math.min(puzLevel+1,3);renderPip();
        fb.className='puz-feedback ok show';
        fb.innerHTML='🎉 Level '+(puzLevel-1)+' complete! Moving to Level '+puzLevel+'...';
        setTimeout(loadPuzzleWord,2000);
      },2500);
    }else{setTimeout(loadPuzzleWord,2500);}
  }else{
    fb.innerHTML='✗ Not quite. Try again or skip.<br><span style="font-size:11px;color:var(--gray)">Hint: the correct order is '+puzCurrent.parts.join(' → ')+'</span>';
  }
});

document.getElementById('puz-skip').addEventListener('click',()=>{
  const fb=document.getElementById('puz-fb');
  fb.className='puz-feedback err show';
  fb.innerHTML='Answer: '+puzCurrent.parts.join(' + ')+' = <b>'+puzCurrent.literal+'</b>';
  setTimeout(loadPuzzleWord,2500);
});

/* ══════════ SOURCE CODE VIEW ══════════ */
function loadSource(){
  const src=document.documentElement.outerHTML;
  const el=document.getElementById('src-display');
  el.textContent=src.substring(0,8000)+(src.length>8000?'\n\n... ('+Math.round(src.length/1024)+'KB total — use "Copy Full Source" for complete code)':'');
}

function copyFullSource(){
  const src=document.documentElement.outerHTML;
  navigator.clipboard.writeText(src).then(()=>{
    const btn=event.target;btn.textContent='Copied!';btn.style.background='var(--green)';
    setTimeout(()=>{btn.textContent='Copy Full Source';btn.style.background='';},2000);
  }).catch(()=>{
    const ta=document.createElement('textarea');ta.value=src;document.body.appendChild(ta);ta.select();document.execCommand('copy');document.body.removeChild(ta);
    alert('Source copied to clipboard!');
  });
}

function downloadSource(){
  const src=document.documentElement.outerHTML;
  const a=document.createElement('a');a.href=URL.createObjectURL(new Blob([src],{type:'text/html'}));
  a.download='atupale-yoruba.html';a.click();
}

function copyCode(id){
  const el=document.getElementById(id);
  const txt=el.textContent.replace('Copy','').trim();
  navigator.clipboard.writeText(txt).then(()=>{
    const btn=el.querySelector('.copy-btn');if(btn){btn.textContent='Copied!';setTimeout(()=>btn.textContent='Copy',2000);}
  }).catch(()=>{});
}


/* ══════════ LANGUAGE TAB ══════════ */
let langDone=false;

const ALPHABET=[
  {l:'A',name:'A',sound:'ah (as in "father")',ex:'Apá — Arm',note:'Pure open vowel'},
  {l:'B',name:'Bí',sound:'b',ex:'Bí — To bear/birth',note:'Same as English B'},
  {l:'D',name:'Dí',sound:'d',ex:'Dá — To break',note:'Dental D (tongue on teeth)'},
  {l:'E',name:'E',sound:'ay (as in "say")',ex:'Eré — Play',note:'Closed mid-front vowel'},
  {l:'Ẹ',name:'Ẹ',sound:'eh (as in "bed")',ex:'Ẹni — Person',note:'Open mid-front vowel — unique to Yorùbá'},
  {l:'F',name:'Fí',sound:'f',ex:'Fẹ́ — To desire',note:'Same as English F'},
  {l:'G',name:'Gí',sound:'g (hard)',ex:'Gá — Tall',note:'Always hard G, never soft'},
  {l:'Gb',name:'Gbí',sound:'gb (simultaneous)',ex:'Gbà — To receive',note:'Unique Yorùbá digraph — lips close like B while throat opens like G'},
  {l:'H',name:'Hí',sound:'h',ex:'Há — To hang',note:'Breathy H, same as English'},
  {l:'I',name:'I',sound:'ee (as in "feet")',ex:'Igi — Tree',note:'High front vowel'},
  {l:'J',name:'Jí',sound:'j (as in "joy")',ex:'Já — To cut loose',note:'Same as English J'},
  {l:'K',name:'Kí',sound:'k',ex:'Kú — To die',note:'Unaspirated K'},
  {l:'Kp',name:'Kpí',sound:'kp (simultaneous)',ex:'Kpọ́n — Mortar',note:'Unique digraph — lips close like P while tongue hits palate like K (dialectal)'},
  {l:'L',name:'Lí',sound:'l',ex:'Lé — To add / chase',note:'Lateral L, same as English'},
  {l:'M',name:'Mí',sound:'m',ex:'Mú — To take / hold',note:'Also functions as a syllabic nasal'},
  {l:'N',name:'Ní',sound:'n',ex:'Ní — To have / at',note:'Also a syllabic nasal forming full syllables alone'},
  {l:'O',name:'O',sound:'oh (as in "go")',ex:'Owó — Money',note:'Closed mid-back vowel'},
  {l:'Ọ',name:'Ọ',sound:'aw (as in "law")',ex:'Ọmọ — Child',note:'Open mid-back vowel — unique to Yorùbá'},
  {l:'P',name:'Pí',sound:'p (implosive)',ex:'Pà — To make/create',note:'Not the English P — it is an implosive stop in classic Yorùbá (replaced by Kp in some dialects)'},
  {l:'R',name:'Rí',sound:'r (flapped)',ex:'Rí — To see',note:'A single flap of the tongue — like the Spanish R, never the English R'},
  {l:'S',name:'Sí',sound:'s',ex:'Sí — To (preposition)',note:'Plain S, same as English'},
  {l:'Ṣ',name:'Ṣí',sound:'sh (as in "shoe")',ex:'Ṣe — To do/make',note:'Palatal sibilant — unique Yorùbá letter, always SH sound'},
  {l:'T',name:'Tí',sound:'t',ex:'Tí — That (relative)',note:'Dental T (tongue on teeth)'},
  {l:'U',name:'U',sound:'oo (as in "food")',ex:'Umú — Nose (dialectal)',note:'High back vowel'},
  {l:'W',name:'Wí',sound:'w',ex:'Wá — To come',note:'Bilabial glide'},
  {l:'Y',name:'Yí',sound:'y',ex:'Yà — To turn',note:'Palatal glide'},
];

const CONSONANTS=[
  {c:'B',class:'Stop',place:'Bilabial',voice:'Voiced',note:'Both lips close and release — same as English'},
  {c:'D',class:'Stop',place:'Alveolar',voice:'Voiced',note:'Tongue touches upper gum ridge'},
  {c:'F',class:'Fricative',place:'Labiodental',voice:'Voiceless',note:'Teeth on lower lip — same as English F'},
  {c:'G',class:'Stop',place:'Velar',voice:'Voiced',note:'Back of tongue on soft palate — always HARD G'},
  {c:'Gb',class:'Stop',place:'Labial-velar',voice:'Voiced',note:'⭐ Unique — lips close (B) AND back of tongue rises (G) simultaneously'},
  {c:'H',class:'Fricative',place:'Glottal',voice:'Voiceless',note:'Breath only, from the throat'},
  {c:'J',class:'Affricate',place:'Palatal',voice:'Voiced',note:'Tongue on hard palate — same as English J/DG'},
  {c:'K',class:'Stop',place:'Velar',voice:'Voiceless',note:'Back of tongue on soft palate — unaspirated (no puff of air)'},
  {c:'Kp',class:'Stop',place:'Labial-velar',voice:'Voiceless',note:'⭐ Unique — simultaneous closure of lips (P) and back of tongue (K)'},
  {c:'L',class:'Lateral',place:'Alveolar',voice:'Voiced',note:'Tongue on gum ridge, air flows over sides'},
  {c:'M',class:'Nasal',place:'Bilabial',voice:'Voiced',note:'Both lips together; can form syllable alone: M-ú (hold it!)'},
  {c:'N',class:'Nasal',place:'Alveolar',voice:'Voiced',note:'Tongue on gum ridge; syllabic nasal — can stand alone as a syllable'},
  {c:'P',class:'Stop',place:'Bilabial',voice:'Voiceless',note:'Implosive in classical Yorùbá — air draws inward slightly on release'},
  {c:'R',class:'Flap',place:'Alveolar',voice:'Voiced',note:'⭐ Single quick tap of tongue — like Spanish R, NEVER the English R'},
  {c:'S',class:'Fricative',place:'Alveolar',voice:'Voiceless',note:'Same as English S'},
  {c:'Ṣ',class:'Fricative',place:'Palato-alveolar',voice:'Voiceless',note:'⭐ Always SH sound — tongue pulled back from teeth'},
  {c:'T',class:'Stop',place:'Alveolar',voice:'Voiceless',note:'Tongue on upper teeth (dental) — softer than English T'},
  {c:'W',class:'Glide',place:'Bilabial-velar',voice:'Voiced',note:'Lips round and release quickly — same as English W'},
  {c:'Y',class:'Glide',place:'Palatal',voice:'Voiced',note:'Tongue near hard palate — same as English Y in "yes"'},
];

const VOWELS={
  oral:[
    {v:'A',sound:'ah',ipa:'/a/',ex:'Apá (arm)'},
    {v:'E',sound:'ay',ipa:'/e/',ex:'Eré (play)'},
    {v:'Ẹ',sound:'eh',ipa:'/ɛ/',ex:'Ẹni (person)'},
    {v:'I',sound:'ee',ipa:'/i/',ex:'Igi (tree)'},
    {v:'O',sound:'oh',ipa:'/o/',ex:'Owó (money)'},
    {v:'Ọ',sound:'aw',ipa:'/ɔ/',ex:'Ọmọ (child)'},
    {v:'U',sound:'oo',ipa:'/u/',ex:'Umú (nose)'},
  ],
  nasal:[
    {v:'An',sound:'ahn',ipa:'/ã/',ex:'Àǹ — syllabic nasal'},
    {v:'En',sound:'ayn',ipa:'/ẽ/',ex:'Kòǹ — last'},
    {v:'Ẹn',sound:'ehn',ipa:'/ɛ̃/',ex:'Ẹ̀n — specific'},
    {v:'In',sound:'een',ipa:'/ĩ/',ex:'Ìn — emphasis'},
    {v:'On',sound:'ohn',ipa:'/õ/',ex:'Òǹ — him/her (dialectal)'},
    {v:'Ọn',sound:'awn',ipa:'/ɔ̃/',ex:'Ọ̀n — specific particle'},
    {v:'Un',sound:'oon',ipa:'/ũ/',ex:'Ùn — dialectal form'},
  ]
};

const NUMBERS=[
  {n:1,w:'Ọ̀kan',note:'Base number'},
  {n:2,w:'Èjì',note:'Base number'},
  {n:3,w:'Ẹ̀ta',note:'Base number'},
  {n:4,w:'Ẹ̀rin',note:'Base number'},
  {n:5,w:'Àrún',note:'Base number'},
  {n:6,w:'Ẹ̀fà',note:'Base number'},
  {n:7,w:'Èje',note:'Base number'},
  {n:8,w:'Ẹ̀jọ',note:'Base number'},
  {n:9,w:'Ẹ̀sán',note:'Base number'},
  {n:10,w:'Ẹ̀wá',note:'Base number'},
  {n:11,w:'Ọ̀kanlá',note:'10 + 1'},
  {n:15,w:'Ẹ̀ẹ́dógún',note:'20 − 5 (subtractive!)'},
  {n:20,w:'Ogún',note:'Base 20 (vigesimal system)'},
  {n:25,w:'Ẹ̀ẹ́dọ́gbọ̀n',note:'30 − 5'},
  {n:30,w:'Ọgbọ̀n',note:'Base number'},
  {n:40,w:'Ogójì',note:'20 × 2'},
  {n:45,w:'Ẹ̀ẹ́dẹ́gbẹ̀ta',note:'Wait... 60 − 15? No: 50 − 5'},
  {n:50,w:'Àádọ́ta',note:'60 − 10'},
  {n:60,w:'Ọgọ́ta',note:'20 × 3'},
  {n:100,w:'Ọgọ́rùn-ún',note:'20 × 5'},
  {n:200,w:'Igba',note:'Base 200'},
  {n:400,w:'Irinwó',note:'Base 400'},
];

const TONES={
  marks:[
    {mark:'◌́',name:'Giga (High)',color:'#c9941a',bg:'#fdf3d9',diacritic:'Acute accent ( ´ )',pitch:'High, raised pitch — voice goes UP',musical:'Like singing "Do" (the note)',examples:[{w:'Ẹ̀dá',m:'creature'},{w:'Ìgbà',m:'time'},{w:'Àárọ̀',m:'morning'}],tip:'Think of a question mark tone — your voice rises as if asking something short'},
    {mark:'◌',name:'Àárín (Mid)',color:'#8a8170',bg:'#ece7da',diacritic:'No mark (unmarked)',pitch:'Medium, neutral pitch — voice stays LEVEL',musical:'Like singing "Re" or "Mi"',examples:[{w:'Ile',m:'ground/earth'},{w:'Omi',m:'water'},{w:'Oko',m:'farm'}],tip:'Your natural speaking voice. When you see no accent, stay flat and relaxed'},
    {mark:'◌̀',name:'Ìsàlẹ̀ (Low)',color:'#1c2a47',bg:'#dde2ee',diacritic:'Grave accent ( ` )',pitch:'Low, falling pitch — voice goes DOWN',musical:'Like singing "Sol" dropping to "Fa"',examples:[{w:'Àgbẹ̀',m:'farmer'},{w:'Ìtàfù',m:'table'},{w:'Òjò',m:'rain'}],tip:'Imagine someone tired or announcing something — let your voice drop'},
  ],
  minimalPairs:[
    {a:'Igba',am:'Calabash (gourd)',b:'Ìgbà',bm:'Time/Era',c:'Ígbá',cm:'200 (number)'},
    {a:'Ọkọ',am:'Husband',b:'Oko',bm:'Farm/Hoe',c:'Ọ̀kọ̀',cm:'Spear'},
    {a:'Ewé',am:'Leaf',b:'Ewe',bm:'Undyed cloth',c:'Èwé',cm:'Goat (dialectal)'},
    {a:'Àgbà',am:'Senior/Elder',b:'Agba',bm:'Barrel/Keg',c:'Àgbá',cm:'Type of drum'},
  ]
};

function buildLang(){
  langDone=true;
  let h='';

  /* ── ALPHABET ── */
  h+='<div class="lang-acc" id="acc-alpha"><div class="lang-acc-head" onclick=\"toggleAcc(\'acc-alpha\')\"><div class="lang-acc-icon">🔤</div><div class="lang-acc-titles"><div class="lang-acc-title">Àlfábẹ́ẹ̀tì — Alphabet</div><div class="lang-acc-sub">'+ALPHABET.length+' letters including special Yorùbá characters</div></div><div class="lang-acc-caret">&#9656;</div></div><div class="lang-acc-body"><div class="alpha-grid" id="alpha-grid">';
  ALPHABET.forEach((a,i)=>{
    h+='<div class="alpha-cell" onclick="showAlpha('+i+')"><div class="ac-letter">'+a.l+'</div><div class="ac-name">'+a.name+'</div><div class="ac-sound">'+a.sound.split(' ')[0]+'</div></div>';
  });
  h+='</div><div class="alpha-detail" id="alpha-detail"></div></div></div>';

  /* ── CONSONANTS ── */
  h+='<div class="lang-acc" id="acc-con"><div class="lang-acc-head" onclick=\"toggleAcc(\'acc-con\')\"><div class="lang-acc-icon">🗣️</div><div class="lang-acc-titles"><div class="lang-acc-title">Kọńsónáǹtì — Consonants</div><div class="lang-acc-sub">'+CONSONANTS.length+' consonants including unique Yorùbá sounds</div></div><div class="lang-acc-caret">&#9656;</div></div><div class="lang-acc-body"><table class="con-table"><thead><tr><th>Letter</th><th>Class</th><th>Place</th><th>Voice</th><th>Notes</th></tr></thead><tbody>';
  CONSONANTS.forEach(c=>{
    const special=c.c==='Gb'||c.c==='Kp'||c.c==='R'||c.c==='Ṣ'?'class="con-special"':'';
    h+='<tr '+special+'><td>'+c.c+'</td><td>'+c.class+'</td><td>'+c.place+'</td><td>'+c.voice+'</td><td>'+c.note+'</td></tr>';
  });
  h+='</tbody></table><div style="font-size:11px;color:var(--terra-deep);margin-top:8px;">⭐ = Unique Yorùbá sounds not found in English</div></div></div>';

  /* ── TONES ── */
  h+='<div class="lang-acc" id="acc-tone"><div class="lang-acc-head" onclick=\"toggleAcc(\'acc-tone\')\"><div class="lang-acc-icon">🎵</div><div class="lang-acc-titles"><div class="lang-acc-title">Àmì Ohùn — Tonal Marks</div><div class="lang-acc-sub">3 tones that change the meaning of every word</div></div><div class="lang-acc-caret">&#9656;</div></div><div class="lang-acc-body">';
  h+='<div style="font-size:12.5px;color:var(--ink-soft);line-height:1.6;margin-bottom:12px;">Yorùbá is a <b>tonal language</b> — the same syllable spoken at different pitches becomes completely different words. Every vowel in Yorùbá carries one of three tones.</div>';
  h+='<div class="tone-demo-row">';
  TONES.marks.forEach(t=>{
    h+='<div class="tone-card" style="background:'+t.bg+';border:1.5px solid '+t.color+'20;">'
      +'<div class="tc-mark" style="color:'+t.color+'">'+t.mark+'</div>'
      +'<div class="tc-name" style="color:'+t.color+'">'+t.name+'</div>'
      +'<div class="tc-desc" style="color:var(--ink-soft)">'+t.pitch+'</div>'
      +'<div class="tc-ex">'+t.examples.map(e=>e.w).join(' · ')+'</div>'
      +'</div>';
  });
  h+='</div>';
  h+='<div style="font-size:13px;font-weight:700;color:var(--indigo);margin:14px 0 6px;">Diacritic marks:</div>';
  TONES.marks.forEach(t=>{
    h+='<div style="display:flex;gap:10px;align-items:flex-start;padding:8px 0;border-top:1px dashed var(--edge)">'
      +'<div style="font-family:var(--fd);font-size:26px;font-weight:700;color:'+t.color+';min-width:36px;text-align:center">'+t.mark+'</div>'
      +'<div><div style="font-size:13px;font-weight:600;color:var(--ink)">'+t.diacritic+'</div>'
      +'<div style="font-size:12px;color:var(--ink-soft);margin-top:2px">'+t.pitch+'</div>'
      +'<div style="font-size:11.5px;color:var(--terra-deep);margin-top:3px;font-style:italic">'+t.tip+'</div></div></div>';
  });
  h+='<div style="font-size:13px;font-weight:700;color:var(--indigo);margin:14px 0 8px;">Minimal Pairs — same letters, different tones, different meanings:</div>';
  h+='<div class="tone-pair-grid">';
  TONES.minimalPairs.forEach(p=>{
    h+='<div class="tone-pair"><div class="tp-words">'+p.a+' / '+p.b+(p.c?' / '+p.c:'')+'</div><div class="tp-means">'+p.am+' / '+p.bm+(p.cm?' / '+p.cm:'')+'</div></div>';
  });
  h+='</div></div></div>';

  /* ── VOWELS ── */
  h+='<div class="lang-acc" id="acc-vow"><div class="lang-acc-head" onclick=\"toggleAcc(\'acc-vow\')\"><div class="lang-acc-icon">🔊</div><div class="lang-acc-titles"><div class="lang-acc-title">Àwọn Fáwẹ́lì — Vowels</div><div class="lang-acc-sub">7 oral + 7 nasal vowels, vowel harmony rules</div></div><div class="lang-acc-caret">&#9656;</div></div><div class="lang-acc-body">';
  h+='<div class="vowel-section-label">Oral Vowels (7)</div><div class="vowel-row">';
  VOWELS.oral.forEach(v=>{
    h+='<div class="vowel-chip"><div class="vc-v">'+v.v+'</div><div class="vc-s">'+v.sound+'<br><span style="font-size:9px;color:var(--gray)">'+v.ipa+'</span></div></div>';
  });
  h+='</div><div style="font-size:12px;color:var(--ink-soft);margin-bottom:10px;">';
  VOWELS.oral.forEach(v=>{ h+='<b>'+v.v+'</b> = '+v.sound+' — '+v.ex+'<br>'; });
  h+='</div>';
  h+='<div class="vowel-section-label">Nasal Vowels (7) — vowel + N together</div><div class="vowel-row">';
  VOWELS.nasal.forEach(v=>{
    h+='<div class="vowel-chip"><div class="vc-v" style="font-size:16px">'+v.v+'</div><div class="vc-s">'+v.sound+'</div></div>';
  });
  h+='</div>';
  h+='<div class="harmony-box"><h4>Vowel Harmony</h4><p>Yorùbá vowels split into two sets. Within a word, all vowels must belong to the same set. This is why prefix vowels change to match their root — e.g. <b>Oní → Ẹlẹ́</b> before ẹja (fish monger).</p><div class="hb-pair"><div class="hb-item">Set 1: A · E · I · O · U</div><div class="hb-item">Set 2: A · Ẹ · I · Ọ · U</div></div><p style="margin-top:8px;font-size:11px;opacity:.75;">Note: A, I, U appear in both sets and are neutral — they can harmonize with either group.</p></div>';
  h+='</div></div>';

  /* ── NUMBERS ── */
  h+='<div class="lang-acc" id="acc-num"><div class="lang-acc-head" onclick=\"toggleAcc(\'acc-num\')\"><div class="lang-acc-icon">🔢</div><div class="lang-acc-titles"><div class="lang-acc-title">Àwọn Nọ́mbà — Numbers</div><div class="lang-acc-sub">Vigesimal (base-20) subtractive counting system</div></div><div class="lang-acc-caret">&#9656;</div></div><div class="lang-acc-body">';
  h+='<div class="num-intro">Yorùbá uses a <b>base-20 (vigesimal)</b> counting system — unlike English which uses base-10. Even more uniquely, many numbers are formed <b>subtractively</b>: instead of "fifteen" meaning 10+5, Yorùbá says <i>ẹ̀ẹ́dógún</i> which means <b>20 minus 5</b>.</div>';
  NUMBERS.forEach(n=>{
    h+='<div class="num-row"><div class="num-digit">'+n.n+'</div><div class="num-word">'+n.w+'</div><div class="num-note">'+n.note+'</div></div>';
  });
  h+='<div class="num-system-box"><h4>How the system works</h4><div style="font-size:12.5px;color:var(--ink-soft);line-height:1.7;">'
    +'<b>Base numbers:</b> 1–10, 20, 30, 200, 400<br>'
    +'<b>Addition:</b> 11–14 = 10 + (1–4) → <i>ọ̀kanlá, èjìlá...</i><br>'
    +'<b>Subtraction:</b> 15 = 20 − 5 → <i>ẹ̀ẹ́dógún</i><br>'
    +'<b>Multiplication:</b> 40 = 20 × 2 → <i>ogójì</i><br>'
    +'<b>Combined:</b> 35 = (20×2) − 5 → <i>ẹ̀ẹ́dọ́gbọ̀n</i><br>'
    +'<b>Base 200 & 400:</b> Large numbers use <i>igba</i> (200) and <i>irinwó</i> (400) as anchors</div></div>';
  h+='</div></div>';

  document.getElementById('lang-out').innerHTML=h;
}

function toggleAcc(id){
  document.getElementById(id).classList.toggle('open');
}

function showAlpha(i){
  const a=ALPHABET[i];
  const el=document.getElementById('alpha-detail');
  const isOpen=el.classList.contains('show')&&el.dataset.i==i;
  if(isOpen){el.classList.remove('show');el.dataset.i='';return;}
  el.dataset.i=i;
  el.innerHTML='<div class="ad-letter">'+a.l+'</div>'
    +'<div class="ad-name">Name: <b>'+a.name+'</b></div>'
    +'<div class="ad-sound">Sound: '+a.sound+'</div>'
    +'<div class="ad-example">Example: '+a.ex+'</div>'
    +'<div class="ad-example" style="margin-top:4px;color:rgba(255,255,255,.6)">'+a.note+'</div>';
  el.classList.add('show');
}



/* ══════════ PI NETWORK INTEGRATION ══════════ */
const PI_APP_NAME = 'ÀTÚPALẸ̀';
let piUser = null;
let piReady = false;

function isPiBrowser(){
  return typeof window.Pi !== 'undefined';
}

async function initPi(){
  const bar = document.getElementById('pi-bar');
  if(!bar) return;
  bar.style.display = 'flex';

  if(!isPiBrowser()){
    document.getElementById('pi-username').textContent = 'Open in Pi Browser';
    document.getElementById('pi-status').textContent = 'Pi features require the Pi Browser app';
    bar.style.background = '#5c5341';
    return;
  }

  try{
    Pi.init({ version: '2.0', sandbox: false });

    const scopes = ['username', 'payments'];

    function onIncompletePaymentFound(payment){
      // Handle any incomplete payment left from a previous session
      console.log('Incomplete payment found:', payment);
    }

    const auth = await Pi.authenticate(scopes, onIncompletePaymentFound);
    piUser = auth.user;
    piReady = true;

    document.getElementById('pi-username').textContent = 'π ' + (piUser.username || 'Pioneer');
    document.getElementById('pi-status').textContent = 'Signed in · ÀTÚPALẸ̀ Yorùbá App';

    // Show the pay-to-play puzzle button
    const payBtn = document.getElementById('pi-pay-puzzle');
    if(payBtn) payBtn.style.display = 'inline-block';

  }catch(e){
    console.error('Pi auth error:', e);
    document.getElementById('pi-username').textContent = 'Pi sign-in failed';
    document.getElementById('pi-status').textContent = 'Tap to retry or continue as guest';
    bar.addEventListener('click', initPi, {once:true});
  }
}

// Pi payment for puzzle play (1π per session)
async function piPayForPuzzle(){
  if(!piReady || !isPiBrowser()){
    alert('Please open ÀTÚPALẸ̀ in the Pi Browser app to use Pi payments.');
    return;
  }

  const paymentData = {
    amount: 1,
    memo: 'ÀTÚPALẸ̀ — Yorùbá Word Puzzle (1 session)',
    metadata: {
      app: 'atupale-yoruba',
      feature: 'puzzle-session',
      user: piUser ? piUser.username : 'unknown',
      timestamp: Date.now()
    }
  };

  const callbacks = {
    onReadyForServerApproval: function(paymentId){
      // In a full backend setup you'd call your server here to approve.
      // For this frontend-only app we auto-approve via Pi's sandbox flow.
      console.log('Ready for approval, paymentId:', paymentId);
    },
    onReadyForServerCompletion: function(paymentId, txid){
      console.log('Payment complete! txid:', txid);
      // Unlock puzzle session
      unlockPuzzleSession();
    },
    onCancel: function(paymentId){
      console.log('Payment cancelled:', paymentId);
    },
    onError: function(error, payment){
      console.error('Payment error:', error, payment);
      alert('Payment failed: ' + (error.message || error));
    }
  };

  try{
    await Pi.createPayment(paymentData, callbacks);
  }catch(e){
    console.error('createPayment error:', e);
  }
}

function unlockPuzzleSession(){
  // Mark puzzle as paid and switch to puzzle tab
  sessionStorage.setItem('puzzle_paid', '1');
  document.querySelectorAll('.tab').forEach(b=>b.classList.remove('on'));
  document.querySelectorAll('.panel').forEach(p=>p.classList.remove('on'));
  document.querySelector('[data-tab="puz"]').classList.add('on');
  document.getElementById('p-puz').classList.add('on');
  initPuzzle();

  const bar = document.getElementById('pi-bar');
  if(bar){
    document.getElementById('pi-status').textContent = '✓ Puzzle unlocked! Enjoy your session.';
  }
}

// Wire up the Pay button
document.addEventListener('DOMContentLoaded', function(){
  const payBtn = document.getElementById('pi-pay-puzzle');
  if(payBtn) payBtn.addEventListener('click', piPayForPuzzle);

  // Auto-init Pi on load
  initPi();
});

</script>
</body>
</html>
