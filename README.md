<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Zero-to-Hero ›› — старт карьеры для студентов</title>
<style>
:root{
  --bg:#F7F7F4;--surface:#FFFFFF;--ink:#16161A;--muted:#6B6B72;--faint:#95959C;--hair:#E7E7E1;--hair2:#EFEFE9;
  --blue:#3F5BF6;--blue-soft:#EEF1FE;--blue-ink:#1E2F9E;
  --teal:#0F9E75;--teal-soft:#E1F5EE;--teal-ink:#0A5F48;
  --amber:#B9791A;--amber-soft:#FBF0DC;--amber-ink:#7A4E0C;
  --purple:#6C4DD6;--purple-soft:#EFEBFB;--purple-ink:#3E2A8C;
  --green:#3B7D22;--green-soft:#ECF4E2;--green-ink:#274F14;
  --red:#C0392B;--red-soft:#FBEBEA;--red-ink:#7E241B;
  --radius:12px;--font:'Inter',-apple-system,BlinkMacSystemFont,'Segoe UI',Roboto,sans-serif;
}
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Martian+Mono:wght@600;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@700;800&display=swap');
/* ============================================================
   Young&&Yandex-flavoured dark skin. Applied via <body class="yy">.
   Dark by default, lavender + electric-green accents, striped cards,
   oversized display type. Everything is a token override so the
   existing light/dark app keeps working underneath. */
body.yy{
  /* Changellenge-flavoured — LIGHT & business. Clean white, ink-black text,
     one confident indigo accent, generous whitespace, no playful stripes. */
  --bg:#FFFFFF;--surface:#FFFFFF;--surface2:#F5F6FA;--ink:#141419;--muted:#5C5C68;--faint:#9494A0;
  --hair:#E8E8EE;--hair2:#F1F1F5;
  --yy:#2B44FF;           /* Changellenge-style confident indigo */
  --yy-ink:#FFFFFF;
  --yy-dark:#0E1330;      /* deep navy for headings/hero */
  --yy-soft:#EEF0FF;      /* pale indigo fill */
  --yy-green:#10B981;--yy-amber:#F59E0B;--yy-pink:#EC4899;--yy-cyan:#06B6D4;
  --accent:var(--yy);--accent-soft:var(--yy-soft);--accent-ink:#1B2ECC;
  --blue:var(--yy);--blue-soft:var(--yy-soft);--blue-ink:#1B2ECC;
  --disp:'Manrope',sans-serif;--mono:'Martian Mono',monospace;
  background:var(--bg);color:var(--ink);
}
*{box-sizing:border-box;margin:0;padding:0}
html,body{height:100%}
body{font-family:var(--font);background:var(--bg);color:var(--ink);line-height:1.5;-webkit-font-smoothing:antialiased}
body.dark{
  --bg:#141417;--surface:#1E1E24;--ink:#F2F2F0;--muted:#A0A0A8;--faint:#6B6B72;--hair:#30303A;--hair2:#282830;
  /* soft backgrounds: deep, low-saturation tints */
  --blue-soft:#20264D;--teal-soft:#123B2E;--amber-soft:#3A2C12;--purple-soft:#282052;--green-soft:#1E3316;--red-soft:#3A1E1B;
  /* ink (text/icons on soft bg): LIGHT tints so they read on dark — critical fix */
  --blue-ink:#9FB0FF;--teal-ink:#5FD6AE;--amber-ink:#E0B267;--purple-ink:#B4A0F0;--green-ink:#8FD86A;--red-ink:#F0938A;
  /* base accents slightly brightened for dark */
  --blue:#5B74FF;--teal:#16B589;--amber:#D69A3A;--green:#5BA23C;--red:#D9584A;
}
button{font-family:inherit;cursor:pointer;border:none;background:none}
a{color:inherit;text-decoration:none}
.mono{font-family:ui-monospace,SFMono-Regular,Menlo,monospace}
.hidden{display:none!important}

/* ---------- preferences: density, type scale, motion, accent ---------- */
/* the design uses px, not rem — so scale the content area itself */
.content{zoom:var(--font-scale,1)}
@supports not (zoom:1){.content{transform:scale(var(--font-scale,1));transform-origin:top left;width:calc(100% / var(--font-scale,1))}}
body.compact .panel{padding:14px 16px}
body.compact .g{gap:10px}
body.compact .statcard{padding:13px}
body.compact .statcard .sc-ic{width:32px;height:32px;margin-bottom:9px}
body.compact .statcard .sc-v{font-size:22px}
body.compact .li{padding:8px 0}
body.compact .nav-item{height:36px}
body.compact .hero-banner{padding:18px 20px}
body.compact .content{padding:18px}
body.no-motion *,body.no-motion *::before,body.no-motion *::after{transition:none!important;animation:none!important}

/* interview banner */
.iv-banner{display:flex;align-items:center;gap:14px;background:var(--purple-soft);border:1.5px solid var(--purple);border-radius:13px;padding:13px 15px;margin-bottom:13px}
.iv-banner .iv-ic{width:38px;height:38px;border-radius:11px;background:var(--purple);color:#fff;display:flex;align-items:center;justify-content:center;flex:none}
.iv-banner .iv-ic .onb-icon{width:18px;height:18px}
.iv-banner .iv-b{flex:1;min-width:0}
.iv-banner .iv-t{font-size:13.5px;font-weight:700;color:var(--purple-ink)}
.iv-banner .iv-d{font-size:12px;color:var(--purple-ink);opacity:.8;margin-top:2px}
.iv-banner.soon{background:var(--amber-soft);border-color:var(--amber)}
.iv-banner.soon .iv-ic{background:var(--amber)}
.iv-banner.soon .iv-t,.iv-banner.soon .iv-d{color:var(--amber-ink)}
.iv-banner.past{background:var(--hair2);border-color:var(--hair)}
.iv-banner.past .iv-ic{background:var(--faint)}
.iv-banner.past .iv-t,.iv-banner.past .iv-d{color:var(--muted)}
.iv-banner .btn{width:auto;height:34px;font-size:12px;padding:0 12px;flex:none}
.iv-set{display:flex;gap:8px;align-items:center;flex-wrap:wrap;margin-top:12px}
.iv-set input[type=datetime-local]{height:38px;border:1.5px solid var(--hair);border-radius:10px;padding:0 11px;font-family:inherit;font-size:12.5px;background:var(--surface);color:var(--ink);outline:none}
.iv-set input:focus{border-color:var(--accent)}
.iv-set .lbl{font-size:11.5px;color:var(--muted);display:flex;align-items:center;gap:6px}
.iv-set .lbl .onb-icon{width:13px;height:13px}

/* stage history */
.slog{margin-top:12px}
.slog-h{font-size:11.5px;font-weight:600;color:var(--muted);display:flex;align-items:center;gap:7px;margin-bottom:8px;cursor:pointer}
.slog-h .onb-icon{width:13px;height:13px;transition:.18s}
.slog.open .slog-h .onb-icon{transform:rotate(90deg)}
.slog-body{display:none;background:var(--bg);border-radius:10px;padding:10px 12px}
.slog.open .slog-body{display:block}
.slog-row{display:flex;align-items:center;gap:10px;padding:6px 0;font-size:12px;border-bottom:1px solid var(--hair2)}
.slog-row:last-child{border:none}
.slog-row .sl-d{width:8px;height:8px;border-radius:50%;flex:none}
.slog-row .sl-n{flex:1;font-weight:600}
.slog-row .sl-t{color:var(--faint);font-size:11px}

/* search + archive toggle */
.app-search{flex:1;min-width:180px;display:flex;align-items:center;gap:9px;height:38px;padding:0 12px;border:1.5px solid var(--hair);border-radius:10px;background:var(--surface)}
.app-search input{flex:1;border:none;outline:none;background:none;font-family:inherit;font-size:13.5px;color:var(--ink)}
.app-search .onb-icon{width:15px;height:15px;color:var(--muted);flex:none}
.arch-toggle{display:inline-flex;align-items:center;gap:7px;height:38px;padding:0 13px;border:1.5px solid var(--hair);border-radius:10px;background:var(--surface);color:var(--muted);font-size:12.5px;font-weight:500;cursor:pointer;white-space:nowrap}
.arch-toggle:hover{border-color:var(--accent)}
.arch-toggle.on{background:var(--accent);border-color:var(--accent);color:#fff;font-weight:600}
.arch-toggle .onb-icon{width:14px;height:14px}
.appcard.archived{opacity:.62;background:var(--bg)}
.appcard.archived .ac-logo{filter:grayscale(1)}
.arch-badge{font-size:9.5px;font-weight:700;text-transform:uppercase;letter-spacing:.04em;background:var(--hair2);color:var(--faint);padding:3px 8px;border-radius:20px}

/* ---------- diagnostics ---------- */
.dg-intro{max-width:640px;margin:0 auto}
.dg-hero{position:relative;overflow:hidden;background:var(--accent);color:#fff;border-radius:22px;padding:32px;text-align:center;margin-bottom:20px}
.dg-hero::before{content:"";position:absolute;right:-70px;top:-90px;width:250px;height:250px;border-radius:50%;background:rgba(255,255,255,.09)}
.dg-hero::after{content:"";position:absolute;left:-50px;bottom:-100px;width:200px;height:200px;border-radius:50%;background:rgba(255,255,255,.06)}
.dg-hero>*{position:relative;z-index:1}
.dg-hero .dh-ic{width:66px;height:66px;border-radius:20px;background:rgba(255,255,255,.2);border:2px solid rgba(255,255,255,.28);display:flex;align-items:center;justify-content:center;margin:0 auto 16px}
.dg-hero .dh-ic .onb-icon{width:32px;height:32px}
.dg-hero h2{font-size:24px;font-weight:800;letter-spacing:-.025em;line-height:1.2}
.dg-hero p{font-size:14.5px;opacity:.92;margin-top:8px;line-height:1.55;max-width:440px;margin-left:auto;margin-right:auto}
.dg-meta{display:flex;justify-content:center;gap:22px;margin-top:18px;flex-wrap:wrap}
.dg-meta span{display:flex;align-items:center;gap:6px;font-size:12.5px;opacity:.9}
.dg-meta .onb-icon{width:14px;height:14px}

.dg-sections{display:flex;flex-direction:column;gap:10px;margin-bottom:20px}
.dg-sec{display:flex;align-items:center;gap:13px;border:1.5px solid var(--hair);border-radius:14px;padding:14px 16px;background:var(--surface);transition:.14s}
.dg-sec.done{border-color:var(--green);background:var(--green-soft)}
.dg-sec.cur{border-color:var(--accent);box-shadow:0 6px 20px rgba(63,91,246,.1)}
.dg-sec .ds-ic{width:40px;height:40px;border-radius:12px;background:var(--accent-soft);color:var(--accent);display:flex;align-items:center;justify-content:center;flex:none}
.dg-sec.done .ds-ic{background:var(--green);color:#fff}
.dg-sec .ds-ic .onb-icon{width:19px;height:19px}
.dg-sec .ds-b{flex:1;min-width:0}
.dg-sec .ds-t{font-size:14px;font-weight:600;letter-spacing:-.01em}
.dg-sec .ds-d{font-size:12px;color:var(--muted);margin-top:2px}
.dg-sec .ds-c{font-size:12px;font-weight:700;color:var(--muted);flex:none}
.dg-sec.done .ds-c{color:var(--green-ink)}

/* question card */
.dg-wrap{max-width:660px;margin:0 auto}
.dg-bar{height:6px;background:var(--hair2);border-radius:3px;overflow:hidden;margin-bottom:8px}
.dg-bar i{display:block;height:100%;background:var(--accent);border-radius:3px;transition:width .35s cubic-bezier(.4,0,.2,1)}
.dg-bar-l{display:flex;justify-content:space-between;font-size:11.5px;color:var(--muted);margin-bottom:22px}

.dg-card{border:1.5px solid var(--hair);border-radius:20px;background:var(--surface);padding:26px 28px}
.dg-tag{display:inline-flex;align-items:center;gap:6px;font-size:10.5px;font-weight:700;letter-spacing:.05em;text-transform:uppercase;padding:5px 11px;border-radius:20px;margin-bottom:14px}
.dg-tag.self{background:var(--blue-soft);color:var(--blue-ink)}
.dg-tag.test{background:var(--purple-soft);color:var(--purple-ink)}
.dg-tag .onb-icon{width:12px;height:12px}
.dg-q{font-size:19px;font-weight:700;letter-spacing:-.02em;line-height:1.35;margin-bottom:20px}
.dg-opts{display:flex;flex-direction:column;gap:10px}
.dg-opt{display:flex;align-items:center;gap:13px;text-align:left;padding:15px 17px;border:1.5px solid var(--hair);border-radius:14px;background:var(--surface);color:var(--ink);font-size:14px;font-weight:500;cursor:pointer;transition:.14s;width:100%}
.dg-opt:hover{border-color:var(--accent);background:var(--accent-soft)}
.dg-opt .do-k{width:26px;height:26px;border-radius:8px;border:1.5px solid var(--hair);display:flex;align-items:center;justify-content:center;font-size:11.5px;font-weight:700;color:var(--muted);flex:none;transition:.14s}
.dg-opt:hover .do-k{border-color:var(--accent);color:var(--accent)}
.dg-opt.on{border-color:var(--accent);background:var(--accent-soft);color:var(--accent-ink);font-weight:600}
.dg-opt.on .do-k{background:var(--accent);border-color:var(--accent);color:#fff}
.dg-nav{display:flex;align-items:center;gap:10px;margin-top:24px}
.dg-nav .btn{width:auto;height:42px}
.dg-nav .dg-exit{margin-left:auto;font-size:12.5px;color:var(--faint);cursor:pointer}
.dg-nav .dg-exit:hover{color:var(--accent)}
.dg-hint{display:flex;gap:9px;align-items:flex-start;background:var(--bg);border-radius:11px;padding:11px 13px;margin-top:16px;font-size:12.5px;color:var(--muted);line-height:1.45}
.dg-hint .onb-icon{width:14px;height:14px;color:var(--accent);flex:none;margin-top:2px}

/* result */
.dg-result{max-width:760px;margin:0 auto}
.dg-score{display:flex;align-items:center;gap:26px;background:var(--surface);border:1px solid var(--hair);border-radius:20px;padding:26px 28px;margin-bottom:18px;flex-wrap:wrap}
.dg-ring{position:relative;width:118px;height:118px;flex:none}
.dg-ring svg{transform:rotate(-90deg)}
.dg-ring .dr-v{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center}
.dg-ring .dr-n{font-size:28px;font-weight:800;letter-spacing:-.03em;line-height:1}
.dg-ring .dr-l{font-size:9.5px;color:var(--muted);text-transform:uppercase;letter-spacing:.06em;margin-top:4px}
.dg-lvl{flex:1;min-width:220px}
.dg-lvl .dl-badge{display:inline-flex;align-items:center;gap:7px;font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:.05em;padding:5px 12px;border-radius:20px;color:#fff}
.dg-lvl h3{font-size:21px;font-weight:800;letter-spacing:-.02em;margin-top:10px}
.dg-lvl p{font-size:13.5px;color:var(--muted);margin-top:6px;line-height:1.5}
.dg-quiz{flex:none;text-align:center;background:var(--bg);border-radius:14px;padding:16px 20px}
.dg-quiz .dq-v{font-size:22px;font-weight:800;letter-spacing:-.02em}
.dg-quiz .dq-l{font-size:11px;color:var(--muted);margin-top:3px}

.skill-row{display:flex;align-items:center;gap:14px;padding:14px 0;border-bottom:1px solid var(--hair2)}
.skill-row:last-child{border:none}
.skill-row .sr-n{width:150px;flex:none;font-size:13.5px;font-weight:600}
.skill-row .sr-track{flex:1;height:9px;background:var(--hair2);border-radius:5px;overflow:hidden;position:relative}
.skill-row .sr-track i{display:block;height:100%;border-radius:5px;transition:width .5s}
.skill-row .sr-self{position:absolute;top:-3px;width:2px;height:15px;background:var(--faint);border-radius:1px}
.skill-row .sr-v{width:38px;flex:none;text-align:right;font-size:13px;font-weight:700}
.skill-row .sr-gap{width:104px;flex:none;text-align:right;font-size:11px;font-weight:600}
.gap-over{color:var(--amber-ink)}
.gap-under{color:var(--accent)}
.gap-match{color:var(--green)}

.dg-legend{display:flex;gap:18px;flex-wrap:wrap;font-size:11.5px;color:var(--muted);margin-top:14px;padding-top:12px;border-top:1px solid var(--hair2)}
.dg-legend span{display:flex;align-items:center;gap:6px}
.dg-legend .lg-d{width:10px;height:3px;border-radius:2px}

.advice{display:flex;gap:14px;align-items:flex-start;border:1.5px solid var(--hair);border-radius:15px;padding:16px;background:var(--surface);margin-bottom:10px}
.advice .ad-ic{width:38px;height:38px;border-radius:12px;background:var(--amber-soft);color:var(--amber);display:flex;align-items:center;justify-content:center;flex:none}
.advice .ad-ic .onb-icon{width:18px;height:18px}
.advice .ad-b{flex:1;min-width:0}
.advice .ad-t{font-size:14px;font-weight:700}
.advice .ad-d{font-size:12.5px;color:var(--muted);margin-top:3px;line-height:1.45}
.advice .btn{width:auto;height:34px;font-size:12.5px;flex:none}

/* review of the knowledge check */
.dg-review{margin-top:10px}
.rev-row{border:1.5px solid var(--hair);border-radius:13px;padding:14px 16px;margin-bottom:9px}
.rev-row.ok{border-color:var(--green);background:var(--green-soft)}
.rev-row.bad{border-color:var(--red);background:var(--red-soft)}
.rev-h{display:flex;align-items:flex-start;gap:10px;font-size:13.5px;font-weight:600;line-height:1.4}
.rev-h .rh-ic{width:20px;height:20px;border-radius:6px;display:flex;align-items:center;justify-content:center;flex:none;color:#fff;margin-top:1px}
.rev-row.ok .rh-ic{background:var(--green)}
.rev-row.bad .rh-ic{background:var(--red)}
.rev-h .onb-icon{width:12px;height:12px;stroke-width:3.5}
.rev-a{font-size:12.5px;margin-top:9px;padding-left:30px}
.rev-a .ra-y{color:var(--muted)}
.rev-a .ra-c{color:var(--green-ink);font-weight:600;margin-top:3px}
.rev-why{font-size:12.5px;color:var(--muted);line-height:1.5;margin-top:9px;padding:10px 12px;background:var(--surface);border-radius:9px}

@media(max-width:640px){.skill-row .sr-n{width:100px;font-size:12.5px}.skill-row .sr-gap{display:none}.dg-card{padding:20px}}

/* ---------- applications: stats band, expandable rows, notes ---------- */
.app-stats{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin-bottom:16px}
@media(max-width:760px){.app-stats{grid-template-columns:repeat(2,1fr)}}
.app-toolbar{display:flex;gap:10px;align-items:center;flex-wrap:wrap;margin-bottom:14px}
.app-toolbar .sort-sel{max-width:190px;height:38px}
.app-toolbar .ps{margin:0}

.appcard{position:relative;transition:.18s}
.appcard.open{border-color:var(--accent);box-shadow:0 10px 30px rgba(63,91,246,.12)}
.appcard .ac-chev{width:28px;height:28px;border-radius:8px;display:flex;align-items:center;justify-content:center;color:var(--muted);flex:none;transition:.18s}
.appcard.open .ac-chev{transform:rotate(180deg);color:var(--accent)}
.appcard .ac-chev .onb-icon{width:15px;height:15px}
.app-body{border-top:1px solid var(--hair2);margin-top:14px;padding-top:14px}
.app-body.hidden{display:none}

.nudge{display:flex;gap:9px;align-items:flex-start;background:var(--amber-soft);border-radius:11px;padding:11px 13px;margin-bottom:12px;font-size:12.5px;color:var(--amber-ink);line-height:1.45}
.nudge .onb-icon{width:14px;height:14px;flex:none;margin-top:2px}
.nudge b{font-weight:700}

.app-note{width:100%;min-height:64px;border:1.5px solid var(--hair);border-radius:11px;padding:10px 12px;font-family:inherit;font-size:12.5px;line-height:1.5;outline:none;resize:vertical;background:var(--bg);color:var(--ink);transition:.14s}
.app-note:focus{border-color:var(--accent);background:var(--surface)}
.app-note::placeholder{color:var(--faint)}
.note-head{display:flex;align-items:center;gap:7px;font-size:11.5px;font-weight:600;color:var(--muted);margin-bottom:7px}
.note-head .onb-icon{width:13px;height:13px}
.note-saved{margin-left:auto;font-size:10.5px;color:var(--green);opacity:0;transition:.2s}
.note-saved.on{opacity:1}

.app-actions{display:flex;gap:8px;flex-wrap:wrap;margin-top:14px}
.app-actions .btn{width:auto;height:34px;font-size:12.5px;padding:0 13px}
.btn-withdraw{color:var(--red);border:1.5px solid var(--hair);background:var(--surface);border-radius:9px}
.btn-withdraw:hover{border-color:var(--red);background:var(--red-soft)}

.stage-move{display:flex;gap:5px;align-items:center;margin-top:12px;flex-wrap:wrap}
.stage-move .sm-l{font-size:11px;color:var(--faint);margin-right:4px}
.stage-move button{font-size:11px;font-weight:600;padding:5px 10px;border-radius:16px;border:1.5px solid var(--hair);background:var(--surface);color:var(--muted)}
.stage-move button:hover{border-color:var(--accent);color:var(--accent-ink)}
.stage-move button.on{background:var(--accent);border-color:var(--accent);color:#fff}

/* ---------- applications funnel (student) ---------- */
.app-stages{display:grid;grid-template-columns:repeat(5,1fr);gap:10px;margin-bottom:18px}
@media(max-width:820px){.app-stages{grid-template-columns:repeat(3,1fr)}}
@media(max-width:520px){.app-stages{grid-template-columns:repeat(2,1fr)}}
.app-stage{border:1.5px solid var(--hair);border-radius:14px;padding:14px;background:var(--surface);cursor:pointer;transition:.14s;position:relative;overflow:hidden}
.app-stage::after{content:"";position:absolute;left:0;right:0;bottom:0;height:3px;background:var(--as-c,var(--accent));transform:scaleX(0);transform-origin:left;transition:.2s}
.app-stage:hover{border-color:var(--as-c,var(--accent))}
.app-stage.on{border-color:var(--as-c,var(--accent));background:var(--bg)}
.app-stage.on::after{transform:scaleX(1)}
.app-stage .as-d{width:8px;height:8px;border-radius:50%;background:var(--as-c,var(--accent));margin-bottom:9px}
.app-stage .as-v{font-size:22px;font-weight:800;letter-spacing:-.02em;line-height:1}
.app-stage .as-l{font-size:11.5px;color:var(--muted);margin-top:4px}

.appcard{display:flex;align-items:center;gap:14px;border:1px solid var(--hair);border-radius:15px;background:var(--surface);padding:15px 18px;margin-bottom:10px;cursor:pointer;transition:.14s}
.appcard:hover{border-color:var(--accent);box-shadow:0 6px 18px rgba(0,0,0,.06)}
.appcard .ac-logo{width:44px;height:44px;border-radius:12px;flex:none;display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;font-size:17px}
.appcard .ac-b{flex:1;min-width:0}
.appcard .ac-t{font-size:14.5px;font-weight:700;letter-spacing:-.01em}
.appcard .ac-d{font-size:12.5px;color:var(--muted);margin-top:2px}
.appcard .ac-meta{display:flex;gap:12px;flex-wrap:wrap;margin-top:7px;font-size:11.5px;color:var(--faint)}
.appcard .ac-meta span{display:flex;align-items:center;gap:4px}
.appcard .ac-meta .onb-icon{width:11px;height:11px}
.appcard .ac-right{flex:none;text-align:right}
.stage-pill{display:inline-flex;align-items:center;gap:6px;font-size:11px;font-weight:700;padding:5px 11px;border-radius:20px;white-space:nowrap}
.stage-pill .d{width:6px;height:6px;border-radius:50%}

/* timeline inside an application */
.tl{position:relative;padding-left:26px;margin-top:14px}
.tl::before{content:"";position:absolute;left:7px;top:6px;bottom:6px;width:2px;background:var(--hair)}
.tl-row{position:relative;padding:8px 0;font-size:12.5px}
.tl-row::before{content:"";position:absolute;left:-23px;top:13px;width:10px;height:10px;border-radius:50%;background:var(--hair);border:2px solid var(--surface)}
.tl-row.done::before{background:var(--green)}
.tl-row.cur::before{background:var(--accent);box-shadow:0 0 0 3px var(--accent-soft)}
.tl-row .tl-t{font-weight:600}
.tl-row .tl-d{color:var(--faint);font-size:11.5px;margin-top:1px}

/* ---------- portfolio ---------- */
.pf-grid2{display:grid;grid-template-columns:repeat(auto-fill,minmax(320px,1fr));gap:16px}
.folio{border:1px solid var(--hair);border-radius:18px;background:var(--surface);overflow:hidden;transition:.16s}
.folio:hover{transform:translateY(-3px);box-shadow:0 14px 34px rgba(0,0,0,.09)}
.folio .fo-top{padding:18px 20px;display:flex;gap:12px;align-items:flex-start;border-bottom:1px solid var(--hair2)}
.folio .fo-logo{width:42px;height:42px;border-radius:12px;flex:none;display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;font-size:16px}
.folio .fo-t{font-size:14.5px;font-weight:700;letter-spacing:-.01em;line-height:1.3}
.folio .fo-c{font-size:12px;color:var(--muted);margin-top:2px}
.folio .fo-score{margin-left:auto;flex:none;text-align:center}
.folio .fo-sv{font-size:21px;font-weight:800;letter-spacing:-.02em}
.folio .fo-sl{font-size:9.5px;color:var(--faint);text-transform:uppercase;letter-spacing:.05em}
.folio .fo-body{padding:16px 20px 18px}
.folio .fo-bars{display:flex;flex-direction:column;gap:8px;margin-bottom:14px}
.folio .fo-bar{display:flex;align-items:center;gap:10px;font-size:12px}
.folio .fo-bar .n{flex:1;color:var(--muted)}
.folio .fo-bar .b{width:70px;height:5px;background:var(--hair2);border-radius:3px;overflow:hidden;flex:none}
.folio .fo-bar .b i{display:block;height:100%;border-radius:3px}
.folio .fo-bar .v{font-size:11.5px;font-weight:700;min-width:24px;text-align:right}
.folio .fo-tags{display:flex;flex-wrap:wrap;gap:6px}
.folio .fo-tag{font-size:11px;font-weight:500;padding:4px 10px;border-radius:14px;background:var(--accent-soft);color:var(--accent-ink)}
.folio-empty{border:1.5px dashed var(--hair);border-radius:18px;padding:48px 24px;text-align:center;background:var(--surface)}
/* the decorative icon sits in its own circle — it can never be confused with a button icon */
.folio-empty .fe-ic{width:72px;height:72px;border-radius:22px;background:var(--accent-soft);color:var(--accent);
  display:flex;align-items:center;justify-content:center;margin:0 auto 16px}
.folio-empty .fe-ic>.onb-icon{width:32px;height:32px}
.folio-empty h3{font-size:17px;font-weight:700;letter-spacing:-.02em}
.folio-empty p{font-size:13.5px;color:var(--muted);margin-top:7px;line-height:1.55;max-width:400px;margin-left:auto;margin-right:auto}

/* ---------- candidate search (company) ---------- */
.cand-filters{display:flex;gap:12px;flex-wrap:wrap;margin-bottom:16px;align-items:center}
.cand-search{flex:1;min-width:220px;display:flex;align-items:center;gap:9px;height:44px;padding:0 14px;border:1.5px solid var(--hair);border-radius:12px;background:var(--surface)}
.cand-search input{flex:1;border:none;outline:none;background:none;font-family:inherit;font-size:14px;color:var(--ink)}
.cand-search .onb-icon{width:17px;height:17px;color:var(--muted);flex:none}
.cand-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:14px}
.candcard{border:1px solid var(--hair);border-radius:16px;background:var(--surface);padding:18px;transition:.16s;cursor:pointer}
.candcard:hover{transform:translateY(-3px);box-shadow:0 12px 30px rgba(0,0,0,.08);border-color:var(--accent)}
.candcard .cc-head{display:flex;gap:12px;align-items:center;margin-bottom:13px}
.candcard .cc-ava{width:46px;height:46px;border-radius:14px;flex:none;background:var(--accent-soft);color:var(--accent-ink);display:flex;align-items:center;justify-content:center;font-weight:800;font-size:16px}
.candcard .cc-n{font-size:14.5px;font-weight:700;letter-spacing:-.01em}
.candcard .cc-u{font-size:12px;color:var(--muted);margin-top:2px}
.candcard .cc-fit{margin-left:auto;flex:none;font-size:13px;font-weight:800;color:var(--accent-ink);background:var(--accent-soft);padding:5px 10px;border-radius:9px}
.candcard .cc-skills{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:12px}
.candcard .cc-sk{font-size:11px;font-weight:500;padding:4px 9px;border-radius:13px;background:var(--hair2);color:var(--ink)}
.candcard .cc-sk.hit{background:var(--green-soft);color:var(--green-ink);font-weight:700}
.candcard .cc-foot{display:flex;align-items:center;gap:14px;padding-top:12px;border-top:1px solid var(--hair2);font-size:11.5px;color:var(--muted)}
.candcard .cc-foot span{display:flex;align-items:center;gap:5px}
.candcard .cc-foot .onb-icon{width:12px;height:12px}
.cc-open{margin-left:auto;font-size:11.5px;font-weight:700;color:var(--accent)}

/* ---------- placement (university) ---------- */
.place-band{display:grid;grid-template-columns:repeat(4,1fr);gap:14px;margin-bottom:18px}
@media(max-width:760px){.place-band{grid-template-columns:repeat(2,1fr)}}
.funnel-wrap{display:flex;flex-direction:column;gap:9px;margin-top:12px}
.funnel-b{display:flex;align-items:center;gap:12px}
.funnel-b .fb-n{width:110px;flex:none;font-size:13px}
.funnel-b .fb-t{flex:1;height:26px;background:var(--hair2);border-radius:7px;overflow:hidden}
.funnel-b .fb-t i{display:block;height:100%;border-radius:7px;display:flex;align-items:center;padding-left:10px;color:#fff;font-size:11.5px;font-weight:700}
.funnel-b .fb-p{width:44px;flex:none;text-align:right;font-size:12px;font-weight:700;color:var(--muted)}
.emp-row{display:flex;align-items:center;gap:12px;padding:12px 0;border-bottom:1px solid var(--hair2)}
.emp-row:last-child{border:none}
.emp-row .er-logo{width:36px;height:36px;border-radius:10px;flex:none;display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;font-size:14px}
.emp-row .er-b{flex:1;min-width:0}
.emp-row .er-n{font-size:13.5px;font-weight:600}
.emp-row .er-d{font-size:12px;color:var(--muted);margin-top:1px}
.emp-row .er-c{font-size:16px;font-weight:800;color:var(--accent-ink);flex:none}

/* ---------- simulations ---------- */
.sim-hero{position:relative;overflow:hidden;background:var(--accent);color:#fff;border-radius:20px;padding:24px 26px;margin-bottom:18px;display:flex;align-items:center;gap:24px;flex-wrap:wrap}
.sim-hero::before{content:"";position:absolute;right:-60px;top:-80px;width:240px;height:240px;border-radius:50%;background:rgba(255,255,255,.09)}
.sim-hero>*{position:relative;z-index:1}
.sim-hero .sh-b{flex:1;min-width:220px}
.sim-hero h2{font-size:21px;font-weight:800;letter-spacing:-.02em}
.sim-hero p{font-size:13.5px;opacity:.9;margin-top:5px;line-height:1.5}
.sim-hero .sh-stats{display:flex;gap:22px;flex-wrap:wrap;margin-top:14px}
.sim-hero .sh-s .v{font-size:19px;font-weight:800;letter-spacing:-.02em}
.sim-hero .sh-s .l{font-size:11px;opacity:.8;text-transform:uppercase;letter-spacing:.05em;margin-top:2px}

.sim-filters{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:16px}
.sim-filters .sf{padding:8px 15px;border-radius:20px;border:1.5px solid var(--hair);background:var(--surface);color:var(--muted);font-size:13px;font-weight:500;cursor:pointer;transition:.14s}
.sim-filters .sf:hover{border-color:var(--accent)}
.sim-filters .sf.on{background:var(--accent);border-color:var(--accent);color:#fff;font-weight:600}

.sims-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(340px,1fr));gap:16px}
.simcard2{position:relative;border:1px solid var(--hair);border-radius:18px;background:var(--surface);padding:20px;cursor:pointer;transition:.16s;display:flex;flex-direction:column;overflow:hidden}
.simcard2:hover{transform:translateY(-3px);box-shadow:0 14px 34px rgba(0,0,0,.09);border-color:var(--accent)}
.simcard2.done{border-color:var(--green);background:var(--green-soft)}
.simcard2.done:hover{border-color:var(--green)}
.simcard2 .s2-done{position:absolute;top:14px;right:14px;display:inline-flex;align-items:center;gap:5px;background:var(--green);color:#fff;font-size:10px;font-weight:700;padding:4px 9px;border-radius:20px;text-transform:uppercase;letter-spacing:.04em}
.simcard2 .s2-done .onb-icon{width:11px;height:11px;stroke-width:3.5}
.simcard2 .s2-head{display:flex;gap:12px;align-items:flex-start;margin-bottom:13px}
.simcard2 .s2-logo{width:44px;height:44px;border-radius:12px;flex:none;display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;font-size:18px}
.simcard2 .s2-tt{flex:1;min-width:0;padding-right:60px}
.simcard2 .s2-t{font-size:15.5px;font-weight:700;letter-spacing:-.015em;line-height:1.3}
.simcard2 .s2-co{font-size:12.5px;color:var(--muted);margin-top:3px}
.simcard2 .s2-meta{display:flex;flex-wrap:wrap;gap:7px;margin-bottom:12px}
.simcard2 .s2-pill{font-size:11.5px;font-weight:500;padding:4px 10px;border-radius:8px;background:var(--hair2);color:var(--ink);display:inline-flex;align-items:center;gap:5px;white-space:nowrap}
.simcard2 .s2-pill .onb-icon{width:12px;height:12px;color:var(--muted)}
.simcard2 .s2-brief{font-size:12.5px;color:var(--muted);line-height:1.5;margin-bottom:13px;flex:1;display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical;overflow:hidden}
.simcard2 .s2-tags{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:14px}
.simcard2 .s2-tag{font-size:11px;font-weight:500;padding:4px 10px;border-radius:14px;background:var(--accent-soft);color:var(--accent-ink)}
.simcard2 .s2-foot{display:flex;align-items:center;justify-content:space-between;gap:12px;padding-top:13px;border-top:1px solid var(--hair2)}
.simcard2 .s2-match{display:flex;align-items:center;gap:8px;flex:1}
.simcard2 .s2-bar{flex:1;max-width:80px;height:6px;background:var(--hair2);border-radius:3px;overflow:hidden}
.simcard2 .s2-bar i{display:block;height:100%;background:var(--accent);border-radius:3px}
.simcard2 .s2-mv{font-size:12.5px;font-weight:700;color:var(--accent-ink)}
.simcard2 .s2-xp{font-size:12.5px;font-weight:800;color:var(--accent)}

/* detail: workspace */
.sim-head{display:flex;gap:16px;align-items:flex-start;flex-wrap:wrap}
.sim-head .sd-logo{width:56px;height:56px;border-radius:15px;flex:none;display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;font-size:22px}
.sim-steps{display:flex;gap:0;margin:18px 0;align-items:center;flex-wrap:wrap}
.sim-stp{display:flex;align-items:center;gap:8px;font-size:12.5px;color:var(--muted)}
.sim-stp .n{width:24px;height:24px;border-radius:50%;border:2px solid var(--hair);display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:700;background:var(--surface);flex:none}
.sim-stp.on{color:var(--ink);font-weight:600}
.sim-stp.on .n{border-color:var(--accent);color:var(--accent-ink)}
.sim-stp.ok .n{background:var(--green);border-color:var(--green);color:#fff}
.sim-stp.ok .n .onb-icon{width:12px;height:12px;stroke-width:3.5}
.sim-line{width:26px;height:2px;background:var(--hair);margin:0 6px}
.sim-line.ok{background:var(--green)}

.rubric-row{display:flex;align-items:center;gap:12px;padding:10px 0;border-bottom:1px solid var(--hair2);font-size:13.5px}
.rubric-row:last-child{border:none}
.rubric-row .rb-n{flex:1}
.rubric-row .rb-bar{width:70px;height:6px;background:var(--hair2);border-radius:3px;overflow:hidden;flex:none}
.rubric-row .rb-bar i{display:block;height:100%;background:var(--accent);border-radius:3px}
.rubric-row .rb-w{font-size:12px;font-weight:700;color:var(--accent-ink);min-width:32px;text-align:right}

.answer-box{width:100%;min-height:170px;border:1.5px solid var(--hair);border-radius:12px;padding:13px;font-family:inherit;font-size:13.5px;line-height:1.6;outline:none;resize:vertical;background:var(--surface);color:var(--ink);transition:.14s}
.answer-box:focus{border-color:var(--accent);box-shadow:0 0 0 3px var(--accent-soft)}
.answer-meta{display:flex;align-items:center;gap:12px;margin-top:10px;font-size:11.5px;color:var(--muted)}
.answer-meta .ok{color:var(--green);font-weight:600}
.answer-meta .warn{color:var(--amber-ink);font-weight:600}

/* AI review after submit */
.ai-review{border:1.5px solid var(--accent);border-radius:16px;overflow:hidden;margin-bottom:16px}
.ai-review .ar-top{background:var(--accent);color:#fff;padding:16px 18px;display:flex;align-items:center;gap:11px}
.ai-review .ar-top .onb-icon{width:19px;height:19px}
.ai-review .ar-t{font-size:15px;font-weight:700;flex:1}
.ai-review .ar-score{font-size:22px;font-weight:800;letter-spacing:-.02em}
.ai-review .ar-body{padding:18px;background:var(--surface)}
.ai-score-row{display:flex;align-items:center;gap:12px;padding:9px 0;font-size:13px}
.ai-score-row .as-n{flex:1}
.ai-score-row .as-bar{width:110px;height:7px;background:var(--hair2);border-radius:4px;overflow:hidden;flex:none}
.ai-score-row .as-bar i{display:block;height:100%;border-radius:4px}
.ai-score-row .as-v{font-size:12.5px;font-weight:700;min-width:36px;text-align:right}
.ai-note{display:flex;gap:9px;align-items:flex-start;background:var(--bg);border-radius:11px;padding:12px 14px;margin-top:14px;font-size:12.5px;color:var(--muted);line-height:1.5}
.ai-note .onb-icon{width:14px;height:14px;color:var(--accent);flex:none;margin-top:2px}

/* ---------- languages: compact chips that expand into a level card ---------- */
.lang-grid{display:flex;flex-wrap:wrap;gap:9px}
.lang-chip{display:inline-flex;align-items:center;gap:8px;padding:10px 15px;border:1.5px solid var(--hair);border-radius:12px;background:var(--surface);color:var(--ink);font-size:13.5px;font-weight:500;cursor:pointer;transition:.16s}
.lang-chip:hover{border-color:var(--accent);background:var(--accent-soft)}
.lang-chip .lc-plus{width:16px;height:16px;border-radius:50%;border:1.5px solid var(--hair);display:flex;align-items:center;justify-content:center;color:var(--faint);flex:none;transition:.14s}
.lang-chip:hover .lc-plus{border-color:var(--accent);color:var(--accent)}
.lang-chip .lc-plus .onb-icon{width:9px;height:9px;stroke-width:3.5}

.lang-card{width:100%;border:1.5px solid var(--accent);background:var(--accent-soft);border-radius:14px;padding:12px 14px;animation:skIn .2s ease-out}
body.no-motion .lang-card{animation:none}
.lang-card .lc-head{display:flex;align-items:center;gap:10px}
.lang-card .lc-check{width:20px;height:20px;border-radius:6px;background:var(--accent);color:#fff;display:flex;align-items:center;justify-content:center;flex:none}
.lang-card .lc-check .onb-icon{width:12px;height:12px;stroke-width:3.5}
.lang-card .lc-name{font-size:13.5px;font-weight:700;color:var(--accent-ink);flex:1;min-width:0}
.lang-card .lc-x{width:24px;height:24px;border-radius:7px;color:var(--accent-ink);opacity:.5;display:flex;align-items:center;justify-content:center;font-size:12px;flex:none}
.lang-card .lc-x:hover{opacity:1;background:rgba(0,0,0,.07)}

/* level rail: plain-language names first, CEFR code as a small footnote */
.lang-rail{display:flex;gap:5px;margin-top:11px}
.lang-lvl{flex:1;cursor:pointer;text-align:center;transition:.14s;min-width:0}
.lang-lvl .ll-bar{height:6px;border-radius:3px;background:rgba(255,255,255,.6);transition:.18s}
body.dark .lang-lvl .ll-bar{background:rgba(255,255,255,.14)}
.lang-lvl.filled .ll-bar{background:var(--accent)}
.lang-lvl:hover .ll-bar{background:var(--accent);opacity:.55}
.lang-lvl .ll-t{font-size:10px;font-weight:600;color:var(--muted);margin-top:6px;line-height:1.25;transition:.14s}
.lang-lvl .ll-code{font-size:9px;font-weight:700;color:var(--faint);letter-spacing:.04em;margin-top:2px}
.lang-lvl.active .ll-t{color:var(--accent-ink);font-weight:700}
.lang-lvl.active .ll-code{color:var(--accent)}
.lang-lvl:hover .ll-t{color:var(--accent-ink)}
.lang-explain{display:flex;gap:8px;align-items:flex-start;background:var(--surface);border-radius:10px;padding:10px 12px;margin-top:11px;font-size:12px;color:var(--muted);line-height:1.45}
.lang-explain .onb-icon{width:13px;height:13px;color:var(--accent);flex:none;margin-top:2px}
.lang-explain b{color:var(--ink);font-weight:600}

/* "what do these levels mean?" disclosure */
.lvl-help{margin-top:10px}
.lvl-help summary{font-size:12px;color:var(--accent);cursor:pointer;font-weight:600;list-style:none;display:inline-flex;align-items:center;gap:6px}
.lvl-help summary::-webkit-details-marker{display:none}
.lvl-help summary .onb-icon{width:13px;height:13px;transition:.18s}
.lvl-help[open] summary .onb-icon{transform:rotate(90deg)}
.lvl-help .lh-body{margin-top:10px;background:var(--bg);border-radius:11px;padding:12px 14px}
.lvl-help .lh-row{display:flex;gap:11px;padding:7px 0;font-size:12.5px;line-height:1.45;border-bottom:1px solid var(--hair2)}
.lvl-help .lh-row:last-child{border:none}
.lvl-help .lh-code{font-size:10.5px;font-weight:700;color:var(--accent-ink);background:var(--accent-soft);padding:3px 8px;border-radius:6px;height:fit-content;flex:none;min-width:38px;text-align:center}
.lvl-help .lh-n{font-weight:600;color:var(--ink)}
.lvl-help .lh-d{color:var(--muted);margin-top:1px}

@media(max-width:560px){.lang-lvl .ll-t{font-size:9.5px}.lang-lvl .ll-code{font-size:9px}}

/* ---------- skills with proficiency level ---------- */
.skill-grid{display:flex;flex-wrap:wrap;gap:9px}
/* unselected: a plain chip */
.skill-chip{display:inline-flex;align-items:center;gap:8px;padding:10px 15px;border:1.5px solid var(--hair);border-radius:12px;background:var(--surface);color:var(--ink);font-size:13.5px;font-weight:500;cursor:pointer;transition:.16s}
.skill-chip:hover{border-color:var(--accent);background:var(--accent-soft)}
.skill-chip .sk-plus{width:16px;height:16px;border-radius:50%;border:1.5px solid var(--hair);display:flex;align-items:center;justify-content:center;color:var(--faint);flex:none;transition:.14s}
.skill-chip:hover .sk-plus{border-color:var(--accent);color:var(--accent)}
.skill-chip .sk-plus .onb-icon{width:9px;height:9px;stroke-width:3.5}

/* selected: expands into a card with a level picker */
.skill-card{width:100%;border:1.5px solid var(--accent);background:var(--accent-soft);border-radius:14px;padding:12px 14px;animation:skIn .2s ease-out}
@keyframes skIn{from{opacity:0;transform:scale(.97)}to{opacity:1;transform:none}}
body.no-motion .skill-card{animation:none}
.skill-card .sk-head{display:flex;align-items:center;gap:10px}
.skill-card .sk-check{width:20px;height:20px;border-radius:6px;background:var(--accent);color:#fff;display:flex;align-items:center;justify-content:center;flex:none}
.skill-card .sk-check .onb-icon{width:12px;height:12px;stroke-width:3.5}
.skill-card .sk-name{font-size:13.5px;font-weight:700;color:var(--accent-ink);flex:1;min-width:0}
.skill-card .sk-x{width:24px;height:24px;border-radius:7px;color:var(--accent-ink);opacity:.5;display:flex;align-items:center;justify-content:center;font-size:12px;flex:none}
.skill-card .sk-x:hover{opacity:1;background:rgba(0,0,0,.07)}

/* level bar: four segments, filled up to the chosen level */
.lvl-pick{display:flex;gap:5px;margin-top:11px}
.lvl-seg{flex:1;cursor:pointer;text-align:center;transition:.14s}
.lvl-seg .ls-bar{height:6px;border-radius:3px;background:rgba(255,255,255,.6);transition:.18s}
body.dark .lvl-seg .ls-bar{background:rgba(255,255,255,.14)}
.lvl-seg.filled .ls-bar{background:var(--accent)}
.lvl-seg .ls-t{font-size:10.5px;font-weight:600;color:var(--muted);margin-top:6px;transition:.14s;white-space:nowrap}
.lvl-seg.active .ls-t{color:var(--accent-ink);font-weight:700}
.lvl-seg:hover .ls-bar{background:var(--accent);opacity:.55}
.lvl-seg:hover .ls-t{color:var(--accent-ink)}
.lvl-hint{font-size:11px;color:var(--muted);margin-top:9px;display:flex;align-items:center;gap:6px;line-height:1.4}
.lvl-hint .onb-icon{width:12px;height:12px;color:var(--accent);flex:none}

/* summary strip */
.sk-summary{display:flex;align-items:center;gap:10px;background:var(--bg);border-radius:11px;padding:10px 13px;margin-top:12px;font-size:12.5px;color:var(--muted)}
.sk-summary .onb-icon{width:14px;height:14px;color:var(--accent);flex:none}
.sk-summary b{color:var(--ink);font-weight:600}

@media(max-width:560px){.skill-card{padding:11px}.lvl-seg .ls-t{font-size:9.5px}}

/* ---------- personal trajectory ---------- */
.tj-hero{position:relative;overflow:hidden;background:var(--accent);color:#fff;border-radius:22px;padding:26px 28px;margin-bottom:18px;box-shadow:0 14px 40px rgba(63,91,246,.26)}
.tj-hero::before{content:"";position:absolute;right:-70px;top:-90px;width:270px;height:270px;border-radius:50%;background:rgba(255,255,255,.09)}
.tj-hero::after{content:"";position:absolute;right:90px;bottom:-120px;width:190px;height:190px;border-radius:50%;background:rgba(255,255,255,.06)}
.tj-hero>*{position:relative;z-index:1}
.tj-top{display:flex;align-items:center;gap:22px;flex-wrap:wrap}
.tj-ring{position:relative;width:96px;height:96px;flex:none}
.tj-ring svg{transform:rotate(-90deg)}
.tj-ring .r-v{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center}
.tj-ring .r-n{font-size:21px;font-weight:800;letter-spacing:-.02em;line-height:1}
.tj-ring .r-l{font-size:9px;opacity:.85;text-transform:uppercase;letter-spacing:.06em;margin-top:3px}
.tj-info{flex:1;min-width:220px}
.tj-info h2{font-size:22px;font-weight:800;letter-spacing:-.025em;line-height:1.15}
.tj-info p{font-size:13.5px;opacity:.9;margin-top:5px;line-height:1.5}
.tj-bars{display:flex;gap:20px;margin-top:16px;flex-wrap:wrap}
.tj-bar{min-width:120px}
.tj-bar .b-l{font-size:11px;opacity:.8;text-transform:uppercase;letter-spacing:.05em}
.tj-bar .b-v{font-size:17px;font-weight:800;letter-spacing:-.02em;margin-top:3px}
.tj-cta{flex:none}
.tj-cta .btn{background:#fff;color:var(--accent);height:42px;padding:0 20px;font-weight:700;width:auto}
.tj-cta .btn:hover{transform:translateY(-1px);box-shadow:0 8px 22px rgba(0,0,0,.2)}
@media(max-width:900px){.tj-ring{display:none}}

/* XP bar */
.xp-track{height:9px;background:rgba(255,255,255,.22);border-radius:5px;overflow:hidden;margin-top:14px}
.xp-track i{display:block;height:100%;background:#fff;border-radius:5px;transition:width .5s cubic-bezier(.4,0,.2,1)}

/* the road */
.road{position:relative;padding-left:6px}
.tj-step{position:relative;display:flex;gap:18px;padding-bottom:14px;cursor:pointer}
.tj-step:last-child{padding-bottom:0}
/* connector */
.tj-step::before{content:"";position:absolute;left:23px;top:52px;bottom:-2px;width:3px;background:var(--hair);border-radius:2px}
.tj-step:last-child::before{display:none}
.tj-step.done::before{background:var(--green)}
.tj-node{width:48px;height:48px;border-radius:16px;border:2px solid var(--hair);background:var(--surface);display:flex;align-items:center;justify-content:center;flex:none;z-index:1;transition:.18s;color:var(--muted)}
.tj-node .onb-icon{width:21px;height:21px}
.tj-step.done .tj-node{background:var(--green);border-color:var(--green);color:#fff}
.tj-step.cur .tj-node{border-color:var(--accent);color:var(--accent);box-shadow:0 0 0 5px var(--accent-soft)}
.tj-step.locked .tj-node{background:var(--hair2);border-color:var(--hair2);color:var(--faint)}
.tj-step:not(.locked):hover .tj-node{transform:scale(1.05)}

.tj-card{flex:1;min-width:0;border:1.5px solid var(--hair);border-radius:16px;background:var(--surface);padding:16px 18px;transition:.16s}
.tj-step.cur .tj-card{border-color:var(--accent);box-shadow:0 8px 26px rgba(63,91,246,.12)}
.tj-step.locked .tj-card{background:var(--bg);border-style:dashed;opacity:.75}
.tj-step:not(.locked):hover .tj-card{border-color:var(--accent)}
.tj-h{display:flex;align-items:center;gap:10px;flex-wrap:wrap}
.tj-t{font-size:15px;font-weight:700;letter-spacing:-.015em}
.tj-step.done .tj-t{color:var(--muted)}
.tj-badge{font-size:10px;font-weight:700;letter-spacing:.04em;text-transform:uppercase;padding:3px 9px;border-radius:20px}
.tj-badge.done{background:var(--green-soft);color:var(--green-ink)}
.tj-badge.cur{background:var(--accent);color:#fff}
.tj-badge.lock{background:var(--hair2);color:var(--faint)}
.tj-d{font-size:12.5px;color:var(--muted);margin-top:5px;line-height:1.5}
.tj-meta{display:flex;gap:14px;flex-wrap:wrap;margin-top:11px;font-size:11.5px;color:var(--muted)}
.tj-meta span{display:flex;align-items:center;gap:5px}
.tj-meta .onb-icon{width:12px;height:12px}
.tj-meta .xp{color:var(--accent-ink);font-weight:700}
.tj-why{display:flex;gap:8px;align-items:flex-start;background:var(--bg);border-radius:10px;padding:9px 11px;margin-top:12px;font-size:12px;color:var(--muted);line-height:1.45}
.tj-why .onb-icon{width:13px;height:13px;color:var(--accent);flex:none;margin-top:2px}
.tj-act{display:flex;align-items:center;gap:10px;margin-top:13px}
.tj-act .btn{width:auto;height:34px;font-size:12.5px;padding:0 14px}
.tj-progress{flex:1;max-width:160px}
.tj-progress .pt{height:6px;background:var(--hair2);border-radius:3px;overflow:hidden}
.tj-progress .pt i{display:block;height:100%;background:var(--accent);border-radius:3px}
.tj-progress .pl{font-size:10.5px;color:var(--faint);margin-top:4px}

/* milestones */
.tj-flag{display:flex;align-items:center;gap:11px;margin:6px 0 20px 66px;padding:11px 15px;border-radius:12px;background:var(--amber-soft);color:var(--amber-ink);font-size:12.5px;font-weight:600}
.tj-flag .onb-icon{width:15px;height:15px}

/* ---------- profile page ---------- */
/* cover + overlapping avatar, like a modern social profile */
.pf-hero{position:relative;background:var(--surface);border:1px solid var(--hair);border-radius:22px;margin-bottom:16px;overflow:hidden}
.pf-cover{height:118px;position:relative;background:var(--accent);overflow:hidden}
.pf-cover::before{content:"";position:absolute;right:-60px;top:-90px;width:260px;height:260px;border-radius:50%;background:rgba(255,255,255,.10)}
.pf-cover::after{content:"";position:absolute;right:110px;bottom:-130px;width:200px;height:200px;border-radius:50%;background:rgba(255,255,255,.07)}
.pf-status-pill{position:absolute;right:18px;top:18px;z-index:2;display:inline-flex;align-items:center;gap:7px;background:rgba(255,255,255,.18);border:1px solid rgba(255,255,255,.25);color:#fff;font-size:12px;font-weight:600;padding:6px 13px;border-radius:20px;backdrop-filter:blur(6px)}
.pf-body{padding:0 26px 24px;display:flex;gap:22px;align-items:flex-start;flex-wrap:wrap}
.pf-ava{width:118px;height:118px;border-radius:30px;flex:none;position:relative;overflow:hidden;margin-top:-46px;background:var(--accent-soft);color:var(--accent-ink);display:flex;align-items:center;justify-content:center;border:5px solid var(--surface);box-shadow:0 10px 30px rgba(0,0,0,.14);z-index:2}
.pf-ava img{width:100%;height:100%;object-fit:cover}
.pf-ava .onb-icon{width:50px;height:50px}
.pf-ava .pf-cam{position:absolute;left:0;right:0;bottom:0;background:rgba(0,0,0,.62);color:#fff;font-size:10px;font-weight:600;text-align:center;padding:6px 0;cursor:pointer;opacity:0;transition:.15s}
.pf-ava:hover .pf-cam{opacity:1}
.pf-id{flex:1;min-width:220px;padding-top:16px}
.pf-name{font-size:25px;font-weight:800;letter-spacing:-.03em;display:flex;align-items:center;gap:9px;flex-wrap:wrap;line-height:1.15}
.pf-role{font-size:14.5px;color:var(--muted);margin-top:4px;font-weight:500}
.pf-tags{display:flex;gap:7px;flex-wrap:wrap;margin-top:13px}
.pf-tag{display:inline-flex;align-items:center;gap:6px;background:var(--hair2);color:var(--ink);font-size:12px;font-weight:500;padding:6px 12px;border-radius:20px}
.pf-tag .onb-icon{width:13px;height:13px;color:var(--muted)}
.pf-side{flex:none;padding-top:16px;display:flex;gap:8px;flex-wrap:wrap}
.pf-verified{display:inline-flex;align-items:center;gap:5px;font-size:11px;font-weight:700;color:var(--green-ink);background:var(--green-soft);padding:4px 10px;border-radius:20px;white-space:nowrap}
.pf-verified .onb-icon{width:12px;height:12px}
.pf-unverified{color:var(--amber-ink);background:var(--amber-soft);cursor:pointer}
@media(max-width:700px){.pf-body{padding:0 18px 20px}.pf-ava{width:96px;height:96px;margin-top:-38px}.pf-side{width:100%}}

/* public link bar */
.pf-link{display:flex;align-items:center;gap:10px;background:var(--bg);border:1px dashed var(--hair);border-radius:12px;padding:10px 12px;margin-top:16px}
.pf-link .pl-ic{color:var(--muted);display:flex}
.pf-link .pl-ic .onb-icon{width:15px;height:15px}
.pf-link code{flex:1;font-size:12.5px;color:var(--muted);overflow:hidden;text-overflow:ellipsis;white-space:nowrap;font-family:ui-monospace,monospace}
.pf-link button{font-size:12px;font-weight:600;color:var(--accent);padding:5px 10px;border-radius:7px;flex:none}
.pf-link button:hover{background:var(--accent-soft)}

/* completeness */
.pf-meter{display:flex;align-items:center;gap:18px;margin-bottom:14px}
.pf-meter .pm-ring{position:relative;width:74px;height:74px;flex:none}
.pf-meter .pm-ring svg{transform:rotate(-90deg)}
.pf-meter .pm-ring span{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;font-size:17px;font-weight:800;letter-spacing:-.02em;color:var(--accent-ink)}
.pf-meter .pm-b{flex:1;min-width:0}
.pf-meter .pm-t{font-size:14px;font-weight:600}
.pf-meter .pm-d{font-size:12.5px;color:var(--muted);margin-top:3px;line-height:1.45}
.check-list{display:flex;flex-direction:column;gap:2px}
.check-item{display:flex;align-items:center;gap:11px;padding:9px 10px;border-radius:9px;font-size:13.5px;cursor:pointer;transition:.14s}
.check-item:hover{background:var(--hair2)}
.check-item .ci-box{width:19px;height:19px;border-radius:6px;border:2px solid var(--hair);display:flex;align-items:center;justify-content:center;color:transparent;flex:none;transition:.14s}
.check-item.done .ci-box{background:var(--green);border-color:var(--green);color:#fff}
.check-item.done .ci-box .onb-icon{width:12px;height:12px;stroke-width:3}
.check-item.done .ci-t{color:var(--muted)}
.check-item .ci-t{flex:1}
.check-item .ci-go{font-size:11.5px;font-weight:600;color:var(--accent);opacity:0;transition:.14s}
.check-item:hover .ci-go{opacity:1}

/* activity tiles */
.act-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:12px}
@media(max-width:760px){.act-grid{grid-template-columns:repeat(2,1fr)}}
.act{position:relative;background:var(--bg);border:1px solid var(--hair);border-radius:14px;padding:15px;overflow:hidden;transition:.14s}
.act:hover{border-color:var(--accent);transform:translateY(-2px)}
.act .a-ic{width:30px;height:30px;border-radius:9px;display:flex;align-items:center;justify-content:center;margin-bottom:10px}
.act .a-ic .onb-icon{width:15px;height:15px}
.act .a-v{font-size:22px;font-weight:800;letter-spacing:-.02em;line-height:1}
.act .a-l{font-size:11.5px;color:var(--muted);margin-top:4px}

/* fields */
.pf-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px}
@media(max-width:700px){.pf-grid{grid-template-columns:1fr}}
.pf-field label{display:flex;align-items:center;gap:6px;font-size:12px;font-weight:500;color:var(--muted);margin-bottom:6px}
.pf-field label .onb-icon{width:13px;height:13px}
/* profile inputs must match the platform's field styling, not the browser default */
.pf-field input,.pf-field select,.pf-field textarea{
  width:100%;height:46px;border:1.5px solid var(--hair);border-radius:12px;padding:0 14px;
  font-size:14px;font-family:inherit;color:var(--ink);outline:none;background:var(--surface);
  transition:.15s;box-sizing:border-box;-webkit-appearance:none;appearance:none;
}
.pf-field input::placeholder{color:var(--faint)}
.pf-field input:hover:not(:disabled){border-color:var(--hair)}
.pf-field input:focus,.pf-field select:focus{border-color:var(--accent);box-shadow:0 0 0 3px var(--accent-soft)}
/* date input: kill the mono font and align the native picker icon */
.pf-field input[type=date]{font-family:inherit;font-variant-numeric:normal;padding-right:12px}
.pf-field input[type=date]::-webkit-calendar-picker-indicator{opacity:.45;cursor:pointer;filter:var(--cal-filter,none)}
.pf-field input[type=date]::-webkit-calendar-picker-indicator:hover{opacity:.85}
body.dark .pf-field input[type=date]::-webkit-calendar-picker-indicator{filter:invert(1)}
/* locked field reads as intentional, not broken */
.pf-field input:disabled{background:var(--bg);border-style:dashed;color:var(--muted);cursor:default;-webkit-text-fill-color:var(--muted);opacity:1}
.pf-field.locked label{color:var(--faint)}

/* section sub-headings inside a panel */
.pf-sub{font-size:11px;font-weight:700;letter-spacing:.07em;text-transform:uppercase;color:var(--faint);margin:22px 0 12px;padding-bottom:8px;border-bottom:1px solid var(--hair2)}
.pf-sub:first-of-type{margin-top:18px}
.pf-note{font-size:11.5px;color:var(--faint);margin-top:6px}
.pf-field .pf-lock{margin-left:auto;display:inline-flex;align-items:center;gap:4px;font-size:10px;color:var(--faint)}
.pf-field .pf-lock .onb-icon{width:11px;height:11px}

.saved-hint{display:inline-flex;align-items:center;gap:4px;font-size:11px;font-weight:600;color:var(--green-ink);background:var(--green-soft);padding:3px 9px;border-radius:20px;margin-left:8px;opacity:0;transform:translateY(-2px);transition:.2s}
.saved-hint.on{opacity:1;transform:none}
.saved-hint .onb-icon{width:11px;height:11px;stroke-width:3}

/* links */
.link-row{display:flex;align-items:center;gap:11px;padding:11px 0;border-bottom:1px solid var(--hair2)}
.link-row:last-child{border:none}
.link-row .lr-ic{width:36px;height:36px;border-radius:11px;background:var(--accent-soft);color:var(--accent-ink);display:flex;align-items:center;justify-content:center;flex:none}
.link-row .lr-ic .onb-icon{width:16px;height:16px}
.link-row input{flex:1;height:38px}
.link-row .lr-x{width:32px;height:32px;border-radius:8px;color:var(--muted);display:flex;align-items:center;justify-content:center;flex:none}
.link-row .lr-x:hover{background:var(--red-soft);color:var(--red)}
.link-suggest{display:flex;gap:7px;flex-wrap:wrap;margin-top:12px}
.link-suggest button{display:inline-flex;align-items:center;gap:6px;font-size:12px;font-weight:500;padding:7px 12px;border-radius:20px;border:1.5px dashed var(--hair);color:var(--muted);background:var(--surface)}
.link-suggest button:hover{border-color:var(--accent);color:var(--accent-ink);border-style:solid}
.link-suggest .onb-icon{width:13px;height:13px}

/* status picker */
.status-pick{display:flex;gap:9px;flex-wrap:wrap}
.status-opt{flex:1;min-width:150px;border:1.5px solid var(--hair);border-radius:13px;padding:14px;cursor:pointer;transition:.14s;background:var(--surface)}
.status-opt:hover{border-color:var(--accent)}
.status-opt.on{border-color:var(--accent);background:var(--accent-soft)}
.status-opt .so-h{display:flex;align-items:center;gap:8px;font-size:13.5px;font-weight:600}
.status-opt.on .so-h{color:var(--accent-ink)}
.status-opt .so-d{font-size:11.5px;color:var(--muted);margin-top:5px;line-height:1.4}
.status-dot{width:8px;height:8px;border-radius:50%;flex:none}

/* skills & languages chips */
.pf-chips{display:flex;gap:7px;flex-wrap:wrap}
.pf-chip{display:inline-flex;align-items:center;gap:7px;background:var(--accent-soft);color:var(--accent-ink);font-size:12.5px;font-weight:600;padding:6px 12px;border-radius:9px}
.pf-chip .lvl{font-size:10.5px;font-weight:700;opacity:.7;text-transform:uppercase;letter-spacing:.03em}
.pf-chip.plain{background:var(--hair2);color:var(--ink)}

/* application history */
.app-row{display:flex;align-items:center;gap:12px;padding:12px 0;border-bottom:1px solid var(--hair2)}
.app-row:last-child{border:none}
.app-row .ar-logo{width:36px;height:36px;border-radius:10px;flex:none;display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;font-size:14px}
.app-row .ar-b{flex:1;min-width:0}
.app-row .ar-t{font-size:13.5px;font-weight:600}
.app-row .ar-d{font-size:12px;color:var(--muted);margin-top:1px}
.app-row .ar-s{font-size:11px;font-weight:700;padding:4px 10px;border-radius:20px;background:var(--blue-soft);color:var(--blue-ink);flex:none}

/* ---------- settings page ---------- */
.set-nav{display:flex;gap:7px;flex-wrap:wrap;margin-bottom:18px}
.set-nav button{padding:8px 15px;border-radius:20px;border:1.5px solid var(--hair);background:var(--surface);color:var(--muted);font-size:13px;font-weight:500;transition:.14s}
.set-nav button:hover{border-color:var(--accent)}
.set-nav button.on{background:var(--accent);border-color:var(--accent);color:#fff;font-weight:600}
.set-row{display:flex;align-items:center;gap:16px;padding:14px 0;border-bottom:1px solid var(--hair2)}
.set-row:last-child{border-bottom:none}
.set-row .st{font-size:14px;font-weight:600;letter-spacing:-.01em;display:flex;align-items:center;gap:8px}
.set-row .st .onb-icon{width:15px;height:15px;color:var(--muted)}
.set-row .sd{font-size:12.5px;color:var(--muted);margin-top:3px;line-height:1.45;max-width:520px}
.set-row .set-ctl{margin-left:auto;flex:none;display:flex;align-items:center;gap:8px}
.set-warn{font-size:11.5px;color:var(--amber-ink);background:var(--amber-soft);padding:3px 9px;border-radius:20px;font-weight:600;white-space:nowrap}
/* segmented control */
.seg-ctl{display:flex;border:1.5px solid var(--hair);border-radius:10px;overflow:hidden}
.seg-ctl button{padding:7px 13px;font-size:12.5px;font-weight:500;background:var(--surface);color:var(--muted);white-space:nowrap;transition:.14s}
.seg-ctl button:hover{color:var(--ink)}
.seg-ctl button.on{background:var(--accent);color:#fff;font-weight:600}
/* swatches */
.sw-row{display:flex;gap:8px}
.sw{width:30px;height:30px;border-radius:9px;border:2px solid transparent;cursor:pointer;position:relative;transition:.14s}
.sw:hover{transform:scale(1.08)}
.sw.on{border-color:var(--ink)}
.sw.on::after{content:"";position:absolute;inset:0;display:flex;align-items:center;justify-content:center;background:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='14' height='14' viewBox='0 0 24 24' fill='none' stroke='white' stroke-width='3.5' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpath d='M20 6L9 17l-5-5'/%3E%3C/svg%3E") center no-repeat}
/* range */
.set-range{display:flex;align-items:center;gap:11px}
.set-range input[type=range]{width:130px;accent-color:var(--accent)}
.set-range .rv{font-size:12.5px;font-weight:700;color:var(--accent-ink);min-width:44px;text-align:right}
/* danger zone */
.danger{border-color:var(--red)!important}
.danger h3{color:var(--red)}
.btn-danger{background:var(--red);color:#fff}
.btn-danger:hover{filter:brightness(.92)}
.storage-bar{height:8px;background:var(--hair2);border-radius:4px;overflow:hidden;margin:10px 0 6px}
.storage-bar i{display:block;height:100%;background:var(--accent);border-radius:4px}

/* ---------- role accent theming ---------- */
/* draws the eye to the role cards when "Начать" is pressed */
@keyframes lp-ring{0%,100%{box-shadow:none}30%,70%{box-shadow:0 0 0 3px var(--blue-soft)}}
.lp-pulse .lp-card{animation:lp-ring 1.5s ease}
@media(prefers-reduced-motion:reduce){.lp-pulse .lp-card{animation:none}}

/* ============================================================
   Changellenge-flavoured light business skin
   ============================================================ */
.cl-hero2{position:relative;overflow:hidden;background:linear-gradient(135deg,#EEF0FF 0%,#F5F3FF 50%,#FDF0F7 100%);padding:80px 24px 64px}
body.yy.dark .cl-hero2{background:linear-gradient(135deg,#0E1330 0%,#161033 50%,#2A1030 100%)}
.cl-hero-canvas{position:absolute;inset:0;width:100%;height:100%;z-index:0;pointer-events:none}
/* floating blurred orbs = depth */
.cl-orb{position:absolute;border-radius:50%;filter:blur(60px);opacity:.55;z-index:0;pointer-events:none}
.cl-orb-1{width:380px;height:380px;background:#7B5CFF;top:-120px;left:-80px;animation:cl-float 18s ease-in-out infinite}
.cl-orb-2{width:320px;height:320px;background:#10B981;bottom:-120px;right:-60px;animation:cl-float 22s ease-in-out infinite reverse}
.cl-orb-3{width:280px;height:280px;background:#EC4899;top:40%;right:20%;opacity:.35;animation:cl-float 26s ease-in-out infinite}
body.yy.dark .cl-orb{opacity:.4}
@keyframes cl-float{0%,100%{transform:translate(0,0) scale(1)}33%{transform:translate(40px,-30px) scale(1.08)}66%{transform:translate(-30px,20px) scale(.95)}}
@media(prefers-reduced-motion:reduce){.cl-orb{animation:none}}
.cl-hero2-inner{position:relative;z-index:2;max-width:1100px;margin:0 auto;text-align:center;display:flex;flex-direction:column;align-items:center}

/* ---- MEGA TYPOGRAPHY hero ---- */
.cl-mega{font-family:var(--disp);font-weight:800;font-size:clamp(64px,13vw,180px);line-height:.9;letter-spacing:-.05em;color:var(--yy-dark);display:flex;align-items:center;gap:.06em;margin:10px 0;will-change:transform}
.cl-mega-word{display:inline-flex}
/* letters cascade in */
.cl-ml{font-style:normal;display:inline-block;opacity:0;transform:translateY(.35em) rotate(4deg);animation:cl-ml-in .6s cubic-bezier(.2,.8,.2,1) forwards;animation-delay:calc(var(--li)*70ms)}
@keyframes cl-ml-in{to{opacity:1;transform:none}}
/* Hero shimmers with a moving gradient */
/* gradient + clip must live on each letter: a parent-level clip dies as soon as
   the child letters get their own composited layers from the entrance animation */
.cl-mega-hero .cl-ml{background:linear-gradient(100deg,var(--yy-dark) 0%,var(--yy-dark) 35%,var(--yy) 50%,var(--yy-pink) 58%,var(--yy-dark) 72%,var(--yy-dark) 100%);background-size:600% 100%;background-position:calc(var(--li)*-40%) 0;-webkit-background-clip:text;background-clip:text;color:transparent;-webkit-text-fill-color:transparent;animation:cl-ml-in .6s cubic-bezier(.2,.8,.2,1) forwards,cl-shimmer 5s ease-in-out infinite 1.6s;animation-delay:calc(var(--li)*70ms),1.6s}
body.yy.dark .cl-mega-hero .cl-ml{background-image:linear-gradient(100deg,#F2F3F8 0%,#F2F3F8 35%,#8FA0FF 50%,#F472B6 58%,#F2F3F8 72%,#F2F3F8 100%)}
@keyframes cl-shimmer{0%,100%{background-position:0% 0}50%{background-position:100% 0}}
@media(prefers-reduced-motion:reduce){.cl-ml{animation:none;opacity:1;transform:none}.cl-mega-hero{animation:none}}
.cl-mega-arrow{font-family:var(--mono);color:var(--yy);font-size:.5em;letter-spacing:-.08em;animation:cl-arrow 2.2s ease-in-out infinite}
@keyframes cl-arrow{0%,100%{transform:translateX(0);opacity:.65}50%{transform:translateX(.12em);opacity:1}}
@media(prefers-reduced-motion:reduce){.cl-mega-arrow{animation:none}}

/* ---- interactive journey map ---- */
.cl-journey{position:relative;width:100%;max-width:900px;margin:24px auto 44px;padding:36px 0}
.cl-journey-svg{width:100%;height:160px;display:block;overflow:visible}
.cl-jline{stroke:var(--yy);stroke-width:3;stroke-linecap:round;stroke-dasharray:1600;stroke-dashoffset:1600;opacity:.35;filter:drop-shadow(0 2px 8px rgba(123,92,255,.3))}
.cl-jline.drawn{animation:cl-draw 2.4s cubic-bezier(.4,0,.2,1) forwards}
@keyframes cl-draw{to{stroke-dashoffset:0}}
.cl-jrunner{fill:var(--yy);filter:drop-shadow(0 0 10px var(--yy))}
.cl-jtrail{fill:var(--yy);opacity:.18;filter:blur(6px)}
.cl-journey-note{margin-top:20px;font-size:13.5px;color:var(--muted);max-width:560px;margin-left:auto;margin-right:auto;line-height:1.5}
.cl-journey-note{background:var(--yy-soft);color:var(--accent-ink);padding:10px 18px;border-radius:100px;display:inline-block}
.cl-journey-nodes{position:absolute;left:0;right:0;top:36px;bottom:36px;pointer-events:none}
.cl-jnode{position:absolute;transform:translate(-50%,-50%);pointer-events:auto;background:none;border:none;cursor:pointer;transition:opacity .5s;opacity:0;animation:cl-node-in .5s forwards}
.cl-jdot{display:block;width:18px;height:18px;border-radius:50%;background:var(--nc);box-shadow:0 0 0 4px color-mix(in oklab,var(--nc) 25%,transparent),0 4px 12px color-mix(in oklab,var(--nc) 40%,transparent);transition:transform .2s}
/* подпись выносится от линии: вверх для «гребней», вниз для «впадин» — текст никогда не ложится на кривую */
.cl-jlabel{position:absolute;left:50%;transform:translateX(-50%);width:130px;display:flex;flex-direction:column;align-items:center;gap:4px;text-align:center;pointer-events:none}
.cl-jnode.up .cl-jlabel{bottom:calc(50% + 18px)}
.cl-jnode.down .cl-jlabel{top:calc(50% + 18px)}
.cl-jnode.up .cl-jlabel{flex-direction:column-reverse}
.cl-jnode:nth-child(1){animation-delay:.6s}.cl-jnode:nth-child(2){animation-delay:1s}.cl-jnode:nth-child(3){animation-delay:1.4s}.cl-jnode:nth-child(4){animation-delay:1.8s}.cl-jnode:nth-child(5){animation-delay:2.2s}
@keyframes cl-node-in{from{opacity:0}to{opacity:1}}
.cl-jnode:hover .cl-jdot{transform:scale(1.35)}
.cl-jnode b{font-family:var(--disp);font-weight:800;font-size:14px;color:var(--yy-dark)}
.cl-jnode em{font-style:normal;font-size:11px;color:var(--muted);line-height:1.35}
@media(max-width:760px){
  .cl-journey{padding:44px 0}
  .cl-journey-svg{height:110px}
  .cl-jlabel{width:88px}
  .cl-jnode b{font-size:11px}
  .cl-jnode em{display:none}
  .cl-jnode.up .cl-jlabel{bottom:calc(50% + 15px)}
  .cl-jnode.down .cl-jlabel{top:calc(50% + 15px)}
}

.cl-hero2-inner{max-width:1100px;margin:0 auto;text-align:center;display:flex;flex-direction:column;align-items:center}
.cl-badge{display:inline-block;font-size:12px;font-weight:600;letter-spacing:.04em;text-transform:uppercase;color:var(--yy);background:#fff;border:1px solid var(--hair);padding:8px 16px;border-radius:100px;margin-bottom:24px}
.cl-h1{font-family:var(--disp);font-weight:800;font-size:clamp(34px,5.5vw,64px);line-height:1.03;letter-spacing:-.03em;color:var(--yy-dark);max-width:16ch}
.cl-mark{color:var(--yy)}
.cl-lead{font-size:clamp(15px,1.8vw,19px);color:var(--muted);line-height:1.55;max-width:600px;margin:22px auto 0}
.cl-hero-stats{display:flex;gap:44px;justify-content:center;flex-wrap:wrap;margin-top:34px}
.cl-hstat b{display:block;font-family:var(--disp);font-weight:800;font-size:34px;color:var(--yy-dark);letter-spacing:-.02em;line-height:1}
.cl-hstat span{font-size:13px;color:var(--muted);margin-top:6px;display:block}
/* role cards — a centered row directly under the hero */
.cl-roles{display:grid;grid-template-columns:repeat(3,1fr);gap:18px;width:100%;max-width:1080px;margin:44px auto 0}
.cl-rolecard{position:relative;overflow:hidden;display:flex;flex-direction:column;gap:12px;background:#fff;border:1px solid var(--hair);border-radius:20px;padding:24px;cursor:pointer;text-align:left;will-change:transform;transition:transform .2s cubic-bezier(.2,.8,.2,1),border-color .2s,box-shadow .2s}
.cl-rolecard:hover,.cl-rolecard:focus-visible{transform:translateY(-6px);border-color:var(--rc);box-shadow:0 20px 44px color-mix(in oklab,var(--rc) 22%,transparent);outline:none}
/* top strip of colour appears on hover — signals "this is live" */
.cl-rolecard:before{content:"";position:absolute;top:0;left:0;right:0;height:4px;background:var(--rc);transform:scaleX(0);transform-origin:left;transition:transform .3s cubic-bezier(.2,.8,.2,1)}
.cl-rolecard:hover:before,.cl-rolecard:focus-visible:before{transform:scaleX(1)}
.cl-rolecard:after{content:"";position:absolute;inset:0;background:radial-gradient(240px circle at var(--gx,50%) var(--gy,50%),color-mix(in oklab,var(--rc) 12%,transparent),transparent 60%);opacity:0;transition:opacity .25s;pointer-events:none}
.cl-rolecard:hover:after{opacity:1}
.cl-rolecard-top{display:flex;align-items:center;gap:14px}
.cl-rolecard-ic{width:54px;height:54px;border-radius:16px;background:var(--rc);color:#fff;display:flex;align-items:center;justify-content:center;flex:none;transition:transform .25s cubic-bezier(.2,.8,.2,1);box-shadow:0 8px 20px color-mix(in oklab,var(--rc) 35%,transparent)}
.cl-rolecard:hover .cl-rolecard-ic{transform:scale(1.08) rotate(-4deg)}
.cl-rolecard-ic svg,.cl-rolecard-ic .onb-icon{width:26px;height:26px}
.cl-rolecard-top h3{font-family:var(--disp);font-weight:800;font-size:20px;color:var(--yy-dark);letter-spacing:-.01em}
.cl-rolecard p{font-size:13.5px;color:var(--muted);line-height:1.5;flex:1}
.cl-rolecard-cta{display:inline-flex;align-items:center;gap:7px;font-family:var(--disp);font-weight:700;font-size:14px;color:var(--rc);margin-top:2px}
.cl-rolecard-cta b{font-weight:700;transition:transform .2s cubic-bezier(.2,.8,.2,1)}
.cl-rolecard:hover .cl-rolecard-cta b{transform:translateX(5px)}
.cl-btn{font-family:var(--disp);font-weight:700;font-size:15px;color:var(--yy-ink);background:var(--yy);border:none;border-radius:12px;padding:14px 28px;cursor:pointer;transition:transform .12s,filter .12s}
.cl-btn:hover{transform:translateY(-2px);filter:brightness(1.06)}
.cl-btn-white{background:#fff;color:var(--yy)}
@media(max-width:860px){.cl-roles{grid-template-columns:1fr;max-width:460px}}
.cl-roles-pulse .cl-rolecard{animation:cl-pulse 1.5s ease}
@keyframes cl-pulse{0%,100%{box-shadow:0 0 0 0 transparent}30%{box-shadow:0 0 0 4px var(--yy-soft)}}

/* logo carousel *//* logo carousel */
.cl-logos{overflow:hidden;border-top:1px solid var(--hair);border-bottom:1px solid var(--hair);padding:22px 0;-webkit-mask-image:linear-gradient(90deg,transparent,#000 8%,#000 92%,transparent);mask-image:linear-gradient(90deg,transparent,#000 8%,#000 92%,transparent)}
.cl-logos-track{display:flex;gap:48px;width:max-content;animation:cl-scroll 30s linear infinite;align-items:center}
@keyframes cl-scroll{to{transform:translateX(-50%)}}
.cl-logo{font-family:var(--disp);font-weight:800;font-size:20px;color:var(--faint);white-space:nowrap;letter-spacing:-.01em}
@media(prefers-reduced-motion:reduce){.cl-logos-track{animation:none}}

.cl-sec{max-width:1240px;margin:0 auto;padding:56px 24px}
.cl-sec-head{text-align:center;max-width:680px;margin:0 auto 36px}
.cl-sec-head-row{display:flex;align-items:center;justify-content:space-between;text-align:left;max-width:none}
.cl-h2{font-family:var(--disp);font-weight:800;font-size:clamp(26px,4vw,38px);line-height:1.08;letter-spacing:-.03em;color:var(--yy-dark)}
.cl-sub{font-size:15px;color:var(--muted);line-height:1.55;margin-top:12px}
.cl-link{background:none;border:none;font-family:var(--disp);font-weight:700;font-size:14px;color:var(--yy);cursor:pointer;padding:0}

/* career path — photo-style cards (dark gradient stands in for a real photo) */
.cl-path{display:grid;grid-template-columns:repeat(5,1fr);gap:16px;align-items:stretch}
.cl-pcard{position:relative;border-radius:22px;overflow:hidden;min-height:340px;display:flex;flex-direction:column;justify-content:flex-end;background:var(--pg);cursor:default;transition:transform .18s}
.cl-path{perspective:1400px}
.cl-pcard{transition:transform .25s cubic-bezier(.2,.7,.2,1),box-shadow .3s;will-change:transform}
.cl-pcard:hover{box-shadow:0 30px 60px rgba(20,20,25,.28);z-index:5}
.cl-pcard .cl-glare{position:absolute;inset:0;z-index:2;background:radial-gradient(320px circle at var(--gx,50%) var(--gy,30%),rgba(255,255,255,.22),transparent 55%);opacity:0;transition:opacity .25s;pointer-events:none}
.cl-pcard:hover .cl-glare{opacity:1}
.cl-pcard-hero{min-height:378px;margin-top:-18px;box-shadow:0 24px 60px rgba(20,20,25,.22)}
.cl-pcard-course{position:absolute;top:18px;left:50%;transform:translateX(-50%);z-index:3;font-size:12px;font-weight:700;color:#14141E;background:#fff;padding:7px 16px;border-radius:100px;white-space:nowrap;box-shadow:0 2px 8px rgba(0,0,0,.15)}
/* dark scrim so text is always readable over the gradient */
.cl-pcard-fill{position:absolute;inset:0;background:linear-gradient(180deg,transparent 30%,rgba(0,0,0,.55) 100%);z-index:1}
.cl-pcard-scene{position:absolute;left:0;right:0;bottom:0;height:62%;z-index:0;overflow:hidden;opacity:.9}
.cl-pcard-scene svg{position:absolute;bottom:-6px;left:0;width:100%;height:100%}
.cl-pcard-body{position:relative;z-index:2;padding:22px 20px}
.cl-pcard-hero .cl-pcard-body{padding-top:58px}
.cl-pcard-body h3{font-family:var(--disp);font-weight:800;font-size:19px;color:#fff;letter-spacing:-.01em;line-height:1.15}
.cl-pcard-body p{font-size:13px;color:rgba(255,255,255,.82);line-height:1.5;margin-top:8px}
.cl-pcard-btn{margin-top:16px;background:#fff;color:var(--yy-dark);border:none;border-radius:100px;font-family:var(--disp);font-weight:700;font-size:13.5px;padding:11px 22px;cursor:pointer;transition:transform .12s}
.cl-pcard-hero .cl-pcard-btn{background:var(--yy-pink);color:#fff}
.cl-pcard-btn:hover{transform:translateY(-2px)}
@media(max-width:1000px){.cl-path{grid-template-columns:repeat(2,1fr)}.cl-pcard-hero{margin-top:0}}
@media(max-width:560px){.cl-path{grid-template-columns:1fr}}

/* event cards *//* event cards */
.cl-events{display:grid;grid-template-columns:repeat(4,1fr);gap:16px}
.cl-jobs{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}
.cl-jobcard{background:var(--surface);border:1px solid var(--hair);border-radius:16px;padding:20px;cursor:pointer;transition:.16s;display:flex;flex-direction:column}
.cl-jobcard:hover{border-color:var(--yy);transform:translateY(-3px)}
.cl-jc-top{display:flex;align-items:center;justify-content:space-between;margin-bottom:14px}
.cl-jc-logo{width:44px;height:44px;border-radius:12px;display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;font-size:17px}
.cl-jc-fav{width:34px;height:34px;border-radius:9px;border:1px solid var(--hair);background:none;color:var(--faint);cursor:pointer;display:flex;align-items:center;justify-content:center;transition:.14s}
.cl-jc-fav:hover{color:var(--yy);border-color:var(--yy)}
.cl-jc-fav svg{width:16px;height:16px}
.cl-jc-title{font-family:var(--disp);font-weight:800;font-size:17px;letter-spacing:-.01em;margin-bottom:3px}
.cl-jc-co{font-size:13px;color:var(--muted);margin-bottom:14px}
.cl-jc-tags{display:flex;flex-wrap:wrap;gap:7px;margin-bottom:16px}
.cl-jc-tag{font-size:12px;padding:5px 11px;border-radius:20px;background:var(--hair2);color:var(--muted)}
.cl-jc-foot{display:flex;align-items:center;justify-content:space-between;margin-top:auto;padding-top:12px;border-top:1px solid var(--hair2)}
.cl-jc-sal{font-weight:700;font-size:14px;color:var(--yy-green)}
.cl-jc-more{font-size:12.5px;color:var(--yy);font-weight:600}
.cl-cta-btn{background:var(--yy);color:#fff;border:none;border-radius:14px;padding:15px 32px;font-family:var(--disp);font-weight:700;font-size:15px;cursor:pointer;transition:.15s}
.cl-cta-btn:hover{filter:brightness(1.08);transform:translateY(-2px)}
.cl-bignums{display:grid;grid-template-columns:repeat(4,1fr);gap:20px}
.cl-bignum{background:var(--surface);border:1px solid var(--hair);border-radius:16px;padding:26px 22px;display:flex;flex-direction:column;gap:6px}
.cl-bignum b{font-family:var(--disp);font-weight:800;font-size:42px;letter-spacing:-.03em;line-height:1;color:var(--ink)}
.cl-bignum span{font-size:13.5px;color:var(--muted);line-height:1.4}
.cl-bn-tag{align-self:flex-start;margin-top:6px;font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:.05em;padding:3px 9px;border-radius:20px;font-style:normal}
.cl-bn-market{background:var(--yy-green-soft,rgba(34,197,94,.15));color:var(--yy-green)}
.cl-bn-goal{background:var(--hair2);color:var(--faint)}
@media(max-width:900px){.cl-bignums{grid-template-columns:1fr 1fr}}
@media(max-width:560px){.cl-bignums{grid-template-columns:1fr}.cl-bignum b{font-size:36px}}

/* ===== лендинг · интерактивный Match Score ===== */
.lm-card{display:grid;grid-template-columns:1.3fr 1fr;gap:28px;background:var(--surface);border:1px solid var(--hair);border-radius:20px;padding:28px}
.lm-lbl{display:block;font-size:12.5px;font-weight:700;text-transform:uppercase;letter-spacing:.04em;color:var(--muted);margin-bottom:10px}
.lm-field{margin-bottom:20px}
.lm-field:last-child{margin-bottom:0}
.lm-vacs{display:flex;flex-direction:column;gap:8px}
.lm-vac{display:flex;align-items:center;gap:10px;padding:11px 13px;border:1.5px solid var(--hair);border-radius:12px;background:none;color:var(--ink);font-size:14px;font-weight:600;cursor:pointer;transition:.14s;text-align:left;width:100%}
.lm-vac:hover{border-color:var(--yy)}
.lm-vac.on{border-color:var(--yy);background:rgba(43,68,255,.06)}
.lm-vac-logo{width:28px;height:28px;border-radius:8px;color:#fff;font-weight:800;font-size:14px;display:flex;align-items:center;justify-content:center;flex:none}
.lm-vac-co{margin-left:auto;font-size:12px;font-weight:500;color:var(--muted)}
.lm-skills{display:flex;flex-wrap:wrap;gap:8px}
.lm-skill{font-size:13px;padding:7px 13px;border-radius:20px;border:1.5px solid var(--hair);background:none;color:var(--muted);cursor:pointer;transition:.12s;font-weight:500}
.lm-skill:hover{border-color:var(--yy)}
.lm-skill.on{background:var(--yy);border-color:var(--yy);color:#fff;font-weight:600}
.lm-result{display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;border-left:1px solid var(--hair);padding-left:28px}
.lm-ring{position:relative;width:150px;height:150px;margin-bottom:16px}
.lm-ring svg{width:100%;height:100%;transform:rotate(-90deg)}
.lm-ring-bg{fill:none;stroke:var(--hair2);stroke-width:8}
.lm-ring-fg{fill:none;stroke:var(--rc);stroke-width:8;stroke-linecap:round;transition:stroke-dasharray .6s cubic-bezier(.4,0,.2,1),stroke .3s}
.reveal .lm-ring-fg{stroke-dashoffset:264;transition:none}
.reveal.in .lm-ring-fg{stroke-dashoffset:0;transition:stroke-dashoffset 1.1s cubic-bezier(.4,0,.2,1) .2s,stroke-dasharray .6s cubic-bezier(.4,0,.2,1),stroke .3s}
@media(prefers-reduced-motion:reduce){.reveal .lm-ring-fg,.reveal.in .lm-ring-fg{stroke-dashoffset:0;transition:none}}
.lm-ring-num{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center}
.lm-ring-num b{font-family:var(--disp);font-weight:800;font-size:34px;line-height:1;color:var(--rc)}
.lm-ring-num span{font-size:10px;text-transform:uppercase;letter-spacing:.08em;color:var(--muted);margin-top:2px}
.lm-expl{width:100%}
.lm-expl-role{font-weight:700;font-size:14px;margin-bottom:8px}
.lm-gap{font-size:13.5px;color:var(--ink);line-height:1.5;margin-bottom:6px}
.lm-gap b{color:var(--yy)}
.lm-ok{font-size:14px;font-weight:700;color:var(--yy-green);margin-bottom:6px}
.lm-hint{font-size:12.5px;color:var(--muted);line-height:1.5;margin-bottom:16px}
.lm-cta{width:100%;padding:13px 20px;font-size:14px}
@media(max-width:760px){.lm-card{grid-template-columns:1fr;gap:22px}.lm-result{border-left:none;border-top:1px solid var(--hair);padding-left:0;padding-top:22px}}

/* ===== лендинг · блок «нет опыта» ===== */
.cl-noexp{display:grid;grid-template-columns:1fr 1.1fr;gap:40px;align-items:center;background:var(--surface);border:1px solid var(--hair);border-radius:20px;padding:36px}
.cl-noexp-badge{display:inline-block;font-size:12.5px;font-weight:700;color:var(--yy);background:rgba(43,68,255,.08);padding:6px 14px;border-radius:20px;margin-bottom:16px}
.cl-noexp-steps{display:flex;flex-direction:column;gap:14px}
.cl-noexp-step{display:flex;align-items:flex-start;gap:14px;position:relative;padding-left:4px}
.cl-noexp-num{width:26px;height:26px;border-radius:50%;background:var(--yy);color:#fff;font-weight:800;font-size:13px;display:flex;align-items:center;justify-content:center;flex:none}
.cl-noexp-ic{width:38px;height:38px;border-radius:11px;background:var(--hair2);color:var(--yy);display:flex;align-items:center;justify-content:center;flex:none}
.cl-noexp-ic svg{width:19px;height:19px}
.cl-noexp-st{font-weight:700;font-size:14.5px;margin-bottom:2px}
.cl-noexp-sx{font-size:13px;color:var(--muted);line-height:1.45}
/* анимированная схема-поток */
.cl-flow{position:relative;padding:20px 0}
.cl-flow-track{position:absolute;top:47px;left:6%;right:6%;height:3px;background:var(--hair2);border-radius:3px;overflow:visible}
.cl-flow-fill{height:100%;width:0;background:var(--yy);border-radius:3px;transition:width 1.6s cubic-bezier(.4,0,.2,1) .3s}
.reveal.in .cl-flow-fill{width:100%}
.cl-flow-dot{position:absolute;top:50%;left:0;width:14px;height:14px;margin:-7px 0 0 -7px;border-radius:50%;background:var(--yy);box-shadow:0 0 0 4px rgba(43,68,255,.2);opacity:0}
.reveal.in .cl-flow-dot{animation:cl-flow-run 1.9s cubic-bezier(.4,0,.2,1) .3s forwards}
@keyframes cl-flow-run{0%{left:0;opacity:1}90%{opacity:1}100%{left:100%;opacity:0}}
.cl-flow-nodes{display:grid;grid-template-columns:repeat(4,1fr);gap:8px;position:relative}
.cl-flow-node{display:flex;flex-direction:column;align-items:center;gap:10px;text-align:center;opacity:0;transform:translateY(12px);transition:opacity .5s ease,transform .5s ease;transition-delay:calc(.4s + var(--fd))}
.reveal.in .cl-flow-node{opacity:1;transform:none}
.cl-flow-ic{width:54px;height:54px;border-radius:16px;background:var(--surface);border:2px solid var(--hair);color:var(--muted);display:flex;align-items:center;justify-content:center;transition:border-color .4s,color .4s,background .4s;transition-delay:calc(.9s + var(--fd))}
.cl-flow-ic svg{width:24px;height:24px}
.reveal.in .cl-flow-node .cl-flow-ic{border-color:var(--yy);color:var(--yy);background:rgba(43,68,255,.06)}
.cl-flow-node:last-child .cl-flow-ic{transition-delay:1.9s}
.reveal.in .cl-flow-node:last-child .cl-flow-ic{border-color:var(--yy-green);color:var(--yy-green);background:var(--yy-green-soft,rgba(34,197,94,.1))}
.cl-flow-lbl{font-weight:700;font-size:14px}
@media(prefers-reduced-motion:reduce){.cl-flow-fill{width:100%;transition:none}.cl-flow-dot{display:none}.cl-flow-node{opacity:1;transform:none}}
@media(max-width:560px){.cl-flow-nodes{grid-template-columns:1fr 1fr;gap:20px}.cl-flow-track{display:none}}
@media(max-width:760px){.cl-noexp{grid-template-columns:1fr;gap:28px;padding:26px}}

/* ===== лендинг · секция вуза ===== */
.cl-uni{background:var(--surface);border:1px solid var(--hair);border-radius:20px;padding:36px}
.cl-uni-head{max-width:680px;margin-bottom:28px}
.cl-uni-badge{display:inline-block;font-size:12.5px;font-weight:700;color:var(--yy-green);background:var(--yy-green-soft,rgba(34,197,94,.12));padding:6px 14px;border-radius:20px;margin-bottom:16px}
.cl-uni-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:18px;margin-bottom:28px}
.cl-uni-feat{background:var(--bg);border:1px solid var(--hair);border-radius:14px;padding:20px;opacity:0;transform:translateY(16px);transition:opacity .5s ease,transform .5s ease}
.reveal.in .cl-uni-feat{opacity:1;transform:none}
.reveal.in .cl-uni-feat:nth-child(1){transition-delay:.05s}
.reveal.in .cl-uni-feat:nth-child(2){transition-delay:.15s}
.reveal.in .cl-uni-feat:nth-child(3){transition-delay:.25s}
.reveal.in .cl-uni-feat:nth-child(4){transition-delay:.35s}
@media(prefers-reduced-motion:reduce){.cl-uni-feat{opacity:1;transform:none}}
.cl-uni-ic{width:42px;height:42px;border-radius:12px;background:var(--yy-green-soft,rgba(34,197,94,.12));color:var(--yy-green);display:flex;align-items:center;justify-content:center;margin-bottom:14px}
.cl-uni-ic svg{width:20px;height:20px}
.cl-uni-ft{font-weight:700;font-size:14.5px;margin-bottom:6px}
.cl-uni-fx{font-size:12.5px;color:var(--muted);line-height:1.5}
@media(max-width:900px){.cl-uni-grid{grid-template-columns:1fr 1fr}}
@media(max-width:560px){.cl-uni-grid{grid-template-columns:1fr}.cl-uni{padding:26px}}
.cl-co-badge{color:var(--yy);background:rgba(43,68,255,.08)}
.cl-co-ic{background:rgba(43,68,255,.1);color:var(--yy)}
@media(max-width:900px){.cl-jobs{grid-template-columns:1fr 1fr}}
@media(max-width:560px){.cl-jobs{grid-template-columns:1fr}}
.cl-event{background:var(--surface);border:1px solid var(--hair);border-radius:18px;padding:20px;cursor:pointer;transition:transform .15s,border-color .15s,box-shadow .15s;display:flex;flex-direction:column}
.cl-event:hover{transform:translateY(-4px);border-color:var(--yy);box-shadow:0 12px 30px rgba(43,68,255,.08)}
.cl-event-top{display:flex;align-items:center;gap:10px;margin-bottom:14px}
.cl-event-logo{width:32px;height:32px;border-radius:9px;background:var(--ec);color:#fff;font-family:var(--disp);font-weight:800;font-size:14px;display:flex;align-items:center;justify-content:center;flex:none}
.cl-event-co{font-size:12px;font-weight:600;color:var(--muted)}
.cl-event h4{font-family:var(--disp);font-weight:800;font-size:16px;color:var(--yy-dark);letter-spacing:-.01em;line-height:1.25}
.cl-event p{font-size:13px;color:var(--muted);line-height:1.5;margin-top:8px;flex:1}
.cl-event-meta{display:flex;gap:14px;margin-top:14px}
.cl-event-meta span{display:inline-flex;align-items:center;gap:5px;font-size:12px;color:var(--faint)}
.cl-event-meta svg,.cl-event-meta .onb-icon{width:14px;height:14px}
.cl-event-tag{margin-top:12px;font-size:11px;font-weight:600;color:var(--yy-green);display:inline-flex;align-items:center;gap:5px}
.cl-event-tag:before{content:"";width:6px;height:6px;border-radius:50%;background:var(--yy-green)}
@media(max-width:900px){.cl-events{grid-template-columns:1fr 1fr}}
@media(max-width:560px){.cl-events{grid-template-columns:1fr}}

/* cta band */
.cl-cta-band{background:#0E1330;border-radius:24px;padding:44px 40px;display:flex;align-items:center;justify-content:space-between;gap:24px;flex-wrap:wrap}
body.yy.dark .cl-cta-band{background:#080A16;border:1px solid var(--hair)}
@media(max-width:640px){.cl-cta-band{flex-direction:column;text-align:center;padding:36px 24px}}

/* ===== public sections: shared heads ===== *//* ===== public sections: shared heads ===== */
.sec-head{max-width:720px;margin:0 auto 28px;text-align:center}
.sec-eyebrow{display:inline-block;font-size:12px;font-weight:700;letter-spacing:.08em;text-transform:uppercase;color:var(--accent-ink);background:var(--accent-soft);padding:5px 12px;border-radius:20px;margin-bottom:14px}
.sec-head h2{font-size:28px;font-weight:700;letter-spacing:-.02em;line-height:1.2}
.sec-sub{font-size:15px;color:var(--muted);margin-top:10px;line-height:1.55}
.pub-sec-cta{text-align:center;background:var(--accent-soft);border-radius:24px;padding:48px 24px;margin-top:12px}
.pub-sec-cta h2{font-size:26px;font-weight:700;letter-spacing:-.02em}
.pub-sec-cta .sec-sub{margin:10px auto 22px;max-width:460px}

/* ===== course-path ribbon (signature element) ===== */
.cpath{display:flex;align-items:flex-start;justify-content:center;gap:0;flex-wrap:nowrap;overflow-x:auto;padding:8px 4px 4px}
.cpath-step{flex:1;min-width:130px;max-width:190px;text-align:center;position:relative;padding:0 6px}
.cpath-year{font-size:11.5px;font-weight:700;letter-spacing:.04em;text-transform:uppercase;color:var(--accent-ink);margin-bottom:12px}
.cpath-dot{width:48px;height:48px;border-radius:15px;background:var(--accent-soft);color:var(--accent-ink);display:flex;align-items:center;justify-content:center;margin:0 auto 12px}
.cpath-dot svg,.cpath-dot .onb-icon{width:22px;height:22px}
.cpath-t{font-size:15px;font-weight:700;letter-spacing:-.01em}
.cpath-d{font-size:12.5px;color:var(--muted);margin-top:5px;line-height:1.45}
.cpath-link{flex:0 0 24px;align-self:flex-start;height:2px;background:var(--hair);margin-top:71px}
@media(max-width:720px){.cpath{flex-direction:column;align-items:stretch;gap:18px}.cpath-step{max-width:none;display:grid;grid-template-columns:48px 1fr;column-gap:14px;text-align:left;padding:0}.cpath-dot{grid-column:1;grid-row:1/4;margin:0;align-self:start}.cpath-year{grid-column:2;margin:0 0 3px}.cpath-t{grid-column:2}.cpath-d{grid-column:2;margin-top:3px}.cpath-link{display:none}}

/* ===== doors (FutureToday navigator) ===== */
.doors{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;max-width:900px;margin:0 auto}
.door{background:var(--surface);border:1px solid var(--hair);border-radius:16px;padding:20px;cursor:pointer;transition:border-color .15s}
.door:hover{border-color:var(--accent)}
.door-top{display:flex;align-items:center;justify-content:space-between;gap:8px;margin-bottom:12px}
.door-g{font-size:16px;font-weight:700;letter-spacing:-.01em}
.door-n{font-size:11.5px;font-weight:700;color:var(--accent-ink);background:var(--accent-soft);padding:4px 10px;border-radius:20px;white-space:nowrap}
.door-d{font-size:13px;color:var(--muted);line-height:1.55;margin-bottom:14px}
.door-go{font-size:13px;font-weight:600;color:var(--accent-ink)}
@media(max-width:720px){.doors{grid-template-columns:1fr}}

/* ===== employer offer ===== */
.offer-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;max-width:900px;margin:0 auto}
.offer-card{background:var(--surface);border:1px solid var(--hair);border-radius:16px;padding:20px 18px;text-align:center}
.offer-v{font-size:24px;font-weight:700;letter-spacing:-.02em;color:var(--ink);line-height:1.1}
.offer-l{font-size:12.5px;color:var(--muted);margin-top:8px;line-height:1.45}
@media(max-width:720px){.offer-grid{grid-template-columns:repeat(2,1fr)}}
.offer-steps{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;max-width:900px;margin:0 auto}
.offer-step{display:flex;gap:14px;align-items:flex-start}
.offer-num{width:34px;height:34px;border-radius:50%;background:var(--accent);color:#fff;font-weight:700;font-size:15px;display:flex;align-items:center;justify-content:center;flex:none}
.offer-st{font-size:15px;font-weight:700;letter-spacing:-.01em}
.offer-sd{font-size:13px;color:var(--muted);margin-top:4px;line-height:1.5}
@media(max-width:720px){.offer-steps{grid-template-columns:1fr}}
.fields-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;max-width:760px;margin:0 auto}
.field-tile{background:var(--surface);border:1px solid var(--hair);border-radius:14px;padding:22px 18px;text-align:center;cursor:pointer;transition:border-color .15s}
.field-tile:hover{border-color:var(--accent)}
.field-ic{width:44px;height:44px;border-radius:13px;background:var(--accent-soft);color:var(--accent-ink);display:flex;align-items:center;justify-content:center;margin:0 auto 12px}
.field-t{font-size:14px;font-weight:600}
@media(max-width:720px){.fields-grid{grid-template-columns:repeat(2,1fr)}}
.offer-note{display:inline-flex;align-items:center;gap:7px;font-size:12px;color:var(--muted);margin-top:18px}

/* ===== talent profile =====
   .cc-* live under .candcard; outside that scope they render as bare inline text. */
/* textarea inherits the UA monospace default unless told otherwise */
.field textarea{font-family:inherit;font-size:14px;line-height:1.5;padding:11px 13px;border:1px solid var(--hair);border-radius:11px;background:var(--surface);color:var(--ink);resize:vertical}
.field textarea:focus{outline:none;border-color:var(--accent)}

.tp-ava{width:60px;height:60px;border-radius:16px;flex:none;background:var(--accent-soft);color:var(--accent-ink);display:flex;align-items:center;justify-content:center;font-weight:800;font-size:20px}
.tp-skills{display:flex;flex-wrap:wrap;gap:7px;margin-top:12px}
.tp-sk{font-size:12px;font-weight:500;padding:5px 11px;border-radius:14px;background:var(--hair2);color:var(--ink)}
.tp-fit{font-size:30px;font-weight:700;color:var(--accent-ink);letter-spacing:-.03em;line-height:1}
.tp-fit-l{font-size:11.5px;color:var(--muted);margin-top:3px}

/* ===== companies ===== */
.co-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:14px}
.co-card{background:var(--surface);border:1px solid var(--hair);border-radius:16px;padding:18px;cursor:pointer;transition:border-color .15s}
.co-card:hover{border-color:var(--accent)}
.co-top{display:flex;align-items:center;justify-content:space-between;margin-bottom:13px}
.co-logo{width:44px;height:44px;border-radius:13px;color:#fff;font-weight:700;font-size:15px;display:flex;align-items:center;justify-content:center;flex:none;letter-spacing:.02em}
.co-open{font-size:11px;font-weight:700;padding:4px 10px;border-radius:20px;background:var(--blue-soft);color:var(--blue-ink)}
.co-open.muted{background:var(--hair2);color:var(--faint)}
.co-name{font-size:16px;font-weight:700;letter-spacing:-.01em}
.co-sub{font-size:12.5px;color:var(--muted);margin-top:2px}
.co-meta{display:flex;flex-wrap:wrap;gap:6px;margin-top:11px}
.co-meta span{display:inline-flex;align-items:center;gap:5px;font-size:11.5px;color:var(--faint)}
.co-fig{margin-top:13px;padding-top:12px;border-top:1px solid var(--hair2);display:flex;align-items:baseline;gap:7px}
.co-fig b{font-size:19px;font-weight:700;color:var(--ink);letter-spacing:-.02em}
.co-fig span{font-size:11.5px;color:var(--muted)}
.co-stats{display:grid;grid-template-columns:repeat(auto-fit,minmax(120px,1fr));gap:12px;margin-top:18px;padding-top:16px;border-top:1px solid var(--hair2)}
.co-stat{background:var(--accent-soft);border-radius:12px;padding:14px}
.co-stat .cs-v{font-size:22px;font-weight:700;color:var(--accent-ink);letter-spacing:-.02em}
.co-stat .cs-l{font-size:11.5px;color:var(--accent-ink);opacity:.78;margin-top:3px;line-height:1.35}
.co-progs{display:flex;flex-direction:column;gap:10px;margin-top:12px}
.co-prog{border:1px solid var(--hair);border-radius:13px;padding:14px}
.cp-head{display:flex;align-items:center;justify-content:space-between;gap:10px;flex-wrap:wrap}
.cp-title{font-size:14px;font-weight:600}
.cp-paid{display:inline-flex;align-items:center;gap:4px;font-size:11px;font-weight:700;padding:3px 9px;border-radius:20px;background:var(--green-soft);color:var(--green-ink)}
.cp-meta{display:flex;flex-wrap:wrap;gap:6px;margin-top:10px}
/* ===== hiring stepper ===== */
.hs{display:flex;align-items:flex-start;margin-top:16px;overflow-x:auto;padding-bottom:4px}
.hs-step{flex:1;min-width:88px;display:flex;flex-direction:column;align-items:center;position:relative}
.hs-step:not(:last-child):after{content:"";position:absolute;top:15px;left:calc(50% + 18px);right:calc(-50% + 18px);height:2px;background:var(--hair)}
.hs-dot{width:32px;height:32px;border-radius:50%;background:var(--accent-soft);color:var(--accent-ink);font-size:13px;font-weight:700;display:flex;align-items:center;justify-content:center;position:relative;z-index:1}
.hs-lbl{font-size:11.5px;color:var(--muted);text-align:center;margin-top:8px;line-height:1.35;padding:0 4px}
/* ===== deadline pills ===== */
.jc-pill.dl-urgent{background:var(--red-soft);color:var(--red-ink);font-weight:600}
.jc-pill.dl-closed{background:var(--hair2);color:var(--faint)}
.jobcard.closed,.jobrow.closed{opacity:.5}
/* ===== events ===== */
.ev-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:14px;align-items:stretch}
.ev-card{background:var(--surface);border:1px solid var(--hair);border-radius:16px;padding:18px;display:flex;flex-direction:column}
.ev-card.ev-closed{opacity:.55}
.ev-top{display:flex;align-items:center;justify-content:space-between;gap:8px;margin-bottom:11px}
.ev-type{font-size:11px;font-weight:700;padding:4px 10px;border-radius:20px}
.ev-fmt{display:inline-flex;align-items:center;gap:5px;font-size:11.5px;color:var(--faint)}
.ev-title{font-size:15px;font-weight:700;line-height:1.35;letter-spacing:-.01em;min-height:2.7em}
.ev-co{display:flex;align-items:center;flex-wrap:wrap;gap:7px;margin-top:9px;font-size:12px;color:var(--muted)}
.ev-logo{width:20px;height:20px;border-radius:6px;color:#fff;font-size:9px;font-weight:700;display:flex;align-items:center;justify-content:center;flex:none}
.ev-uni{display:inline-flex;align-items:center;gap:4px;color:var(--faint)}
.ev-desc{font-size:12.5px;color:var(--muted);line-height:1.55;margin-top:10px;flex:1}
.ev-seats{margin-top:13px}
.ev-bar{height:6px;background:var(--hair2);border-radius:4px;overflow:hidden}
.ev-bar i{display:block;height:100%;background:var(--accent);border-radius:4px}
.ev-seats span{display:block;font-size:11.5px;color:var(--faint);margin-top:6px}
.ev-foot{display:flex;align-items:center;justify-content:space-between;gap:8px;margin-top:12px;padding-top:11px;border-top:1px solid var(--hair2)}
.ev-date{display:inline-flex;align-items:center;gap:5px;font-size:12px;font-weight:600}
.ev-dl{font-size:11.5px;color:var(--muted)}
.ev-dl.urgent{color:var(--red-ink);background:var(--red-soft);padding:3px 9px;border-radius:20px;font-weight:600}
.ev-dl.closed{color:var(--faint)}
/* ===== public counters ===== */
/* Counters share the cards' 960px grid; a narrower box read as a stray element.
   No card chrome — three plain figures under the promise, not a fourth widget. */
.pub-stats{display:grid;grid-template-columns:repeat(3,1fr);gap:0;max-width:560px;margin:0 auto 40px}
.pub-stat{padding:0 12px;text-align:center;position:relative}
.pub-stat+.pub-stat:before{content:"";position:absolute;left:0;top:50%;transform:translateY(-50%);width:1px;height:34px;background:var(--hair)}
.pub-stat .pv{font-size:28px;font-weight:700;letter-spacing:-.03em;color:var(--ink);line-height:1.1;font-variant-numeric:tabular-nums}
.pub-stat .pl{font-size:12.5px;color:var(--muted);margin-top:4px}
@media(max-width:560px){.pub-stats{max-width:340px;gap:0}.pub-stat .pv{font-size:23px}.pub-stat .pl{font-size:11.5px}}
/* ===== profile nudge (deferred password flow) ===== */
.nudge-profile{display:flex;align-items:center;gap:13px;background:var(--blue-soft);border-radius:13px;padding:14px 16px;margin-bottom:16px}
.nudge-profile .np-ic{width:38px;height:38px;border-radius:11px;background:var(--blue);color:#fff;display:flex;align-items:center;justify-content:center;flex:none}
.nudge-profile .np-t{font-size:13.5px;font-weight:700;color:var(--blue-ink)}
.nudge-profile .np-d{font-size:12px;color:var(--blue-ink);opacity:.8;margin-top:2px}
body[data-role="student"]{--accent:var(--blue);--accent-soft:var(--blue-soft);--accent-ink:var(--blue-ink)}
/* yy skin keeps one accent across all roles — lavender wins over role tints */
/* ---- yy DARK variant: same indigo identity on a deep navy canvas ---- */
body.yy.dark{
  --bg:#0B0D1A;--surface:#141830;--surface2:#1B2040;--ink:#F2F3F8;--muted:#A0A4B8;--faint:#6B7090;
  --hair:#262B45;--hair2:#1E2238;
  --yy:#6E82FF;--yy-ink:#0B0D1A;--yy-dark:#F2F3F8;--yy-soft:#1C2145;
  --yy-green:#34D399;--yy-amber:#FBBF24;--yy-pink:#F472B6;--yy-cyan:#22D3EE;
  --accent:var(--yy);--accent-soft:var(--yy-soft);--accent-ink:#B8C2FF;
  --blue:var(--yy);--blue-soft:var(--yy-soft);--blue-ink:#B8C2FF;
  background:var(--bg);color:var(--ink);
}
/* hero gradient + logo track adapt to dark */
body.yy.dark .cl-hero2{background:linear-gradient(135deg,#141830 0%,#1B1640 50%,#2A1030 100%)}
body.yy.dark .cl-badge{background:var(--surface);color:var(--yy)}
body.yy.dark .cl-rolecard{background:var(--surface)}
body.yy.dark .cl-event,body.yy.dark .cl-pcard-btn{background:var(--surface2)}
body.yy.dark .cl-pcard-btn{color:var(--ink)}
body.yy[data-role],body.yy[data-role="student"],body.yy[data-role="university"],body.yy[data-role="company"]{--accent:var(--yy);--accent-soft:var(--yy-soft);--accent-ink:#1B2ECC}
body[data-role="university"]{--accent:var(--teal);--accent-soft:var(--teal-soft);--accent-ink:var(--teal-ink)}
body[data-role="company"]{--accent:var(--amber);--accent-soft:var(--amber-soft);--accent-ink:var(--amber-ink)}
body[data-role="mentor"]{--accent:var(--green);--accent-soft:var(--green-soft);--accent-ink:var(--green-ink)}
body[data-role="admin"]{--accent:var(--purple);--accent-soft:var(--purple-soft);--accent-ink:var(--purple-ink)}
body{--accent:var(--blue);--accent-soft:var(--blue-soft);--accent-ink:var(--blue-ink)}
/* accent presets — override the role tint when the user picks one */
body[data-accent="teal"]{--accent:var(--teal);--accent-soft:var(--teal-soft);--accent-ink:var(--teal-ink)}
body[data-accent="violet"]{--accent:var(--purple);--accent-soft:var(--purple-soft);--accent-ink:var(--purple-ink)}
body[data-accent="amber"]{--accent:var(--amber);--accent-soft:var(--amber-soft);--accent-ink:var(--amber-ink)}


/* ================= AUTH / ONBOARDING (centered) ================= */
.center-screen{min-height:100%;display:flex;align-items:center;justify-content:center;padding:32px 20px}
.card{background:var(--surface);border:1px solid var(--hair);border-radius:18px;padding:32px;width:100%;max-width:440px}
.brand{display:flex;align-items:center;gap:10px;margin-bottom:24px}
.logo{width:30px;height:30px;border-radius:8px;background:var(--blue);display:flex;align-items:center;justify-content:center;color:#fff;font-weight:700;font-size:15px}
.brand b{font-size:16px;font-weight:700;letter-spacing:-.01em}
.brand span{font-size:12px;color:var(--muted);margin-left:auto}
h2.title{font-size:22px;font-weight:700;letter-spacing:-.02em;margin-bottom:4px}
.subtitle{font-size:13.5px;color:var(--muted);margin-bottom:22px}
.field{margin-bottom:14px}
.field label{display:block;font-size:12px;font-weight:500;color:var(--muted);margin-bottom:6px}
/* unified control styling: inputs + ALL selects across the app */
.field input,.field select,select{width:100%;height:44px;border:1.5px solid var(--hair);border-radius:11px;padding:0 12px;font-size:14px;font-family:inherit;color:var(--ink);outline:none;background:var(--surface);transition:.15s;box-sizing:border-box}
select{
  -webkit-appearance:none;-moz-appearance:none;appearance:none;
  padding-right:40px;cursor:pointer;
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='20' height='20' viewBox='0 0 24 24' fill='none' stroke='%236B6B72' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpath d='M6 9l6 6 6-6'/%3E%3C/svg%3E");
  background-repeat:no-repeat;background-position:right 12px center;
}
.field input:focus,.field select:focus,select:focus{border-color:var(--accent);box-shadow:0 0 0 3px var(--accent-soft)}
select:hover{border-color:var(--accent)}
select:invalid,select option[value=""]{color:var(--muted)}
.btn{height:42px;border-radius:10px;font-size:14px;font-weight:600;display:inline-flex;align-items:center;justify-content:center;gap:7px;padding:0 18px;transition:.15s;width:100%}
.btn-primary{background:var(--accent);color:#fff}
.btn-primary:hover{filter:brightness(1.06)}
.btn-ghost{background:transparent;border:1px solid var(--hair);color:var(--ink)}
.btn-ghost:hover{background:var(--hair2)}
.btn-sm{height:34px;font-size:13px;padding:0 13px;width:auto;border-radius:8px}
.divider{display:flex;align-items:center;gap:12px;margin:18px 0;color:var(--faint);font-size:12px}
.divider::before,.divider::after{content:"";flex:1;height:1px;background:var(--hair)}
.tabs{display:flex;gap:4px;background:var(--hair2);padding:4px;border-radius:10px;margin-bottom:22px}
.tabs button{flex:1;height:34px;border-radius:7px;font-size:13px;font-weight:500;color:var(--muted)}
.tabs button.on{background:var(--surface);color:var(--ink);box-shadow:0 1px 3px rgba(0,0,0,.06)}
.hint{font-size:12px;color:var(--muted);text-align:center;margin-top:16px}
.hint a{color:var(--accent);font-weight:500;cursor:pointer}

/* role picker */
.roles{display:flex;flex-direction:column;gap:10px;margin-bottom:8px}
.role-opt{display:flex;align-items:center;gap:13px;padding:14px;border:1.5px solid var(--hair);border-radius:12px;transition:.15s;text-align:left;width:100%}
.role-opt:hover{border-color:var(--accent)}
.role-opt.on{border-color:var(--accent);background:var(--accent-soft)}
.role-opt .ri{width:38px;height:38px;border-radius:9px;flex:none;display:flex;align-items:center;justify-content:center;font-size:18px}
.role-opt .rt{font-weight:600;font-size:14px}
.role-opt .rd{font-size:12px;color:var(--muted)}
.role-opt .chk{margin-left:auto;color:var(--accent);font-weight:700;opacity:0}
.role-opt.on .chk{opacity:1}
.steps-bar{height:5px;background:var(--hair2);border-radius:3px;margin-bottom:8px;overflow:hidden}
.steps-bar i{display:block;height:100%;background:var(--accent);transition:.3s;border-radius:3px}
.steps-label{font-size:12px;color:var(--muted);margin-bottom:18px}
.steps-label b{color:var(--ink)}
.nav-btns{display:flex;gap:10px;margin-top:24px}
.nav-btns .btn{width:auto}
.nav-btns .grow{margin-left:auto}

/* ================= APP SHELL ================= */
.shell{display:flex;min-height:100%}
.sidebar{width:250px;flex:none;background:var(--surface);border-right:1px solid var(--hair);display:flex;flex-direction:column;padding:16px 12px;position:sticky;top:0;height:100vh;overflow:hidden;transition:width .18s ease,padding .18s ease}
.sb-brand{display:flex;align-items:center;gap:9px;padding:6px 8px 16px;flex:none}
.sb-brand .logo{width:26px;height:26px;font-size:13px;background:var(--accent)}
.sb-brand b{font-size:14.5px;font-weight:700}
.role-switch{flex:none;margin:0 6px 14px;padding:9px 11px;background:var(--accent-soft);border-radius:10px;font-size:11.5px;color:var(--accent-ink);display:flex;align-items:center;gap:8px}
.role-switch .rdot{width:8px;height:8px;border-radius:50%;background:var(--accent)}
.role-switch b{font-weight:600}
.nav-group{display:flex;flex-direction:column;gap:2px;flex:1;min-height:0;overflow-y:auto;overflow-x:hidden;margin:0 -4px;padding:0 4px;scrollbar-width:thin;scrollbar-color:var(--hair) transparent}
.nav-group::-webkit-scrollbar{width:6px}
.nav-group::-webkit-scrollbar-thumb{background:var(--hair);border-radius:3px}
.nav-group::-webkit-scrollbar-track{background:transparent}
.nav-item{display:flex;align-items:center;gap:11px;padding:9px 11px;border-radius:9px;font-size:13.5px;font-weight:500;color:var(--muted);transition:.12s;width:100%;text-align:left}
.nav-item:hover{background:var(--hair2);color:var(--ink)}
.nav-item.on{background:var(--accent-soft);color:var(--accent-ink);font-weight:600}
.nav-item .ic{width:18px;text-align:center;font-size:15px;flex:none}
.nav-badge{display:none;margin-left:auto;min-width:18px;height:18px;padding:0 5px;border-radius:9px;background:var(--accent);color:#fff;font-size:11px;font-weight:700;align-items:center;justify-content:center;line-height:1}
body.sb-collapsed .nav-badge{position:absolute;top:5px;right:5px;margin:0;min-width:16px;height:16px;font-size:9.5px}
.nav-sep{height:1px;background:var(--hair);margin:12px 8px}
.nav-grp-label{font-size:10px;font-weight:700;letter-spacing:.06em;text-transform:uppercase;color:var(--faint);padding:14px 11px 5px;user-select:none}
.nav-grp-label:first-child{padding-top:4px}
.sb-foot{display:flex;flex-direction:column;gap:2px;flex:none;padding-top:8px;margin-top:8px;border-top:1px solid var(--hair)}
.sb-user{display:flex;align-items:center;gap:10px;padding:9px 8px;margin-top:4px;flex:none}
.sb-user .av{width:30px;height:30px;border-radius:50%;background:var(--accent);color:#fff;display:flex;align-items:center;justify-content:center;font-size:13px;font-weight:600;flex:none}
.sb-user .un{font-size:13px;font-weight:600;line-height:1.2}
.sb-user .ue{font-size:11px;color:var(--muted)}
.sb-user button{margin-left:auto;color:var(--faint);font-size:16px;padding:4px}
.sb-user button:hover{color:var(--red)}
.sb-collapse-btn{margin-left:auto;color:var(--faint);padding:4px;border-radius:7px;flex:none;transition:.15s;display:flex;align-items:center}
.sb-collapse-btn:hover{color:var(--ink);background:var(--hair2)}
.sb-collapse-btn svg{width:16px;height:16px}

/* ===== свёрнутый сайдбар (десктоп): только иконки ===== */
body.sb-collapsed .sidebar{width:64px;padding:16px 8px}
body.sb-collapsed .sb-brand b,
body.sb-collapsed .role-switch,
body.sb-collapsed .nav-grp-label,
body.sb-collapsed .nav-item{overflow:hidden}
body.sb-collapsed .sb-brand b{display:none}
body.sb-collapsed .role-switch{padding:9px 0;justify-content:center;margin:0 0 14px}
body.sb-collapsed .role-switch b,body.sb-collapsed .role-switch{font-size:0}
body.sb-collapsed .role-switch .rdot{margin:0}
body.sb-collapsed .nav-grp-label{height:1px;padding:8px 0 7px;color:transparent;background:var(--hair);margin:6px 10px;overflow:hidden}
body.sb-collapsed .nav-item{justify-content:center;padding:10px 0;gap:0;font-size:0}
body.sb-collapsed .nav-item .ic{font-size:15px}
body.sb-collapsed .sb-user{justify-content:center;padding:9px 0}
body.sb-collapsed .sb-user>div:not(.av),body.sb-collapsed .sb-user button{display:none}
body.sb-collapsed .sb-collapse-btn{margin:0}
body.sb-collapsed .sb-collapse-btn svg{transform:rotate(180deg)}
body.sb-collapsed .sb-brand{justify-content:center;padding:6px 0 16px}
body.sb-collapsed .sb-brand .logo{margin:0}
/* тултип названия при наведении на иконку в свёрнутом виде */
body.sb-collapsed .nav-item{position:relative}
body.sb-collapsed .nav-item:hover::after{content:attr(data-label);position:absolute;left:100%;margin-left:10px;top:50%;transform:translateY(-50%);background:var(--ink);color:var(--surface);font-size:11.5px;font-weight:600;padding:5px 9px;border-radius:7px;white-space:nowrap;z-index:60;pointer-events:none}

.main{flex:1;min-width:0;display:flex;flex-direction:column}
.topbar{height:58px;border-bottom:1px solid var(--hair);background:var(--surface);display:flex;align-items:center;gap:14px;padding:0 24px;position:sticky;top:0;z-index:5}
.topbar .crumb{font-size:13px;color:var(--muted)}
.topbar .crumb b{color:var(--ink);font-weight:600}
.search-mini{margin-left:16px;flex:1;max-width:420px;display:flex;align-items:center;gap:9px;height:38px;padding:0 14px;border:1.5px solid var(--hair);border-radius:10px;color:var(--faint);font-size:13.5px;cursor:pointer;background:var(--bg);transition:.14s}
.search-mini:hover{border-color:var(--accent);background:var(--surface)}
.search-mini kbd{margin-left:auto;font-size:10px;background:var(--hair2);padding:2px 6px;border-radius:5px;color:var(--muted)}
.bell{width:36px;height:36px;border-radius:9px;display:flex;align-items:center;justify-content:center;font-size:16px;color:var(--muted);position:relative}
.bell:hover{background:var(--hair2)}
.bell i{position:absolute;top:7px;right:8px;width:7px;height:7px;background:var(--red);border-radius:50%;border:1.5px solid var(--surface)}
.content{padding:28px 32px 60px;max-width:1120px;width:100%}

/* page header */
.ph{margin-bottom:22px}
.ph h1{font-size:24px;font-weight:700;letter-spacing:-.02em}
.ph p{font-size:14px;color:var(--muted);margin-top:4px}
.ph .row{display:flex;align-items:flex-end;gap:16px}
.ph .row .btn{margin-left:auto}

/* generic cards & grid */
.g{display:grid;gap:16px}
.g2{grid-template-columns:repeat(2,1fr)}
.g3{grid-template-columns:repeat(3,1fr)}
.g4{grid-template-columns:repeat(4,1fr)}
.panel{background:var(--surface);border:1px solid var(--hair);border-radius:var(--radius);padding:18px}
.sd{font-size:12.5px;color:var(--muted);line-height:1.5}
.panel h3{font-size:16px;font-weight:700;letter-spacing:-.01em;margin-bottom:3px;display:flex;align-items:center;gap:8px}
.panel .ps{font-size:12px;color:var(--muted);margin-bottom:14px}
.stat{background:var(--surface);border:1px solid var(--hair);border-radius:var(--radius);padding:16px}
.stat .sv{font-size:26px;font-weight:700;letter-spacing:-.02em}
.stat .sl{font-size:12.5px;color:var(--muted);margin-top:2px}
.stat .sd{font-size:11.5px;font-weight:600;margin-top:6px}
.up{color:var(--green)}.down{color:var(--red)}

.list{display:flex;flex-direction:column}
.li{display:flex;align-items:center;gap:12px;padding:12px 0;border-bottom:1px solid var(--hair2)}
.li:last-child{border-bottom:none;padding-bottom:0}
.li:first-child{padding-top:0}
.li .li-ic{width:34px;height:34px;border-radius:9px;background:var(--accent-soft);color:var(--accent-ink);display:flex;align-items:center;justify-content:center;font-size:15px;flex:none}
.li .li-b{flex:1;min-width:0}
.li .li-t{font-size:13.5px;font-weight:600;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.li .li-d{font-size:12px;color:var(--muted)}
.li .li-r{font-size:12px;color:var(--muted);text-align:right;flex:none}

.badge{font-size:11px;font-weight:600;padding:2px 9px;border-radius:20px;white-space:nowrap;display:inline-block}
.b-blue{background:var(--blue-soft);color:var(--blue-ink)}
.b-teal{background:var(--teal-soft);color:var(--teal-ink)}
.b-amber{background:var(--amber-soft);color:var(--amber-ink)}
.b-green{background:var(--green-soft);color:var(--green-ink)}
.b-red{background:var(--red-soft);color:var(--red-ink)}
.b-gray{background:var(--hair2);color:var(--gray-ink,#3A3A37)}
.b-purple{background:var(--purple-soft);color:var(--purple-ink)}

.progress{height:8px;background:var(--hair2);border-radius:5px;overflow:hidden}
.progress i{display:block;height:100%;background:var(--accent);border-radius:5px}

/* ===== HTD — Заказ на кадры (усиленный) ===== */
.htd-stats{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin-bottom:18px}
.htd-stat{background:var(--surface);border:1px solid var(--hair);border-radius:var(--radius);padding:16px}
.htd-stat b{display:block;font-family:var(--disp);font-weight:800;font-size:28px;letter-spacing:-.02em;line-height:1}
.htd-stat span{font-size:12px;color:var(--muted);margin-top:5px;display:block}
.htd-card{background:var(--surface);border:1px solid var(--hair);border-radius:16px;padding:20px;transition:.16s;cursor:pointer;position:relative;overflow:hidden}
.htd-card:hover{border-color:var(--accent);box-shadow:0 8px 24px rgba(0,0,0,.08);transform:translateY(-2px)}
.htd-card::before{content:"";position:absolute;left:0;top:0;bottom:0;width:4px;background:var(--hc,var(--accent))}
.htd-card-h{display:flex;align-items:flex-start;justify-content:space-between;gap:12px;margin-bottom:4px}
.htd-card-t{font-family:var(--disp);font-weight:800;font-size:17px;letter-spacing:-.01em}
.htd-card-meta{font-size:12px;color:var(--muted);margin-bottom:12px}
.htd-skills{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:14px}
.htd-skill{font-size:11.5px;font-weight:600;color:var(--accent-ink);background:var(--accent-soft);padding:4px 10px;border-radius:20px}
/* мини-воронка на карточке списка */
.htd-mini{display:flex;gap:3px;margin-bottom:12px}
.htd-mini-seg{flex:1;height:6px;border-radius:3px;background:var(--hair2);overflow:hidden}
.htd-mini-seg i{display:block;height:100%;background:var(--hc,var(--accent))}
.htd-card-foot{display:flex;align-items:center;justify-content:space-between;font-size:12px;color:var(--muted)}
/* деталь: воронка ступенями */
.htd-funnel{display:flex;flex-direction:column;gap:2px}
.htd-fstep{position:relative;background:var(--surface-2,var(--hair2));border-radius:10px;overflow:hidden}
.htd-fbar{position:absolute;inset:0;background:linear-gradient(90deg,var(--fc1),var(--fc2));opacity:.9;border-radius:10px}
.htd-frow{position:relative;display:flex;align-items:center;justify-content:space-between;padding:14px 18px;z-index:1}
.htd-flabel{display:flex;align-items:center;gap:10px;font-weight:700;font-size:14px;color:#fff}
.htd-fnum{font-family:var(--disp);font-weight:800;font-size:20px;color:#fff;font-variant-numeric:tabular-nums}
.htd-fdot{width:26px;height:26px;border-radius:50%;background:rgba(255,255,255,.22);display:flex;align-items:center;justify-content:center;font-size:12px;font-weight:800}
.htd-fconv{text-align:center;font-size:11px;color:var(--muted);padding:2px 0}
/* пайплайн H-T-D стадии */
.htd-pipe{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin-bottom:16px}
.htd-pipe-cell{border:1px solid var(--hair);border-radius:12px;padding:14px;text-align:center;position:relative}
.htd-pipe-cell.on{border-color:var(--accent);background:var(--accent-soft)}
.htd-pipe-ic{width:38px;height:38px;border-radius:10px;margin:0 auto 8px;display:flex;align-items:center;justify-content:center;background:var(--hair2);color:var(--muted)}
.htd-pipe-cell.on .htd-pipe-ic{background:var(--accent);color:#fff}
.htd-pipe-t{font-weight:700;font-size:13px}
.htd-pipe-d{font-size:11px;color:var(--muted);margin-top:2px}
.htd-modules{display:flex;flex-direction:column;gap:8px}
.htd-mod{display:flex;align-items:center;gap:12px;padding:11px 14px;border:1px solid var(--hair);border-radius:10px}
.htd-mod-n{width:26px;height:26px;border-radius:8px;flex:none;background:var(--accent-soft);color:var(--accent-ink);display:flex;align-items:center;justify-content:center;font-size:12px;font-weight:800}
@media(max-width:720px){.htd-stats{grid-template-columns:repeat(2,1fr)}.htd-pipe{grid-template-columns:1fr}}

/* ===== график/расписание практики (Этап 8) ===== */
.psch{display:flex;gap:4px;margin:14px 0 6px;overflow-x:auto;padding-bottom:4px}
.psch-w{flex:1;min-width:44px;text-align:center}
.psch-bar{height:34px;border-radius:8px;background:var(--hair2);display:flex;align-items:center;justify-content:center;font-size:12px;font-weight:700;color:var(--muted);position:relative;transition:.15s}
.psch-w.done .psch-bar{background:var(--green);color:#fff}
.psch-w.cur .psch-bar{background:var(--accent);color:#fff;box-shadow:0 0 0 3px var(--accent-soft)}
.psch-w.overdue .psch-bar{background:var(--red);color:#fff}
.psch-w.future .psch-bar{background:var(--hair2);color:var(--faint);border:1.5px dashed var(--hair)}
.psch-w .psch-d{font-size:9.5px;color:var(--muted);margin-top:4px;white-space:nowrap}
.psch-legend{display:flex;gap:14px;flex-wrap:wrap;font-size:11.5px;color:var(--muted);margin-top:8px}
.psch-legend span{display:flex;align-items:center;gap:5px}
.psch-legend i{width:10px;height:10px;border-radius:3px;display:block}

/* ===== мини-тред: сквозная коммуникация студент↔ментор↔вуз (Этап 8) ===== */
.pthread{display:flex;flex-direction:column;gap:10px}
.pmsg{display:flex;gap:10px;align-items:flex-start}
.pmsg-av{width:30px;height:30px;border-radius:9px;flex:none;display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:800;color:#fff}
.pmsg-b{flex:1;min-width:0;background:var(--bg);border:1px solid var(--hair2);border-radius:10px;padding:9px 12px}
.pmsg-h{display:flex;gap:8px;align-items:baseline;margin-bottom:2px}
.pmsg-n{font-size:12.5px;font-weight:700}
.pmsg-role{font-size:10.5px;color:var(--muted)}
.pmsg-t{font-size:10.5px;color:var(--faint);margin-left:auto}
.pmsg-x{font-size:13px;line-height:1.5}
.pthread-foot{display:flex;gap:8px;margin-top:12px}
.pthread-foot input{flex:1;height:38px;border:1.5px solid var(--hair);border-radius:10px;padding:0 12px;font-family:inherit;font-size:13px;background:var(--surface);color:var(--ink);outline:none}
.pthread-foot input:focus{border-color:var(--accent)}

/* ===== TASKS модуль ===== */
.tk-filters{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:16px}
.tk-filters select{height:36px;border:1.5px solid var(--hair);border-radius:9px;padding:0 10px;font-family:inherit;font-size:12.5px;background:var(--surface);color:var(--ink);outline:none;cursor:pointer}
.tk-filters select:focus{border-color:var(--accent)}
.tk-card{border:1px solid var(--hair);border-radius:14px;padding:16px;background:var(--surface);cursor:pointer;transition:.15s;display:flex;flex-direction:column;gap:9px}
.tk-card:hover{border-color:var(--accent);transform:translateY(-1px)}
.tk-card-h{display:flex;justify-content:space-between;align-items:flex-start;gap:10px}
.tk-card-t{font-weight:700;font-size:15px;line-height:1.3}
.tk-card-meta{font-size:12px;color:var(--muted)}
.tk-badges{display:flex;gap:6px;flex-wrap:wrap;align-items:center}
.tk-skills{display:flex;gap:6px;flex-wrap:wrap}
.tk-skill{font-size:11px;padding:3px 9px;border-radius:20px;background:var(--accent-soft);color:var(--accent);font-weight:600}
.tk-card-foot{display:flex;justify-content:space-between;align-items:center;font-size:12px;color:var(--muted);border-top:1px solid var(--hair2);padding-top:9px;margin-top:1px}
.tk-over{color:var(--red);font-weight:600}
.tk-funnel{display:grid;grid-template-columns:repeat(5,1fr);gap:8px;margin:8px 0 18px}
.tk-fcell{background:var(--surface);border:1px solid var(--hair);border-radius:11px;padding:12px 8px;text-align:center}
.tk-fcell b{display:block;font-family:var(--disp);font-size:22px;font-weight:800;line-height:1}
.tk-fcell span{font-size:10.5px;color:var(--muted);margin-top:5px;display:block}
.tk-score{display:flex;gap:8px;align-items:center;margin:8px 0}
.tk-score label{font-size:13px;min-width:120px}
.tk-score-btns{display:flex;gap:5px}
.tk-score-btns button{width:34px;height:34px;border:1.5px solid var(--hair);border-radius:8px;background:var(--surface);color:var(--ink);cursor:pointer;font-weight:700;font-size:13px;transition:.12s}
.tk-score-btns button.on{background:var(--accent);color:#fff;border-color:var(--accent)}
.tk-review-box{border:1px solid var(--hair);border-radius:12px;padding:14px;margin-bottom:14px;background:var(--bg)}
.tk-price{font-weight:800;color:var(--green);font-size:13.5px;white-space:nowrap}
.tk-escrow-steps{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-top:6px}
.tk-es{text-align:center;font-size:11.5px;font-weight:600;color:var(--muted);padding:9px 4px;border-radius:9px;background:var(--hair2);border:1.5px solid transparent;position:relative}
.tk-es.done{background:var(--accent-soft);color:var(--accent-ink);border-color:var(--accent)}
.tk-escrow{border:1px solid var(--hair)}
.tk-stars{display:inline-flex;gap:1px;color:var(--hair);font-size:13px;letter-spacing:1px}
.tk-star.on,.tk-stars .tk-star.on{color:#F5A623}
.tk-stars .tk-star{color:var(--hair)}
.tk-stars.on,.tk-star{color:var(--hair)}
.tk-fl-card{border:1px solid var(--hair);border-radius:14px;padding:16px;background:var(--surface);cursor:pointer;transition:.15s}
.tk-fl-card:hover{border-color:var(--accent);transform:translateY(-1px)}
.tk-fl-h{display:flex;align-items:center;gap:11px}
.tk-fl-av{width:40px;height:40px;border-radius:11px;background:var(--accent);color:#fff;display:flex;align-items:center;justify-content:center;font-weight:800;font-size:14px;flex:none}
.tk-fl-name{font-weight:700;font-size:14.5px;line-height:1.2}
.tk-fl-title{font-size:12px;color:var(--muted)}
.tk-fl-rate{display:flex;align-items:center;gap:7px;margin-top:10px;font-size:13px}
.tk-fl-rate b{font-weight:800}
.tk-portf{display:flex;flex-direction:column;gap:8px;margin-top:10px}
.tk-portf-item{padding:10px 12px;border:1px solid var(--hair);border-radius:10px;font-size:13px;background:var(--bg)}
.tk-star{font-size:13px}

/* ===== обучающий центр ===== */
.help-hero{border:1px solid var(--hair);background:var(--accent-soft)}
.help-hero-ic{width:44px;height:44px;border-radius:12px;background:var(--accent);color:#fff;display:flex;align-items:center;justify-content:center;flex:none}
.help-hero-ic svg{width:22px;height:22px}
.help-guides{display:flex;flex-direction:column;gap:10px}
.help-card{display:flex;align-items:flex-start;gap:13px;padding:15px;border:1px solid var(--hair);border-radius:13px;background:var(--surface);cursor:pointer;transition:.15s}
.help-card:hover{border-color:var(--accent);transform:translateY(-1px)}
.help-card-ic{width:38px;height:38px;border-radius:10px;background:var(--accent-soft);color:var(--accent);display:flex;align-items:center;justify-content:center;flex:none}
.help-card-ic svg{width:18px;height:18px}
.help-card-t{font-weight:700;font-size:14.5px;margin-bottom:3px}
.help-card-x{font-size:13px;color:var(--muted);line-height:1.5}
.help-card-tip{font-size:12px;color:var(--accent-ink);margin-top:7px;display:flex;align-items:center;gap:5px}
.help-card-tip svg{width:13px;height:13px;flex:none}
.help-card-go{color:var(--faint);flex:none;align-self:center}
.help-card-go svg{width:17px;height:17px}
.help-faq{display:flex;flex-direction:column;gap:8px}
.help-q{border:1px solid var(--hair);border-radius:11px;padding:13px 15px;background:var(--surface);cursor:pointer;transition:.12s}
.help-q:hover{border-color:var(--accent)}
.help-q-h{display:flex;justify-content:space-between;align-items:center;gap:12px;font-weight:600;font-size:14px}
.help-q-ch{font-size:19px;color:var(--accent);font-weight:400;flex:none;line-height:1}
.help-q-a{font-size:13px;color:var(--muted);line-height:1.6;margin-top:9px}

/* ===== Match Score ===== */
.ms-card{border:1px solid var(--hair);border-radius:14px;padding:16px;background:var(--surface);cursor:pointer;transition:.15s}
.ms-card:hover{border-color:var(--accent);transform:translateY(-1px)}
.ms-card-h{display:flex;justify-content:space-between;align-items:flex-start;gap:12px}
.ms-card-t{font-weight:700;font-size:15px}
.ms-card-meta{font-size:12px;color:var(--muted);margin-top:2px}
.ms-ring{flex:none;width:58px;height:58px;border-radius:50%;display:flex;flex-direction:column;align-items:center;justify-content:center;border:3px solid var(--hair2)}
.ms-ring b{font-size:16px;font-weight:800;line-height:1}
.ms-ring span{font-size:9px;color:var(--muted);text-transform:uppercase;letter-spacing:.03em}
.ms-ring.ms-hi{border-color:var(--green);color:var(--green)}
.ms-ring.ms-mid{border-color:var(--amber);color:var(--amber)}
.ms-ring.ms-lo{border-color:var(--muted)}
.ms-ring-lg{width:76px;height:76px;border-width:4px}
.ms-ring-lg b{font-size:21px}
.ms-skills{display:flex;gap:6px;flex-wrap:wrap;margin:12px 0}
.ms-chip{font-size:11.5px;padding:4px 10px;border-radius:20px;font-weight:600;display:inline-flex;align-items:center;gap:4px}
.ms-chip svg{width:12px;height:12px}
.ms-ok{background:var(--green-soft,rgba(15,158,117,.12));color:var(--green)}
.ms-half{background:var(--amber-soft);color:var(--amber-ink)}
.ms-gap{background:var(--hair2);color:var(--muted)}
.ms-expl{font-size:12.5px;color:var(--muted);line-height:1.5;border-top:1px solid var(--hair2);padding-top:10px}
.ms-detail .ms-bars{display:flex;flex-direction:column;gap:8px}
.ms-bar-row{display:flex;justify-content:space-between;align-items:center;gap:12px;padding:8px 0;border-bottom:1px solid var(--hair2)}
.ms-bar-l{font-size:13.5px;font-weight:500}
.ms-gap-box{margin-top:14px;padding:13px 15px;border-radius:11px;background:var(--accent-soft);color:var(--accent-ink);font-size:13px;line-height:1.55;display:flex;gap:8px;align-items:flex-start}
.ms-gap-box svg{width:16px;height:16px;flex:none;margin-top:2px}
.ms-gap-ok{background:var(--green-soft,rgba(15,158,117,.1));color:var(--green)}

/* ===== career.edu.uz sync ===== */
.ce-hero{border:1px solid var(--hair);background:var(--accent-soft)}
.ce-ic{width:42px;height:42px;border-radius:11px;background:var(--accent);color:#fff;display:flex;align-items:center;justify-content:center;flex:none}
.ce-ic svg{width:21px;height:21px}
.ce-priv{border:1px solid var(--hair)}

/* ===== E-imzo флоу ===== */
.eimzo-cert{display:flex;align-items:center;gap:11px;padding:12px;border:1px solid var(--hair);border-radius:11px;cursor:pointer;margin-bottom:8px;transition:.12s}
.eimzo-cert:hover{border-color:var(--accent);background:var(--accent-soft)}
.eimzo-cert svg{width:18px;height:18px;color:var(--accent)}
.eimzo-spin{width:38px;height:38px;border:3px solid var(--hair2);border-top-color:var(--accent);border-radius:50%;margin:0 auto;animation:eimzo-rot .8s linear infinite}
@keyframes eimzo-rot{to{transform:rotate(360deg)}}

/* ===== подписка вуза ===== */
.sub-plan{display:flex;flex-direction:column;border:1px solid var(--hair)}
.sub-hl{border:2px solid var(--accent)}
.sub-price{font-family:var(--disp);font-weight:800;font-size:26px;margin:12px 0 14px}
.sub-price span{font-size:13px;font-weight:500;color:var(--muted)}
.sub-feats{display:flex;flex-direction:column;gap:9px}
.sub-feat{display:flex;align-items:flex-start;gap:9px;font-size:13px;line-height:1.4}
.sub-feat svg{width:16px;height:16px;flex:none;margin-top:1px}
.sub-feat.on{color:var(--ink)}
.sub-feat.on svg{color:var(--green)}
.sub-feat.off{color:var(--faint)}
.sub-feat.off svg{color:var(--faint)}
.ms-order-sel{height:38px;border:1.5px solid var(--hair);border-radius:10px;padding:0 12px;font-family:inherit;font-size:13px;background:var(--surface);color:var(--ink);outline:none;cursor:pointer;max-width:260px}
.ms-order-sel:focus{border-color:var(--accent)}
.ord-skills{display:flex;gap:8px;flex-wrap:wrap}
.ord-skill{font-size:12.5px;padding:6px 12px;border-radius:20px;border:1.5px solid var(--hair);cursor:pointer;transition:.12s;display:inline-flex;align-items:center;gap:5px;user-select:none}
.ord-skill:hover{border-color:var(--accent)}
.ord-skill.on{background:var(--accent-soft);border-color:var(--accent);color:var(--accent-ink);font-weight:600}
.ord-skill svg{width:13px;height:13px}
.trk-mods{display:flex;flex-direction:column;gap:8px}
.trk-mod{display:flex;align-items:center;gap:12px;padding:12px 14px;border:1px solid var(--hair);border-radius:11px;background:var(--surface)}
.trk-mod.done{background:var(--bg)}
.trk-mod.cur{border-color:var(--accent);box-shadow:0 0 0 2px var(--accent-soft)}
.trk-mod-ic{width:28px;height:28px;border-radius:8px;background:var(--hair2);color:var(--muted);display:flex;align-items:center;justify-content:center;font-weight:700;font-size:13px;flex:none}
.trk-mod.done .trk-mod-ic{background:var(--green);color:#fff}
.trk-mod.cur .trk-mod-ic{background:var(--accent);color:#fff}
.trk-mod-ic svg{width:15px;height:15px}
.trk-mod-t{font-weight:600;font-size:14px}
.trk-dot{width:8px;height:8px;border-radius:50%;background:#fff}
.trk-enr{display:flex;align-items:center;gap:12px;padding:10px 0;border-bottom:1px solid var(--hair2)}
.trk-enr:last-child{border-bottom:none}
.trk-enr-av{width:34px;height:34px;border-radius:9px;background:var(--accent);color:#fff;display:flex;align-items:center;justify-content:center;font-weight:700;font-size:12px;flex:none}
.trk-enr-n{font-weight:600;font-size:14px}
.trk-enr-p{font-size:13px;font-weight:700;flex:none;min-width:44px;text-align:right}

/* trajectory steps */
.traj{display:flex;flex-direction:column;gap:10px}
.tstep{display:flex;align-items:center;gap:14px;padding:13px 16px;border:1px solid var(--hair);border-radius:11px;background:var(--surface);transition:.15s;cursor:pointer}
.tstep:hover{border-color:var(--accent)}
.tstep .tn{width:32px;height:32px;border-radius:50%;flex:none;display:flex;align-items:center;justify-content:center;font-size:13px;font-weight:700;background:var(--hair2);color:var(--muted)}
.tstep.done .tn{background:var(--green);color:#fff}
.tstep.cur{border-color:var(--accent);background:var(--accent-soft)}
.tstep.cur .tn{background:var(--accent);color:#fff}
.tstep .tt{font-weight:600;font-size:14px}
.tstep .td{font-size:12px;color:var(--muted)}
.tstep .tstat{margin-left:auto;font-size:11.5px;font-weight:600}

/* simulation / job cards */
.cards{display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:16px}
.simcard{background:var(--surface);border:1px solid var(--hair);border-radius:var(--radius);padding:18px;transition:.15s;cursor:pointer;display:flex;flex-direction:column;gap:10px}
.simcard:hover{border-color:var(--accent);box-shadow:0 4px 16px rgba(0,0,0,.06);transform:translateY(-1px)}
.simcard .sc-top{display:flex;align-items:flex-start;justify-content:space-between;gap:10px}
.simcard .sc-t{font-size:15px;font-weight:600;letter-spacing:-.01em;line-height:1.3}
.simcard .sc-meta{font-size:12px;color:var(--muted)}
.simcard .sc-d{font-size:13px;color:var(--muted);line-height:1.5}
.simcard .sc-tags{display:flex;flex-wrap:wrap;gap:6px}
.simcard .sc-foot{display:flex;align-items:center;justify-content:space-between;margin-top:auto;padding-top:6px}
.match{display:flex;align-items:center;gap:7px;font-size:12px;font-weight:600;color:var(--accent-ink)}
.match .mbar{width:52px;height:6px;background:var(--hair2);border-radius:4px;overflow:hidden}
.match .mbar i{display:block;height:100%;background:var(--accent)}

/* kanban */
.kanban{display:grid;grid-template-columns:repeat(4,1fr);gap:14px}
.kcol{background:var(--hair2);border-radius:12px;padding:12px;min-height:200px}
.kcol h4{font-size:12.5px;font-weight:600;color:var(--muted);margin-bottom:10px;display:flex;align-items:center;justify-content:space-between}
.kcol h4 span{background:var(--surface);padding:1px 7px;border-radius:20px;font-size:11px}
.kcard{background:var(--surface);border:1px solid var(--hair);border-radius:9px;padding:11px;margin-bottom:8px;cursor:grab;transition:.12s}
.kcard:hover{border-color:var(--accent);box-shadow:0 2px 8px rgba(0,0,0,.05)}
.kcard .kn{font-size:13px;font-weight:600}
.kcard .kr{font-size:11.5px;color:var(--muted)}
.kcard .kfoot{display:flex;align-items:center;gap:6px;margin-top:8px}

/* table */
.tbl{width:100%;border-collapse:collapse}
.tbl th{text-align:left;font-size:11.5px;font-weight:600;color:var(--muted);text-transform:uppercase;letter-spacing:.04em;padding:10px 12px;border-bottom:1px solid var(--hair)}
.tbl td{padding:12px;font-size:13.5px;border-bottom:1px solid var(--hair2)}
.tbl tr:hover td{background:var(--hair2)}
.tbl tr:last-child td{border-bottom:none}
.tbl .nm{font-weight:600}

/* gap matrix */
.matrix{display:grid;gap:5px}
.mcell{aspect-ratio:1.6;border-radius:7px;display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:600;color:#fff}
.mhead{font-size:11px;font-weight:600;color:var(--muted);display:flex;align-items:center;justify-content:center;text-align:center}
.mrow-label{font-size:12px;font-weight:500;display:flex;align-items:center;padding-right:8px}

/* diagnostics */
.diag-q{background:var(--surface);border:1px solid var(--hair);border-radius:14px;padding:24px}
.diag-q .qn{font-size:12px;font-weight:600;color:var(--accent-ink);margin-bottom:8px}
.diag-q .qt{font-size:18px;font-weight:600;margin-bottom:18px;letter-spacing:-.01em}
.opts{display:flex;flex-direction:column;gap:9px}
.opt{padding:13px 15px;border:1.5px solid var(--hair);border-radius:11px;font-size:14px;transition:.12s;text-align:left}
.opt:hover{border-color:var(--accent);background:var(--accent-soft)}
.opt.on{border-color:var(--accent);background:var(--accent-soft);font-weight:600}

/* resume split */
.split{display:grid;grid-template-columns:1fr 1fr;gap:16px}
.resume-prev{background:var(--surface);border:1px solid var(--hair);border-radius:12px;padding:26px;min-height:400px}
.resume-prev .rh{font-size:22px;font-weight:700}
.resume-prev .rsub{color:var(--accent-ink);font-weight:600;font-size:14px;margin-bottom:14px}
.resume-prev .rsec{font-size:11px;font-weight:600;text-transform:uppercase;letter-spacing:.05em;color:var(--muted);margin:16px 0 6px;border-bottom:1px solid var(--hair);padding-bottom:4px}
.resume-prev p{font-size:13px;color:var(--ink);line-height:1.6}

/* chat */
.chat{display:grid;grid-template-columns:240px 1fr;border:1px solid var(--hair);border-radius:14px;overflow:hidden;background:var(--surface);height:520px}
.chat-side{border-right:1px solid var(--hair);overflow-y:auto}
.chat-c{padding:12px 14px;border-bottom:1px solid var(--hair2);cursor:pointer;transition:.12s}
.chat-c:hover,.chat-c.on{background:var(--accent-soft)}
.chat-c .cn{font-size:13px;font-weight:600}
.chat-c .cp{font-size:11.5px;color:var(--muted);white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.chat-main{display:flex;flex-direction:column}
.chat-msgs{flex:1;padding:18px;overflow-y:auto;display:flex;flex-direction:column;gap:12px}
.msg{max-width:70%;padding:10px 13px;border-radius:12px;font-size:13.5px;line-height:1.45}
.msg.them{background:var(--hair2);align-self:flex-start;border-bottom-left-radius:3px}
.msg.me{background:var(--accent);color:#fff;align-self:flex-end;border-bottom-right-radius:3px}
.chat-input{border-top:1px solid var(--hair);padding:12px;display:flex;gap:8px}
.chat-input input{flex:1;height:40px;border:1px solid var(--hair);border-radius:10px;padding:0 12px;font-size:14px;font-family:inherit;outline:none}
.chat-input input:focus{border-color:var(--accent)}

/* notifications */
.notif{display:flex;gap:12px;padding:14px 16px;border:1px solid var(--hair);border-radius:11px;margin-bottom:10px;background:var(--surface)}
.notif.unread{border-left:3px solid var(--accent)}
.notif .ni{width:34px;height:34px;border-radius:9px;flex:none;display:flex;align-items:center;justify-content:center;font-size:15px}

/* modal (command palette / search) */
.overlay{position:fixed;inset:0;background:rgba(20,20,26,.4);display:flex;align-items:flex-start;justify-content:center;padding-top:14vh;z-index:50}
.palette{background:var(--surface);border-radius:14px;width:100%;max-width:520px;overflow:hidden;box-shadow:0 20px 60px rgba(0,0,0,.25)}
.palette input{width:100%;height:52px;border:none;border-bottom:1px solid var(--hair);padding:0 18px;font-size:15px;font-family:inherit;outline:none}
.palette .presults{max-height:340px;overflow-y:auto;padding:8px}
.pres{display:flex;align-items:center;gap:12px;padding:10px 12px;border-radius:9px;font-size:13.5px}
.pres:hover{background:var(--accent-soft)}
.pres .pk{margin-left:auto;font-size:11px;color:var(--faint)}

/* settings */
.set-row{display:flex;align-items:center;justify-content:space-between;padding:14px 0;border-bottom:1px solid var(--hair2)}
.set-row:last-child{border-bottom:none}
.set-row .st{font-size:14px;font-weight:500}
.set-row .sd{font-size:12.5px;color:var(--muted)}
.toggle{width:42px;height:24px;background:var(--hair);border-radius:14px;position:relative;transition:.2s;flex:none}
.toggle.on{background:var(--accent)}
.toggle::after{content:"";position:absolute;top:2px;left:2px;width:20px;height:20px;background:#fff;border-radius:50%;transition:.2s}
.toggle.on::after{transform:translateX(18px)}

.section-label{font-size:11px;font-weight:600;letter-spacing:.05em;text-transform:uppercase;color:var(--faint);margin:24px 0 12px}
.empty{text-align:center;padding:50px 20px;color:var(--muted)}
.empty .ei{font-size:32px;margin-bottom:10px}
.empty h3{font-size:16px;font-weight:600;color:var(--ink);margin-bottom:4px}

.back-link{display:inline-flex;align-items:center;gap:6px;font-size:13px;color:var(--muted);font-weight:500;margin-bottom:14px}
.back-link:hover{color:var(--accent)}

/* ---------- public / marketing ---------- */
#scr-public{min-height:100%;display:flex;flex-direction:column}
.pub-head{border-bottom:1px solid var(--hair);background:var(--surface);position:sticky;top:0;z-index:10}
.pub-inner{max-width:1080px;margin:0 auto;padding:14px 24px;display:flex;align-items:center;gap:24px}
.pub-nav{display:flex;gap:20px;margin-right:auto}
.pub-icon-btn{display:inline-flex;align-items:center;justify-content:center;min-width:38px;height:38px;padding:0 10px;font-family:var(--disp);font-weight:700;font-size:13px;color:var(--ink);background:transparent;border:1px solid var(--hair);border-radius:10px;cursor:pointer;transition:background .16s,border-color .16s}
.pub-icon-btn:hover{background:var(--surface-2,rgba(0,0,0,.04));border-color:var(--hair2,var(--hair))}
.pub-icon-btn svg{display:block}
.pub-icon-btn .ti-moon{display:none}
body.dark .pub-icon-btn .ti-sun{display:none}
body.dark .pub-icon-btn .ti-moon{display:block}
.pub-nav a{font-size:13.5px;font-weight:500;color:var(--muted);cursor:pointer;transition:.12s}
.pub-nav a:hover{color:var(--ink)}
.pub-foot{border-top:1px solid var(--hair);background:var(--surface);margin-top:auto}
/* ===== content additions ===== */
.cl-logo{display:inline-flex;align-items:center;gap:9px}
.cl-logo i{font-style:normal;width:26px;height:26px;border-radius:8px;background:var(--lc);color:#fff;font-family:var(--disp);font-weight:800;font-size:13px;display:inline-flex;align-items:center;justify-content:center}
.cl-logos:hover .cl-logos-track{animation-play-state:paused}
.cl-stat-note{font-size:12px;color:var(--faint);margin-top:10px}
.cl-demo-note{font-size:12px;color:var(--faint);margin-top:10px;text-align:right}
.cl-how{display:grid;grid-template-columns:repeat(4,1fr);gap:18px}
/* ===== pin-стек «Как это работает» ===== */
.cl-howpin{position:relative;height:340vh;max-width:1240px;margin:0 auto;padding:0 24px}
.cl-howpin-stage{position:sticky;top:0;height:100vh;display:flex;flex-direction:column;align-items:center;justify-content:center;overflow:hidden}
.cl-howpin-stage:before{content:"";position:absolute;inset:0;background-image:linear-gradient(color-mix(in oklab,var(--yy) 8%,transparent) 1px,transparent 1px),linear-gradient(90deg,color-mix(in oklab,var(--yy) 8%,transparent) 1px,transparent 1px);background-size:64px 64px;-webkit-mask-image:radial-gradient(ellipse 60% 55% at 50% 50%,#000 20%,transparent 72%);mask-image:radial-gradient(ellipse 60% 55% at 50% 50%,#000 20%,transparent 72%);opacity:.7;pointer-events:none}
.cl-howstack{position:relative;width:min(900px,94%);height:400px}
.cl-hcard{position:absolute;left:0;right:0;top:0;background:var(--surface);border:1.5px solid var(--hc);border-radius:26px;padding:48px 52px;min-height:380px;overflow:hidden;box-shadow:0 30px 80px rgba(10,10,25,.35),0 0 0 1px color-mix(in oklab,var(--hc) 20%,transparent);transition:transform .55s cubic-bezier(.16,1,.3,1),opacity .55s;will-change:transform,opacity}
.cl-hcard:before{content:"";position:absolute;top:0;left:0;right:0;height:4px;background:var(--hc)}
.cl-hcard:after{content:"";position:absolute;top:-40%;right:-10%;width:420px;height:420px;background:radial-gradient(circle,color-mix(in oklab,var(--hc) 30%,transparent),transparent 65%);filter:blur(40px);opacity:.5;pointer-events:none}
.cl-hcard-ghost{position:absolute;bottom:-40px;right:20px;font-family:var(--mono);font-weight:800;font-size:280px;line-height:1;color:var(--hc);opacity:.06;pointer-events:none;user-select:none}
.cl-hcard-body{position:relative;z-index:2;display:grid;grid-template-columns:1fr 1fr;gap:40px;align-items:center;height:100%;min-height:284px}
.cl-hcard-col{display:flex;flex-direction:column;justify-content:center}
.cl-hcard-num{width:66px;height:66px;border-radius:18px;background:color-mix(in oklab,var(--hc) 14%,transparent);border:1.5px solid var(--hc);color:var(--hc);display:flex;align-items:center;justify-content:center;font-family:var(--mono);font-weight:700;font-size:22px;margin-bottom:24px}
.cl-hcard-t{font-family:var(--disp);font-weight:800;font-size:38px;letter-spacing:-.02em;color:var(--yy-dark);line-height:1.05}
.cl-hcard-d{font-size:18px;color:var(--muted);line-height:1.65}
.cl-howdots{display:flex;gap:9px;margin-top:44px}
.cl-howdots span{width:8px;height:8px;border-radius:50%;background:var(--hair);transition:.3s}
.cl-howdots span.on{width:26px;border-radius:4px;background:var(--yy)}
.cl-how-mob{display:none}
@media(prefers-reduced-motion:reduce){.cl-howpin{height:auto}.cl-howpin-stage{position:static;height:auto;display:none}.cl-how-mob{display:grid}}
@media(max-width:900px){.cl-hcard-body{grid-template-columns:1fr;gap:20px;align-items:start}.cl-hcard-t{font-size:30px}.cl-hcard-ghost{font-size:200px}}
@media(max-width:760px){.cl-howpin{height:auto;padding:0}.cl-howpin-stage{display:none}.cl-how-mob{display:grid;grid-template-columns:1fr;gap:14px}}
.cl-howstep{position:relative;padding:22px;background:var(--surface);border:1px solid var(--hair);border-radius:18px}
.cl-hownum{font-family:var(--mono);font-weight:700;font-size:13px;color:var(--hc)}
.cl-howline{height:3px;border-radius:2px;background:var(--hc);width:34px;margin:12px 0 14px;transform-origin:left;transform:scaleX(0);transition:transform .7s cubic-bezier(.2,.8,.2,1) .3s}
.cl-howstep.in .cl-howline{transform:scaleX(1)}
.cl-howstep h3{font-family:var(--disp);font-weight:800;font-size:17px;color:var(--yy-dark);letter-spacing:-.01em}
.cl-howstep p{font-size:13px;color:var(--muted);line-height:1.55;margin-top:8px}
@media(max-width:900px){.cl-how{grid-template-columns:1fr 1fr}}
@media(max-width:560px){.cl-how{grid-template-columns:1fr}}
.cl-quotes{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}
.cl-quote{background:var(--surface);border:1px solid var(--hair);border-radius:18px;padding:24px;margin:0}
.cl-quote blockquote{font-size:15px;line-height:1.6;color:var(--ink);margin:0}
.cl-quote figcaption{font-size:12.5px;color:var(--muted);margin-top:14px}
@media(max-width:860px){.cl-quotes{grid-template-columns:1fr}}
.cl-faq{max-width:760px;margin:0 auto}
.cl-faq-item{border:1px solid var(--hair);border-radius:14px;background:var(--surface);margin-bottom:10px;overflow:hidden}
.cl-faq-item summary{display:flex;align-items:center;justify-content:space-between;gap:12px;cursor:pointer;list-style:none;padding:16px 20px;font-family:var(--disp);font-weight:700;font-size:15px;color:var(--yy-dark)}
.cl-faq-item summary::-webkit-details-marker{display:none}
.cl-faq-x{color:var(--yy);font-weight:400;transition:transform .25s}
.cl-faq-item[open] .cl-faq-x{transform:rotate(45deg)}
.cl-faq-item p{padding:0 20px 16px;font-size:14px;line-height:1.6;color:var(--muted)}
.cl-lead{display:flex;flex-direction:column;align-items:flex-end;gap:8px}
.cl-lead-or{font-size:12px;color:rgba(255,255,255,.55)}
.cl-lead-row{display:flex;gap:8px}
.cl-lead-row input{border:none;border-radius:12px;padding:12px 14px;font-size:14px;width:180px;background:rgba(255,255,255,.14);color:#fff}
.cl-lead-row input::placeholder{color:rgba(255,255,255,.5)}
@media(max-width:640px){.cl-lead{align-items:center}}

/* ===== Финальный CTA: анимированный путь до оффера ===== */
.cl-finale{position:relative;background:#0B0F26;border-radius:28px;padding:56px 48px 48px;overflow:hidden}
body.yy.dark .cl-finale{background:#080A16;border:1px solid var(--hair)}
.cl-finale-glow{position:absolute;right:-120px;top:-120px;width:420px;height:420px;border-radius:50%;background:radial-gradient(circle,rgba(43,68,255,.28),transparent 62%);pointer-events:none}
.cl-finale-head{position:relative;max-width:640px;margin:0 auto 40px;text-align:center}
.cl-finale-eyebrow{font-family:var(--disp);font-size:12px;font-weight:700;letter-spacing:.14em;text-transform:uppercase;color:var(--yy);margin-bottom:14px}
.cl-finale-h{font-family:var(--disp);font-weight:800;font-size:clamp(28px,4vw,44px);line-height:1.05;color:#fff;letter-spacing:-.02em}
.cl-finale-sub{font-size:clamp(14px,1.6vw,17px);color:rgba(255,255,255,.66);margin-top:14px;line-height:1.5}
/* путь в финальном CTA — уникальный префикс, чтобы не сталкиваться с .cl-path (карточки шагов) */
.cl-finpath{position:relative;max-width:760px;margin:0 auto 44px}
.cl-finpath svg{display:block;width:100%;height:64px;overflow:visible}
.cl-finpath-track{fill:none;stroke:rgba(255,255,255,.12);stroke-width:2}
.cl-finpath-live{fill:none;stroke:url(#clPathGrad);stroke-width:2.5;stroke-linecap:round;stroke-dasharray:var(--len);stroke-dashoffset:var(--len);transition:stroke-dashoffset 2.1s cubic-bezier(.65,.02,.3,1)}
.cl-finpath.on .cl-finpath-live{stroke-dashoffset:0}
.cl-finpath-steps{position:absolute;inset:0;display:flex;justify-content:space-between;align-items:center}
.cl-finstep{display:flex;flex-direction:column;align-items:center;gap:10px;opacity:0;transform:translateY(6px);transition:opacity .4s,transform .4s}
.cl-finpath.on .cl-finstep{opacity:1;transform:none}
.cl-findot{width:15px;height:15px;border-radius:50%;background:#0B0F26;border:2px solid rgba(255,255,255,.22);position:relative;z-index:2;transition:border-color .3s,background .3s,box-shadow .3s}
body.yy.dark .cl-findot{background:#080A16}
.cl-finpath.on .cl-finstep.lit .cl-findot{border-color:var(--c);background:var(--c);box-shadow:0 0 0 5px color-mix(in srgb,var(--c) 22%,transparent)}
.cl-finpath.on .cl-finstep.goal .cl-findot{animation:clGoal 1.6s ease-in-out .3s infinite}
@keyframes clGoal{0%,100%{box-shadow:0 0 0 5px color-mix(in srgb,var(--c) 26%,transparent)}50%{box-shadow:0 0 0 12px color-mix(in srgb,var(--c) 4%,transparent)}}
.cl-finlabel{font-family:var(--disp);font-size:11.5px;font-weight:700;color:rgba(255,255,255,.5);letter-spacing:.02em;white-space:nowrap;transition:color .3s}
.cl-finpath.on .cl-finstep.lit .cl-finlabel{color:#fff}
/* действия */
.cl-finale-act{position:relative;display:flex;flex-direction:column;align-items:center;gap:16px}
.cl-finale-primary{font-family:var(--disp);font-weight:800;font-size:16px;color:var(--yy-ink);background:var(--yy);border:none;border-radius:14px;padding:17px 40px;cursor:pointer;display:inline-flex;align-items:center;gap:10px;transition:transform .14s,box-shadow .14s,filter .14s;box-shadow:0 8px 28px rgba(43,68,255,.34)}
.cl-finale-primary:hover{transform:translateY(-2px);box-shadow:0 12px 36px rgba(43,68,255,.46)}
.cl-finale-primary .cl-arr{transition:transform .2s}
.cl-finale-primary:hover .cl-arr{transform:translateX(4px)}
.cl-finale-meta{font-size:13px;color:rgba(255,255,255,.5)}
.cl-finale-wait{position:relative;display:flex;align-items:center;gap:6px;margin-top:6px;padding:6px;background:rgba(255,255,255,.06);border:1px solid rgba(255,255,255,.12);border-radius:100px;transition:border-color .2s,box-shadow .2s}
.cl-finale-wait:focus-within{border-color:rgba(43,68,255,.6);box-shadow:0 0 0 4px rgba(43,68,255,.18)}
/* селектор кода страны */
.cl-cc{position:relative;flex:none}
.cl-cc-btn{display:inline-flex;align-items:center;gap:6px;font-family:var(--disp);font-weight:700;font-size:15px;color:#fff;background:rgba(255,255,255,.06);border:none;border-radius:100px;padding:11px 12px 11px 14px;cursor:pointer;transition:background .16s;font-variant-numeric:tabular-nums}
.cl-cc-btn:hover{background:rgba(255,255,255,.12)}
.cl-cc-flag{font-size:16px;line-height:1}
.cl-cc-arr{opacity:.6;transition:transform .2s}
.cl-cc.open .cl-cc-arr{transform:rotate(180deg)}
.cl-cc-menu{position:absolute;bottom:calc(100% + 10px);left:0;min-width:250px;background:#12162E;border:1px solid rgba(255,255,255,.14);border-radius:16px;padding:6px;box-shadow:0 20px 50px rgba(0,0,0,.5);opacity:0;transform:translateY(6px);pointer-events:none;transition:opacity .18s,transform .18s;z-index:20}
.cl-cc.open .cl-cc-menu{opacity:1;transform:none;pointer-events:auto}
.cl-cc-item{display:flex;align-items:center;gap:10px;width:100%;background:none;border:none;border-radius:10px;padding:10px 12px;cursor:pointer;text-align:left;transition:background .14s}
.cl-cc-item:hover{background:rgba(255,255,255,.08)}
.cl-cc-name{flex:1;font-size:13.5px;color:rgba(255,255,255,.82)}
.cl-cc-num{font-family:var(--disp);font-weight:700;font-size:13.5px;color:rgba(255,255,255,.55);font-variant-numeric:tabular-nums}
.cl-finale-wait input{border:none;border-radius:100px;padding:12px 18px 12px 6px;font-size:15px;font-variant-numeric:tabular-nums;letter-spacing:.02em;width:170px;background:transparent;color:#fff;transition:background .2s}
.cl-finale-wait input:focus{outline:none}
.cl-finale-wait input::placeholder{color:rgba(255,255,255,.4)}
.cl-finale-wait button{font-family:var(--disp);font-weight:700;font-size:14.5px;color:#fff;background:var(--yy);border:none;border-radius:100px;padding:12px 24px;cursor:pointer;display:inline-flex;align-items:center;gap:8px;transition:transform .14s,box-shadow .14s,opacity .2s,filter .2s;box-shadow:0 6px 18px rgba(43,68,255,.36)}
.cl-finale-wait button:hover{transform:translateY(-1px);box-shadow:0 10px 26px rgba(43,68,255,.48)}
.cl-finale-wait button:disabled,.cl-finale-wait.pending button{opacity:.5;filter:grayscale(.4);cursor:default;transform:none;box-shadow:none}
.cl-finale-wait button .cl-wchk{width:16px;height:16px;opacity:0;transition:opacity .2s}
/* состояние успеха: пилл превращается в подтверждение */
.cl-finale-wait.done{border-color:rgba(16,185,129,.5);box-shadow:0 0 0 4px rgba(16,185,129,.14);justify-content:center;padding:12px 26px;pointer-events:none}
.cl-finale-wait.done input,.cl-finale-wait.done button{display:none}
.cl-finale-wait-ok{display:none;align-items:center;gap:10px;color:#fff;font-family:var(--disp);font-weight:700;font-size:14.5px;white-space:nowrap}
.cl-finale-wait.done .cl-finale-wait-ok{display:inline-flex;animation:cl-wok .4s cubic-bezier(.2,.9,.3,1.2)}
.cl-finale-wait-ok .cl-wok-ic{width:24px;height:24px;flex:none;border-radius:50%;background:#10B981;display:inline-flex;align-items:center;justify-content:center}
.cl-finale-wait-ok svg{width:14px;height:14px;stroke:#fff;stroke-width:3;fill:none;stroke-linecap:round;stroke-linejoin:round;stroke-dasharray:20;stroke-dashoffset:20;animation:cl-wcheck .45s .12s cubic-bezier(.6,0,.4,1) forwards}
@keyframes cl-wok{from{opacity:0;transform:scale(.94)}to{opacity:1;transform:none}}
@keyframes cl-wcheck{to{stroke-dashoffset:0}}
.cl-finale-wait-label{width:100%;text-align:center;font-size:12px;color:rgba(255,255,255,.4);margin-top:14px;margin-bottom:2px}

/* ===== усиление: сетка-подложка + второе свечение ===== */
.cl-finale-grid{position:absolute;inset:0;background-image:linear-gradient(rgba(255,255,255,.04) 1px,transparent 1px),linear-gradient(90deg,rgba(255,255,255,.04) 1px,transparent 1px);background-size:44px 44px;mask-image:radial-gradient(circle at 50% 30%,#000,transparent 72%);-webkit-mask-image:radial-gradient(circle at 50% 30%,#000,transparent 72%);pointer-events:none}
.cl-finale-glow2{position:absolute;left:-140px;bottom:-160px;width:460px;height:460px;border-radius:50%;background:radial-gradient(circle,rgba(16,185,129,.16),transparent 64%);pointer-events:none}

/* ===== переключатель ролей ===== */
.cl-roletabs{display:inline-flex;gap:4px;padding:5px;background:rgba(255,255,255,.07);border:1px solid rgba(255,255,255,.1);border-radius:100px;margin-bottom:6px}
.cl-roletab{font-family:var(--disp);font-weight:700;font-size:13.5px;color:rgba(255,255,255,.62);background:none;border:none;border-radius:100px;padding:9px 20px;cursor:pointer;transition:color .18s,background .18s;display:inline-flex;align-items:center;gap:7px}
.cl-roletab:hover{color:#fff}
.cl-roletab.on{color:#fff;background:var(--rc,var(--yy))}
.cl-roletab svg{width:15px;height:15px}
/* панель роли: подводка меняется под выбор */
.cl-rolepane{min-height:26px;font-size:14.5px;color:rgba(255,255,255,.72);margin:2px 0 4px;transition:opacity .2s}
.cl-rolepane b{color:#fff;font-weight:600}
/* первичная кнопка перекрашивается под роль */
.cl-finale-primary{--pc:var(--yy);background:var(--pc);box-shadow:0 8px 28px color-mix(in srgb,var(--pc) 40%,transparent)}
.cl-finale-primary:hover{box-shadow:0 12px 36px color-mix(in srgb,var(--pc) 52%,transparent)}
@media(max-width:680px){
  .cl-finale{padding:40px 22px 36px}
  .cl-finlabel{font-size:9px}
  .cl-finpath svg{height:48px}
  .cl-roletabs{width:100%;justify-content:center;flex-wrap:wrap}
  .cl-roletab{padding:9px 14px;font-size:12.5px}
  .cl-roletab svg{display:none}
}
@media(prefers-reduced-motion:reduce){
  .cl-finpath-live{transition:none;stroke-dashoffset:0}
  .cl-finstep{transition:none;opacity:1;transform:none}
  .cl-finpath.on .cl-finstep.goal .cl-findot{animation:none}
}

/* ===== motion upgrades (brief §A/§B) ===== */
.reveal{filter:blur(8px)}
.reveal.in{filter:blur(0)}
.cl-mega-arrow s{text-decoration:none;display:inline-block;opacity:0;animation:cl-a-in .5s cubic-bezier(.2,.8,.2,1) forwards,cl-a-wave 2.2s ease-in-out infinite;animation-delay:calc(.5s + var(--ai)*.14s),calc(1.4s + var(--ai)*.18s)}
@keyframes cl-a-in{from{opacity:0;transform:translateX(-.4em)}to{opacity:1;transform:none}}
@keyframes cl-a-wave{0%,100%{transform:translateX(0);opacity:.65}50%{transform:translateX(.1em);opacity:1}}
/* path deck: cards start gathered as a stack, fan out on reveal */
.cl-path .cl-pcard{transition:transform .8s cubic-bezier(.2,.8,.2,1),box-shadow .3s,opacity .6s}
.cl-path:not(.in) .cl-pcard:nth-child(1){transform:translateX(130%) rotate(-7deg);opacity:0}
.cl-path:not(.in) .cl-pcard:nth-child(2){transform:translateX(60%) rotate(-3deg);opacity:0}
.cl-path:not(.in) .cl-pcard:nth-child(4){transform:translateX(-60%) rotate(3deg);opacity:0}
.cl-path:not(.in) .cl-pcard:nth-child(5){transform:translateX(-130%) rotate(7deg);opacity:0}
.cl-path.in .cl-pcard{transition-delay:calc(.08s*var(--i,0))}
/* hero gradient slowly drifts */
.cl-hero2{background-size:160% 160%;animation:cl-bgdrift 22s ease-in-out infinite}
@keyframes cl-bgdrift{0%,100%{background-position:0% 0%}50%{background-position:100% 60%}}
@media(prefers-reduced-motion:reduce){.reveal{filter:none}.cl-hero2{animation:none}.cl-mega-arrow s{animation:none;opacity:1}.cl-path:not(.in) .cl-pcard{transform:none;opacity:1}}

/* scroll progress bar across the very top */
#scrollBar{position:fixed;top:0;left:0;height:3px;width:0;background:linear-gradient(90deg,var(--yy),var(--yy-pink));z-index:2000;transition:width .1s linear;pointer-events:none}

/* scroll reveal: elements start hidden-below, IntersectionObserver adds .in */
.reveal{opacity:0;transform:translateY(28px);transition:opacity .7s cubic-bezier(.2,.7,.2,1),transform .7s cubic-bezier(.2,.7,.2,1)}
.reveal.in{opacity:1;transform:none}
.reveal[data-d="1"]{transition-delay:.08s}
.reveal[data-d="2"]{transition-delay:.16s}
.reveal[data-d="3"]{transition-delay:.24s}
.reveal[data-d="4"]{transition-delay:.32s}
@media(prefers-reduced-motion:reduce){.reveal{opacity:1;transform:none;transition:none}}

/* ---- rich footer (yy/Changellenge) ---- */
.cl-foot{background:var(--yy-dark);color:#fff;margin-top:auto}
body.yy.dark .cl-foot{background:#080A16;border-top:1px solid var(--hair)}
.cl-foot-top{max-width:1240px;margin:0 auto;padding:56px 24px 40px;display:grid;grid-template-columns:1.4fr 2fr;gap:48px}
.cl-foot-brand{max-width:340px}
.cl-foot-logo{font-family:var(--disp);font-weight:800;font-size:22px;letter-spacing:-.02em;color:#fff}
.cl-foot-logo span{color:var(--yy)}
.cl-foot-brand p{font-size:14px;line-height:1.6;color:rgba(255,255,255,.6);margin-top:14px}
.cl-foot-social{display:flex;gap:10px;margin-top:20px}
.cl-foot-social a{width:40px;height:40px;border-radius:11px;background:rgba(255,255,255,.08);display:flex;align-items:center;justify-content:center;color:#fff;cursor:pointer;transition:background .15s,transform .15s}
.cl-foot-social a:hover{background:var(--yy);transform:translateY(-2px)}
.cl-foot-social svg,.cl-foot-social .onb-icon{width:18px;height:18px}
.cl-foot-cols{display:grid;grid-template-columns:repeat(3,1fr);gap:32px}
.cl-foot-col h4{font-family:var(--disp);font-weight:800;font-size:13px;text-transform:uppercase;letter-spacing:.05em;color:#fff;margin-bottom:16px}
.cl-foot-col a{display:block;font-size:14px;color:rgba(255,255,255,.62);cursor:pointer;padding:6px 0;transition:color .15s,padding-left .15s}
.cl-foot-col a:hover{color:#fff;padding-left:4px}
.cl-foot-bottom{border-top:1px solid rgba(255,255,255,.1);max-width:1240px;margin:0 auto;padding:20px 24px;display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:12px}
.cl-foot-bottom>span{font-size:13px;color:rgba(255,255,255,.5)}
.cl-foot-bottom nav{display:flex;gap:20px}
.cl-foot-bottom nav a{font-size:13px;color:rgba(255,255,255,.5);cursor:pointer;transition:color .15s}
.cl-foot-bottom nav a:hover{color:#fff}
@media(max-width:860px){.cl-foot-top{grid-template-columns:1fr;gap:36px}.cl-foot-cols{grid-template-columns:1fr 1fr}.cl-foot-bottom{flex-direction:column;align-items:flex-start}}

#pub-body{width:100%;margin:0;padding:0}
.hero{padding:72px 0 56px;text-align:center}
.hero .eyebrow{font-size:12px;font-weight:600;letter-spacing:.08em;text-transform:uppercase;color:var(--blue);margin-bottom:14px}
.hero h1{font-size:44px;font-weight:700;letter-spacing:-.03em;line-height:1.08;max-width:760px;margin:0 auto}
.hero p{font-size:17px;color:var(--muted);max-width:560px;margin:18px auto 28px;line-height:1.55}
.hero .cta-row{display:flex;gap:12px;justify-content:center;flex-wrap:wrap}
.hero .cta-row .btn{width:auto;height:46px;padding:0 24px;font-size:15px}
.trust{display:flex;gap:26px;justify-content:center;flex-wrap:wrap;padding:22px 0 8px;border-top:1px solid var(--hair);border-bottom:1px solid var(--hair);margin-bottom:56px}
.trust span{font-size:15px;font-weight:600;color:var(--faint)}
.pub-sec{padding:44px 24px;max-width:1080px;margin:0 auto}
.pub-sec h2{font-size:30px;font-weight:700;letter-spacing:-.02em;text-align:center;margin-bottom:8px}
.pub-sec .lead{font-size:15px;color:var(--muted);text-align:center;max-width:520px;margin:0 auto 34px}
.aud-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}
.aud{border:1px solid var(--hair);border-radius:16px;padding:26px;background:var(--surface);transition:.15s;cursor:pointer}
.aud:hover{border-color:var(--blue);box-shadow:0 6px 24px rgba(0,0,0,.06);transform:translateY(-2px)}
.aud .ai{width:48px;height:48px;border-radius:12px;display:flex;align-items:center;justify-content:center;font-size:22px;margin-bottom:14px}
.aud h3{font-size:18px;font-weight:600;margin-bottom:6px}
.aud p{font-size:13.5px;color:var(--muted);line-height:1.55}
.aud .more{font-size:13px;font-weight:600;color:var(--blue);margin-top:12px;display:inline-block}
.how-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:14px}
.how{text-align:center;padding:8px}
.how .hn{width:40px;height:40px;border-radius:50%;background:var(--blue-soft);color:var(--blue-ink);display:flex;align-items:center;justify-content:center;font-weight:700;margin:0 auto 12px}
.how h4{font-size:15px;font-weight:600;margin-bottom:5px}
.how p{font-size:13px;color:var(--muted);line-height:1.5}
.metrics-band{display:grid;grid-template-columns:repeat(4,1fr);gap:16px;background:var(--blue-soft);border-radius:18px;padding:32px 24px;margin:20px 0}
.metric{text-align:center}
.metric .mv{font-size:34px;font-weight:700;letter-spacing:-.02em;color:var(--blue-ink)}
.metric .ml{font-size:13px;color:var(--blue-ink);opacity:.8;margin-top:4px}
.price-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}
.price{border:1px solid var(--hair);border-radius:16px;padding:26px;background:var(--surface);display:flex;flex-direction:column}
.price.hot{border:2px solid var(--blue);position:relative}
.price.hot::before{content:"Популярно";position:absolute;top:-11px;left:50%;transform:translateX(-50%);background:var(--blue);color:#fff;font-size:11px;font-weight:600;padding:3px 12px;border-radius:20px}
.price .pn{font-size:16px;font-weight:600}
.price .pp{font-size:28px;font-weight:700;margin:10px 0 4px}
.price .ptag{font-size:12.5px;color:var(--muted);margin-bottom:16px}
.price ul{list-style:none;margin:0 0 20px;padding:0;flex:1}
.price li{font-size:13px;padding:6px 0;color:var(--ink);display:flex;gap:8px}
.price li::before{content:"✓";color:var(--green);font-weight:700}
.faq-item{border-bottom:1px solid var(--hair);padding:16px 0}
.faq-item summary{font-size:15px;font-weight:600;cursor:pointer;list-style:none;display:flex;justify-content:space-between}
.faq-item summary::after{content:"+";color:var(--muted)}
.faq-item[open] summary::after{content:"−"}
.faq-item p{font-size:13.5px;color:var(--muted);margin-top:10px;line-height:1.6}
.legal-doc{max-width:680px;margin:0 auto;padding:48px 0}
.legal-doc h1{font-size:28px;font-weight:700;margin-bottom:8px}
.legal-doc .upd{font-size:12.5px;color:var(--faint);margin-bottom:24px}
.legal-doc h3{font-size:16px;font-weight:600;margin:22px 0 8px}
.legal-doc p{font-size:14px;color:var(--muted);line-height:1.7;margin-bottom:10px}
.pub-back{display:inline-flex;align-items:center;gap:6px;font-size:13px;color:var(--muted);font-weight:500;cursor:pointer;padding:24px 0 0}
.pub-back:hover{color:var(--blue)}
@media(max-width:900px){
  .pub-nav{display:none}
  .hero h1{font-size:32px}
  .aud-grid,.how-grid,.metrics-band,.price-grid{grid-template-columns:1fr}
  .metrics-band{grid-template-columns:repeat(2,1fr)}
}
/* ---------- NEW FEATURES styles (onboarding / ai / payment) ---------- */
.pass-wrap{display:flex;gap:8px}
.pass-wrap input{flex:1}
.pass-gen{margin-top:10px;display:flex;gap:8px;align-items:center}
.pass-strength{font-size:11.5px;color:var(--green);font-weight:600}
.otp-note{font-size:12px;color:var(--muted);text-align:center;margin-top:12px;padding:10px;background:var(--accent-soft);border-radius:9px;color:var(--accent-ink)}
.wiz-steps{display:flex;gap:6px;margin-bottom:20px}
.wiz-steps i{flex:1;height:4px;background:var(--hair2);border-radius:2px}
.wiz-steps i.on{background:var(--accent)}
.rec-band{background:var(--accent-soft);border:1px solid transparent;border-radius:14px;padding:18px 20px;margin-bottom:16px}
.rec-band h3{font-size:14px;font-weight:600;color:var(--accent-ink);margin-bottom:10px;display:flex;align-items:center;gap:8px}
.rec-chips{display:flex;flex-wrap:wrap;gap:8px}
.rec-chip{background:var(--surface);border:1px solid var(--hair);border-radius:10px;padding:8px 13px;font-size:13px;font-weight:500;display:flex;align-items:center;gap:8px}
.rec-chip .rc-badge{font-size:10px;color:var(--green);font-weight:700}
.mic-btn{width:56px;height:56px;border-radius:50%;background:var(--accent);color:#fff;display:flex;align-items:center;justify-content:center;font-size:22px;flex:none;transition:.2s;border:none;cursor:pointer}
.mic-btn.rec{animation:pulse 1s infinite}
@keyframes pulse{0%{box-shadow:0 0 0 0 rgba(63,91,246,.4)}70%{box-shadow:0 0 0 14px rgba(63,91,246,0)}100%{box-shadow:0 0 0 0 rgba(63,91,246,0)}}
.plan-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}
.plan{border:1px solid var(--hair);border-radius:16px;padding:24px;background:var(--surface);display:flex;flex-direction:column}
.plan.hot{border:2px solid var(--accent);position:relative}
.plan.hot::before{content:"Рекомендуем";position:absolute;top:-11px;left:50%;transform:translateX(-50%);background:var(--accent);color:#fff;font-size:11px;font-weight:600;padding:3px 12px;border-radius:20px}
.plan .pn{font-size:16px;font-weight:600}
.plan .pp{font-size:26px;font-weight:700;margin:8px 0 4px}
.plan .ptag{font-size:12.5px;color:var(--muted);margin-bottom:16px}
.plan ul{list-style:none;margin:0 0 18px;padding:0;flex:1}
.plan li{font-size:13px;padding:5px 0;display:flex;gap:8px}
.plan li::before{content:"✓";color:var(--green);font-weight:700}
.success-modal{background:var(--surface);border-radius:16px;padding:34px;text-align:center;max-width:380px;width:100%}
.success-modal .si{width:64px;height:64px;border-radius:50%;background:var(--green-soft);color:var(--green);display:flex;align-items:center;justify-content:center;font-size:30px;margin:0 auto 16px}
.stub-screen{text-align:center;padding:80px 24px}
.stub-screen .stub-ic{font-size:48px;margin-bottom:16px}
.stub-screen h1{font-size:26px;font-weight:700;margin-bottom:8px}
.stub-screen p{font-size:15px;color:var(--muted);max-width:360px;margin:0 auto}
@media(max-width:900px){.plan-grid{grid-template-columns:1fr}}

/* ---------- NEW: recommendations panel ---------- */
.rec-tabs{display:flex;gap:6px;margin-bottom:18px;flex-wrap:wrap}
.rec-tab{height:32px;padding:0 13px;border-radius:8px;font-size:13px;font-weight:500;color:var(--muted);border:1px solid var(--hair);background:var(--surface)}
.rec-tab.on{background:var(--accent);color:#fff;border-color:transparent}
.rec-summary{display:flex;gap:12px;flex-wrap:wrap;margin-bottom:20px}
.rec-kpi{background:var(--surface);border:1px solid var(--hair);border-radius:11px;padding:12px 16px;min-width:120px}
.rec-kpi .v{font-size:22px;font-weight:700;letter-spacing:-.02em}
.rec-kpi .l{font-size:12px;color:var(--muted);margin-top:2px}
.rec-sec{margin-bottom:26px}
.rec-sec-h{display:flex;align-items:center;gap:10px;margin-bottom:12px}
.rec-sec-h .ico{width:32px;height:32px;border-radius:9px;background:var(--accent-soft);color:var(--accent-ink);display:flex;align-items:center;justify-content:center;font-size:16px;flex:none}
.rec-sec-h h3{font-size:16px;font-weight:700}
.rec-sec-h .rc{font-size:12px;color:var(--muted);background:var(--hair2);padding:2px 9px;border-radius:20px;font-weight:600}
.rec-card{display:flex;align-items:flex-start;gap:13px;padding:14px 16px;border:1px solid var(--hair);border-radius:12px;background:var(--surface);margin-bottom:9px;transition:.15s}
.rec-card:hover{border-color:var(--accent)}
.rec-card.done{opacity:.55;background:var(--green-soft);border-color:transparent}
.rec-check{width:22px;height:22px;border-radius:6px;border:2px solid var(--hair);flex:none;margin-top:1px;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:13px;color:transparent;transition:.15s}
.rec-card.done .rec-check{background:var(--green);border-color:var(--green);color:#fff}
.rec-body{flex:1;min-width:0}
.rec-title{font-size:14px;font-weight:600;line-height:1.35}
.rec-card.done .rec-title{text-decoration:line-through}
.rec-desc{font-size:12.5px;color:var(--muted);margin-top:4px;line-height:1.5}
.rec-tags{display:flex;gap:6px;flex-wrap:wrap;margin-top:8px}
.rec-p{font-size:10.5px;font-weight:700;padding:2px 8px;border-radius:20px}
.rec-p.p1{background:var(--red-soft);color:var(--red-ink)}
.rec-p.p2{background:var(--amber-soft);color:var(--amber-ink)}
.rec-p.p3{background:var(--hair2);color:var(--muted)}
.rec-eff{font-size:10.5px;font-weight:600;padding:2px 8px;border-radius:20px;background:var(--blue-soft);color:var(--blue-ink)}

/* ---------- toast ---------- */
.z2h-toast{position:fixed;left:50%;bottom:28px;transform:translateX(-50%) translateY(20px);background:var(--ink);color:var(--bg);padding:12px 20px;border-radius:10px;font-size:13.5px;font-weight:500;z-index:100;opacity:0;pointer-events:none;transition:.25s;box-shadow:0 8px 30px rgba(0,0,0,.2);max-width:90vw;text-align:center}
.z2h-toast.show{opacity:1;transform:translateX(-50%) translateY(0)}

/* ---------- NEW: student onboarding v2 (icons, no emoji) ---------- */
.onb-icon{width:20px;height:20px;flex:none;display:inline-flex;stroke:currentColor;stroke-width:2;fill:none;stroke-linecap:round;stroke-linejoin:round;vertical-align:middle}
.onb-icon.lg{width:26px;height:26px}
.role-pick{display:grid;grid-template-columns:1fr;gap:12px;margin-bottom:6px}
.role-pick .role-opt .ri{color:var(--accent-ink)}
.form-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.form-grid .full{grid-column:1/-1}
.seg{display:flex;gap:8px;flex-wrap:wrap}
.seg button{flex:1;min-width:90px;height:42px;border:1.5px solid var(--hair);border-radius:10px;font-size:13.5px;font-weight:500;color:var(--muted);background:var(--surface);display:flex;align-items:center;justify-content:center;gap:7px}
.seg button.on{border-color:var(--accent);background:var(--accent-soft);color:var(--accent-ink);font-weight:600}
.chip-pick{display:flex;flex-wrap:wrap;gap:9px}
.chip-pick button{padding:9px 14px;border:1.5px solid var(--hair);border-radius:10px;font-size:13.5px;font-weight:500;display:flex;align-items:center;gap:8px;background:var(--surface);color:var(--ink);cursor:pointer;transition:.14s}
.chip-pick button:hover{border-color:var(--accent);background:var(--accent-soft)}
.chip-pick button .onb-icon{color:var(--muted);width:15px;height:15px}
.chip-pick button.on{border-color:var(--accent);background:var(--accent-soft);color:var(--accent-ink);font-weight:600}
.chip-pick button.on .onb-icon{color:var(--accent)}
/* work-fields step: search + scrollable chips (30 directions) */
.field-search{display:flex;align-items:center;gap:9px;height:42px;padding:0 14px;border:1.5px solid var(--hair);border-radius:11px;background:var(--surface);margin-bottom:10px}
.field-search .onb-icon{width:16px;height:16px;color:var(--muted);flex:none}
.field-search input{flex:1;border:none;outline:none;background:none;font-family:inherit;font-size:14px;color:var(--ink)}
.chip-count{font-size:12px;color:var(--muted);margin-bottom:10px}
.chip-scroll{max-height:290px;overflow-y:auto;padding:2px 4px 2px 2px;margin-bottom:4px}
.chip-scroll::-webkit-scrollbar{width:6px}
.chip-scroll::-webkit-scrollbar-thumb{background:var(--hair);border-radius:3px}
.chip-scroll::-webkit-scrollbar-track{background:transparent}
.big-choice{display:grid;grid-template-columns:1fr 1fr;gap:14px}
.bc-card{border:1.5px solid var(--hair);border-radius:16px;padding:26px 20px;text-align:center;background:var(--surface);transition:.15s;cursor:pointer}
.bc-card:hover{border-color:var(--accent);box-shadow:0 6px 24px rgba(0,0,0,.07);transform:translateY(-2px)}
.bc-card .bc-ic{width:48px;height:48px;border-radius:13px;background:var(--accent-soft);color:var(--accent-ink);display:flex;align-items:center;justify-content:center;margin:0 auto 14px}
.bc-card h4{font-size:16px;font-weight:600;margin-bottom:5px}
.bc-card p{font-size:12.5px;color:var(--muted);line-height:1.45}
.onb-banner{background:var(--accent);color:#fff;border-radius:18px;padding:30px 28px;margin-bottom:22px}
.onb-banner h2{font-size:24px;font-weight:700;letter-spacing:-.02em;line-height:1.15;margin-bottom:6px;display:flex;align-items:center;gap:12px}
.onb-banner p{font-size:14.5px;opacity:.9}
.onb-banner .onb-icon{color:#fff}
.brief-q{margin-bottom:18px}
.brief-q label{display:flex;align-items:center;gap:8px;font-size:14px;font-weight:600;margin-bottom:9px}
.brief-q label .onb-icon{color:var(--accent)}
.brief-q textarea,.brief-q input{width:100%;border:1.5px solid var(--hair);border-radius:11px;padding:11px 12px;font-family:inherit;font-size:14px;color:var(--ink);outline:none;resize:vertical;background:var(--surface);transition:.15s}
.brief-q textarea:focus,.brief-q input:focus{border-color:var(--accent);box-shadow:0 0 0 3px var(--accent-soft)}
.phone-field .pf-code{padding-right:28px;background-position:right 8px center}
.ai-preview{background:var(--surface);border:1px solid var(--hair);border-radius:16px;padding:26px}
.ai-preview .aip-badge{display:inline-flex;align-items:center;gap:7px;background:var(--accent-soft);color:var(--accent-ink);font-size:12px;font-weight:600;padding:5px 12px;border-radius:20px;margin-bottom:16px}
.ai-preview .rh{font-size:22px;font-weight:700}
.ai-preview .rsub{color:var(--accent-ink);font-weight:600;font-size:14px;margin-bottom:14px}
.ai-preview .rsec{font-size:11px;font-weight:600;text-transform:uppercase;letter-spacing:.05em;color:var(--muted);margin:16px 0 6px;border-bottom:1px solid var(--hair);padding-bottom:4px}
.ai-preview p{font-size:13px;line-height:1.6}
.upload-zone{border:2px dashed var(--hair);border-radius:14px;padding:30px;text-align:center;color:var(--muted);cursor:pointer;transition:.15s}
.upload-zone:hover{border-color:var(--accent);color:var(--accent-ink)}
.upload-zone>.onb-icon{width:32px;height:32px;margin-bottom:10px;color:var(--accent)}

/* ---------- NEW: hero role picker (first onboarding screen) ---------- */
.role-hero{max-width:920px;margin:0 auto;text-align:center;padding:8px 0}
.role-hero .rh-eyebrow{font-size:12px;font-weight:600;letter-spacing:.08em;text-transform:uppercase;color:var(--accent);margin-bottom:12px}
.role-hero h1{font-size:30px;font-weight:700;letter-spacing:-.02em;line-height:1.15;margin-bottom:8px}
.role-hero .rh-sub{font-size:15px;color:var(--muted);max-width:460px;margin:0 auto 30px}
.role-cards{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;text-align:left}
.role-card{position:relative;border:1.5px solid var(--hair);border-radius:18px;padding:26px 22px;background:var(--surface);cursor:pointer;transition:.18s;overflow:hidden}
.role-card::after{content:"";position:absolute;inset:0;border-radius:18px;box-shadow:inset 0 0 0 0 var(--accent);transition:.18s;pointer-events:none}
.role-card:hover{transform:translateY(-3px);box-shadow:0 12px 32px rgba(0,0,0,.09);border-color:var(--accent)}
.role-card.on{border-color:var(--accent)}
.role-card.on::after{box-shadow:inset 0 0 0 2px var(--accent)}
.role-card .rc-top{display:flex;align-items:center;justify-content:space-between;margin-bottom:18px}
.role-card .rc-ic{width:52px;height:52px;border-radius:14px;background:var(--accent-soft);color:var(--accent-ink);display:flex;align-items:center;justify-content:center}
.role-card .rc-ic .onb-icon{width:26px;height:26px}
.role-card .rc-check{width:26px;height:26px;border-radius:50%;border:2px solid var(--hair);display:flex;align-items:center;justify-content:center;color:transparent;transition:.15s}
.role-card.on .rc-check{background:var(--accent);border-color:var(--accent);color:#fff}
.role-card .rc-check .onb-icon{width:15px;height:15px;stroke-width:3}
.role-card h3{font-size:19px;font-weight:700;letter-spacing:-.01em;margin-bottom:6px}
.role-card .rc-desc{font-size:13.5px;color:var(--muted);line-height:1.5;margin-bottom:16px}
.role-card .rc-feats{list-style:none;margin:0;padding:0;border-top:1px solid var(--hair2);padding-top:14px}
.role-card .rc-feats li{font-size:12.5px;color:var(--ink);display:flex;align-items:center;gap:8px;padding:3px 0}
.role-card .rc-feats li .onb-icon{width:15px;height:15px;color:var(--accent);flex:none}
.role-card .rc-go{margin-top:16px;font-size:13.5px;font-weight:600;color:var(--accent);display:flex;align-items:center;gap:6px;opacity:0;transition:.15s}
.role-card:hover .rc-go,.role-card.on .rc-go{opacity:1}
@media(max-width:820px){.role-cards{grid-template-columns:1fr}.role-hero h1{font-size:24px}}

/* Baseline for icons inside buttons: match the label size and inherit its colour.
   The real bug was decorative container rules (.folio-empty .onb-icon) cascading
   into buttons — those are now scoped with `>`, so no !important is needed here.
   Specific buttons (.hp-send, .menu-btn, .hb-btn…) still override this freely. */
.btn>.onb-icon{width:16px;height:16px;flex:none;color:currentColor;margin:0}
.btn-sm>.onb-icon{width:14px;height:14px}

/* nav & topbar SVG icons */
.nav-item .ic .onb-icon{width:18px;height:18px}
.bell .onb-icon{width:18px;height:18px}
.menu-btn .onb-icon{width:20px;height:20px}
.search-mini .onb-icon{width:16px;height:16px}
.li-ic .onb-icon,.ni .onb-icon,.rc-ic .onb-icon,.bc-ic .onb-icon,.stat .onb-icon{width:18px;height:18px}
.stub-ic .onb-icon{width:46px;height:46px}
.onb-icon.ok{color:var(--green)}
.onb-icon.danger{color:var(--red)}
.onb-icon.info{color:var(--accent)}
.empty .ei .onb-icon,.onb-icon.stub-mail{width:34px;height:34px;color:var(--muted)}
/* only an icon used inside the page title itself — not the action buttons beside it */
.ph h1 .onb-icon{width:22px;height:22px;vertical-align:-4px}
h3 .onb-icon,.panel h3 .onb-icon{width:16px;height:16px;vertical-align:-2px}

/* ---------- dashboard profile banner + avatar ---------- */
/* ---------- zero-state motivation + visual trajectory ---------- */
.next-hero{position:relative;overflow:hidden;background:var(--surface);border:1.5px solid var(--hair);border-radius:20px;padding:26px 28px;margin-bottom:18px;display:flex;align-items:center;gap:24px}
.next-hero::before{content:"";position:absolute;left:0;top:0;bottom:0;width:5px;background:var(--accent)}
.next-hero .nh-badge{position:absolute;right:22px;top:22px;font-size:10.5px;font-weight:700;letter-spacing:.06em;text-transform:uppercase;color:var(--accent-ink);background:var(--accent-soft);padding:5px 11px;border-radius:20px}
.next-hero .nh-ic{width:64px;height:64px;border-radius:18px;background:var(--accent-soft);color:var(--accent);display:flex;align-items:center;justify-content:center;flex:none}
.next-hero .nh-ic .onb-icon{width:30px;height:30px}
.next-hero .nh-b{flex:1;min-width:0}
.next-hero h3{font-size:20px;font-weight:700;letter-spacing:-.02em}
.next-hero p{font-size:14px;color:var(--muted);margin-top:5px;line-height:1.5}
.next-hero .nh-meta{display:flex;gap:14px;margin-top:12px;font-size:12px;color:var(--muted)}
.next-hero .nh-meta span{display:flex;align-items:center;gap:5px}
.next-hero .nh-meta .onb-icon{width:13px;height:13px}
@media(max-width:640px){.next-hero{flex-wrap:wrap;padding:22px}}

/* visual step trail */
.trail{display:flex;flex-direction:column;gap:0;margin-top:6px}
.trail-step{display:flex;gap:14px;position:relative;padding-bottom:18px;cursor:pointer}
.trail-step:last-child{padding-bottom:0}
.trail-step::before{content:"";position:absolute;left:17px;top:36px;bottom:0;width:2px;background:var(--hair)}
.trail-step:last-child::before{display:none}
.trail-step.done::before{background:var(--green)}
.trail-num{width:36px;height:36px;border-radius:50%;border:2px solid var(--hair);background:var(--surface);display:flex;align-items:center;justify-content:center;font-size:13px;font-weight:700;color:var(--muted);flex:none;z-index:1;transition:.16s}
.trail-step.done .trail-num{background:var(--green);border-color:var(--green);color:#fff}
.trail-step.done .trail-num .onb-icon{width:16px;height:16px;stroke-width:3}
.trail-step.cur .trail-num{border-color:var(--accent);color:var(--accent-ink);box-shadow:0 0 0 4px var(--accent-soft)}
.trail-step:hover .trail-num{border-color:var(--accent)}
.trail-b{padding-top:6px;min-width:0}
.trail-t{font-size:14px;font-weight:600;letter-spacing:-.01em}
.trail-step.done .trail-t{color:var(--muted)}
.trail-d{font-size:12.5px;color:var(--muted);margin-top:2px}
.trail-step.cur .trail-d{color:var(--accent-ink);font-weight:500}
.trail-go{margin-left:auto;align-self:center;font-size:12px;font-weight:600;color:var(--accent);opacity:0;transition:.14s;flex:none}
.trail-step:hover .trail-go{opacity:1}

/* empty-state job card with visual weight */
.mini-job{display:flex;align-items:center;gap:12px;padding:11px 0;border-bottom:1px solid var(--hair2);cursor:pointer;transition:.14s}
.mini-job:last-child{border:none}
.mini-job:hover{padding-left:5px}
.mini-job .mj-logo{width:38px;height:38px;border-radius:10px;flex:none;display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;font-size:15px}
.mini-job .mj-b{flex:1;min-width:0}
.mini-job .mj-t{font-size:13.5px;font-weight:600;letter-spacing:-.01em}
.mini-job .mj-d{font-size:12px;color:var(--muted);margin-top:1px}
.mini-job .mj-m{font-size:12px;font-weight:700;color:var(--accent-ink);background:var(--accent-soft);padding:4px 9px;border-radius:8px;flex:none}

/* ---------- dashboard hero: bold, contrasty, with depth ---------- */
.hero-banner{position:relative;display:flex;align-items:center;gap:24px;background:var(--accent);color:#fff;border-radius:22px;padding:26px 28px;margin-bottom:18px;overflow:hidden;box-shadow:0 14px 40px rgba(63,91,246,.28)}
/* decorative geometry — gives the block presence without imagery */
.hero-banner::before{content:"";position:absolute;right:-70px;top:-90px;width:280px;height:280px;border-radius:50%;background:rgba(255,255,255,.09);pointer-events:none}
.hero-banner::after{content:"";position:absolute;right:80px;bottom:-120px;width:200px;height:200px;border-radius:50%;background:rgba(255,255,255,.06);pointer-events:none}
.hero-banner>*{position:relative;z-index:1}

.hero-banner .hb-avatar{width:88px;height:88px;border-radius:24px;flex:none;position:relative;overflow:hidden;background:rgba(255,255,255,.18);border:3px solid rgba(255,255,255,.28);display:flex;align-items:center;justify-content:center;backdrop-filter:blur(4px)}
.hero-banner .hb-avatar .ph-illu{width:100%;height:100%;display:flex;align-items:center;justify-content:center;color:#fff}
.hero-banner .hb-avatar .ph-illu .onb-icon{width:42px;height:42px;stroke-width:1.5}
.hero-banner .hb-avatar img{width:100%;height:100%;object-fit:cover}
.hero-banner .hb-upload{position:absolute;bottom:0;right:0;left:0;background:rgba(0,0,0,.55);color:#fff;font-size:9.5px;font-weight:600;text-align:center;padding:4px 0;cursor:pointer;opacity:0;transition:.15s}
.hero-banner .hb-avatar:hover .hb-upload{opacity:1}

.hero-banner .hb-info{flex:1;min-width:0}
.hero-banner .hb-hi{font-size:26px;font-weight:800;letter-spacing:-.025em;line-height:1.1}
.hero-banner .hb-sub{font-size:14px;opacity:.9;margin-top:4px;font-weight:500}
.hero-banner .hb-meta{display:flex;gap:8px;flex-wrap:wrap;margin-top:14px}
.hero-banner .hb-chip{background:rgba(255,255,255,.16);border:1px solid rgba(255,255,255,.18);border-radius:20px;padding:5px 12px;font-size:12px;font-weight:500;color:#fff;display:flex;align-items:center;gap:6px;backdrop-filter:blur(4px)}
.hero-banner .hb-chip .onb-icon{width:13px;height:13px;opacity:.9}

/* readiness ring inside the hero */
.hb-ring{flex:none;position:relative;width:104px;height:104px;display:flex;align-items:center;justify-content:center}
.hb-ring svg{transform:rotate(-90deg)}
.hb-ring .hbr-v{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center;color:#fff}
.hb-ring .hbr-num{font-size:24px;font-weight:800;letter-spacing:-.02em;line-height:1}
.hb-ring .hbr-lbl{font-size:9px;opacity:.85;text-transform:uppercase;letter-spacing:.06em;margin-top:3px}

.hero-banner .hb-cta{flex:none;display:flex;flex-direction:column;gap:8px}
.hb-btn{background:#fff;color:var(--accent);border-radius:11px;height:38px;padding:0 16px;font-size:13px;font-weight:700;display:flex;align-items:center;gap:7px;white-space:nowrap;transition:.14s}
.hb-btn:hover{transform:translateY(-1px);box-shadow:0 6px 18px rgba(0,0,0,.18)}
.hb-btn .onb-icon{width:15px;height:15px}
.hb-btn.ghost{background:rgba(255,255,255,.16);color:#fff;border:1px solid rgba(255,255,255,.25)}
@media(max-width:900px){.hb-ring{display:none}}
@media(max-width:640px){.hero-banner{flex-wrap:wrap;padding:22px}.hero-banner .hb-cta{width:100%;flex-direction:row}.hb-btn{flex:1;justify-content:center}}

/* ---------- resume: inline editing ---------- */
.ce{outline:none;border-radius:5px;padding:1px 4px;margin:0 -4px;transition:.12s;cursor:text;min-width:24px;display:inline-block}
.ce:hover{background:var(--hair2)}
.ce:focus{background:var(--accent-soft);box-shadow:0 0 0 2px var(--accent)}
.ce:empty::before{content:attr(data-ph);color:var(--faint);font-style:italic}
.pdf-clean .ce{background:none!important;box-shadow:none!important}
.pdf-clean .rd-item-actions,.pdf-clean .rd-edit,.pdf-clean .rs-x,.pdf-clean .rs-lvl{display:none!important}

/* resume document */
.resume-doc{background:var(--surface);border:1px solid var(--hair);border-radius:16px;overflow:hidden;box-shadow:0 4px 24px rgba(0,0,0,.05)}
.rd-head{padding:28px 30px;display:flex;align-items:center;gap:20px}
.rd-idbox{min-width:0;flex:1}
.rd-photo{width:78px;height:78px;border-radius:16px;flex:none;background:rgba(255,255,255,.2);display:flex;align-items:center;justify-content:center;overflow:hidden;cursor:pointer}
.rd-photo.plain{background:var(--accent-soft);color:var(--accent-ink)}
.rd-photo .onb-icon{width:38px;height:38px}
.rd-photo img{width:100%;height:100%;object-fit:cover}
.rd-name{font-size:24px;font-weight:700;letter-spacing:-.02em}
.rd-role{font-size:14px;font-weight:600;opacity:.9;margin-top:2px}
.rd-contacts{display:flex;gap:14px;flex-wrap:wrap;margin-top:8px;font-size:12px;opacity:.85}
.rd-contacts span{display:flex;align-items:center;gap:5px}
.rd-contacts .onb-icon{width:13px;height:13px}
.rd-body{padding:22px 30px 30px}
.rd-body.two-col{display:grid;grid-template-columns:1fr 240px;gap:26px}
.rd-col-side{border-left:1px solid var(--hair2);padding-left:22px}

/* ---------- template variants: genuinely different looks ---------- */
/* CLASSIC — accent header band, rounded photo, accent section rules */
.tpl-classic .rd-head{background:var(--accent);color:#fff;padding:28px 30px}
.tpl-classic .rd-photo{border-radius:16px}

/* MINIMAL — no colour band, centered header, circular photo, hairline rules, serif-ish scale */
.tpl-minimal .rd-head{background:var(--surface);color:var(--ink);flex-direction:column;text-align:center;gap:12px;padding:32px 30px 22px;border-bottom:1px solid var(--hair)}
.tpl-minimal .rd-photo{border-radius:50%;width:88px;height:88px}
.tpl-minimal .rd-idbox{text-align:center}
.tpl-minimal .rd-contacts{justify-content:center;opacity:1;color:var(--muted)}
.tpl-minimal .rd-name{font-size:27px;font-weight:600;letter-spacing:.01em}
.tpl-minimal .rd-role{font-size:13px;font-weight:400;text-transform:uppercase;letter-spacing:.14em;color:var(--muted);margin-top:6px}
.tpl-minimal .rd-sec h4{color:var(--muted);border-bottom:1px solid var(--hair);font-weight:600;letter-spacing:.1em}
.tpl-minimal .rd-sec h4 .onb-icon{display:none}

/* BOLD — heavy black header, square photo, thick dark rules, oversized name */
.tpl-bold .rd-head{background:var(--ink);color:var(--bg);padding:30px}
.tpl-bold .rd-photo{border-radius:4px;background:rgba(255,255,255,.15)}
.tpl-bold .rd-name{font-size:30px;font-weight:800;letter-spacing:-.03em;text-transform:uppercase}
.tpl-bold .rd-role{font-weight:500;opacity:.75}
.tpl-bold .rd-sec h4{color:var(--ink);border-bottom:3px solid var(--ink);font-size:12px;letter-spacing:.02em}
.tpl-bold .rd-tag{background:var(--ink);color:var(--bg)}

/* SIDEBAR — two columns, tinted side rail, compact header */
.tpl-sidebar .rd-head{background:var(--accent);color:#fff;padding:24px 28px}
.tpl-sidebar .rd-photo{border-radius:12px}
.tpl-sidebar .rd-col-side{background:var(--accent-soft);border-left:none;border-radius:12px;padding:18px}
.tpl-sidebar .rd-col-side .rd-sec h4{border-bottom-color:var(--accent);font-size:10px}
.tpl-sidebar .rd-sec{margin-bottom:16px}

.rd-sec{margin-bottom:20px}
.rd-sec h4{font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:.06em;color:var(--accent-ink);margin-bottom:9px;display:flex;align-items:center;gap:7px;border-bottom:2px solid var(--accent-soft);padding-bottom:6px}
.rd-sec h4 .onb-icon{width:14px;height:14px}
.rd-edit{margin-left:auto;background:var(--hair2);border-radius:7px;width:24px;height:24px;display:inline-flex;align-items:center;justify-content:center;color:var(--muted);cursor:pointer;transition:.14s}
.rd-edit:hover{background:var(--accent-soft);color:var(--accent-ink)}
.rd-edit .onb-icon{width:13px;height:13px}
.rd-para{font-size:13px;line-height:1.65;color:var(--ink)}
.rd-empty{color:var(--faint);font-style:italic;font-size:12.5px}

.rd-item{padding:9px 0;border-bottom:1px solid var(--hair2);position:relative}
.rd-item:last-child{border:none}
.rd-item.rd-bullet{padding:5px 0;border:none;display:flex;gap:8px}
.rd-item.rd-bullet::before{content:"•";color:var(--accent);flex:none}
.ri-head{display:flex;justify-content:space-between;gap:12px;align-items:baseline}
.ri-t{font-size:13.5px;font-weight:600}
.ri-period{font-size:11.5px;color:var(--muted);font-weight:500;flex:none}
.ri-d{font-size:12.5px;color:var(--muted);margin-top:1px}
.ri-body{font-size:12.5px;color:var(--ink);line-height:1.55;margin-top:4px}
.rd-item-actions{position:absolute;right:0;top:8px;display:flex;gap:5px;opacity:0;transition:.14s}
.rd-item:hover .rd-item-actions{opacity:1}
.rd-item-actions button{width:22px;height:22px;border-radius:6px;background:var(--hair2);color:var(--muted);display:flex;align-items:center;justify-content:center;font-size:11px}
.rd-item-actions button:hover{background:var(--red-soft);color:var(--red)}

/* skills & languages with levels */
.rd-skills{display:flex;flex-direction:column;gap:7px}
.rd-skill{display:flex;align-items:center;gap:8px}
.rd-skill .rs-name{flex:1;font-size:13px;font-weight:500;min-width:0}
.rd-skill .rs-lvl{max-width:120px;height:30px;font-size:12px;padding:0 8px;flex:none}
.rd-skill .rs-lvl-static{font-size:11px;font-weight:600;color:var(--accent-ink);background:var(--accent-soft);padding:3px 9px;border-radius:12px}
.rd-skill .rs-x{width:22px;height:22px;border-radius:6px;background:var(--hair2);color:var(--muted);font-size:11px;flex:none}
.rd-skill .rs-x:hover{background:var(--red-soft);color:var(--red)}

/* links */
.rd-links{display:flex;flex-direction:column;gap:8px}
.rd-link{display:flex;align-items:center;gap:8px;font-size:12.5px}
.rd-link .onb-icon{width:14px;height:14px;color:var(--muted);flex:none}
.rd-link .rl-label{font-weight:600;flex:none}
.rd-link .rl-url{color:var(--accent-ink);min-width:0;overflow:hidden;text-overflow:ellipsis}

/* editor sidebar: section order */
.rc-order{background:var(--surface);border:1px solid var(--hair);border-radius:12px;padding:6px}
.ord-row{display:flex;align-items:center;gap:8px;padding:7px 8px;border-radius:8px;font-size:12.5px}
.ord-row:hover{background:var(--hair2)}
.ord-row.off{opacity:.42}
.ord-row .ord-ic{width:22px;height:22px;border-radius:6px;background:var(--accent-soft);color:var(--accent-ink);display:flex;align-items:center;justify-content:center;flex:none}
.ord-row .ord-ic .onb-icon{width:12px;height:12px}
.ord-row .ord-l{flex:1;font-weight:500;min-width:0;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.ord-row button{width:22px;height:22px;border-radius:6px;background:var(--hair2);color:var(--muted);font-size:11px;flex:none}
.ord-row button:hover:not(:disabled){background:var(--accent-soft);color:var(--accent-ink)}
.ord-row button:disabled{opacity:.3;cursor:default}

/* template picker with visual previews */
.rc-templates{display:grid;grid-template-columns:1fr 1fr;gap:8px}
.rc-tpl{border:1.5px solid var(--hair);border-radius:11px;padding:9px 8px;text-align:center;cursor:pointer;font-size:11.5px;font-weight:500;transition:.14s}
.rc-tpl.on{border-color:var(--accent);background:var(--accent-soft);color:var(--accent-ink)}
.tpl-preview{height:34px;border-radius:5px;background:var(--hair2);margin-bottom:6px;padding:4px;display:flex;flex-direction:column;gap:2px;overflow:hidden}
.tpl-preview span{display:block;background:var(--faint);border-radius:1px;height:3px}
.tpl-p-classic span:first-child{height:9px;background:var(--accent)}
.tpl-p-minimal span:first-child{height:6px;background:var(--ink);width:50%;margin:0 auto;border-radius:3px}
.tpl-p-bold span:first-child{height:12px;background:var(--ink)}
.tpl-p-sidebar{flex-direction:row;gap:3px}
.tpl-p-sidebar span{width:100%;height:100%}
.tpl-p-sidebar span:first-child{background:var(--faint);flex:2}
.tpl-p-sidebar span:nth-child(2){background:var(--accent);flex:1}
.tpl-p-sidebar span:last-child{display:none}

.rc-wrap{display:grid;grid-template-columns:320px 1fr;gap:20px;align-items:start}
.rc-side{display:flex;flex-direction:column;gap:14px;position:sticky;top:74px}
.rc-meter{background:var(--surface);border:1px solid var(--hair);border-radius:14px;padding:16px}
.rc-meter .rm-top{display:flex;justify-content:space-between;align-items:baseline;margin-bottom:8px}
.rc-meter .rm-v{font-size:22px;font-weight:700;color:var(--accent-ink)}
.rc-meter .rm-l{font-size:12px;color:var(--muted)}
.rc-photo-ctl{display:flex;gap:12px;align-items:center;background:var(--surface);border:1px solid var(--hair);border-radius:12px;padding:12px}
.rc-photo-ctl .rcp-thumb{width:56px;height:56px;border-radius:12px;flex:none;overflow:hidden;background:var(--accent-soft);color:var(--accent-ink);display:flex;align-items:center;justify-content:center}
.rc-photo-ctl .rcp-thumb img{width:100%;height:100%;object-fit:cover}
.rc-photo-ctl .rcp-thumb .onb-icon{width:26px;height:26px}
@media(max-width:900px){.rc-wrap{grid-template-columns:1fr}.rc-side{position:static}.rd-body.two-col{grid-template-columns:1fr}.rd-col-side{border-left:none;padding-left:0;border-top:1px solid var(--hair2);padding-top:18px}}

/* overview visual upgrade: hero progress + colored stat cards */
.ov-hero{display:flex;gap:22px;align-items:center;background:var(--surface);border:1px solid var(--hair);border-radius:18px;padding:24px 26px;margin-bottom:16px}
.ov-ring{flex:none;position:relative;width:96px;height:96px}
.ov-ring svg{transform:rotate(-90deg)}
.ov-ring .ov-ring-v{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center}
.ov-ring .ov-ring-num{font-size:22px;font-weight:800;letter-spacing:-.02em;color:var(--accent-ink)}
.ov-ring .ov-ring-lbl{font-size:9px;color:var(--muted);text-transform:uppercase;letter-spacing:.04em}
.ov-hero-info{flex:1;min-width:0}
.ov-hero-info h3{font-size:18px;font-weight:700;letter-spacing:-.01em}
.ov-hero-info .ov-step{font-size:13px;color:var(--muted);margin:3px 0 12px}
.ov-hero-info .progress{margin-bottom:6px}
.statcard{background:var(--surface);border:1px solid var(--hair);border-radius:16px;padding:18px;position:relative;overflow:hidden;transition:.16s;cursor:default}
.statcard::after{content:"";position:absolute;left:0;right:0;bottom:0;height:3px;background:var(--sc-color,var(--accent));transform:scaleX(0);transform-origin:left;transition:.22s}
.statcard:hover{transform:translateY(-3px);box-shadow:0 12px 30px rgba(0,0,0,.08);border-color:var(--sc-color,var(--accent))}
.statcard:hover::after{transform:scaleX(1)}
.statcard .sc-ic{width:40px;height:40px;border-radius:12px;display:flex;align-items:center;justify-content:center;margin-bottom:14px}
.statcard .sc-ic .onb-icon{width:20px;height:20px}
.statcard .sc-v{font-size:28px;font-weight:800;letter-spacing:-.03em;line-height:1}
.statcard .sc-l{font-size:12.5px;color:var(--muted);margin-top:6px;font-weight:500}
.statcard .sc-delta{font-size:11px;font-weight:600;color:var(--green);margin-top:8px;display:flex;align-items:center;gap:4px}
/* zero-state: soften the numbers so a wall of 0s doesn't look broken */
.statcard.zero .sc-v{color:var(--faint)}
.statcard .sc-hint{font-size:11px;color:var(--faint);margin-top:8px}
/* micro sparkline strip */
.statcard .sc-spark{display:flex;align-items:flex-end;gap:3px;height:22px;margin-top:10px}
.statcard .sc-spark i{flex:1;background:var(--sc-soft,var(--accent-soft));border-radius:2px;display:block}

/* ---------- landing hero role picker (requirement 1) ---------- */
.hero-roles{text-align:center;padding:52px 0 20px;position:relative;overflow:hidden}
.hero-roles::before{content:"";position:absolute;top:-120px;left:50%;transform:translateX(-50%);width:680px;height:420px;background:radial-gradient(closest-side,var(--accent-soft),transparent 70%);opacity:.7;z-index:0;pointer-events:none}
.hero-roles>*{position:relative;z-index:1}
.hero-roles .hr-eyebrow{display:inline-flex;align-items:center;gap:8px;font-size:12.5px;font-weight:600;letter-spacing:.04em;color:var(--accent-ink);background:var(--accent-soft);padding:7px 15px;border-radius:20px;margin-bottom:22px}
.hero-roles .hr-eyebrow .onb-icon{width:14px;height:14px}
.hero-roles h1{font-size:46px;font-weight:800;letter-spacing:-.03em;line-height:1.08;max-width:800px;margin:0 auto 18px}
.hero-roles h1 .accent{color:var(--accent)}
.hero-roles .hr-sub{font-size:17px;color:var(--muted);max-width:560px;margin:0 auto 28px;line-height:1.55}
.hero-roles .hr-hint{font-size:13px;color:var(--muted);margin-bottom:30px;display:flex;align-items:center;gap:8px;justify-content:center}
.hero-roles .hr-hint .onb-icon{width:15px;height:15px;color:var(--accent)}
.lp-cards{display:grid;grid-template-columns:repeat(3,1fr);gap:18px;max-width:960px;margin:0 auto;text-align:left}
.lp-card{position:relative;border:1.5px solid var(--hair);border-radius:22px;padding:30px 26px;background:var(--surface);cursor:pointer;transition:.18s;overflow:hidden}
.lp-card::before{content:"";position:absolute;left:0;top:0;right:0;height:5px;background:var(--lp-accent,var(--accent));transform:scaleX(0);transform-origin:left;transition:.22s}
.lp-card:hover{transform:translateY(-6px);box-shadow:0 20px 46px rgba(0,0,0,.12);border-color:var(--lp-accent,var(--accent))}
.lp-card:hover::before{transform:scaleX(1)}
.lp-card .lp-ic{width:60px;height:60px;border-radius:18px;background:var(--lp-soft,var(--accent-soft));color:var(--lp-accent,var(--accent-ink));display:flex;align-items:center;justify-content:center;margin-bottom:20px}
.lp-card .lp-ic .onb-icon{width:30px;height:30px}
.lp-card h3{font-size:22px;font-weight:700;letter-spacing:-.01em;margin-bottom:8px}
.lp-card .lp-d{font-size:14px;color:var(--muted);line-height:1.5;margin-bottom:18px}
.lp-card .lp-feats{list-style:none;margin:0 0 20px;padding:16px 0 0;border-top:1px solid var(--hair2)}
.lp-card .lp-feats li{font-size:13px;padding:5px 0;display:flex;align-items:center;gap:9px;color:var(--ink)}
.lp-card .lp-feats li .onb-icon{width:15px;height:15px;color:var(--lp-accent,var(--accent));flex:none}
.lp-card .lp-go{font-size:14px;font-weight:700;color:var(--lp-accent,var(--accent));display:flex;align-items:center;gap:7px}
@media(max-width:820px){.lp-cards{grid-template-columns:1fr}.hero-roles{padding:32px 0 10px}.hero-roles h1{font-size:31px}}

/* phone mask field (requirement 2) */
.phone-field .pf-row{display:flex;gap:8px;align-items:stretch;position:relative}
.phone-field .pf-code{max-width:100px;flex:none}
.phone-field .pf-input{flex:1;padding-right:34px}
.phone-field .pf-status{position:absolute;right:12px;top:50%;transform:translateY(-50%);display:flex;color:var(--green)}
.phone-field .pf-status .onb-icon{width:18px;height:18px}
.phone-field .phone-hint{font-size:11.5px;color:var(--muted);margin-top:5px}
.phone-field.err .pf-input{border-color:var(--red)}
.phone-field.err .phone-hint{color:var(--red)}
.phone-field.ok .pf-input{border-color:var(--green)}
.phone-field.ok .phone-hint{color:var(--green)}

/* ---------- onboarding UX: stepper, consent, other-input, summary ---------- */
.onb-stepper{display:flex;align-items:center;gap:0;margin:2px 0 20px;flex-wrap:wrap;justify-content:center}
.onb-stepper .step{display:flex;align-items:center;gap:7px;font-size:12px;color:var(--muted)}
.onb-stepper .step .sdot{width:22px;height:22px;border-radius:50%;border:2px solid var(--hair);display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:700;color:var(--muted);flex:none;background:var(--surface);transition:.15s}
.onb-stepper .step.done .sdot{background:var(--green);border-color:var(--green);color:#fff}
.onb-stepper .step.done .sdot .onb-icon{width:12px;height:12px;stroke-width:3}
.onb-stepper .step.cur .sdot{border-color:var(--accent);color:var(--accent-ink)}
.onb-stepper .step.cur{color:var(--ink);font-weight:600}
.onb-stepper .sline{width:22px;height:2px;background:var(--hair);margin:0 4px}
.onb-stepper .sline.done{background:var(--green)}
@media(max-width:560px){.onb-stepper .step span{display:none}.onb-stepper .sline{width:14px}}
.onb-nav{display:flex;gap:10px;margin-top:16px}
.onb-nav .btn{width:auto}
.onb-nav .grow{flex:1}
.consent{display:flex;gap:10px;align-items:flex-start;margin:14px 0 4px;cursor:pointer;font-size:12.5px;color:var(--muted);line-height:1.5}
.consent .cbox{width:20px;height:20px;border-radius:6px;border:2px solid var(--hair);flex:none;display:flex;align-items:center;justify-content:center;color:transparent;transition:.15s;margin-top:1px}
.consent.on .cbox{background:var(--accent);border-color:var(--accent);color:#fff}
.consent.on .cbox .onb-icon{width:13px;height:13px;stroke-width:3}
.consent a{color:var(--accent);text-decoration:underline}
.consent.err .cbox{border-color:var(--red)}
.field.invalid input,.field.invalid select{border-color:var(--red)!important}
.field .field-err{font-size:11px;color:var(--red);margin-top:4px;display:none}
.field.invalid .field-err{display:block}
.other-row{display:flex;gap:8px;margin-top:8px}
.other-row input{flex:1}
/* searchable combo for long reference books */
.combo{position:relative;display:flex}
.combo .combo-input{width:100%;padding-right:40px}
.combo .combo-ic{position:absolute;right:12px;top:50%;transform:translateY(-50%);display:flex;pointer-events:none}
.combo .combo-ic .onb-icon{width:16px;height:16px;color:var(--muted)}
.combo-hint{font-size:11.5px;color:var(--muted);margin-top:5px}

/* ---------- multi-select combo (search + chips + dropdown) ---------- */
.mcombo{position:relative}
.mcombo-box{display:flex;flex-wrap:wrap;gap:7px;align-items:center;min-height:46px;padding:8px 40px 8px 12px;border:1.5px solid var(--hair);border-radius:11px;background:var(--surface);transition:.14s;cursor:text}
.mcombo-box:focus-within{border-color:var(--accent);box-shadow:0 0 0 3px var(--accent-soft)}
.mcombo-box .mc-ic{position:absolute;right:13px;top:14px;display:flex;pointer-events:none}
.mcombo-box .mc-ic .onb-icon{width:16px;height:16px;color:var(--muted)}
.mchip{display:inline-flex;align-items:center;gap:6px;background:var(--accent-soft);color:var(--accent-ink);font-size:12.5px;font-weight:600;padding:5px 8px 5px 11px;border-radius:8px;max-width:100%}
.mchip span{overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.mchip button{width:17px;height:17px;border-radius:5px;display:flex;align-items:center;justify-content:center;color:var(--accent-ink);opacity:.55;font-size:11px;line-height:1;flex:none}
.mchip button:hover{opacity:1;background:rgba(0,0,0,.08)}
.mcombo-input{flex:1;min-width:110px;border:none;outline:none;background:none;font-family:inherit;font-size:14px;color:var(--ink);padding:4px 0}
.mcombo-input::placeholder{color:var(--faint)}
.mcombo-list{position:absolute;left:0;right:0;top:calc(100% + 6px);z-index:20;background:var(--surface);border:1.5px solid var(--hair);border-radius:12px;box-shadow:0 12px 32px rgba(0,0,0,.12);max-height:240px;overflow-y:auto;padding:6px}
.mcombo-list::-webkit-scrollbar{width:6px}
.mcombo-list::-webkit-scrollbar-thumb{background:var(--hair);border-radius:3px}
.mcombo-opt{display:flex;align-items:center;gap:10px;padding:9px 11px;border-radius:8px;font-size:13.5px;cursor:pointer;color:var(--ink)}
.mcombo-opt:hover{background:var(--accent-soft)}
.mcombo-opt.on{color:var(--accent-ink);font-weight:600}
.mcombo-opt .mo-box{width:17px;height:17px;border-radius:5px;border:1.5px solid var(--hair);display:flex;align-items:center;justify-content:center;color:transparent;flex:none}
.mcombo-opt.on .mo-box{background:var(--accent);border-color:var(--accent);color:#fff}
.mcombo-opt .mo-box .onb-icon{width:11px;height:11px;stroke-width:3}
.mcombo-add{display:flex;align-items:center;gap:9px;padding:9px 11px;border-radius:8px;font-size:13px;cursor:pointer;color:var(--accent-ink);font-weight:600}
.mcombo-add:hover{background:var(--accent-soft)}
.mcombo-add .onb-icon{width:14px;height:14px}
.mcombo-empty{padding:12px;font-size:13px;color:var(--muted);text-align:center}
.mcombo-foot{font-size:11.5px;color:var(--muted);margin-top:6px}
.sum-card{background:var(--surface);border:1px solid var(--hair);border-radius:14px;overflow:hidden}
.sum-row{display:flex;justify-content:space-between;gap:14px;padding:12px 16px;border-bottom:1px solid var(--hair2);font-size:13.5px}
.sum-row:last-child{border:none}
.sum-row .sk{color:var(--muted)}
.sum-row .sv{font-weight:600;text-align:right}
.skip-link{display:block;text-align:center;margin-top:12px;font-size:13px;color:var(--muted);cursor:pointer}
.skip-link:hover{color:var(--accent)}
.lang-rows{display:flex;flex-direction:column;gap:8px}
.lang-row{display:flex;gap:8px;align-items:center}
.lang-row .lang-name{flex:1;text-align:left;padding:10px 12px;border:1.5px solid var(--hair);border-radius:10px;background:var(--surface);color:var(--ink);font-size:13.5px;font-weight:500;cursor:pointer;display:flex;align-items:center;gap:8px;transition:.14s}
.lang-row .lang-name:hover{border-color:var(--accent)}
.lang-row .lang-name .onb-icon{width:15px;height:15px;color:var(--accent)}
.lang-row.on .lang-name{border-color:var(--accent);background:var(--accent-soft);color:var(--accent-ink);font-weight:600}
.lang-row .lang-lvl{max-width:110px;flex:none}

/* ---------- vacancies: rich job cards ---------- */
.job-filters{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:18px}
.job-selects{display:flex;gap:8px;flex-wrap:wrap;margin:-6px 0 18px}
.job-seg{display:flex;gap:6px;margin-bottom:16px;background:var(--hair2);padding:4px;border-radius:12px;width:fit-content}
.js-tab{display:flex;align-items:center;gap:7px;padding:8px 16px;border:none;background:none;border-radius:9px;font-size:13px;font-weight:600;color:var(--muted);cursor:pointer;transition:.14s}
.js-tab svg{width:15px;height:15px}
.js-tab.on{background:var(--surface);color:var(--ink);box-shadow:0 1px 3px rgba(0,0,0,.08)}
.jsel{height:36px;border:1.5px solid var(--hair);border-radius:10px;padding:0 12px;font-family:inherit;font-size:13px;background:var(--surface);color:var(--ink);outline:none;cursor:pointer}
.jsel:focus{border-color:var(--accent)}
.jsel-reset{height:36px;padding:0 14px;border:none;background:none;color:var(--accent);font-weight:600;font-size:13px;cursor:pointer;border-radius:10px}
.jsel-reset:hover{background:var(--accent-soft)}
.cd-panel{display:flex;align-items:center;justify-content:space-between;gap:16px;flex-wrap:wrap}
.cd-label{font-size:13px;color:var(--muted);display:flex;align-items:center;gap:8px}
.cd-label svg{width:16px;height:16px}
.cd-timer{font-family:var(--mono);font-size:20px;font-weight:700;color:var(--accent);letter-spacing:.01em}
.cd-timer b{font-family:var(--disp);font-weight:800}
.cd-sep{opacity:.4;margin:0 6px}
.job-filters .jf{padding:7px 14px;border:1.5px solid var(--hair);border-radius:20px;font-size:13px;font-weight:500;cursor:pointer;background:var(--surface);color:var(--muted);transition:.14s}
.job-filters .jf:hover{border-color:var(--accent)}
.job-filters .jf.on{background:var(--accent);border-color:var(--accent);color:#fff}
.jobs-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(340px,1fr));gap:16px}
.jobcard{border:1px solid var(--hair);border-radius:18px;background:var(--surface);padding:20px;cursor:pointer;transition:.16s;position:relative;overflow:hidden;display:flex;flex-direction:column}
.jobcard:hover{transform:translateY(-3px);box-shadow:0 14px 34px rgba(0,0,0,.09);border-color:var(--accent)}
.jobcard .jc-head{display:flex;gap:13px;align-items:flex-start;margin-bottom:14px}
.jc-logo{width:48px;height:48px;border-radius:13px;flex:none;display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;font-size:20px;line-height:1;letter-spacing:-.02em;overflow:hidden}
.jobcard .jc-tt{flex:1;min-width:0}
.jobcard .jc-title{font-size:16px;font-weight:700;letter-spacing:-.01em;line-height:1.25}
.jobcard .jc-co{font-size:13px;color:var(--muted);margin-top:2px}
.jobcard .jc-new{position:absolute;top:14px;right:14px;background:var(--green);color:#fff;font-size:10px;font-weight:700;padding:3px 8px;border-radius:20px;text-transform:uppercase;letter-spacing:.04em}
.jc-meta{display:flex;flex-wrap:wrap;gap:7px;margin-bottom:13px}
.jc-pill{font-size:11.5px;font-weight:500;padding:4px 10px;border-radius:8px;background:var(--hair2);color:var(--ink);display:inline-flex;align-items:center;gap:6px;white-space:nowrap}
.jc-pill .onb-icon{width:12px;height:12px;color:var(--muted);flex:none}
.jobcard .jc-about{font-size:12.5px;color:var(--muted);line-height:1.5;margin-bottom:14px;flex:1}
.jc-tags{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:15px}
.jc-tag{display:inline-block;font-size:11px;font-weight:500;padding:4px 10px;border-radius:14px;background:var(--accent-soft);color:var(--accent-ink);white-space:nowrap}
.jobcard .jc-foot{display:flex;align-items:center;justify-content:space-between;gap:12px;padding-top:13px;border-top:1px solid var(--hair2)}
.jobcard .jc-match{display:flex;align-items:center;gap:8px;flex:1}
.jobcard .jc-mbar{flex:1;max-width:90px;height:6px;background:var(--hair2);border-radius:3px;overflow:hidden}
.jobcard .jc-mbar i{display:block;height:100%;background:var(--accent);border-radius:3px}
.jobcard .jc-mval{font-size:13px;font-weight:700;color:var(--accent-ink)}
.jobcard .jc-sal{font-size:13px;font-weight:700;color:var(--green-ink,var(--green))}

/* jobs toolbar: search + view toggle */
.jobs-toolbar{display:flex;gap:12px;align-items:center;margin-bottom:14px;flex-wrap:wrap}
.jobs-search{flex:1;min-width:200px;display:flex;align-items:center;gap:9px;height:42px;padding:0 14px;border:1.5px solid var(--hair);border-radius:11px;background:var(--surface)}
.jobs-search .onb-icon{width:17px;height:17px;color:var(--muted);flex:none}
.jobs-search input{flex:1;border:none;outline:none;background:none;font-family:inherit;font-size:14px;color:var(--ink)}
.view-toggle{display:flex;border:1.5px solid var(--hair);border-radius:10px;overflow:hidden;flex:none}
.view-toggle button{width:40px;height:42px;display:flex;align-items:center;justify-content:center;color:var(--muted);background:var(--surface);transition:.14s}
.view-toggle button.on{background:var(--accent);color:#fff}
.view-toggle button .onb-icon{width:18px;height:18px}
/* list view rows */
.jobs-list{display:flex;flex-direction:column;gap:10px}
.jobrow{display:flex;align-items:center;gap:16px;border:1px solid var(--hair);border-radius:14px;background:var(--surface);padding:14px 18px;cursor:pointer;transition:.14s}
.jobrow:hover{border-color:var(--accent);box-shadow:0 6px 18px rgba(0,0,0,.06)}
.jobrow .jr-logo{width:44px;height:44px;border-radius:11px;flex:none;display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;font-size:18px}
.jobrow .jr-main{flex:1;min-width:0}
.jobrow .jr-title{font-size:15px;font-weight:700;letter-spacing:-.01em;display:flex;align-items:center;gap:8px}
.jobrow .jr-title .jc-new{position:static;padding:2px 7px;font-size:9px}
.jobrow .jr-sub{font-size:12.5px;color:var(--muted);margin-top:3px;display:flex;gap:12px;flex-wrap:wrap}
.jobrow .jr-sub span{display:flex;align-items:center;gap:4px}
.jobrow .jr-sub .onb-icon{width:12px;height:12px}
.jobrow .jr-tags{display:flex;gap:6px;flex-wrap:wrap;margin:0 8px;max-width:220px}
.jobrow .jr-right{text-align:right;flex:none;min-width:110px}
.jobrow .jr-match{display:flex;align-items:center;gap:7px;justify-content:flex-end}
.jobrow .jr-mbar{width:56px;height:6px;background:var(--hair2);border-radius:3px;overflow:hidden}
.jobrow .jr-mbar i{display:block;height:100%;background:var(--accent);border-radius:3px}
.jobrow .jr-mval{font-size:13px;font-weight:700;color:var(--accent-ink)}
.jobrow .jr-sal{font-size:13px;font-weight:700;color:var(--green);margin-top:5px}
@media(max-width:720px){.jobrow .jr-tags{display:none}.jobrow .jr-sub span:nth-child(n+3){display:none}}

@media(max-width:900px){
  .sidebar{position:fixed;top:0;left:-280px;height:100vh;height:100dvh;z-index:40;transition:.2s;box-shadow:2px 0 20px rgba(0,0,0,.1)}
  .sidebar.open{left:0}
  .sb-collapse-btn{display:none}
  /* на мобильном свёрнутый режим не применяется — меню выезжает полностью */
  body.sb-collapsed .sidebar{width:250px;padding:16px 12px}
  body.sb-collapsed .sb-brand b,body.sb-collapsed .role-switch b{display:inline;font-size:revert}
  body.sb-collapsed .role-switch{font-size:11.5px;padding:9px 11px;justify-content:flex-start;margin:0 6px 14px}
  body.sb-collapsed .nav-item{justify-content:flex-start;padding:9px 11px;gap:11px;font-size:13.5px}
  body.sb-collapsed .nav-grp-label{height:auto;padding:14px 11px 5px;color:var(--faint);background:none;margin:0}
  body.sb-collapsed .sb-user{justify-content:flex-start;padding:9px 8px}
  body.sb-collapsed .sb-user>div,body.sb-collapsed .sb-user button{display:flex}
  body.sb-collapsed .nav-item:hover::after{display:none}
  .sb-scrim{position:fixed;inset:0;background:rgba(15,15,20,.4);z-index:39;opacity:0;pointer-events:none;transition:.2s}
  .sb-scrim.on{opacity:1;pointer-events:auto}
  .g2,.g3,.g4,.split,.kanban{grid-template-columns:1fr}
  .kanban{grid-template-columns:repeat(2,1fr)}
  .chat{grid-template-columns:1fr}
  .content{padding:20px 16px 50px}
  .menu-btn{display:flex!important}
}
.menu-btn{display:none;width:36px;height:36px;border-radius:9px;align-items:center;justify-content:center;font-size:18px}
/* ================= HERO — AI assistant (floating, always available) ================= */
.hero-fab{position:fixed;right:24px;bottom:24px;z-index:60;display:flex;align-items:center;gap:10px;height:54px;padding:0 20px 0 16px;border-radius:27px;background:var(--accent);color:#fff;box-shadow:0 8px 28px rgba(63,91,246,.4);transition:.18s;font-weight:600;font-size:14px}
.hero-fab:hover{transform:translateY(-2px);box-shadow:0 12px 34px rgba(63,91,246,.5)}
.hero-fab::before{content:"";position:absolute;inset:0;border-radius:27px;border:2px solid var(--accent);opacity:0;pointer-events:none;animation:hpulse 2.6s ease-out infinite}
@keyframes hpulse{0%{transform:scale(1);opacity:.55}70%{transform:scale(1.18);opacity:0}100%{opacity:0}}
.hero-fab:hover::before{animation-play-state:paused}
.hero-fab .hf-ava{width:30px;height:30px;border-radius:50%;background:rgba(255,255,255,.22);display:flex;align-items:center;justify-content:center;flex:none}
.hero-fab .hf-ava .onb-icon{width:17px;height:17px}
.hero-fab .hf-dot{position:absolute;top:9px;right:16px;width:10px;height:10px;border-radius:50%;background:var(--red);border:2px solid var(--accent)}
.hero-fab.hidden{display:none!important}
@media(max-width:640px){.hero-fab{right:16px;bottom:16px;padding:0 16px 0 12px;height:48px;font-size:13px}}

.hero-panel{position:fixed;right:24px;bottom:24px;z-index:61;width:var(--hp-w,400px);max-width:calc(100vw - 32px);height:var(--hp-h,580px);max-height:calc(100vh - 48px);min-width:320px;min-height:380px;background:var(--surface);border:1px solid var(--hair);border-radius:20px;box-shadow:0 28px 70px rgba(0,0,0,.26);display:flex;flex-direction:column;overflow:hidden;transition:width .18s,height .18s,border-radius .18s}
.hero-panel.hidden{display:none!important}
.hero-panel:not(.hidden){animation:hpIn .2s cubic-bezier(.2,.9,.3,1.2)}
@keyframes hpIn{from{opacity:0;transform:translateY(14px) scale(.97)}to{opacity:1;transform:none}}
.hero-panel.resizing{transition:none;user-select:none}
/* maximized: full-screen workspace */
.hero-panel.max{right:20px;bottom:20px;top:20px;left:20px;width:auto!important;height:auto!important;border-radius:20px}
.hero-panel.max .hp-body{padding:22px 26px}
.hero-panel.max .hmsg{max-width:74%;font-size:14px}
/* collapsed: header only */
.hero-panel.min{height:66px!important;min-height:66px}
.hero-panel.min .hp-body,.hero-panel.min .hp-chips,.hero-panel.min .hp-foot,.hero-panel.min .hp-grip{display:none}
@media(max-width:640px){.hero-panel{right:8px;left:8px;bottom:8px;width:auto!important;height:calc(100vh - 80px)!important}.hero-panel .hp-grip{display:none}}

/* resize grip (top-left corner: panel is anchored bottom-right) */
.hp-grip{position:absolute;left:0;top:0;width:20px;height:20px;cursor:nwse-resize;z-index:3}
.hp-grip::after{content:"";position:absolute;left:6px;top:6px;width:8px;height:8px;border-left:2px solid var(--hair);border-top:2px solid var(--hair);border-radius:2px 0 0 0}
.hp-grip:hover::after{border-color:var(--accent)}

/* header controls */
.hp-btn{width:30px;height:30px;border-radius:8px;color:#fff;display:flex;align-items:center;justify-content:center;opacity:.8;flex:none}
.hp-btn:hover{background:rgba(255,255,255,.16);opacity:1}
.hp-btn .onb-icon{width:15px;height:15px}
.hp-tools{display:flex;gap:2px;align-items:center}

/* attachments */
.hp-atts{display:flex;gap:7px;flex-wrap:wrap;padding:0 14px 10px;background:var(--surface);flex:none}
.hp-att{display:inline-flex;align-items:center;gap:8px;background:var(--bg);border:1px solid var(--hair);border-radius:9px;padding:6px 8px 6px 9px;font-size:12px;max-width:210px}
.hp-att .ha-ic{width:24px;height:24px;border-radius:6px;background:var(--accent-soft);color:var(--accent-ink);display:flex;align-items:center;justify-content:center;flex:none}
.hp-att .ha-ic .onb-icon{width:13px;height:13px}
.hp-att img{width:24px;height:24px;border-radius:6px;object-fit:cover;flex:none}
.hp-att .ha-n{overflow:hidden;text-overflow:ellipsis;white-space:nowrap;font-weight:500}
.hp-att .ha-s{color:var(--muted);font-size:11px;flex:none}
.hp-att .ha-x{width:18px;height:18px;border-radius:5px;color:var(--muted);display:flex;align-items:center;justify-content:center;font-size:11px;flex:none}
.hp-att .ha-x:hover{background:var(--red-soft);color:var(--red)}
.hp-clip{width:40px;height:40px;border-radius:11px;border:1.5px solid var(--hair);background:var(--bg);color:var(--muted);display:flex;align-items:center;justify-content:center;flex:none}
.hp-clip:hover{border-color:var(--accent);color:var(--accent)}
.hp-clip .onb-icon{width:17px;height:17px}

/* message attachment bubble */
.hmsg .hm-files{display:flex;flex-direction:column;gap:6px;margin-top:8px}
.hmsg .hm-file{display:flex;align-items:center;gap:8px;background:rgba(255,255,255,.16);border-radius:8px;padding:6px 9px;font-size:12px}
.hmsg.them .hm-file{background:var(--bg);border:1px solid var(--hair)}
.hmsg .hm-file .onb-icon{width:13px;height:13px;flex:none}
.hmsg .hm-file img{width:100%;max-width:180px;border-radius:8px;display:block}

/* drag-over state */
.hero-panel.drag .hp-body{outline:2px dashed var(--accent);outline-offset:-10px;background:var(--accent-soft)}
.hp-drop{position:absolute;inset:0;z-index:4;display:none;align-items:center;justify-content:center;background:rgba(63,91,246,.08);pointer-events:none;font-size:14px;font-weight:600;color:var(--accent-ink)}
.hero-panel.drag .hp-drop{display:flex}
.hp-head{display:flex;align-items:center;gap:12px;padding:16px 16px 14px;background:var(--accent);color:#fff;flex:none}
.hp-ava{width:38px;height:38px;border-radius:12px;background:rgba(255,255,255,.2);display:flex;align-items:center;justify-content:center;flex:none}
.hp-ava .onb-icon{width:21px;height:21px}
.hp-id{flex:1;min-width:0}
.hp-name{font-size:15px;font-weight:700;letter-spacing:-.01em}
.hp-status{font-size:11.5px;opacity:.85;display:flex;align-items:center;gap:5px}
.hp-status i{width:6px;height:6px;border-radius:50%;background:#6EE7A8;display:block;box-shadow:0 0 0 0 rgba(110,231,168,.7);animation:hdot 2s infinite}
@keyframes hdot{0%{box-shadow:0 0 0 0 rgba(110,231,168,.6)}70%{box-shadow:0 0 0 6px rgba(110,231,168,0)}100%{box-shadow:0 0 0 0 rgba(110,231,168,0)}}
.hp-x{width:32px;height:32px;border-radius:9px;color:#fff;display:flex;align-items:center;justify-content:center;opacity:.8;font-size:15px}
.hp-x:hover{background:rgba(255,255,255,.16);opacity:1}

.hp-body{flex:1;overflow-y:auto;padding:16px;display:flex;flex-direction:column;gap:12px;background:var(--bg)}
.hp-body::-webkit-scrollbar{width:6px}
.hp-body::-webkit-scrollbar-thumb{background:var(--hair);border-radius:3px}
.hmsg{max-width:88%;font-size:13.5px;line-height:1.55;padding:11px 14px;border-radius:14px;animation:hmsgIn .22s ease-out}
@keyframes hmsgIn{from{opacity:0;transform:translateY(6px)}to{opacity:1;transform:none}}
.hmsg.them{background:var(--surface);border:1px solid var(--hair);border-bottom-left-radius:5px;align-self:flex-start;color:var(--ink);box-shadow:0 1px 3px rgba(0,0,0,.04)}
.hmsg.me{background:var(--accent);color:#fff;border-bottom-right-radius:5px;align-self:flex-end;box-shadow:0 3px 10px rgba(63,91,246,.28)}
.hmsg b{font-weight:600}
.hmsg .hm-link{display:inline-flex;align-items:center;gap:5px;margin-top:8px;font-weight:600;color:var(--accent-ink);background:var(--accent-soft);padding:6px 11px;border-radius:8px;font-size:12.5px;cursor:pointer}
.hmsg .hm-link:hover{filter:brightness(.95)}
.hmsg .hm-link .onb-icon{width:13px;height:13px}
.htyping{display:flex;gap:4px;padding:13px 15px;background:var(--surface);border:1px solid var(--hair);border-radius:14px;border-bottom-left-radius:5px;align-self:flex-start}
.htyping i{width:6px;height:6px;border-radius:50%;background:var(--faint);display:block;animation:hbounce 1.2s infinite}
.htyping i:nth-child(2){animation-delay:.15s}
.htyping i:nth-child(3){animation-delay:.3s}
@keyframes hbounce{0%,60%,100%{opacity:.3;transform:translateY(0)}30%{opacity:1;transform:translateY(-4px)}}

.hp-chips{display:flex;gap:7px;flex-wrap:wrap;padding:0 16px 12px;background:var(--bg);flex:none}
.hp-chip{font-size:12px;font-weight:500;padding:7px 12px;border-radius:16px;border:1.5px solid var(--hair);background:var(--surface);color:var(--ink);cursor:pointer;transition:.14s}
.hp-chip:hover{border-color:var(--accent);background:var(--accent-soft);color:var(--accent-ink);transform:translateY(-1px)}

.hp-foot{display:flex;gap:8px;align-items:center;padding:12px 14px;border-top:1px solid var(--hair);background:var(--surface);flex:none}
.hp-foot input{flex:1;height:40px;border:1.5px solid var(--hair);border-radius:11px;padding:0 12px;font-family:inherit;font-size:13.5px;outline:none;background:var(--bg);color:var(--ink)}
.hp-foot input:focus{border-color:var(--accent)}
.hp-send{width:40px;height:40px;border-radius:11px;background:var(--accent);color:#fff;display:flex;align-items:center;justify-content:center;flex:none}
.hp-send .onb-icon{width:17px;height:17px}
.hp-send:disabled{opacity:.4}

/* ---- guided tour spotlight ---- */
/* ---- guided tour: spotlight, welcome & finish screens ---- */
.tour-mask{position:fixed;inset:0;z-index:70;background:transparent;transition:.2s}
.tour-mask.hidden{display:none!important}
.tour-hole{position:absolute;border-radius:14px;box-shadow:0 0 0 9999px rgba(10,10,16,.72);border:2px solid var(--accent);transition:left .32s cubic-bezier(.4,0,.2,1),top .32s cubic-bezier(.4,0,.2,1),width .32s cubic-bezier(.4,0,.2,1),height .32s cubic-bezier(.4,0,.2,1);pointer-events:none}
/* pulsing ring draws the eye to the highlighted element */
.tour-hole::after{content:"";position:absolute;inset:-4px;border-radius:16px;border:2px solid var(--accent);opacity:0;animation:tpulse 2s ease-out infinite}
@keyframes tpulse{0%{transform:scale(1);opacity:.7}70%{transform:scale(1.06);opacity:0}100%{opacity:0}}
body.no-motion .tour-hole::after{animation:none}

.tour-card{position:fixed;z-index:71;width:340px;max-width:calc(100vw - 32px);background:var(--surface);border-radius:18px;padding:20px;box-shadow:0 24px 60px rgba(0,0,0,.34);transition:left .32s cubic-bezier(.4,0,.2,1),top .32s cubic-bezier(.4,0,.2,1);animation:tcIn .26s ease-out}
@keyframes tcIn{from{opacity:0;transform:translateY(8px) scale(.97)}to{opacity:1;transform:none}}
.tour-card.hidden{display:none!important}
/* little arrow pointing at the highlighted element */
.tour-card::before{content:"";position:absolute;width:12px;height:12px;background:var(--surface);transform:rotate(45deg)}
.tour-card[data-side="right"]::before{left:-6px;top:26px}
.tour-card[data-side="left"]::before{right:-6px;top:26px}
.tour-card[data-side="top"]::before{bottom:-6px;left:26px}
.tour-card[data-side="bottom"]::before{top:-6px;left:26px}
.tour-card[data-side="none"]::before{display:none}

.tc-head{display:flex;align-items:center;gap:11px;margin-bottom:12px}
.tc-ic{width:38px;height:38px;border-radius:12px;background:var(--accent-soft);color:var(--accent);display:flex;align-items:center;justify-content:center;flex:none}
.tc-ic .onb-icon{width:19px;height:19px}
.tc-step{font-size:10.5px;font-weight:700;letter-spacing:.07em;text-transform:uppercase;color:var(--accent)}
.tc-title{font-size:17px;font-weight:700;letter-spacing:-.02em;margin-top:1px}
.tc-text{font-size:13.5px;color:var(--muted);line-height:1.55;margin-bottom:16px}
.tc-text b{color:var(--ink);font-weight:600}
.tc-tip{display:flex;gap:9px;align-items:flex-start;background:var(--bg);border-radius:11px;padding:10px 12px;font-size:12.5px;color:var(--muted);line-height:1.45;margin-bottom:16px}
.tc-tip .onb-icon{width:14px;height:14px;color:var(--accent);flex:none;margin-top:2px}

.tc-nav{display:flex;gap:10px;align-items:center;margin-top:14px}
.tc-nav .btn{width:auto;height:38px;font-size:13px;padding:0 18px;margin-left:auto;flex:none}
.tc-nav .btn:focus-visible{outline:2px solid var(--accent);outline-offset:2px}
.tc-nav .btn:focus:not(:focus-visible){outline:none}
.tc-back{width:38px;height:38px;border-radius:10px;border:1.5px solid var(--hair);color:var(--muted);display:flex;align-items:center;justify-content:center;flex:none}
.tc-back:hover{border-color:var(--accent);color:var(--accent)}
.tc-back:disabled{opacity:.35;cursor:not-allowed}
.tc-back .onb-icon{width:15px;height:15px}
.tc-skip{font-size:12.5px;color:var(--faint);cursor:pointer;flex:none}
.tc-skip:hover{color:var(--accent)}
.tc-dots{display:flex;gap:5px;flex-wrap:wrap;justify-content:center;margin-top:16px}
.tc-dots i{width:6px;height:6px;border-radius:50%;background:var(--hair);display:block;transition:.2s;cursor:pointer}
.tc-dots i:hover{background:var(--faint)}
.tc-dots i.on{background:var(--accent);width:18px;border-radius:3px}
.tc-dots i.past{background:var(--accent);opacity:.4}

/* ---- welcome / finish modal ---- */
.tour-modal{position:fixed;inset:0;z-index:72;display:flex;align-items:center;justify-content:center;background:rgba(10,10,16,.7);padding:20px;animation:tmIn .24s ease-out}
@keyframes tmIn{from{opacity:0}to{opacity:1}}
.tour-modal.hidden{display:none!important}
.tm-card{width:460px;max-width:100%;background:var(--surface);border-radius:24px;overflow:hidden;box-shadow:0 30px 80px rgba(0,0,0,.4);animation:tmCardIn .3s cubic-bezier(.2,.9,.3,1.15)}
@keyframes tmCardIn{from{opacity:0;transform:translateY(20px) scale(.95)}to{opacity:1;transform:none}}
.tm-top{background:var(--accent);color:#fff;padding:32px 30px 28px;text-align:center;position:relative;overflow:hidden}
.tm-top::before{content:"";position:absolute;right:-60px;top:-80px;width:220px;height:220px;border-radius:50%;background:rgba(255,255,255,.1)}
.tm-top::after{content:"";position:absolute;left:-50px;bottom:-90px;width:180px;height:180px;border-radius:50%;background:rgba(255,255,255,.07)}
.tm-top>*{position:relative;z-index:1}
.tm-ava{width:66px;height:66px;border-radius:20px;background:rgba(255,255,255,.2);border:2px solid rgba(255,255,255,.3);display:flex;align-items:center;justify-content:center;margin:0 auto 16px}
.tm-ava .onb-icon{width:32px;height:32px}
.tm-h{font-size:23px;font-weight:800;letter-spacing:-.025em;line-height:1.2}
.tm-s{font-size:14px;opacity:.9;margin-top:7px;line-height:1.5}
.tm-body{padding:24px 30px 28px}
.tm-list{display:flex;flex-direction:column;gap:12px;margin-bottom:22px}
.tm-item{display:flex;gap:12px;align-items:flex-start}
.tm-item .ti-ic{width:34px;height:34px;border-radius:11px;background:var(--accent-soft);color:var(--accent);display:flex;align-items:center;justify-content:center;flex:none}
.tm-item .ti-ic .onb-icon{width:16px;height:16px}
.tm-item .ti-t{font-size:14px;font-weight:600;letter-spacing:-.01em}
.tm-item .ti-d{font-size:12.5px;color:var(--muted);margin-top:2px;line-height:1.45}
.tm-meta{display:flex;align-items:center;justify-content:center;gap:7px;font-size:12px;color:var(--faint);margin-bottom:18px}
.tm-meta .onb-icon{width:13px;height:13px}
.tm-actions{display:flex;flex-direction:column;gap:9px}
.tm-actions .btn{width:100%;height:44px}
.tm-later{text-align:center;font-size:13px;color:var(--faint);cursor:pointer;padding:6px}
.tm-later:hover{color:var(--accent)}
/* confetti-free celebration: a simple check burst */
.tm-done .tm-ava{background:rgba(255,255,255,.24)}
.tm-stat{display:flex;gap:10px;justify-content:center;margin-bottom:20px}
.tm-stat div{flex:1;background:var(--bg);border-radius:12px;padding:12px;text-align:center}
.tm-stat .s-v{font-size:19px;font-weight:800;letter-spacing:-.02em;color:var(--accent-ink)}
.tm-stat .s-l{font-size:11px;color:var(--muted);margin-top:2px}
@media(max-width:520px){.tm-top{padding:26px 22px 22px}.tm-body{padding:20px 22px 24px}}
</style>
<!-- PDF export: real generation (loaded from CDN, used only when user clicks "Скачать PDF") -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
</head>
<body class="yy">

<!-- ======================= PUBLIC / MARKETING ======================= -->
<div id="scr-public">
  <header class="pub-head">
    <div class="pub-inner">
      <div class="brand" style="margin:0"><div class="logo">Z</div><b>Zero-to-Hero <span style="color:var(--yy)">››</span></b></div>
      <nav class="pub-nav" id="pub-nav">
        <a onclick="pubGo('for-students')" data-i18n="nav_students">Студентам</a>
        <a onclick="pubGo('for-universities')" data-i18n="nav_universities">ВУЗам</a>
        <a onclick="pubGo('for-companies')" data-i18n="nav_companies">Компаниям</a>
        <a onclick="pubGo('about')" data-i18n="nav_about">О нас</a>
        <a onclick="pubGo('help')" data-i18n="nav_help">Помощь</a>
      </nav>
      <div style="display:flex;gap:8px;align-items:center">
        <button class="pub-icon-btn" id="langBtn" onclick="toggleLang()" title="Til / Язык" aria-label="Сменить язык">RU</button>
        <button class="pub-icon-btn" id="themeBtn" onclick="toggleTheme()" title="Тема" aria-label="Сменить тему">
          <svg class="ti-sun" viewBox="0 0 24 24" width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="4"/><path d="M12 2v2M12 20v2M4.9 4.9l1.4 1.4M17.7 17.7l1.4 1.4M2 12h2M20 12h2M6.3 17.7l-1.4 1.4M19.1 4.9l-1.4 1.4"/></svg>
          <svg class="ti-moon" viewBox="0 0 24 24" width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 12.8A9 9 0 1 1 11.2 3a7 7 0 0 0 9.8 9.8Z"/></svg>
        </button>
        <button class="btn btn-ghost btn-sm" onclick="show('scr-auth')" data-i18n="login">Войти</button>
        <button class="btn btn-primary btn-sm" onclick="startOnb2()" data-i18n="start">Начать</button>
      </div>
    </div>
  </header>
  <div id="pub-body"></div>
  <footer class="cl-foot">
    <div class="cl-foot-top">
      <div class="cl-foot-brand">
        <div class="cl-foot-logo">Zero-to-Hero <span>&gt;&gt;</span></div>
        <p>Карьерная платформа для студентов Узбекистана. От первого курса до первого оффера — через реальные кейсы.</p>
        <div class="cl-foot-social">
          <a onclick="toast('Telegram — скоро')" title="Telegram" aria-label="Telegram"><svg viewBox="0 0 24 24" width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 3 3 10.5l6 2.5 2.5 6L21 3z"/><path d="M9 13.5 21 3"/></svg></a>
          <a onclick="toast('Instagram — скоро')" title="Instagram" aria-label="Instagram"><svg viewBox="0 0 24 24" width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none"/></svg></a>
          <a onclick="pubGo('contact')" title="Почта" aria-label="Почта"><svg viewBox="0 0 24 24" width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="5" width="18" height="14" rx="2"/><path d="m3 7 9 6 9-6"/></svg></a>
        </div>
      </div>
      <div class="cl-foot-cols">
        <div class="cl-foot-col">
          <h4>Студентам</h4>
          <a onclick="pubGo('for-students')">Карьерный путь</a>
          <a onclick="startOnbAs('student')">Стажировки</a>
          <a onclick="startOnbAs('student')">Кейс-чемпионаты</a>
          <a onclick="startOnb2()">Начать бесплатно</a>
        </div>
        <div class="cl-foot-col">
          <h4>Партнёрам</h4>
          <a onclick="pubGo('for-companies')">Компаниям</a>
          <a onclick="pubGo('for-universities')">ВУЗам</a>
        </div>
        <div class="cl-foot-col">
          <h4>Компания</h4>
          <a onclick="pubGo('about')">О нас</a>
          <a onclick="pubGo('help')">Помощь</a>
          <a onclick="pubGo('contact')">Контакты</a>
        </div>
      </div>
    </div>
    <div class="cl-foot-bottom">
      <span>© 2026 Zero-to-Hero · Ташкент, Узбекистан</span>
      <nav>
        <a onclick="pubGo('legal-terms')">Условия</a>
        <a onclick="pubGo('legal-privacy')">Конфиденциальность</a>
      </nav>
    </div>
  </footer>
</div>

<!-- ======================= AUTH SCREEN (phone login, matches registration) ======================= -->
<div id="scr-auth" class="center-screen hidden">
  <div class="card">
    <div class="brand"><div class="logo">Z</div><b>Zero-to-Hero</b><span>карьерный центр</span></div>
    <div id="auth-body"></div>
    <p class="hint"><a onclick="startOnbPickRole()">Нет аккаунта? Зарегистрироваться</a></p>
    <p class="hint"><a onclick="show('scr-public')">← На главную</a></p>
  </div>
</div>

<!-- ======================= NEW FEATURE: features/onboarding (phone → code → role → password) ======================= -->
<div id="scr-onb2" class="center-screen hidden">
  <div class="card">
    <div class="brand"><div class="logo">Z</div><b>Zero-to-Hero</b></div>
    <div id="onb2-stepper"></div>
    <div id="onb2-body"></div>
    <p class="hint"><a onclick="show('scr-public')">← На главную</a></p>
  </div>
</div>

<!-- ======================= APP SHELL ======================= -->
<div id="scr-app" class="shell hidden">
  <aside class="sidebar" id="sidebar">
    <div class="sb-brand"><div class="logo">Z</div><b>Zero-to-Hero</b>
      <button class="sb-collapse-btn" id="sb-collapse-btn" onclick="toggleCollapse()" title="Свернуть меню"><svg class="onb-icon" viewBox="0 0 24 24"><path d="M15 6l-6 6 6 6"/></svg></button>
    </div>
    <div class="role-switch"><span class="rdot"></span>Роль: <b id="sb-role">Студент</b></div>
    <nav class="nav-group" id="nav-main"></nav>
    <nav class="sb-foot" id="nav-foot"></nav>
    <div class="sb-user">
      <div class="av" id="u-av">С</div>
      <div><div class="un" id="u-name">Студент</div><div class="ue" id="u-email">student@z2h.uz</div></div>
      <button onclick="logout()" title="Выйти">⏻</button>
    </div>
  </aside>
  <div class="sb-scrim" id="sb-scrim" onclick="closeSidebar()"></div>

  <div class="main">
    <div class="topbar">
      <button class="menu-btn" onclick="toggleSidebar()"><svg class="onb-icon" viewBox="0 0 24 24"><path d="M3 6h18M3 12h18M3 18h18"/></svg></button>
      <div class="crumb" id="crumb"><b>Обзор</b></div>
      <div class="search-mini" onclick="openPalette()"><svg class="onb-icon" viewBox="0 0 24 24"><circle cx="11" cy="11" r="7"/><path d="M21 21l-4-4"/></svg> Поиск вакансий, симуляций, разделов…<kbd>⌘K</kbd></div>
      <button class="bell" onclick="toggleTheme()" title="Сменить тему"><svg class="onb-icon" viewBox="0 0 24 24"><path d="M21 12.8A9 9 0 1111.2 3a7 7 0 009.8 9.8z"/></svg></button>
      <button class="bell" onclick="go('notifications')"><svg class="onb-icon" viewBox="0 0 24 24"><path d="M18 8a6 6 0 00-12 0c0 7-3 9-3 9h18s-3-2-3-9M13.7 21a2 2 0 01-3.4 0"/></svg><i></i></button>
    </div>
    <div class="content" id="content"></div>
  </div>
</div>

<!-- command palette -->
<div id="palette" class="overlay hidden" onclick="if(event.target===this)closePalette()">
  <div class="palette">
    <input id="pal-input" placeholder="Перейти к разделу или найти…" oninput="renderPalette(this.value)" onkeydown="if(event.key==='Escape')closePalette()">
    <div class="presults" id="pal-results"></div>
  </div>
</div>

<!-- ======================= HERO — AI assistant ======================= -->
<button id="hero-fab" class="hero-fab hidden" onclick="heroOpen()">
  <span class="hf-ava"><svg class="onb-icon" viewBox="0 0 24 24"><rect x="4" y="8" width="16" height="12" rx="2"/><path d="M12 8V4M8 4h8"/><circle cx="9" cy="14" r="1"/><circle cx="15" cy="14" r="1"/></svg></span>
  Hero
  <i id="hero-dot" class="hf-dot hidden"></i>
</button>

<div id="hero-panel" class="hero-panel hidden">
  <div class="hp-grip" id="hp-grip" title="Потяните, чтобы изменить размер"></div>
  <div class="hp-drop">Отпустите файл — Hero его посмотрит</div>
  <div class="hp-head">
    <div class="hp-ava"><svg class="onb-icon" viewBox="0 0 24 24"><rect x="4" y="8" width="16" height="12" rx="2"/><path d="M12 8V4M8 4h8"/><circle cx="9" cy="14" r="1"/><circle cx="15" cy="14" r="1"/></svg></div>
    <div class="hp-id">
      <div class="hp-name">Hero</div>
      <div class="hp-status"><i></i>Ваш AI-навигатор по платформе</div>
    </div>
    <div class="hp-tools">
      <button class="hp-btn" id="hp-min" onclick="heroToggleMin()" title="Свернуть"><svg class="onb-icon" viewBox="0 0 24 24"><path d="M5 12h14"/></svg></button>
      <button class="hp-btn" id="hp-max" onclick="heroToggleMax()" title="Развернуть"><svg class="onb-icon" viewBox="0 0 24 24"><path d="M8 3H5a2 2 0 00-2 2v3M16 3h3a2 2 0 012 2v3M8 21H5a2 2 0 01-2-2v-3M16 21h3a2 2 0 002-2v-3"/></svg></button>
      <button class="hp-btn" onclick="heroClose()" title="Закрыть"><svg class="onb-icon" viewBox="0 0 24 24"><path d="M18 6L6 18M6 6l12 12"/></svg></button>
    </div>
  </div>
  <div class="hp-body" id="hero-msgs"></div>
  <div class="hp-chips" id="hero-chips"></div>
  <div class="hp-atts" id="hero-atts"></div>
  <div class="hp-foot">
    <button class="hp-clip" onclick="heroPickFile()" title="Прикрепить файл"><svg class="onb-icon" viewBox="0 0 24 24"><path d="M21.4 11.05l-9.19 9.19a6 6 0 01-8.49-8.49l9.2-9.19a4 4 0 015.66 5.66l-9.2 9.19a2 2 0 01-2.83-2.83l8.49-8.48"/></svg></button>
    <input id="hero-input" placeholder="Спросите или прикрепите файл…" onkeydown="if(event.key==='Enter')heroSend()">
    <button class="hp-send" onclick="heroSend()"><svg class="onb-icon" viewBox="0 0 24 24"><path d="M22 2L11 13M22 2l-7 20-4-9-9-4z"/></svg></button>
  </div>
</div>

<!-- guided tour -->
<div id="tour-mask" class="tour-mask hidden"><div id="tour-hole" class="tour-hole"></div></div>
<div id="tour-card" class="tour-card hidden" data-side="right">
  <div class="tc-head">
    <div class="tc-ic" id="tc-ic"></div>
    <div><div class="tc-step" id="tc-step"></div><div class="tc-title" id="tc-title"></div></div>
  </div>
  <div class="tc-text" id="tc-text"></div>
  <div class="tc-tip hidden" id="tc-tip"></div>
  <div class="tc-dots" id="tc-dots"></div>
  <div class="tc-nav">
    <button class="tc-back" id="tc-back" onclick="tourBack()" title="Назад">
      <svg class="onb-icon" viewBox="0 0 24 24"><path d="M19 12H5M12 19l-7-7 7-7"/></svg>
    </button>
    <span class="tc-skip" onclick="tourSkip()">Пропустить</span>
    <button class="btn btn-primary" id="tc-next" onclick="tourNext()">Далее →</button>
  </div>
</div>

<!-- tour welcome / finish -->
<div id="tour-modal" class="tour-modal hidden">
  <div class="tm-card" id="tm-card"></div>
</div>

<script>
/* icon set (defined first — used everywhere) */
const IC={
  student:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M22 10L12 5 2 10l10 5 10-5z"/><path d="M6 12v5c3 3 9 3 12 0v-5"/></svg>',
  company:'<svg class="onb-icon" viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M9 8h.01M9 12h.01M9 16h.01M15 8h.01M15 12h.01M15 16h.01"/></svg>',
  university:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M3 21h18M5 21V7l7-4 7 4v14M9 21v-6h6v6"/></svg>',
  phone:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M22 16.9v3a2 2 0 01-2.2 2 19.8 19.8 0 01-8.6-3 19.5 19.5 0 01-6-6 19.8 19.8 0 01-3-8.6A2 2 0 014.1 2h3a2 2 0 012 1.7c.1.9.4 1.8.7 2.7a2 2 0 01-.5 2.1L8.1 9.9a16 16 0 006 6l1.4-1.2a2 2 0 012.1-.5c.9.3 1.8.6 2.7.7a2 2 0 011.7 2z"/></svg>',
  check:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M20 6L9 17l-5-5"/></svg>',
  doc:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M14 2H6a2 2 0 00-2 2v16a2 2 0 002 2h12a2 2 0 002-2V8z"/><path d="M14 2v6h6M16 13H8M16 17H8M10 9H8"/></svg>',
  upload:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M21 15v4a2 2 0 01-2 2H5a2 2 0 01-2-2v-4M17 8l-5-5-5 5M12 3v12"/></svg>',
  spark:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M12 3l1.9 5.6L19.5 10l-5.6 1.9L12 17l-1.9-5.6L4.5 10l5.6-1.4z"/></svg>',
  globe:'<svg class="onb-icon" viewBox="0 0 24 24"><circle cx="12" cy="12" r="9"/><path d="M3 12h18M12 3a15 15 0 010 18 15 15 0 010-18z"/></svg>',
  briefcase:'<svg class="onb-icon" viewBox="0 0 24 24"><rect x="2" y="7" width="20" height="14" rx="2"/><path d="M16 21V5a2 2 0 00-2-2h-4a2 2 0 00-2 2v16"/></svg>',
  megaphone:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M3 11v2a1 1 0 001 1h2l5 4V6L6 10H4a1 1 0 00-1 1z"/><path d="M15 8a5 5 0 010 8"/></svg>',
  users:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M17 21v-2a4 4 0 00-4-4H5a4 4 0 00-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 00-3-3.9M16 3.1a4 4 0 010 7.8"/></svg>',
  code:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M16 18l6-6-6-6M8 6l-6 6 6 6"/></svg>',
  palette:'<svg class="onb-icon" viewBox="0 0 24 24"><circle cx="12" cy="12" r="9"/><circle cx="8.5" cy="10.5" r="1"/><circle cx="15.5" cy="10.5" r="1"/><circle cx="12" cy="15" r="1"/></svg>',
  chat:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M21 15a2 2 0 01-2 2H7l-4 4V5a2 2 0 012-2h14a2 2 0 012 2z"/></svg>',
  user:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M20 21v-2a4 4 0 00-4-4H8a4 4 0 00-4 4v2"/><circle cx="12" cy="7" r="4"/></svg>',
  target:'<svg class="onb-icon" viewBox="0 0 24 24"><circle cx="12" cy="12" r="9"/><circle cx="12" cy="12" r="5"/><circle cx="12" cy="12" r="1"/></svg>',
  home:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M3 10l9-7 9 7v10a2 2 0 01-2 2h-4v-7H9v7H5a2 2 0 01-2-2z"/></svg>',
  compass:'<svg class="onb-icon" viewBox="0 0 24 24"><circle cx="12" cy="12" r="9"/><path d="M16 8l-2 6-6 2 2-6z"/></svg>',
  chart:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M3 3v18h18"/><path d="M7 15l4-4 3 3 5-6"/></svg>',
  puzzle:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M9 3a2 2 0 014 0v1h3a1 1 0 011 1v3h1a2 2 0 010 4h-1v3a1 1 0 01-1 1h-3v-1a2 2 0 00-4 0v1H5a1 1 0 01-1-1v-3H3a2 2 0 010-4h1V5a1 1 0 011-1h4z"/></svg>',
  resume:'<svg class="onb-icon" viewBox="0 0 24 24"><rect x="4" y="3" width="16" height="18" rx="2"/><circle cx="9" cy="9" r="2"/><path d="M13 8h4M13 12h4M7 15h10"/></svg>',
  bell:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M18 8a6 6 0 00-12 0c0 7-3 9-3 9h18s-3-2-3-9M13.7 21a2 2 0 01-3.4 0"/></svg>',
  gear:'<svg class="onb-icon" viewBox="0 0 24 24"><circle cx="12" cy="12" r="3"/><path d="M19.4 15a1.6 1.6 0 00.3 1.8l.1.1a2 2 0 11-2.8 2.8l-.1-.1a1.6 1.6 0 00-2.7.7 1.6 1.6 0 01-3.2 0 1.6 1.6 0 00-2.7-.7l-.1.1a2 2 0 11-2.8-2.8l.1-.1A1.6 1.6 0 004.6 15a1.6 1.6 0 00-1.5-1H3a2 2 0 010-4h.1A1.6 1.6 0 004.6 9a1.6 1.6 0 00-.3-1.8l-.1-.1a2 2 0 112.8-2.8l.1.1a1.6 1.6 0 001.8.3H9a1.6 1.6 0 001-1.5V3a2 2 0 014 0v.1a1.6 1.6 0 001 1.5 1.6 1.6 0 001.8-.3l.1-.1a2 2 0 112.8 2.8l-.1.1a1.6 1.6 0 00-.3 1.8V9a1.6 1.6 0 001.5 1H21a2 2 0 010 4h-.1a1.6 1.6 0 00-1.5 1z"/></svg>',
  list:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M8 6h13M8 12h13M8 18h13M3 6h.01M3 12h.01M3 18h.01"/></svg>',
  folder:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M3 7a2 2 0 012-2h4l2 2h8a2 2 0 012 2v8a2 2 0 01-2 2H5a2 2 0 01-2-2z"/></svg>',
  plus:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>',
  search:'<svg class="onb-icon" viewBox="0 0 24 24"><circle cx="11" cy="11" r="7"/><path d="M21 21l-4-4"/></svg>',
  bot:'<svg class="onb-icon" viewBox="0 0 24 24"><rect x="4" y="8" width="16" height="12" rx="2"/><path d="M12 8V4M8 4h8"/><circle cx="9" cy="14" r="1"/><circle cx="15" cy="14" r="1"/></svg>',
  card:'<svg class="onb-icon" viewBox="0 0 24 24"><rect x="2" y="5" width="20" height="14" rx="2"/><path d="M2 10h20"/></svg>',
  mic:'<svg class="onb-icon" viewBox="0 0 24 24"><rect x="9" y="2" width="6" height="12" rx="3"/><path d="M5 10a7 7 0 0014 0M12 17v4"/></svg>',
  calendar:'<svg class="onb-icon" viewBox="0 0 24 24"><rect x="3" y="4" width="18" height="18" rx="2"/><path d="M3 10h18M8 2v4M16 2v4"/></svg>',
  trophy:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M8 21h8M12 17v4M7 4h10v4a5 5 0 01-10 0zM7 4H4v2a3 3 0 003 3M17 4h3v2a3 3 0 01-3 3"/></svg>',
  flame:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M12 2c1 3 4 5 4 9a4 4 0 01-8 0c0-1 .5-2 1-3 .5 2 2 2 2 2s-2-3 1-8z"/></svg>',
  pin:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M12 21s7-6.5 7-12a7 7 0 10-14 0c0 5.5 7 12 7 12z"/><circle cx="12" cy="9" r="2.5"/></svg>',
  brain:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M9 3a3 3 0 00-3 3 3 3 0 00-2 5 3 3 0 001 5 3 3 0 006 1V5a2 2 0 00-2-2zM15 3a3 3 0 013 3 3 3 0 012 5 3 3 0 01-1 5 3 3 0 01-6 1V5a2 2 0 012-2z"/></svg>',
  alert:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M12 9v4M12 17h.01M10.3 3.9L1.8 18a2 2 0 001.7 3h17a2 2 0 001.7-3L14.7 3.9a2 2 0 00-3.4 0z"/></svg>',
  wave:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M18 11V6a2 2 0 00-4 0M14 10V4a2 2 0 00-4 0v2M10 10.5V6a2 2 0 00-4 0v8a8 8 0 0016 0v-4a2 2 0 00-4 0"/></svg>',
  dot:'<svg class="onb-icon" viewBox="0 0 24 24"><circle cx="12" cy="12" r="6" fill="currentColor" stroke="none"/></svg>',
  ban:'<svg class="onb-icon" viewBox="0 0 24 24"><circle cx="12" cy="12" r="9"/><path d="M5.6 5.6l12.8 12.8"/></svg>',
  mail:'<svg class="onb-icon" viewBox="0 0 24 24"><rect x="3" y="5" width="18" height="14" rx="2"/><path d="M3 7l9 6 9-6"/></svg>',
  moon:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M21 12.8A9 9 0 1111.2 3a7 7 0 009.8 9.8z"/></svg>',
  menu:'<svg class="onb-icon" viewBox="0 0 24 24"><path d="M3 6h18M3 12h18M3 18h18"/></svg>',
  clock:'<svg class="onb-icon" viewBox="0 0 24 24"><circle cx="12" cy="12" r="9"/><path d="M12 7v5l3 2"/></svg>',
  data:'<svg class="onb-icon" viewBox="0 0 24 24"><ellipse cx="12" cy="5" rx="8" ry="3"/><path d="M4 5v6c0 1.7 3.6 3 8 3s8-1.3 8-3V5M4 11v6c0 1.7 3.6 3 8 3s8-1.3 8-3v-6"/></svg>',
};
/* render an icon by key; falls back to a neutral dot */
function ico(name,cls){ const svg=IC[name]||IC.dot; return cls?svg.replace('class="onb-icon"',`class="onb-icon ${cls}"`):svg; }

/* ---- small shared utilities (dates, plurals, deadline UI) ---- */
/* plural() already exists further down the file — reused, not redefined. */
/* A number under 10 is noise, not proof — drop the card rather than shrink it. */
/* An off switch should read as a deliberate choice, not a broken page. */
/* mark every notification row as read (demo: just dims them) */
function markAllRead(){
  try{ NOTIFICATIONS.forEach(n=>n.unread=false); }catch(e){}
  updateNavBadges();
  toast('Отмечено как прочитанное');
  if(state.page==='notifications') go('notifications');
}
/* send the message typed in a chat input next to the button */
function chatSend(btn){
  const wrap=btn.closest('.chat-input');
  const inp=wrap && wrap.querySelector('input');
  const msgs=document.querySelector('.chat-msgs');
  if(!inp||!inp.value.trim()||!msgs) return;
  msgs.insertAdjacentHTML('beforeend','<div class="msg me">'+inp.value.replace(/</g,'&lt;')+'</div>');
  inp.value=''; msgs.scrollTop=msgs.scrollHeight;
}

function featureOff(title,why){
  return ph(title,"Раздел скрыт в этой сборке")+`<div class="empty" style="padding:60px 20px">
    <div class="ei">${ico('ban')}</div>
    <h3>Раздел временно скрыт</h3>
    <p>${why}</p>
  </div>`;
}

function pubStats(){
  const cards=[
    [STATS.students,     "студентов"],
    [STATS.universities, "вузов"],
    [STATS.companies,    "компаний"],
  ].filter(x=>x[0]>=10);
  if(!cards.length) return '';
  return `<div class="pub-stats">${cards.map(x=>
    `<div class="pub-stat"><div class="pv">${x[0].toLocaleString('ru-RU')}</div><div class="pl">${x[1]}</div></div>`).join('')}</div>`;
}

const MONTHS_GEN=["января","февраля","марта","апреля","мая","июня","июля","августа","сентября","октября","ноября","декабря"];
/* A fixed "today" keeps the demo deterministic — real deadlines would drift
   past every mock date within weeks and the whole screen would read "закрыто". */
const TODAY=new Date("2026-07-10T00:00:00Z");
function parseISO(d){ return new Date(d+"T00:00:00Z"); }
function fmtDate(iso){ const d=parseISO(iso); return `${d.getUTCDate()} ${MONTHS_GEN[d.getUTCMonth()]}`; }
function daysLeft(iso){ return Math.ceil((parseISO(iso)-TODAY)/86400000); }
function isPast(iso){ return daysLeft(iso)<0; }

/* one deadline pill, three states, used on cards, rows and detail alike */
function deadlinePill(j){
  if(!j.deadline) return '';
  const left=daysLeft(j.deadline);
  if(left<0)   return `<span class="jc-pill dl-closed">${ico('ban')}Набор закрыт</span>`;
  if(left<=7)  return `<span class="jc-pill dl-urgent">${ico('flame')}Осталось ${left} ${plural(left,'день','дня','дней')}</span>`;
  return `<span class="jc-pill">${ico('calendar')}до ${fmtDate(j.deadline)}</span>`;
}

/* numbered circles joined by a line — inherits from the company when absent */
function hiringStepper(steps){
  return `<div class="hs">${steps.map((s,i)=>`
    <div class="hs-step">
      <div class="hs-dot">${i+1}</div>
      <div class="hs-lbl">${s}</div>
    </div>`).join('')}</div>`;
}
function jobSteps(j){
  if(j.hiringSteps&&j.hiringSteps.length) return j.hiringSteps;
  const c=companyByName(j.co);
  return (c&&c.hiringSteps)||[];
}
/* ============================================================
   STATE
   ============================================================ */
const state = {
  role: null,
  authed: false,
  name: "Студент",
  email: "student@z2h.uz",
  onboardComplete: false,
  page: "home",
  obStep: 1,
  obRole: null,
};

const ROLE_EMAIL = { student:"student@z2h.uz", university:"curator@nuu.uz", company:"hr@uzum.uz" };
const ROLE_META = {
  student:    {label:"Студент",     home:"s",   letter:"С", accent:"blue"},
  university: {label:"ВУЗ",         home:"u",   letter:"В", accent:"teal"},
  company:    {label:"Компания",    home:"c",   letter:"К", accent:"amber"},
  mentor:     {label:"Ментор",      home:"m",   letter:"М", accent:"green"},
  admin:      {label:"Админ",       home:"a",   letter:"А", accent:"violet"},
};

/* nav config per role (mirrors nav-config.tsx) */
const NAV = {
  student: {
    main:[
      ["home","home","Обзор"],
      ["__group","Развитие"],
      ["path","compass","Траектория"],["orders","target","Заказы на кадры"],["track","puzzle","Мой трек"],["diagnostics","chart","Диагностика"],
      ["simulations","puzzle","Симуляции"],["portfolio","folder","Портфолио"],
      ["passport","trophy","Паспорт навыков"],
      ["__group","Практика"],
      ["diary","doc","Дневник практики"],
      ["__group","Трудоустройство"],
      ["jobs","briefcase","Вакансии"],["companies","company","Компании"],
      ["tasks","target","Фриланс"],["freelancers","users","Исполнители"],
      ["events","calendar","События"],["applications","mail","Мои отклики"],
      ["__group","Материалы"],
      ["resume","resume","AI-резюме"],["messages","chat","Сообщения"],
    ],
    foot:[["notifications","bell","Уведомления"],["profile","user","Профиль"],["help","spark","Обучение"],["settings","gear","Настройки"]],
  },
  university: {
    main:[
      ["home","home","Обзор"],
      ["__group","Студенты"],
      ["cohorts","folder","Когорты"],["students","users","Студенты"],
      ["gaps","chart","Gap-матрица"],
      ["__group","Практика и трудоустройство"],
      ["contracts","list","Договоры практики"],["placement","trophy","Трудоустройство"],
      ["kpi","chart","KPI деканата"],["tasks","target","Фриланс студентов"],
      ["career-sync","globe","career.edu.uz"],
      ["__group","Партнёры"],
      ["partners","company","Компании-партнёры"],
      ["__group","Управление"],
      ["subscription","card","Подписка"],
      ["reports","list","Отчёты"],["team","plus","Команда"],
    ],
    foot:[["notifications","bell","Уведомления"],["help","spark","Обучение"],["settings","gear","Настройки"]],
  },
  company: {
    main:[
      ["home","home","Обзор"],
      ["__group","Найм"],
      ["internships","briefcase","Стажировки"],["htd","puzzle","Заказ на кадры"],
      ["tasks","target","Фриланс"],["freelancers","users","Исполнители"],
      ["candidate-search","search","Поиск кандидатов"],["candidates","list","Кандидаты"],
      ["__group","Таланты"],
      ["talent-showcase","trophy","Витрина талантов"],
      ["__group","Связи"],
      ["partners","university","ВУЗы-партнёры"],
      ["events","calendar","События"],["messages","chat","Сообщения"],
      ["__group","Организация"],
      ["company","company","Компания"],["team","plus","Команда"],
    ],
    foot:[["notifications","bell","Уведомления"],["help","spark","Обучение"],["settings","gear","Настройки"]],
  },
  admin: {
    main:[
      ["home","home","Обзор"],["contracts","list","Реестр договоров"],
      ["placement","trophy","Трудоустройство"],["kpi","chart","Сводный KPI"],
      ["tasks","target","Модерация фриланса"],
    ],
    foot:[["help","spark","Обучение"],["settings","gear","Настройки"]],
  },
  mentor: {
    main:[
      ["home","home","Мои практиканты"],["review","check","На проверку"],
    ],
    foot:[["notifications","bell","Уведомления"],["help","spark","Обучение"],["settings","gear","Настройки"]],
  },
};

const LABELS = {
  home:"Обзор",path:"Траектория",diagnostics:"Диагностика",simulations:"Симуляции",
  jobs:"Вакансии",resume:"AI-резюме",messages:"Сообщения",notifications:"Уведомления",
  profile:"Профиль",settings:"Настройки",cohorts:"Когорты",students:"Студенты",
  gaps:"Gap-матрица",reports:"Отчёты",team:"Команда",internships:"Стажировки",
  candidates:"Кандидаты",company:"Компания",search:"Поиск",
  applications:"Мои отклики",portfolio:"Портфолио",
  "candidate-search":"Поиск кандидатов",placement:"Трудоустройство",
  forbidden:"Доступ запрещён",invite:"Приглашение",
  companies:"Компании","company-detail":"Компания",events:"События","talent-detail":"Кандидат",
  diary:"Дневник практики",contracts:"Договоры практики",kpi:"KPI деканата",htd:"Заказ на кадры",
  "contract-detail":"Договор практики","htd-detail":"Заказ на кадры","diary-entry":"Запись дневника",
  "talent-showcase":"Витрина талантов",
  "passport":"Паспорт навыков",
  "review":"На проверку","mentor-student":"Практикант","review-entry":"Проверка записи",
  "partners":"Партнёры",
  "tasks":"Фриланс","task-detail":"Задание","my-tasks":"Мои задания","task-new":"Новое задание","task-review":"Проверка задания",
  "freelancers":"Исполнители","freelancer":"Профиль исполнителя",
  "help":"Обучение",
  "orders":"Заказы на кадры","order-detail":"Заказ",
  "career-sync":"career.edu.uz","subscription":"Подписка",
  "order-new":"Новый заказ",
  "track":"Мой трек",
};

/* ============================================================
   AUTH — phone login, mirrors registration. Role from session.
   ============================================================ */
let authMode="signin";
function authTab(m){ authMode='signin'; }
function renderAuth(){
  const saved = (typeof restoreState==='function' ? restoreState() : null) || {};
  const role = saved.role || loadRole();
  const el=document.getElementById('auth-body'); if(!el) return;
  if(role){
    const label={student:"Студент",university:"ВУЗ",company:"Компания"}[role]||role;
    el.innerHTML=`
      <h2 class="title">С возвращением</h2>
      <p class="subtitle">Войдите в кабинет — роль «${label}».</p>
      <div class="field"><label>Номер телефона</label><input id="auth-phone" type="tel" placeholder="+998 90 123 45 67" value="${(saved.reg&&saved.reg.phone)||state.email||''}"></div>
      <button class="btn btn-primary" onclick="authLogin('${role}')">Войти →</button>
      <div class="divider">или</div>
      <button class="btn btn-ghost" onclick="startOnbPickRole()">Сменить роль / новый аккаунт</button>`;
  }else{
    el.innerHTML=`
      <h2 class="title">Вход</h2>
      <p class="subtitle">Ещё нет аккаунта? Пройдите быструю регистрацию.</p>
      <button class="btn btn-primary" onclick="startOnbPickRole()">Выбрать роль и начать →</button>`;
  }
}
function authLogin(role){
  const phone=(document.getElementById('auth-phone')||{}).value;
  if(phone) state.email=phone;
  saveRole(role);
  enterApp(role,true);
}
/* legacy names kept as safe aliases (no password flow anymore) */
function doAuth(){ renderAuth(); }
function magicLink(){ const r=loadRole()||'student'; saveRole(r); enterApp(r,true); }
function resetSend(){ show('scr-auth'); }

/* Legacy onboarding removed — superseded by the icon-based ONB flow (scr-onb2). */


/* ============================================================
   ENTER APP + NAV
   ============================================================ */
function enterApp(role, complete){
  state.role=role;state.authed=true;state.onboardComplete=complete;
  MOCK.users.role=role; MOCK.users.active=true; persistState();
  const m=ROLE_META[role];
  state.name = m.label==="ВУЗ" ? "Куратор ВУЗа" : m.label;
  /* the demo account e-mail must match the role it is signed in as */
  if(!state.email || /@z2h\.uz$/.test(state.email)) state.email = ROLE_EMAIL[role] || state.email;
  document.body.setAttribute('data-role',role);
  document.getElementById('sb-role').textContent=m.label;
  document.getElementById('u-name').textContent=state.name;
  document.getElementById('u-email').textContent=state.email;
  document.getElementById('u-av').textContent=m.letter;
  buildNav();
  show('scr-app');
  go('home');
  /* first time in the app → guided tour; afterwards Hero just badges itself */
  if(typeof tourSeen==='function'){
    if(!tourSeen()) setTimeout(startTour,600);
    else { const dot=document.getElementById('hero-dot'); if(dot) dot.classList.remove('hidden'); }
  }
}
/* Pages gated behind a feature flag. Code stays; only the door closes. */
const FLAGGED_PAGES={ resume:'resumeBuilder', candidates:'recruiterKanban',
  diary:'internship_diary', contracts:'tripartite_contract', 'contract-detail':'tripartite_contract',
  kpi:'uni_kpi_dashboard', htd:'htd', 'htd-detail':'htd',
  'talent-showcase':'talent_showcase',
  'passport':'skills_passport',
  tasks:'tasks', 'task-detail':'tasks', 'my-tasks':'tasks',
  'task-new':'tasks', 'task-review':'tasks',
  'freelancers':'tasks', 'freelancer':'tasks',
  'orders':'match_score', 'order-detail':'match_score',
  'career-sync':'career_edu_sync',
  'subscription':'uni_subscription',
  'order-new':'htd',
  'track':'htd' };
function pageEnabled(id){ const f=FLAGGED_PAGES[id]; return !f || !!FEATURES[f]; }
function buildNav(){
  const cfg=NAV[state.role];
  document.getElementById('nav-main').innerHTML=renderNavItems(cfg.main);
  document.getElementById('nav-foot').innerHTML=renderNavItems(cfg.foot);
  updateNavBadges();
}
/* поддерживает разделители-группы ["__group","Метка"]; пустые группы (все пункты
   которых скрыты фичефлагами) не выводятся, чтобы не осталось «висящих» заголовков */
function renderNavItems(items){
  const out=[]; let pendingLabel=null;
  for(const x of items){
    if(x[0]==='__group'){ pendingLabel=x[1]; continue; }
    if(!pageEnabled(x[0])) continue;
    if(pendingLabel!==null){ out.push(`<div class="nav-grp-label">${pendingLabel}</div>`); pendingLabel=null; }
    out.push(navBtn(x));
  }
  return out.join('');
}
function navBtn([id,ic,label]){
  const badge = id==='notifications' ? `<span class="nav-badge" data-badge-for="notifications"></span>` : '';
  return `<button class="nav-item" data-page="${id}" data-label="${label}" onclick="go('${id}')"><span class="ic">${ico(ic)}</span>${label}${badge}</button>`;
}
/* обновляет числовые бейджи в меню (непрочитанные уведомления) */
function updateNavBadges(){
  try{
    const n=unreadCount();
    document.querySelectorAll('[data-badge-for="notifications"]').forEach(b=>{
      if(n>0){ b.textContent=n; b.style.display='inline-flex'; }
      else b.style.display='none';
    });
  }catch(e){}
}
function toggleHelpFaq(i){ state._helpFaq = state._helpFaq===i ? null : i; go('help'); }
function toggleSidebar(){
  const sb=document.getElementById('sidebar'), sc=document.getElementById('sb-scrim');
  const open=sb.classList.toggle('open'); if(sc) sc.classList.toggle('on',open);
}
function closeSidebar(){
  const sb=document.getElementById('sidebar'), sc=document.getElementById('sb-scrim');
  sb.classList.remove('open'); if(sc) sc.classList.remove('on');
}
/* свернуть/развернуть сайдбар (десктоп) — состояние в PREFS */
function toggleCollapse(){
  try{ PREFS.sidebarCollapsed=!PREFS.sidebarCollapsed; savePrefs(); applyPrefs(); }
  catch(e){ document.body.classList.toggle('sb-collapsed'); }
  const btn=document.getElementById('sb-collapse-btn');
  if(btn) btn.title = document.body.classList.contains('sb-collapsed')?'Развернуть меню':'Свернуть меню';
}
function go(page){
  if(state.page!=='applications' && page!=='applications') state._appOpen=null;  // forget expansion on leaving
  state.page=page;
  trackEvent('view',page);
  document.querySelectorAll('.nav-item').forEach(b=>b.classList.toggle('on',b.dataset.page===page));
  document.getElementById('crumb').innerHTML=`<b>${LABELS[page]||page}</b>`;
  document.getElementById('content').innerHTML = renderPage(page);
  document.getElementById('content').scrollTop=0;
  window.scrollTo(0,0);
  if(typeof closeSidebar==='function') closeSidebar(); else document.getElementById('sidebar').classList.remove('open');
  if(page==='applications' && typeof restoreAppOpen==='function') restoreAppOpen();
  if(page==='notifications'){ try{ NOTIFICATIONS.forEach(n=>n.unread=false); }catch(e){} }
  if(typeof _cdTimer!=='undefined' && _cdTimer && page!=='job-detail'){ clearInterval(_cdTimer); _cdTimer=null; }
  if(page==='job-detail' && typeof startCountdown==='function') startCountdown();
  if(typeof updateNavBadges==='function') updateNavBadges();
}
/* ------- MOCK-трекинг событий (Этап 8) -------
   Лёгкий лог посещений: полезно на демо для вузов («что смотрели»).
   Хранится в памяти сессии, показывается в настройках. Ничего не отправляется. */
const TRACK=[];
function trackEvent(type,name){
  try{ TRACK.push({type,name:LABELS[name]||name,role:state.role,ts:Date.now()});
    if(TRACK.length>200) TRACK.shift(); }catch(e){}
}
function trackSummary(){
  const counts={};
  TRACK.filter(e=>e.type==='view').forEach(e=>{counts[e.name]=(counts[e.name]||0)+1;});
  return Object.entries(counts).sort((a,b)=>b[1]-a[1]).slice(0,8);
}
function logout(){
  state.authed=false;state.role=null;
  clearState();
  /* the public site has no role — otherwise it keeps the amber/teal accent
     of whoever logged out last, and the brand blue silently disappears */
  document.body.removeAttribute('data-role');
  show('scr-public');
}
function show(id){
  ['scr-public','scr-auth','scr-onb2','scr-app'].forEach(s=>{const el=document.getElementById(s); if(el) el.classList.toggle('hidden',s!==id);});
  /* role accent belongs to the app, not to the marketing site or the onboarding */
  if(id==='scr-app'){ if(state.role) document.body.setAttribute('data-role',state.role); }
  else document.body.removeAttribute('data-role');
  if(id==='scr-auth' && typeof renderAuth==='function') renderAuth();
  /* Hero lives inside the app only */
  if(typeof heroShowFab==='function'){ if(id==='scr-app') heroShowFab(); else heroHideFab(); }
}

/* ============================================================
   PAGE RENDERERS
   ============================================================ */
function renderPage(page){
  const r=state.role;
  /* mock onboarding: fresh users from the new flow get role-appropriate first screen */
  if(MOCK.users.fromMockFlow && page==='home'){
    if(r==='university') return PAGES['univ-stub']();
    if(r==='company')    return PAGES['company-stub']();
    if(r==='student')    return freshStudentHome();   // just registered → zero-state, real next step
  }
  if(r==='student' && page==='home'){
    return recommendBlock() + PAGES['student:home']();  // established demo account (veteran numbers)
  }
  const key=r+":"+page;
  if(PAGES[key]) return PAGES[key]();
  if(PAGES[page]) return PAGES[page]();
  return ph(LABELS[page]||page,"Раздел прототипа")+`<div class="empty"><div class="ei">${ico('puzzle')}</div><h3>Экран «${LABELS[page]||page}»</h3><p>Демо-заглушка раздела для роли «${ROLE_META[r].label}».</p></div>`;
}
function ph(title,sub,right){
  return `<div class="ph"><div class="row"><div><h1>${title}</h1>${sub?`<p>${sub}</p>`:''}</div>${right||''}</div></div>`;
}
function back(page,label){return `<a class="back-link" onclick="go('${page}')">← ${label}</a>`;}

/* Единый пустой-стейт: иконка, заголовок, пояснение и необязательное действие.
   Используется во всех разделах, где данных может не быть — чтобы отсутствие
   читалось как осмысленное состояние, а не сломанный экран. */
function emptyState(icon,title,text,action){
  return `<div class="empty" style="padding:56px 24px">
    <div class="ei">${ico(icon)}</div>
    <h3>${title}</h3>
    <p style="max-width:380px;margin:0 auto${action?' 18px':''}">${text}</p>
    ${action?`<button class="btn btn-primary btn-sm" style="width:auto;margin:0 auto" onclick="${action.onclick}">${action.label}</button>`:''}
  </div>`;
}

/* ---- shared data ---- */
/* Each step declares how it is checked (`done`), where it leads (`go`), and what it costs.
   Nothing here is hardcoded to "completed" — progress reflects real user actions. */
const PATH_STEPS=[
  {k:'diag',   t:"Диагностика",              d:"Самооценка плюс проверка знаний",           go:'diagnostics', xp:80,  time:"7 мин",  ic:'brain',
   why:"Без неё траектория и проценты совпадения будут приблизительными"},
  {k:'goals',  t:"Профиль и цели",           d:"Направления, которые вам интересны",         go:'profile',     xp:60,  time:"3 мин",  ic:'target',
   why:"По ним подбираем вакансии и симуляции"},
  {k:'basics', t:"Базовые компетенции",      d:"Коммуникация, критическое мышление",         go:'diagnostics', xp:100, time:"20 мин", ic:'spark',
   why:"Открывается после диагностики — по её результатам"},
  {k:'sim1',   t:"Первая симуляция",         d:"Реальный бизнес-кейс с AI-наставником",      go:'simulations', xp:150, time:"3–5 ч",  ic:'puzzle',
   why:"Решённый кейс весит больше, чем строчка в резюме"},
  {k:'resume', t:"AI-резюме",                d:"Соберите резюме: о себе, навыки, опыт",      go:'resume',      xp:90,  time:"15 мин", ic:'resume',
   why:"Именно его увидит работодатель"},
  {k:'folio',  t:"Портфолио",                d:"Работы, отзывы, подтверждения",              go:'resume',      xp:120, time:"30 мин", ic:'folder',
   why:"Две сданные симуляции формируют портфолио"},
  {k:'spec',   t:"Отраслевая специализация", d:"Углублённое погружение в направление",       go:'simulations', xp:200, time:"10–15 ч",ic:'code',
   why:"Три симуляции в одном направлении"},
  {k:'simmid', t:"Симуляции middle",         d:"Проекты уровня стажировки",                  go:'simulations', xp:250, time:"8–12 ч", ic:'chart',
   why:"Более сложные кейсы — после базовых"},
  {k:'apply',  t:"Отклики и интервью",       d:"Тестовые задания и интервью с компаниями",   go:'jobs',        xp:100, time:"—",      ic:'briefcase',
   why:"Первый отклик открывает этот этап"},
  {k:'offer',  t:"Стажировка / оффер",       d:"Выход на реальную работу",                   go:'jobs',        xp:500, time:"—",      ic:'trophy',
   why:"Финальная цель всего пути"},
];
/* real completion rules — read from the same state the rest of the app uses */
function pathState(){
  profileInit();
  const p=MOCK.profile, d=MOCK.resumeData||{}, r=MOCK.reg||{};
  const diagDone=!!(state._diag&&state._diag.done);
  const sims=(p.doneSims||[]).length;
  const apps=(p.appliedJobs||[]).length;
  const fields=(MOCK.workFields||[]).length+(MOCK.workFieldsOther||[]).length;
  const skills=(r.skillsArr||[]).length;
  const resumeReady=!!(d.about&&d.about.trim())&&skills>0;
  return {
    diag:   diagDone,
    goals:  fields>0 && !!(r.first&&r.last),
    basics: diagDone && skills>0,
    sim1:   sims>=1,
    resume: resumeReady,
    folio:  sims>=2,
    spec:   sims>=3,
    simmid: sims>=4,
    apply:  apps>=1,
    offer:  false,          // nobody gets an offer in a prototype
    _sims:sims,_apps:apps,_skills:skills,
  };
}
function pathProgress(){
  const st=pathState();
  const done=PATH_STEPS.filter(s=>st[s.k]).length;
  const xp=PATH_STEPS.filter(s=>st[s.k]).reduce((a,s)=>a+s.xp,0);
  const total=PATH_STEPS.reduce((a,s)=>a+s.xp,0);
  /* the current step is the first unfinished one */
  const curIdx=PATH_STEPS.findIndex(s=>!st[s.k]);
  return {st,done,total:PATH_STEPS.length,xp,xpTotal:total,curIdx:curIdx<0?PATH_STEPS.length-1:curIdx};
}
/* sub-progress for steps that count things (e.g. "1 of 3 simulations") */
function pathSubProgress(k,st){
  const bar=(cur,need,word)=>({pct:Math.min(100,Math.round(cur/need*100)),label:`${Math.min(cur,need)} из ${need} ${word}`});
  if(k==='sim1')   return bar(st._sims,1,'симуляции');
  if(k==='folio')  return bar(st._sims,2,'симуляций');
  if(k==='spec')   return bar(st._sims,3,'симуляций');
  if(k==='simmid') return bar(st._sims,4,'симуляций');
  if(k==='apply')  return bar(st._apps,1,'отклика');
  return null;
}
/* replace the old alert() with a helpful explanation of what unlocks this step */
function pathLockedHint(i){
  const {curIdx}=pathProgress();
  const blocker=PATH_STEPS[curIdx];
  toast(`Сначала: «${blocker.t}»`);
}

/* a step unlocks once every earlier one is done (the current one is always open) */
function pathLocked(i){
  const {st,curIdx}=pathProgress();
  if(st[PATH_STEPS[i].k]) return false;
  return i>curIdx;
}
/* Each simulation carries its own brief, dataset, deliverables and rubric —
   no more one-size-fits-all text behind every card. */
const SIMS=[
  {id:0,t:"Почему падает удержание в интернет-магазине",co:"Ozon",logo:"O",color:"#005BFF",
   role:"Аналитик данных",lvl:"Junior",dur:"3–5 ч",tags:["SQL","Продукт","Аналитика"],dl:"12 июля",xp:120,field:"IT",cat:"Аналитика",
   brief:"За два месяца доля повторных покупок среди новых клиентов упала с 34% до 21%. Команда не понимает, где ломается путь. Найдите причину и предложите план экспериментов.",
   data:"Таблица заказов (180 тыс. строк), когорты пользователей по неделям, события каталога и корзины, данные о промо-акциях.",
   deliver:["Краткий вывод на один экран","Три проверяемые гипотезы с обоснованием","Метрики успеха и риски каждой гипотезы"],
   tip:"Начните со сравнения когорт по неделям регистрации, затем найдите шаг воронки, где новые клиенты отваливаются чаще старых.",
   rubric:[["Логика анализа",30],["Работа с данными",30],["Качество гипотез",25],["Ясность выводов",15]]},

  {id:1,t:"A/B-тест платного онбординга",co:"Uzum",logo:"U",color:"#7000FF",
   role:"Продуктовый аналитик",lvl:"Junior",dur:"2–4 ч",tags:["A/B","Статистика","Продукт"],dl:"14 июля",xp:100,field:"IT",cat:"Продукт",
   brief:"Продакт предлагает сделать онбординг платным (9 900 сум) — гипотеза в том, что платящие пользователи активнее. Спроектируйте эксперимент и оцените, стоит ли его запускать.",
   data:"Исторические данные активации за 6 месяцев, конверсия в первую покупку, ARPU по сегментам.",
   deliver:["Дизайн эксперимента: метрики, группы, длительность","Расчёт необходимого размера выборки","Риски и что может пойти не так"],
   tip:"Сначала определите главную метрику. Если это активация — платный онбординг почти наверняка её ухудшит. Что тогда мы измеряем?",
   rubric:[["Корректность дизайна",35],["Статистическая грамотность",30],["Оценка рисков",20],["Ясность выводов",15]]},

  {id:2,t:"Landing для SaaS-стартапа",co:"Click",logo:"C",color:"#00A6D6",
   role:"Маркетолог",lvl:"Junior",dur:"4–6 ч",tags:["Копирайтинг","CRO","Маркетинг"],dl:"15 июля",xp:90,field:"Маркетинг",cat:"Маркетинг",
   brief:"Стартап запускает сервис автоматизации отчётности для малого бизнеса. Конверсия текущего лендинга — 0,8%. Переработайте структуру и текст.",
   data:"Текущий лендинг, записи 40 сессий пользователей, интервью с 5 клиентами, анализ трёх конкурентов.",
   deliver:["Структура нового лендинга по экранам","Заголовок и подзаголовок первого экрана","Три гипотезы для A/B-теста"],
   tip:"Посмотрите интервью: клиенты говорят про боль «трачу выходные на отчёты». В текущем заголовке об этом ни слова.",
   rubric:[["Понимание аудитории",30],["Качество текста",30],["Структура и логика",25],["Гипотезы для теста",15]]},

  {id:3,t:"Сегментация клиентов для рассылки",co:"Payme",logo:"P",color:"#12A5A0",
   role:"CRM-маркетолог",lvl:"Middle",dur:"3–5 ч",tags:["Сегментация","Excel","CRM"],dl:"18 июля",xp:110,field:"Маркетинг",cat:"Маркетинг",
   brief:"Массовая рассылка даёт 2% открытий и растит отписки. Разбейте базу на сегменты и предложите разный контент для каждого.",
   data:"База 50 тыс. клиентов: частота транзакций, средний чек, давность последней активности, история откликов.",
   deliver:["Модель сегментации с обоснованием","Контент-стратегия для каждого сегмента","Прогноз метрик после внедрения"],
   tip:"RFM-анализ — самый быстрый путь. Но подумайте, что делать со «спящими» клиентами: их больше половины базы.",
   rubric:[["Логика сегментации",35],["Практичность решения",30],["Работа с данными",20],["Прогноз метрик",15]]},

  {id:4,t:"Дизайн экрана оплаты для маркетплейса",co:"Uzum",logo:"U",color:"#7000FF",
   role:"UX/UI дизайнер",lvl:"Junior",dur:"5–7 ч",tags:["Figma","UX","Прототип"],dl:"20 июля",xp:130,field:"Дизайн",cat:"Дизайн",
   brief:"На экране оплаты отваливается 23% пользователей. Аналитика показывает: люди не понимают, почему просят дополнительные данные. Перепроектируйте экран.",
   data:"Текущий макет, тепловая карта кликов, 12 записей сессий, отчёт службы поддержки.",
   deliver:["Прототип нового экрана в Figma","Обоснование каждого изменения","Что будете замерять после запуска"],
   tip:"Обратите внимание на порядок полей. Просить номер карты до того, как показали итоговую сумму — верный способ потерять человека.",
   rubric:[["Решение проблемы",35],["UX-логика",30],["Визуальное исполнение",20],["Обоснование",15]]},

  {id:5,t:"План найма для растущей команды",co:"EPAM",logo:"E",color:"#38B049",
   role:"HR-специалист",lvl:"Junior",dur:"3–4 ч",tags:["Рекрутинг","Планирование"],dl:"22 июля",xp:95,field:"HR",cat:"HR",
   brief:"Команда разработки растёт с 12 до 30 человек за полгода. Составьте план найма: воронка, сроки, бюджет, риски.",
   data:"Текущая воронка найма, среднее время закрытия вакансии, зарплатные вилки по рынку, бюджет.",
   deliver:["Помесячный план найма","Расчёт воронки: сколько кандидатов нужно на входе","Три главных риска и как их снизить"],
   tip:"Посчитайте конверсию воронки назад: чтобы нанять одного, сколько нужно откликов? И хватит ли рекрутеров на такой поток?",
   rubric:[["Реалистичность плана",35],["Расчёт воронки",30],["Оценка рисков",20],["Структура",15]]},

  {id:6,t:"Финмодель для запуска подписки",co:"TBC Bank",logo:"T",color:"#00AEEF",
   role:"Финансовый аналитик",lvl:"Middle",dur:"5–8 ч",tags:["Excel","Финмодели","Unit-экономика"],dl:"25 июля",xp:150,field:"Финансы",cat:"Финансы",
   brief:"Банк рассматривает премиум-подписку за 49 000 сум/мес. Постройте финмодель на 24 месяца и ответьте: когда окупится?",
   data:"Стоимость привлечения клиента, отток по месяцам, себестоимость обслуживания, данные похожих продуктов.",
   deliver:["Финмодель на 24 месяца","Расчёт LTV/CAC и точки безубыточности","Сценарии: пессимистичный, базовый, оптимистичный"],
   tip:"Главный рычаг здесь не цена, а отток. Посчитайте, как меняется LTV при оттоке 5% и 12% в месяц — разница вас удивит.",
   rubric:[["Корректность модели",35],["Unit-экономика",30],["Сценарный анализ",20],["Оформление",15]]},

  {id:7,t:"Автотесты для API платежей",co:"Payme",logo:"P",color:"#12A5A0",
   role:"QA-инженер",lvl:"Junior",dur:"4–6 ч",tags:["Тестирование","API","Автотесты"],dl:"28 июля",xp:115,field:"IT",cat:"Разработка",
   brief:"Платёжный API уходит в продакшн. Спроектируйте тест-план и напишите автотесты для критичных сценариев.",
   data:"Документация API (12 эндпоинтов), описание бизнес-логики, известные баги прошлых релизов.",
   deliver:["Тест-план с приоритизацией","Автотесты для трёх критичных сценариев","Чек-лист негативных кейсов"],
   tip:"Начните с денег: двойное списание и потерянный платёж — это то, за что увольняют. Остальное подождёт.",
   rubric:[["Покрытие критичных сценариев",35],["Качество тестов",30],["Негативные кейсы",20],["Приоритизация",15]]},
];
const JOBS=[
  {id:0,t:"Data Analyst Intern",co:"Ozon",logo:"O",color:"#005BFF",loc:"Ташкент",fmt:"Гибрид",match:91,dl:"20 июля",deadline:"2026-07-20",courses:[3,4],sal:"350–500 $",field:"IT",lvl:"Junior",type:"Стажировка",tags:["SQL","Python","Дашборды"],about:"Аналитика продуктовых метрик крупнейшего маркетплейса. Наставник, реальные данные, оффер по итогам.",team:"Product Analytics",remote:true,new:true,duties:["Строить дашборды по ключевым продуктовым метрикам","Проводить когортный анализ и A/B-тесты","Готовить выводы для продуктовых команд"],reqs:["SQL: JOIN, оконные функции, агрегации","Python (pandas) на базовом уровне","Понимание метрик retention и конверсии"]},
  {id:1,t:"Junior Product Manager",co:"Uzum",logo:"U",color:"#7000FF",loc:"Ташкент",fmt:"Офис",match:82,dl:"22 июля",deadline:"2026-07-22",courses:[3,4],sal:"400–600 $",field:"Продажи",lvl:"Junior",type:"Стажировка",tags:["Продукт","Аналитика","A/B"],about:"Развитие финтех-продукта: гипотезы, метрики, работа с командой разработки.",team:"Fintech",remote:false,new:true,duties:["Формулировать и проверять продуктовые гипотезы","Вести бэклог вместе с командой разработки","Считать метрики фичей после релиза"],reqs:["Понимание unit-экономики","Опыт работы с A/B-тестами (учебный подойдёт)","Умение писать понятные ТЗ"]},
  {id:2,t:"Marketing Intern",co:"Click",logo:"C",color:"#00A6D6",loc:"Удалённо",fmt:"Онлайн",match:76,dl:"25 июля",deadline:"2026-07-25",courses:[1,2,3,4],sal:"300–450 $",field:"Маркетинг",lvl:"Intern",type:"Стажировка",tags:["SMM","Копирайтинг","CRO"],about:"Продвижение платёжного сервиса: контент, кампании, аналитика воронки.",team:"Growth",remote:true,new:false,duties:["Готовить контент для соцсетей и блога","Запускать и анализировать рекламные кампании","Считать конверсию воронки и предлагать улучшения"],reqs:["Грамотный русский и узбекский язык","Базовое понимание SMM и таргетинга","Готовность работать с цифрами"]},
  {id:3,t:"UX/UI Design Intern",co:"EPAM",logo:"E",color:"#38B049",loc:"Ташкент",fmt:"Гибрид",match:68,dl:"28 июля",deadline:"2026-07-28",courses:[2,3,4],sal:"400–550 $",field:"Дизайн",lvl:"Junior",type:"Стажировка",tags:["Figma","Прототипы","UX"],about:"Проектирование интерфейсов для enterprise-клиентов под менторством senior-дизайнеров.",team:"Design Practice",remote:false,new:false,duties:["Проектировать экраны и пользовательские сценарии","Собирать интерактивные прототипы","Участвовать в дизайн-ревью с командой"],reqs:["Figma: компоненты, автолэйаут","Понимание принципов UX и доступности","Портфолио с учебными или личными проектами"]},
  {id:4,t:"Frontend Developer (React)",co:"Uzum",logo:"U",color:"#7000FF",loc:"Ташкент",fmt:"Офис",match:64,dl:"30 июля",deadline:"2026-07-30",courses:[4,5],sal:"500–800 $",field:"IT",lvl:"Junior",type:"Работа",tags:["React","TypeScript","REST"],about:"Разработка клиентских интерфейсов маркетплейса в продуктовой команде.",team:"Frontend",remote:false,new:false,duties:["Разрабатывать компоненты клиентского интерфейса","Интегрировать REST API","Покрывать код тестами и участвовать в код-ревью"],reqs:["React и TypeScript","Понимание REST и работы с состоянием","Git на уровне веток и pull request"]},
  {id:5,t:"HR Intern",co:"Beeline",logo:"B",color:"#FFCC00",loc:"Ташкент",fmt:"Гибрид",match:59,dl:"1 авг",deadline:"2026-08-01",courses:[2,3,4],sal:"250–400 $",field:"HR",lvl:"Intern",type:"Стажировка",tags:["Рекрутинг","Онбординг"],about:"Подбор и адаптация персонала телеком-оператора. Работа с ATS, интервью.",team:"People",remote:true,new:false,duties:["Вести первичный отбор и скрининг кандидатов","Помогать с онбордингом новых сотрудников","Поддерживать актуальность базы в ATS"],reqs:["Коммуникабельность и внимательность","Базовое понимание процессов подбора","Уверенное владение таблицами"]},
  {id:6,t:"Sales Development Rep",co:"Payme",logo:"P",color:"#12A5A0",loc:"Ташкент",fmt:"Офис",match:71,dl:"3 авг",deadline:"2026-08-03",courses:[3,4,5],sal:"400–700 $",field:"Продажи",lvl:"Junior",type:"Работа",tags:["B2B","CRM","Переговоры"],about:"Развитие B2B-продаж платёжного сервиса: лиды, демо, закрытие сделок.",team:"Sales",remote:false,new:true,duties:["Искать и квалифицировать B2B-лиды","Проводить демо-встречи с клиентами","Вести сделки в CRM до закрытия"],reqs:["Навыки деловых переговоров","Опыт работы с CRM (учебный подойдёт)","Уверенный узбекский и русский"]},
  {id:7,t:"Content Marketing Intern",co:"Anor Bank",logo:"A",color:"#E8542E",loc:"Удалённо",fmt:"Онлайн",match:62,dl:"5 авг",deadline:"2026-07-12",courses:[1,2,3,4],sal:"300–400 $",field:"Маркетинг",lvl:"Intern",type:"Стажировка",tags:["SEO","Контент","Email"],about:"Контент-маркетинг цифрового банка: блог, рассылки, соцсети.",team:"Marketing",remote:true,new:false,duties:["Писать статьи для блога и email-рассылок","Оптимизировать материалы под SEO","Планировать контент-календарь"],reqs:["Отличный письменный язык","Базовое понимание SEO","Умение работать с редакторами и CMS"]},
  {id:8,t:"QA Engineer Intern",co:"EPAM",logo:"E",color:"#38B049",loc:"Ташкент",fmt:"Гибрид",match:66,dl:"8 авг",deadline:"2026-08-08",courses:[3,4],sal:"350–500 $",field:"IT",lvl:"Junior",type:"Стажировка",tags:["Тестирование","Автотесты"],about:"Ручное и авто-тестирование web-приложений в международных проектах.",team:"QA Practice",remote:false,new:false,duties:["Составлять и выполнять тест-кейсы","Заводить и верифицировать баги","Помогать в написании автотестов"],reqs:["Понимание видов тестирования","Базовые знания SQL и HTTP","Внимание к деталям"]},
  {id:9,t:"Financial Analyst Intern",co:"TBC Bank",logo:"T",color:"#00AEEF",loc:"Ташкент",fmt:"Офис",match:73,dl:"10 авг",deadline:"2026-07-08",courses:[4,5],sal:"400–600 $",field:"Финансы",lvl:"Junior",type:"Стажировка",tags:["Excel","Финмодели","Отчётность"],about:"Финансовое моделирование и отчётность в розничном банке.",team:"Finance",remote:false,new:true,duties:["Готовить управленческую отчётность","Строить и поддерживать финансовые модели","Анализировать отклонения план-факт"],reqs:["Excel на продвинутом уровне","Понимание бухгалтерской отчётности","Аккуратность в работе с цифрами"]},
  {id:10,t:"Data Analyst (Remote)",co:"EPAM Global",logo:"E",color:"#38B049",loc:"Польша · удалённо",fmt:"Онлайн",match:70,dl:"15 авг",deadline:"2026-08-15",courses:[4,5],sal:"1200–1800 $",field:"IT",lvl:"Junior",type:"Работа",abroad:true,tags:["SQL","Python","BI"],about:"Международная команда аналитики. Полностью удалённо, релокация не требуется.",team:"Analytics",remote:true,new:true,duties:["Строить отчётность для клиентов из ЕС","Работать с распределённой командой","Поддерживать дашборды"],reqs:["Английский B2+","SQL и Python","Готовность к гибкому графику"]},
  {id:11,t:"Junior QA (Kazakhstan)",co:"Kaspi",logo:"K",color:"#F14635",loc:"Алматы",fmt:"Гибрид",match:65,dl:"20 авг",deadline:"2026-08-20",courses:[3,4,5],sal:"800–1200 $",field:"IT",lvl:"Junior",type:"Работа",abroad:true,tags:["Тестирование","Автотесты","API"],about:"Тестирование финтех-продуктов крупнейшего супераппа Казахстана. Возможна релокация.",team:"QA",remote:false,new:false,duties:["Тестировать мобильные и web-приложения","Писать автотесты","Работать с API-тестами"],reqs:["Английский B1+","Опыт тест-кейсов","Базовое программирование"]},
];
/* real match: base on field alignment with chosen work-fields + diagnostics completion */
/* a job field ("IT") matches a chosen interest ("IT / Разработка") if either
   contains the other's leading token — keeps 30-item list compatible with job data */
function fieldMatches(jobField,chosen){
  const norm=x=>String(x||'').toLowerCase().split('/')[0].trim();
  const jf=norm(jobField);
  return (chosen||[]).some(c=>{ const cf=norm(c); return cf===jf || cf.includes(jf) || jf.includes(cf); });
}
/* how many of a job's required tags the profile actually covers (0..1) */
function skillCoverage(item){
  const mine=(typeof MOCK!=='undefined'&&MOCK.reg&&MOCK.reg.skillsArr)||[];
  const tags=item.tags||[];
  if(!tags.length||!mine.length) return 0;
  const hit=tags.filter(t=>mine.some(s=>{
    const a=s.toLowerCase(), b=t.toLowerCase();
    return a===b||a.includes(b)||b.includes(a);
  })).length;
  return hit/tags.length;
}
function matchFor(item){
  let m=40;
  const fields=(typeof MOCK!=='undefined'&&MOCK.workFields)||[];
  if(item.field && fieldMatches(item.field,fields)) m+=25;      // interest match
  else if(fields.length) m+=8;                                   // some profile exists
  m += Math.round(skillCoverage(item)*25);                       // real skill overlap
  if(typeof state!=='undefined'&&state._diag&&state._diag.done) m+=12; // diagnostics sharpen it
  return Math.min(98,m);
}
const CANDS={
  new:[["Анна К.","Data Analyst · 92%"],["Игорь П.","Product · 84%"]],
  screen:[["Мария С.","Marketing · 78%"],["Дилшод Р.","Analyst · 71%"]],
  interview:[["Нилуфар А.","Product · 88%"]],
  offer:[["Тимур Б.","Data Analyst · 95%"]],
};
const COHORTS=[
  {name:"Аналитика данных · 2025",count:48,ready:78,offers:14},
  {name:"Продуктовый менеджмент",count:36,ready:64,offers:8},
  {name:"Дизайн-мышление",count:29,ready:52,offers:5},
  {name:"Digital-маркетинг",count:41,ready:41,offers:3},
];
const STUDENTS=[
  {name:"Анна Каримова",cohort:"Аналитика",step:"8/10",ready:"88%",status:"interview",sims:6,apps:2},
  {name:"Игорь Петров",cohort:"Продукт",step:"6/10",ready:"71%",status:"active",sims:4,apps:1},
  {name:"Мария Соколова",cohort:"Маркетинг",step:"4/10",ready:"52%",status:"active",sims:2,apps:0},
  {name:"Дилшод Рахимов",cohort:"Аналитика",step:"9/10",ready:"94%",status:"offer",sims:7,apps:3},
  {name:"Нилуфар Азизова",cohort:"Продукт",step:"3/10",ready:"38%",status:"stalled",sims:1,apps:0},
];

/* ============================================================
   CORE MOCK-ДАННЫЕ. Все числа — демо, не реальные метрики.
   Даты считаются относительно TODAY (2026-07-10) для детерминизма.
   ============================================================ */
function dOffset(days){ const d=new Date(TODAY); d.setDate(d.getDate()+days); return d.toISOString().slice(0,10); }

/* ============================================================
   ЕДИНАЯ МОДЕЛЬ ПРАКТИКИ — источник истины.
   Один объект «практика» = студент + компания + факультет + договор + дневник.
   Дневник, реестр договоров и KPI деканата — ПРОЕКЦИИ этого реестра,
   поэтому один и тот же студент виден всеми тремя ролями согласованно.
   Все числа — демо. Даты относительно TODAY.
   ============================================================ */
const PRACTICE=[ // MOCK: no backend
  {
    id:"P-014", student:"Анна Каримова", faculty:"Информатика", company:"Uzum",
    role:"Data Analyst Intern", mentor:"Ботир Юсупов", goalHours:240,
    contractId:"PR-2026-014", contractStatus:"signed", signed:{uni:true,student:true,company:true}, contractDate:dOffset(-42),
    program:"Квалификационная практика · 240 ч",
    entries:[
      {week:1, date:dOffset(-40), hours:32, task:"Онбординг, доступы, знакомство с дашбордами продаж", status:"approved", grade:"A"},
      {week:2, date:dOffset(-33), hours:36, task:"SQL-выгрузки по когортам пользователей, чистка данных", status:"approved", grade:"A"},
      {week:3, date:dOffset(-26), hours:30, task:"A/B-анализ баннера на главной, отчёт для команды", status:"approved", grade:"B"},
      {week:4, date:dOffset(-19), hours:34, task:"Дашборд retention в Metabase", status:"approved", grade:"A"},
      {week:5, date:dOffset(-12), hours:28, task:"Модель оттока: разметка признаков", status:"submitted", grade:null},
      {week:6, date:dOffset(-5),  hours:26, task:"Презентация промежуточных результатов", status:"submitted", grade:null},
      {week:7, date:dOffset(2),   hours:0,  task:"Запись за неделю не сдана", status:"overdue", grade:null, due:dOffset(-1)},
    ],
    criteria:[
      {name:"Технические навыки (SQL, аналитика)", score:4},
      {name:"Самостоятельность", score:5},
      {name:"Коммуникация в команде", score:4},
      {name:"Соблюдение сроков", score:3},
    ],
    employed:true,
  },
  {
    id:"P-021", student:"Дилшод Рахимов", faculty:"Информатика", company:"Ozon",
    role:"Backend Intern", mentor:"Сергей Ким", goalHours:240,
    contractId:"PR-2026-021", contractStatus:"awaiting_company", signed:{uni:true,student:true,company:false}, contractDate:dOffset(-8),
    program:"Квалификационная практика · 240 ч",
    entries:[
      {week:1, date:dOffset(-6), hours:20, task:"Настройка окружения, первый сервис", status:"approved", grade:"B"},
      {week:2, date:dOffset(1),  hours:0,  task:"Запись за неделю не сдана", status:"overdue", grade:null, due:dOffset(0)},
    ],
    criteria:[
      {name:"Технические навыки (Go, БД)", score:4},
      {name:"Самостоятельность", score:3},
      {name:"Коммуникация в команде", score:4},
      {name:"Соблюдение сроков", score:2},
    ],
    employed:false,
  },
  {
    id:"P-027", student:"Игорь Петров", faculty:"Менеджмент", company:"Click",
    role:"Product Intern", mentor:"Алия Усманова", goalHours:160,
    contractId:"PR-2026-027", contractStatus:"awaiting_student", signed:{uni:true,student:false,company:false}, contractDate:dOffset(-3),
    program:"Учебная практика · 160 ч",
    entries:[], // ещё не начал — договор не подписан студентом
    criteria:[],
    employed:false,
  },
  {
    id:"P-031", student:"Мария Соколова", faculty:"Дизайн", company:"EPAM",
    role:"UX Intern", mentor:"—", goalHours:240,
    contractId:"PR-2026-031", contractStatus:"draft", signed:{uni:false,student:false,company:false}, contractDate:dOffset(-1),
    program:"Квалификационная практика · 240 ч",
    entries:[],
    criteria:[],
    employed:false,
  },
];
/* найти практику по студенту / договору (связки между ролями) */
function practiceByStudent(name){ return PRACTICE.find(p=>p.student===name); }
function practiceByContract(cid){ return PRACTICE.find(p=>p.contractId===cid); }
/* сумма подтверждённых часов по практике */
function practiceHours(p){ return (p.entries||[]).filter(e=>e.status==='approved').reduce((s,e)=>s+e.hours,0); }

/* ---- ПРОЕКЦИЯ 1: дневник практики (для текущего студента демо = Анна Каримова) ----
   student:diary читает DIARY; DIARY указывает на первую практику как «мою». */
const MY_PRACTICE_ID="P-014";
function myPractice(){ return PRACTICE.find(p=>p.id===MY_PRACTICE_ID)||PRACTICE[0]; }
/* DIARY сохранён как объект-обёртка над моей практикой для обратной совместимости */
const DIARY=(()=>{ const p=myPractice(); return {
  get goalHours(){return p.goalHours;}, get company(){return p.company;},
  get mentor(){return p.mentor;}, get role(){return p.role;},
  get entries(){return p.entries;}, get criteria(){return p.criteria;},
};})();

/* ---- ПРОЕКЦИЯ 2: реестр договоров (из PRACTICE) ---- */
const CONTRACTS=PRACTICE.map(p=>({
  id:p.contractId, student:p.student, company:p.company, faculty:p.faculty,
  program:p.program, status:p.contractStatus, signed:p.signed, date:p.contractDate,
}));
const CONTRACT_STATUS={
  draft:['b-gray','Черновик'], awaiting_uni:['b-amber','Ждёт вуз'],
  awaiting_student:['b-amber','Ждёт студента'], awaiting_company:['b-amber','Ждёт компанию'],
  signed:['b-green','Подписан'],
};

/* ---- ПРОЕКЦИЯ 3: KPI по факультетам ---- 
   Базовые агрегаты демо-данные, НО строки по практикующим студентам
   (onInternship/employed) дополняются реальными записями из PRACTICE,
   чтобы KPI отражал тех же студентов, что видны в договорах и дневнике. */
const KPI_BASE=[ // демо-агрегаты (фон, не связанный со студентами поимённо)
  {name:"Информатика", students:210, baseIntern:62, baseEmployed:47, avgGrade:4.3},
  {name:"Менеджмент",  students:180, baseIntern:40, baseEmployed:33, avgGrade:4.0},
  {name:"Дизайн",      students:95,  baseIntern:21, baseEmployed:14, avgGrade:4.1},
  {name:"Экономика",   students:160, baseIntern:29, baseEmployed:19, avgGrade:3.8},
];
function kpiFaculties(){
  return KPI_BASE.map(f=>{
    const inFac=PRACTICE.filter(p=>p.faculty===f.name);
    const activeInterns=inFac.filter(p=>p.contractStatus==='signed'||p.entries.length>0).length;
    const employed=inFac.filter(p=>p.employed).length;
    return {name:f.name, students:f.students, avgGrade:f.avgGrade,
      onInternship:f.baseIntern+activeInterns, employed:f.baseEmployed+employed,
      named:inFac};   // поимённый список для drill-down
  });
}

/* ============================================================
   ПАСПОРТ НАВЫКОВ — связующее звено CORE ↔ BRIDGE.
   Навыки студента накапливаются из ЧЕТЫРЁХ источников, каждый с верификацией:
   - диагностика (самооценка+тест) → не верифицирован, только заявлен
   - симуляции (решённые кейсы)     → верифицирован платформой
   - дневник практики (оценка ментора) → верифицирован ментором компании
   - HTD-трек (пройденные модули)   → верифицирован обучением
   Витрина талантов и HTD берут ИМЕННО верифицированные навыки отсюда.
   Все данные — демо.
   ============================================================ */
const SKILL_SOURCE={
  diagnostic:{label:'Диагностика',   ic:'brain',    verified:false, note:'заявлено по самооценке и тесту'},
  simulation:{label:'Симуляции',     ic:'puzzle',   verified:true,  note:'подтверждено решёнными кейсами'},
  mentor:    {label:'Практика',      ic:'check',    verified:true,  note:'подтверждено ментором компании'},
  htd:       {label:'HTD-трек',      ic:'trophy',   verified:true,  note:'подтверждено обучением под заказ'},
  task:      {label:'Задача',        ic:'list',     verified:true,  note:'подтверждено принятой задачей от компании'},
};
/* навыки, заработанные через принятые задачи (TASKS-модуль).
   Заполняется taskAccept() — так accepted-задача пишет в паспорт студента. */
const TASK_SKILLS=[]; // MOCK: {name, level, source:'task', evidence}
/* Паспорт текущего студента демо (Анна Каримова = моя практика P-014).
   Навыки увязаны с её дневником (SQL, Python, дашборды, A/B) и диагностикой. */
function skillsPassport(){
  const p=myPractice();
  const mentorGrade=p.criteria.length? Math.round(p.criteria.reduce((s,c)=>s+c.score,0)/p.criteria.length/5*100):0;
  const hrs=practiceHours(p);
  // навык: name, level%, source-ключ, evidence-строка
  const base=[
      {name:'SQL',              level:82, source:'mentor',     evidence:`${hrs} ч практики в ${p.company}, оценка ментора`},
      {name:'Python',           level:70, source:'mentor',     evidence:`дневник практики: выгрузки и модель оттока`},
      {name:'Дашборды (BI)',    level:75, source:'simulation', evidence:`решённый кейс + дашборд retention на практике`},
      {name:'A/B-тесты',        level:64, source:'simulation', evidence:`A/B-анализ баннера, отчёт для команды`},
      {name:'Аналитика данных', level:72, source:'diagnostic', evidence:`диагностика: самооценка + тест`},
      {name:'Коммуникация',     level:81, source:'diagnostic', evidence:`диагностика: soft-skills`},
  ];
  // навыки из принятых задач: если навык уже есть — поднимаем уровень и переотмечаем источник
  TASK_SKILLS.forEach(ts=>{
    const ex=base.find(b=>b.name.toLowerCase()===ts.name.toLowerCase());
    if(ex){ ex.level=Math.max(ex.level,ts.level); ex.source='task'; ex.evidence=ts.evidence; }
    else base.push(ts);
  });
  return {
    student:p.student, company:p.company, role:p.role,
    skills:base,
    mentorGrade, hrs, goalHours:p.goalHours,
  };
}
/* только верифицированные навыки — их показывает витрина работодателю */
function verifiedSkills(){ return skillsPassport().skills.filter(s=>SKILL_SOURCE[s.source] && SKILL_SOURCE[s.source].verified); }

/* ============================================================
   MATCH SCORE — прозрачное соответствие студента требованиям HTD-заказа.
   Формула (Доп-блок A, детерминированная, без рандома):
   для каждого требуемого навыка: есть+verified = полный вес,
   есть но не verified = половина, нет = 0. score = взвешенная доля.
   Всегда возвращаем И число, И gap (что дообучить) — это наш дифференциатор
   против «магического процента» госплатформы.
   Навыки сопоставляются по нормализованному имени (регистр/пробелы/синонимы).
   ============================================================ */
function normSkill(s){
  return String(s||'').toLowerCase().trim()
    .replace('дашборды (bi)','дашборды').replace('bi','дашборды')
    .replace('a/b-тесты','a/b').replace('ab-тесты','a/b')
    .replace('аналитика данных','аналитика');
}
/* matchScore(requiredSkills[], studentSkills[{name,source}]) → {score, covered, half, missing, gap[], total} */
function matchScore(required, studentSkills){
  const req=(required||[]).map(normSkill);
  const verified=new Set((studentSkills||[]).filter(s=>SKILL_SOURCE[s.source]&&SKILL_SOURCE[s.source].verified).map(s=>normSkill(s.name)));
  const declared=new Set((studentSkills||[]).map(s=>normSkill(s.name)));
  let sum=0; const covered=[], half=[], gap=[];
  (required||[]).forEach((orig,i)=>{
    const n=req[i];
    if(verified.has(n)){ sum+=1; covered.push(orig); }
    else if(declared.has(n)){ sum+=0.5; half.push(orig); }
    else { gap.push(orig); }
  });
  const total=req.length||1;
  return { score:Math.round(sum/total*100), covered, half, gap, total:req.length,
           coveredCount:covered.length };
}
/* Match Score текущего студента (демо-паспорт) против конкретного HTD-заказа */
function myMatchForOrder(order){ return matchScore(order.skills, skillsPassport().skills); }

/* ---- РОЛЬ МЕНТОРА: демо-ментор видит своих практикантов ---- */
const CURRENT_MENTOR="Ботир Юсупов";   // демо: под этим ментором заходим
function mentorPractices(){ return PRACTICE.filter(p=>p.mentor===CURRENT_MENTOR); }
/* записи, ожидающие проверки ментором (submitted/overdue) по всем его практикантам */
function mentorPendingEntries(){
  const out=[];
  mentorPractices().forEach(p=>p.entries.forEach((e,i)=>{
    if(e.status==='submitted'||e.status==='overdue') out.push({p,e,i});
  }));
  return out;
}
/* MOCK: ментор подтверждает часы записи и ставит оценку */
function mentorApprove(practiceId,entryIdx,grade){
  const p=PRACTICE.find(x=>x.id===practiceId); if(!p) return;
  const e=p.entries[entryIdx]; if(!e) return;
  e.status='approved'; if(grade) e.grade=grade;
  notify('check','Практика',`Ментор подтвердил часы за неделю ${e.week} (${p.student}) — засчитано`);
  toast('Часы подтверждены (демо)');
  go('review');
}

/* ============================================================
   РЕЕСТРЫ ПАРТНЁРОВ — стороны договора выбирают друг друга отсюда.
   Вуз видит компании-партнёры, компания видит вузы-партнёры.
   Число совместных практик берётся из единой модели PRACTICE.
   Все данные — демо.
   ============================================================ */
const PARTNER_COMPANIES=[ // компании-партнёры (реестр у вуза)
  {name:"Uzum",  field:"E-commerce",  city:"Ташкент", status:"active",  contact:"hr@uzum.uz"},
  {name:"Ozon",  field:"E-commerce",  city:"Ташкент", status:"active",  contact:"talent@ozon.uz"},
  {name:"Click", field:"Финтех",      city:"Ташкент", status:"active",  contact:"jobs@click.uz"},
  {name:"EPAM",  field:"IT-услуги",   city:"Ташкент", status:"pending", contact:"uz-hr@epam.com"},
  {name:"Artel", field:"Производство",city:"Ташкент", status:"invited", contact:"—"},
];
const PARTNER_UNIS=[ // вузы-партнёры (реестр у компании)
  {name:"ТУИТ",        full:"Ташкентский университет информационных технологий", city:"Ташкент", status:"active",  students:210},
  {name:"Вестминстер", full:"Вестминстерский университет в Ташкенте",            city:"Ташкент", status:"active",  students:180},
  {name:"Инха",        full:"Университет Инха в Ташкенте",                        city:"Ташкент", status:"active",  students:150},
  {name:"ТГЭУ",        full:"Ташкентский государственный экономический универ.",  city:"Ташкент", status:"pending", students:160},
];
const PARTNER_STATUS={ active:['b-green','Активный'], pending:['b-amber','На согласовании'], invited:['b-gray','Приглашён'] };
/* связь через PRACTICE: сколько практик у компании / у вуза */
function companyPractices(name){ return PRACTICE.filter(p=>p.company===name).length; }
function facultyPractices(){ return PRACTICE.length; }

/* ============================================================
   CAREER.EDU.UZ SYNC — выгрузка обязательных данных в госплатформу. MOCK.
   Позиционирование: дополняем, а не заменяем. Обязательные данные уходят
   в госсистему автоматически — это снимает главное возражение вуза.
   Маппинг наших полей на поля career.edu.uz + статусы записей.
   ============================================================ */
const CAREER_EDU_SYNC={ lastSyncedAt:dOffset(-1), exportedRecords:2 };
/* маппинг наших полей → поля госплатформы (демо-таблица соответствия) */
const CAREER_EDU_MAP=[
  {ours:"Студент (ID, ФИО, вуз)", gov:"talaba_id / F.I.O / OTM", note:"без персональных данных — регистрация на нашей стороне"},
  {ours:"Статус практики", gov:"amaliyot_holati", note:"active / completed"},
  {ours:"Трёхсторонний договор", gov:"shartnoma_holati", note:"signed → передаётся факт, не сам документ"},
  {ours:"Факт трудоустройства", gov:"ish_bilan_taminlash", note:"employed → главный KPI госплатформы"},
];
/* записи к выгрузке — вытекают из PRACTICE (единый стор) */
function careerEduRecords(){
  return PRACTICE.map(p=>({
    student:p.student, faculty:p.faculty, company:p.company,
    internship: p.entries.length? (p.contractStatus==='signed'?'completed':'active') : 'not_started',
    contract: p.contractStatus==='signed'?'signed':'draft',
    employed: !!p.employed,
    // статус выгрузки: подписанные+трудоустроенные считаем выгруженными (демо)
    synced: (p.contractStatus==='signed' && p.employed)
  }));
}

/* 4. Hire-Train-Deploy — заказы компаний на кадры */
const HTD_ORDERS=[ // MOCK: no backend
  {id:"HTD-07", company:"Uzum", role:"Data Analyst", count:12, deadline:dOffset(45),
   skills:["SQL","Python","дашборды","A/B-тесты"], stage:"train",
   funnel:{applied:86, enrolled:24, training:18, deployed:0}, track:"Аналитика данных · 8 модулей",
   modules:["SQL с нуля","Python для анализа","Статистика и A/B","Дашборды в BI","Продуктовые метрики","Кейс: воронка продаж","Симуляция Uzum","Защита проекта"]},
  {id:"HTD-11", company:"Ozon", role:"Backend Junior", count:8, deadline:dOffset(60),
   skills:["Go","PostgreSQL","REST","Docker"], stage:"recruit",
   funnel:{applied:54, enrolled:0, training:0, deployed:0}, track:"Backend-инженерия · 10 модулей",
   modules:["Основы Go","PostgreSQL","REST API","Docker и деплой","Тестирование","Кейс: сервис заказов"]},
  {id:"HTD-04", company:"Click", role:"Growth Marketer", count:6, deadline:dOffset(-5),
   skills:["перформанс","аналитика","копирайтинг"], stage:"deploy",
   funnel:{applied:71, enrolled:20, training:20, deployed:14}, track:"Growth-маркетинг · 6 модулей",
   modules:["Перформанс-каналы","Аналитика кампаний","Копирайтинг","Кейс: рост Click","Защита проекта"]},
];
const HTD_STAGE={
  recruit:['b-blue','Набор'], train:['b-purple','Обучение'], deploy:['b-green','Трудоустройство'], done:['b-gray','Завершён'],
};

/* ============================================================
   TRAINING TRACK — трек подготовки студента под HTD-заказ.
   НЕ курс: подготовка под требования конкретного заказа.
   Прогресс по модулям детерминирован (демо). Пройденные модули →
   подтверждают навыки, связанные с заказом.
   Демо-студент Анна (S-014) готовится под HTD-07 (аналитика Uzum).
   ============================================================ */
const MY_STUDENT_ID_TRACK="S-014"; // демо-студент, чей трек показываем (Анна)
/* Реестр треков: самостоятельные объекты, привязанные к HTD-заказу,
   с зачисленными студентами и прогрессом по каждому (модель ТЗ:
   TrainingTrack{ htdOrderId, modules, enrolled[], progress:{studentId:percent} }).
   Модули берём из заказа. Прогресс детерминирован (демо). */
const TRAINING_TRACKS=[
  { id:"TRK-07", htdOrderId:"HTD-07",
    enrolled:["S-014","S-041","S-052"],
    // прогресс в модулях (сколько модулей из трека пройдено каждым)
    modsDone:{ "S-014":6, "S-041":3, "S-052":1 },
    names:{ "S-014":"Анна Каримова", "S-041":"Тимур Бобоев", "S-052":"Дилшод Рахимов" } },
  { id:"TRK-11", htdOrderId:"HTD-11",
    enrolled:["S-061"],
    modsDone:{ "S-061":2 },
    names:{ "S-061":"Азиз Турсунов" } },
];
function trackByOrder(orderId){ return TRAINING_TRACKS.find(t=>t.htdOrderId===orderId); }
function trackModulesFor(trk, studentId){
  const o=HTD_ORDERS.find(x=>x.id===trk.htdOrderId)||HTD_ORDERS[0];
  const done=trk.modsDone[studentId]||0;
  const mods=(o.modules||[]).map((m,i)=>({title:m, done:i<done, current:i===done}));
  const total=mods.length||1;
  return { order:o, modules:mods, doneN:mods.filter(m=>m.done).length, total, percent:Math.round(Math.min(done,total)/total*100) };
}
/* обёртка для страницы студента: трек текущего демо-студента */
function myTrack(){
  const trk=TRAINING_TRACKS.find(t=>t.enrolled.includes(MY_STUDENT_ID_TRACK))||TRAINING_TRACKS[0];
  return { ...trackModulesFor(trk, MY_STUDENT_ID_TRACK), track:trk };
}
const INTERNSHIPS=[
  {name:"Data Analyst Intern",apps:23,status:"Опубликовано"},
  {name:"Product Manager Intern",apps:18,status:"Опубликовано"},
  {name:"Marketing Intern",apps:31,status:"Опубликовано"},
  {name:"QA Intern",apps:0,status:"Черновик"},
];

/* ============================================================
   TASKS — единая модель микрозадач (источник правды для всех ролей). MOCK.
   Задача от компании: тест кандидата ('test') или учебный микропроект ('project').
   Может быть привязана к HTD-заказу (htdOrderId) или standalone.
   Оплата (reward.kind==='stipend') — ВНЕ платформы, здесь только пометка.
   Машина состояний: open→in_progress→submitted→reviewed→accepted|rejected.
   companyId ссылается на COMPANIES[].id; studentId — демо-идентификаторы.
   Все даты — детерминированы через dOffset() от TODAY.
   ============================================================ */
const MY_STUDENT_ID="S-014"; // Анна Каримова (та же, что владеет паспортом/практикой P-014)
const TASK_TYPE={ test:['b-purple','Тест кандидата'], project:['b-blue','Учебный проект'], gig:['b-green','Оплачиваемый гиг'] };
const TASK_STATUS={
  open:['b-gray','Открыта'], in_progress:['b-blue','В работе'], submitted:['b-amber','На проверке'],
  reviewed:['b-purple','Проверена'], accepted:['b-green','Принята'], rejected:['b-red','Отклонена'],
};
/* эскроу — ДЕМО. Платформа НЕ проводит реальных денег: это витрина контура оплаты.
   held → сумма условно заморожена при назначении; released → выплачена при приёмке. */
const ESCROW_STATUS={ none:['b-gray','—'], held:['b-amber','Заморожено'], released:['b-green','Выплачено'], disputed:['b-red','Спор'], refunded:['b-gray','Возврат'] };
const CUR="сум"; // демо-валюта
function fmtMoney(n){ return n? n.toLocaleString('ru-RU')+' '+CUR : '—'; }
const TASKS=[ // MOCK: no backend
  {id:"T-101", title:"SQL-выгрузка: топ-категории по выручке", companyId:0, htdOrderId:"HTD-07",
   type:"project", skills:["SQL","Аналитика данных"], reward:{kind:'none',note:'',price:0}, deadline:dOffset(9),
   description:"Написать SQL-запрос по витрине продаж: топ-10 категорий по выручке за квартал с разбивкой по месяцам. Прислать запрос и краткий вывод.",
   status:"open", applicants:[], assigneeId:null, submission:null, review:null, payment:{escrow:'none',amount:0}},
  {id:"T-102", title:"Дашборд retention для команды", companyId:0, htdOrderId:"HTD-07",
   type:"gig", skills:["Дашборды (BI)","SQL"], reward:{kind:'paid',note:'оплата по договору практики, вне платформы',price:1500000}, deadline:dOffset(14),
   description:"Собрать дашборд удержания пользователей (cohort retention) на демо-данных. Показать помесячные когорты и ключевые метрики.",
   status:"in_progress", applicants:[MY_STUDENT_ID], assigneeId:MY_STUDENT_ID, submission:null, review:null, payment:{escrow:'held',amount:1500000}},
  {id:"T-103", title:"A/B-анализ баннера на главной", companyId:0, htdOrderId:null,
   type:"test", skills:["A/B-тесты","Аналитика данных"], reward:{kind:'none',note:'',price:0}, deadline:dOffset(4),
   description:"Оценить результаты A/B-теста баннера: посчитать значимость, дать рекомендацию раскатывать или нет. Данные приложены (заглушка).",
   status:"submitted", applicants:[MY_STUDENT_ID], assigneeId:MY_STUDENT_ID,
   submission:{text:"Провела z-тест долей: uplift +2.1%, p=0.03. Рекомендую раскатывать на 100%.", attachments:["ab_report.pdf (демо)"], submittedAt:dOffset(-1)}, review:null, payment:{escrow:'none',amount:0}},
  {id:"T-104", title:"Python-скрипт очистки данных", companyId:1, htdOrderId:"HTD-11",
   type:"gig", skills:["Python"], reward:{kind:'paid',note:'оплата по договору практики, вне платформы',price:900000}, deadline:dOffset(-2),
   description:"Написать скрипт на Python для очистки CSV: пропуски, дубликаты, типы. Прислать код и пример до/после.",
   status:"open", applicants:[], assigneeId:null, submission:null, review:null, payment:{escrow:'none',amount:900000}},
  {id:"T-105", title:"Разбор воронки продаж (кейс)", companyId:2, htdOrderId:null,
   type:"test", skills:["Аналитика данных","Коммуникация"], reward:{kind:'none',note:'',price:0}, deadline:dOffset(7),
   description:"Проанализировать воронку продаж по демо-данным, найти узкое место, предложить гипотезы роста. Формат — короткая презентация.",
   status:"accepted", applicants:[MY_STUDENT_ID], assigneeId:MY_STUDENT_ID,
   submission:{text:"Узкое место — переход из корзины в оплату (конверсия 41%). Гипотезы: упрощение оплаты, рассрочка.", attachments:["funnel_case.pdf (демо)"], submittedAt:dOffset(-6)},
   review:{mentorId:"Ботир Юсупов", scores:{hard:4, soft:5}, comment:"Сильный разбор, чёткая рекомендация. Берём в шорт-лист.", decision:"accepted", reviewedAt:dOffset(-4)}, payment:{escrow:'none',amount:0}},
  {id:"T-106", title:"Лендинг для промо-акции (вёрстка)", companyId:0, htdOrderId:null,
   type:"gig", skills:["HTML/CSS","Дизайн"], reward:{kind:'paid',note:'оплата по договору практики, вне платформы',price:2200000}, deadline:dOffset(12),
   description:"Свёрстать одностраничный лендинг по готовому макету: адаптив, анимации появления, форма заявки. Прислать ссылку на демо.",
   status:"open", applicants:[], assigneeId:null, submission:null, review:null, payment:{escrow:'none',amount:2200000}},
];
let TASK_HIDDEN={}; // MOCK-модерация админа: id→true (скрыта с публикации)

/* ============================================================
   FREELANCERS — Fiverr-подобные профили исполнителей. MOCK.
   Рейтинг, уровень, число выполненных гигов, отзывы, портфолио.
   Связаны со студентами платформы (демо).
   ============================================================ */
const FL_LEVEL={ 1:['b-gray','Новичок'], 2:['b-blue','Уровень 1'], 3:['b-purple','Уровень 2'], 4:['b-green','Топ-исполнитель'] };
const FREELANCERS=[
  {id:MY_STUDENT_ID, name:"Анна Каримова", title:"Аналитик данных · SQL, Python, BI", level:3, rating:4.9, reviews:12, done:14, city:"Ташкент",
   skills:["SQL","Python","Дашборды (BI)","A/B-тесты"], from:"ТУИТ",
   portfolio:["Дашборд retention для Uzum","Разбор воронки продаж","A/B-анализ баннера"],
   feedback:[{by:"Uzum",stars:5,text:"Быстро и чисто, дашборд сразу пошёл в работу команды."},{by:"Click",stars:5,text:"Сильный аналитический разбор, рекомендуем."}]},
  {id:"S-021", name:"Дилшод Рахимов", title:"Backend-разработчик · Go, PostgreSQL", level:2, rating:4.6, reviews:5, done:6, city:"Ташкент",
   skills:["Go","PostgreSQL","REST","Docker"], from:"Инха",
   portfolio:["Сервис заказов (учебный)","Скрипт очистки данных"],
   feedback:[{by:"Ozon",stars:5,text:"Аккуратный код, всё по ТЗ."}]},
  {id:"S-031", name:"Мария Ким", title:"Frontend / вёрстка · HTML, CSS, JS", level:2, rating:4.7, reviews:8, done:9, city:"Ташкент",
   skills:["HTML/CSS","Дизайн","JavaScript"], from:"Вестминстер",
   portfolio:["Лендинги промо-акций","UI-кит для стартапа"],
   feedback:[{by:"EPAM",stars:4,text:"Хорошая вёрстка, мелкие правки по адаптиву."}]},
];
function freelancerById(id){ return FREELANCERS.find(f=>f.id===id); }
function myFreelancer(){ return freelancerById(MY_STUDENT_ID); }

/* ---- helpers ---- */
function taskCompany(t){ return (COMPANIES.find(c=>c.id===t.companyId)||{}).name || 'Компания'; }
function taskOverdue(t){ return t.deadline < dOffset(0) && !['accepted','rejected','reviewed'].includes(t.status); }
function taskIsPaid(t){ return t.reward && t.reward.kind==='paid' && t.reward.price>0; }
function tasksVisible(){ return TASKS.filter(t=>!TASK_HIDDEN[t.id]); }
function tasksForStudentFeed(){ return tasksVisible().filter(t=>t.status==='open'); }
function myTasks(){ return tasksVisible().filter(t=>t.applicants.includes(MY_STUDENT_ID)||t.assigneeId===MY_STUDENT_ID); }
function tasksByHtd(orderId){ return TASKS.filter(t=>t.htdOrderId===orderId); }
function tasksAcceptedCount(){ return TASKS.filter(t=>t.status==='accepted').length; }
function taskById(id){ return TASKS.find(t=>t.id===id); }

/* ---- МАШИНА СОСТОЯНИЙ (каждый переход проверяет права роли) ---- */
// студент откликается: open, ещё не в applicants
function taskApply(id){
  const t=taskById(id); if(!t||state.role!=='student') return;
  if(t.status!=='open'){ toast('Отклик возможен только на открытую задачу'); return; }
  if(!t.applicants.includes(MY_STUDENT_ID)) t.applicants.push(MY_STUDENT_ID);
  toast('Отклик отправлен (демо)'); notifyTask(t,'Ваш отклик отправлен: '+t.title); go('task-detail');
}
// компания назначает исполнителя из откликнувшихся: open→in_progress
function taskAssign(id,studentId){
  const t=taskById(id); if(!t||!(state.role==='company'||state.role==='mentor')) return;
  if(t.status!=='open'){ toast('Назначить можно только открытую задачу'); return; }
  if(!t.applicants.includes(studentId)){ toast('Назначить можно только откликнувшегося'); return; }
  t.assigneeId=studentId; t.status='in_progress';
  // ДЕМО-эскроу: при назначении оплачиваемого гига сумма условно замораживается
  if(FEATURES.tasks_payments && taskIsPaid(t)){ t.payment.escrow='held'; t.payment.amount=t.reward.price; }
  toast('Исполнитель назначен (демо)'); go('company:task-review');
}
// студент-assignee сдаёт работу: in_progress→submitted
function taskSubmit(id,text){
  const t=taskById(id); if(!t||state.role!=='student') return;
  if(t.assigneeId!==MY_STUDENT_ID){ toast('Сдать может только назначенный исполнитель'); return; }
  if(t.status!=='in_progress'){ toast('Сдать можно только задачу в работе'); return; }
  t.submission={text:text||'(без комментария)', attachments:["solution.zip (демо)"], submittedAt:dOffset(0)};
  t.status='submitted';
  toast('Работа отправлена на проверку (демо)'); notifyTask(t,'Работа отправлена на проверку: '+t.title); go('my-tasks');
}
// ментор компании-владельца проверяет: submitted→reviewed→accepted|rejected|rework
function taskReview(id,hard,soft,comment,decision){
  const t=taskById(id); if(!t||!(state.role==='company'||state.role==='mentor')) return;
  if(t.status!=='submitted'){ toast('Проверить можно только сданную работу'); return; }
  t.review={mentorId:CURRENT_MENTOR||'Ментор компании', scores:{hard,soft}, comment:comment||'', decision, reviewedAt:dOffset(0)};
  t.status='reviewed';
  if(decision==='accepted') taskAccept(t);
  else if(decision==='rework') taskReject(t,false); // вернуть в работу на доработку
  else taskReject(t,true);                          // rejected → закрыть
}
// принято: пишем навыки в паспорт (+ витрина автоматически, + HTD-воронка если привязана)
function taskAccept(t){
  t.status='accepted';
  const avg=Math.round(((t.review?.scores?.hard||4)+(t.review?.scores?.soft||4))/2);
  const level=Math.min(95, 60+avg*7);
  t.skills.forEach(sk=>{
    TASK_SKILLS.push({name:sk, level, source:'task',
      evidence:`принятая задача «${t.title}» от ${taskCompany(t)}${t.htdOrderId?' ('+t.htdOrderId+')':''}`});
  });
  // HTD-воронка: принятая задача под заказ = +1 к deployed (демо-связь)
  if(t.htdOrderId){ const o=HTD_ORDERS.find(o=>o.id===t.htdOrderId); if(o&&o.funnel&&o.funnel.deployed<o.count) o.funnel.deployed++; }
  // ДЕМО-эскроу: при приёмке оплачиваемого гига средства «выплачиваются» исполнителю
  if(FEATURES.tasks_payments && taskIsPaid(t) && t.payment.escrow==='held'){ t.payment.escrow='released'; }
  // фриланс-профиль исполнителя: +1 выполненный гиг, отзыв компании
  const fl=freelancerById(t.assigneeId);
  if(fl){ fl.done++; if(t.review){ fl.feedback.unshift({by:taskCompany(t),stars:Math.round((t.review.scores.hard+t.review.scores.soft)/2),text:t.review.comment||'Задача принята.'}); fl.reviews++; } }
  toast('Задача принята — навыки добавлены в паспорт (демо)');
  notifyTask(t,'Задача принята: навыки добавлены в паспорт — '+t.title);
  go('company:tasks');
}
// отклонено: doClose=true → закрыть (rejected); иначе вернуть в работу на доработку
function taskReject(t,doClose){
  if(doClose){ t.status='rejected'; if(FEATURES.tasks_payments && t.payment.escrow==='held'){ t.payment.escrow='refunded'; } toast('Задача отклонена и закрыта (демо)'); notifyTask(t,'Задача отклонена: '+t.title); }
  else { t.status='in_progress'; if(t.review) t.review.decision='rework'; toast('Отправлено на доработку (демо)'); notifyTask(t,'Задача возвращена на доработку: '+t.title); }
  go('company:tasks');
}
/* ДЕМО-эскроу — открытие спора (кнопка в UI). Реальных денег нет. */
function escrowDispute(id){
  const t=taskById(id); if(!t||!FEATURES.tasks_payments) return;
  if(t.payment.escrow!=='held'){ toast('Спор возможен только по замороженной сумме'); return; }
  t.payment.escrow='disputed'; toast('Открыт спор (демо) — арбитраж вне прототипа'); go('task-detail');
}
// уведомление о смене статуса → в инбокс (если есть), иначе тост уже показан
/* ============================================================
   NOTIFICATIONS — единый инбокс уведомлений (демо).
   События из задач, договоров, оценок ментора пишутся сюда.
   Бейдж непрочитанных — на пункте меню «Уведомления».
   ============================================================ */
const NOTIFICATIONS=[ // сид-события (демо)
  {icon:'trophy', title:'Достижение', text:'Открыт бейдж «AI-мастер» за 5 решённых кейсов', time:'2 дн назад', unread:false},
  {icon:'doc',    title:'Отклик получен', text:'Ozon получил ваше резюме на Data Analyst Intern', time:'вчера', unread:false},
  {icon:'puzzle', title:'AI-разбор готов', text:'Симуляция «A/B-тест онбординга» оценена на 88%', time:'5 ч назад', unread:true},
  {icon:'check',  title:'Практика', text:'Ментор подтвердил часы за неделю 4 — засчитано вузом', time:'3 ч назад', unread:true},
];
function notify(icon, title, text){
  try{ NOTIFICATIONS.unshift({icon, title, text, time:'только что', unread:true}); }catch(e){}
}
function unreadCount(){ try{ return NOTIFICATIONS.filter(n=>n.unread).length; }catch(e){ return 0; } }
function notifyTask(t,msg){ notify('list','Задачи',msg); }

/* ============================================================
   FEATURE FLAGS — hide, don't delete. Flip one line to restore.
   Rationale: the student cabinet is over-built; the company side pays.
   ============================================================ */
const FEATURES = {
  resumeBuilder: true,    // AI-резюме: конструктор, шаблоны, фото
  skillMatchChart: false, // bar-chart "соответствие по навыкам" на job-detail
  /* Kept ON: the overview and every internship card link to it. Hiding the page
     without hiding those links left six dead references. Off → also clean them. */
  recruiterKanban: true,  // Kanban-воронка в кабинете компании
  studentHero: false,     // hero-баннер + SVG-кольцо прогресса в обзоре студента
  /* ===== CORE — остриё Z2H (главный дифференциатор) ===== */
  internship_diary: true,   // CORE: дневник практики + подтверждение ментором + статус для вуза
  tripartite_contract: true,// CORE: трёхсторонний договор практики (E-imzo, MOCK)
  uni_kpi_dashboard: true,  // CORE: аналитика трудоустройства деканата под гос-KPI
  htd: true,                // CORE: Hire-Train-Deploy (обучение под заказ компании)
  /* ===== BRIDGE — монетизация CORE-данных ===== */
  talent_showcase: true,    // BRIDGE: витрина верифицированных студентов + premium-пейволл
  skills_passport: true,    // связка CORE↔BRIDGE: паспорт навыков с источниками верификации
  /* ===== TASKS — микрозадачи компаний, встроенные в HTD ===== */
  tasks: true,              // биржа реальных микрозадач: тест кандидата / учебный микропроект
  tasks_payments: true,     // ДЕМО-заглушка платёжного эскроу. Реальных денег платформа НЕ проводит — витрина контура оплаты. Для продакшена нужен внешний провайдер (Payme/Click) и юр-лицензия.
  match_score: true,        // CORE: соответствие студента требованиям HTD-заказа + gap («что дообучить»)
  career_edu_sync: true,    // CORE: выгрузка обязательных данных в госплатформу career.edu.uz (MOCK). Дополняем, а не заменяем.
  uni_subscription: true,   // BRIDGE: подписка вуза на расширенную аналитику/договоры
  ai_interview_for_order: false, // OFF/PARITY: интервью привязанное к HTD-заказу. Выключено — у career.edu.uz свой AI-инструмент, не конкурируем; включать только под конкретный заказ.
};

/* ============================================================
   PUBLIC COUNTERS — substitute real numbers here, not array lengths.
   A card with a value under 10 is not rendered at all: an honest
   small number beats a fabricated large one, but a tiny one is noise.
   ============================================================ */
const STATS = { students: 1240, universities: 12, companies: 18 };

/* ============================================================
   COMPANIES — content that can be filled in BEFORE any contract.
   `stats.offerRate === null` → the whole stats block is skipped.
   Never render "нет данных": absence should be invisible, not loud.
   ============================================================ */
const COMPANIES=[
  {id:0,name:"Uzum",initials:"UZ",color:"#7000FF",industry:"Маркетплейс · Финтех",size:"2 000+ сотрудников",city:"Ташкент",
   about:"Крупнейшая e-commerce и финтех-экосистема Узбекистана: маркетплейс, банк, рассрочка. Продуктовые команды растят собственных специалистов из стажёров.",
   programs:[
     {title:"Стажировка в продукте",duration:"6 месяцев",paid:true,courses:[3,4],offerRate:64},
     {title:"Frontend Academy",duration:"3 месяца",paid:true,courses:[2,3,4],offerRate:48}],
   stats:{offerRate:64,internsHired:38,avgTimeToOffer:"4 месяца"},
   hiringSteps:["Анкета","Тестовое задание","Интервью","Выбор команды"],openPositions:2},

  {id:1,name:"Ozon",initials:"OZ",color:"#005BFF",industry:"Маркетплейс",size:"800+ сотрудников",city:"Ташкент",
   about:"Узбекистанское подразделение международного маркетплейса. Аналитика, логистика, разработка. Наставник за каждым стажёром с первого дня.",
   programs:[
     {title:"Data Analytics Internship",duration:"6 месяцев",paid:true,courses:[3,4],offerRate:71}],
   stats:{offerRate:71,internsHired:19,avgTimeToOffer:"3 месяца"},
   hiringSteps:["Анкета","SQL-тест","Интервью","Оффер"],openPositions:1},

  {id:2,name:"Click",initials:"CL",color:"#00789B",industry:"Финтех · Платежи",size:"400+ сотрудников",city:"Ташкент",
   about:"Первая платёжная система страны. Маркетинг, продукт, инфраструктура. Открытая культура: стажёр может предложить фичу и увидеть её в релизе.",
   programs:[
     {title:"Growth Marketing Intern",duration:"4 месяца",paid:true,courses:[2,3,4],offerRate:52}],
   stats:{offerRate:52,internsHired:11,avgTimeToOffer:"5 месяцев"},
   hiringSteps:["Анкета","Кейс","Интервью"],openPositions:1},

  {id:3,name:"EPAM",initials:"EP",color:"#2C8639",industry:"IT-консалтинг",size:"600+ сотрудников",city:"Ташкент",
   about:"Международная инженерная компания. Проекты для клиентов из США и Европы. Собственная школа обучения перед выходом на проект.",
   programs:[
     {title:"UX/UI Design Practice",duration:"3 месяца",paid:true,courses:[2,3,4],offerRate:44},
     {title:"QA Automation Lab",duration:"4 месяца",paid:true,courses:[3,4],offerRate:57}],
   stats:{offerRate:51,internsHired:44,avgTimeToOffer:"4 месяца"},
   hiringSteps:["Анкета","Английский","Техническое интервью","Оффер"],openPositions:2},

  {id:4,name:"Beeline",initials:"BE",color:"#B48A00",industry:"Телеком",size:"3 000+ сотрудников",city:"Ташкент",
   about:"Один из крупнейших операторов связи. HR, маркетинг, дата-аналитика. Стажировка засчитывается как производственная практика в большинстве вузов.",
   programs:[
     {title:"HR Internship",duration:"3 месяца",paid:true,courses:[2,3,4],offerRate:38}],
   stats:{offerRate:38,internsHired:16,avgTimeToOffer:"6 месяцев"},
   hiringSteps:["Анкета","Интервью с HR","Интервью с руководителем"],openPositions:1},

  {id:5,name:"Payme",initials:"PA",color:"#12A5A0",industry:"Финтех · Платежи",size:"350+ сотрудников",city:"Ташкент",
   about:"Платёжный сервис и B2B-эквайринг. Продажи, поддержка, разработка. Стажёры выходят на реальных клиентов с третьей недели.",
   programs:[
     {title:"Sales Development Program",duration:"6 месяцев",paid:true,courses:[3,4,5],offerRate:60}],
   stats:{offerRate:60,internsHired:22,avgTimeToOffer:"3 месяца"},
   hiringSteps:["Анкета","Ролевая игра","Интервью","Оффер"],openPositions:1},

  {id:6,name:"TBC Bank",initials:"TB",color:"#0079A6",industry:"Банк",size:"1 200+ сотрудников",city:"Ташкент",
   about:"Розничный банк грузинской группы TBC. Финансы, риски, продукт. Программа выстроена вокруг ротации между отделами.",
   programs:[
     {title:"Finance Graduate Program",duration:"12 месяцев",paid:true,courses:[4,5],offerRate:73}],
   stats:{offerRate:73,internsHired:14,avgTimeToOffer:"12 месяцев"},
   hiringSteps:["Анкета","Числовой тест","Ассессмент","Интервью"],openPositions:1},

  {id:7,name:"Anor Bank",initials:"AN",color:"#E8542E",industry:"Цифровой банк",size:"250+ сотрудников",city:"Ташкент",
   about:"Мобильный банк без отделений. Контент, продукт, мобильная разработка. Небольшая команда — стажёр общается напрямую с руководителем направления.",
   programs:[
     {title:"Content Marketing Intern",duration:"3 месяца",paid:true,courses:[1,2,3,4],offerRate:null}],
   stats:{offerRate:null,internsHired:6,avgTimeToOffer:null},
   hiringSteps:["Анкета","Тестовый текст","Интервью"],openPositions:1},

  {id:8,name:"Artel",initials:"AR",color:"#C0392B",industry:"Производство · Электроника",size:"12 000+ сотрудников",city:"Ташкент",
   about:"Крупнейший производитель бытовой техники в Центральной Азии. Инженерия, логистика, цепочки поставок. Стажировки на производственных площадках.",
   programs:[
     {title:"Supply Chain Trainee",duration:"6 месяцев",paid:true,courses:[3,4],offerRate:null}],
   /* no published figures at all — the whole stats block must disappear,
      not degrade into "нет данных" placeholders */
   stats:{offerRate:null,internsHired:null,avgTimeToOffer:null},
   hiringSteps:["Анкета","Интервью","Стажировка на площадке"],openPositions:0},

  {id:9,name:"Korzinka",initials:"KO",color:"#3B7D22",industry:"Ритейл",size:"9 000+ сотрудников",city:"Ташкент",
   about:"Сеть супермаркетов и e-grocery. Категорийный менеджмент, аналитика, операции. Программа управленческого резерва для выпускников.",
   programs:[
     {title:"Retail Management Trainee",duration:"9 месяцев",paid:true,courses:[4,5],offerRate:66}],
   stats:{offerRate:66,internsHired:27,avgTimeToOffer:"9 месяцев"},
   hiringSteps:["Анкета","Групповой кейс","Интервью","Оффер"],openPositions:0},
];
const companyByName=n=>COMPANIES.find(c=>c.name===n)||null;
const courseLabel=c=>c===5?"выпускники":`${c} курс`;
function coursesText(arr){
  if(!arr||!arr.length) return "";
  const nums=arr.filter(x=>x<5).sort((a,b)=>a-b);
  const grad=arr.includes(5);
  const parts=[];
  if(nums.length===1) parts.push(`${nums[0]} курс`);
  else if(nums.length>1) parts.push(`${nums[0]}–${nums[nums.length-1]} курс`);
  if(grad) parts.push("выпускники");
  return parts.join(" · ");
}

/* ============================================================
   EVENTS — the cheap door for an employer. An hour of their time,
   not a hiring contract. One hue per type; not a rainbow.
   ============================================================ */
const EV_TYPE={
  "Встреча":        {soft:"var(--blue-soft)",  ink:"var(--blue-ink)"},
  "Мастер-класс":   {soft:"var(--purple-soft)",ink:"var(--purple-ink)"},
  "Кейс-чемпионат": {soft:"var(--amber-soft)", ink:"var(--amber-ink)"},
  "День карьеры":   {soft:"var(--teal-soft)",  ink:"var(--teal-ink)"},
};
const EVENTS=[
  {id:0,title:"Как устроена продуктовая аналитика в маркетплейсе",company:0,type:"Встреча",format:"Онлайн",
   date:"2026-07-18",deadline:"2026-07-16",university:null,seats:120,seatsTaken:87,
   description:"Продуктовые аналитики Uzum разбирают, какие метрики они смотрят каждый день и что спрашивают на интервью."},
  {id:1,title:"Кейс-чемпионат: логистика последней мили",company:1,type:"Кейс-чемпионат",format:"Гибрид",
   date:"2026-07-25",deadline:"2026-07-20",university:"ТУИТ",seats:60,seatsTaken:41,
   description:"Команды по 4 человека решают реальную задачу Ozon: как сократить время доставки в Ташкенте на 20%."},
  {id:2,title:"Мастер-класс: SQL за один вечер",company:1,type:"Мастер-класс",format:"Онлайн",
   date:"2026-07-22",deadline:"2026-07-21",university:null,seats:200,seatsTaken:156,
   description:"Практикум для тех, кто ни разу не писал запрос. К концу вечера соберёте первый дашборд."},
  {id:3,title:"День карьеры в НУУз",company:3,type:"День карьеры",format:"Офлайн",
   date:"2026-08-05",deadline:"2026-08-03",university:"НУУз",seats:300,seatsTaken:112,
   description:"Восемь компаний, стенды, короткие интервью на месте. Приходите с распечатанным резюме."},
  {id:4,title:"Разбор тестового задания в Click",company:2,type:"Мастер-класс",format:"Онлайн",
   date:"2026-07-29",deadline:"2026-07-27",university:null,seats:80,seatsTaken:34,
   description:"Маркетинговая команда Click показывает три работы кандидатов: принятую, доработанную и отклонённую."},
  {id:5,title:"Встреча с инженерами EPAM",company:3,type:"Встреча",format:"Офлайн",
   date:"2026-08-12",deadline:"2026-08-09",university:"Вестминстер",seats:50,seatsTaken:29,
   description:"Как выглядит первый месяц на проекте для международного клиента и зачем нужен английский."},
];

/* ---- page map ---- */
const PAGES = {
/* ---------- STUDENT ---------- */
"student:home":()=>(FEATURES.studentHero?studentHeroBanner():"")+`
  ${FEATURES.studentHero?`
  <div class="ov-hero">
    ${progressRing(40,"пути")}
    <div class="ov-hero-info">
      <h3>Шаг 4 · Первая симуляция</h3>
      <div class="ov-step">До первого оффера ~6 недель. Продолжайте в том же темпе!</div>
      <div class="progress"><i style="width:40%"></i></div>
      <div class="ps">4 из 10 шагов траектории пройдено</div>
    </div>
  </div>`:''}
  <div class="g g4" style="margin-bottom:16px">
    ${statCard('target','74%','Готовность к офферу','var(--blue)','var(--blue-soft)','+8% за нед.',{spark:[30,42,38,55,60,66,74]})}
    ${statCard('puzzle','3','Активные симуляции','var(--purple)','var(--purple-soft)',null,{spark:[20,35,30,45,40,55,60]})}
    ${statCard('briefcase','2','Отклика в работе','var(--teal)','var(--teal-soft)',null,{spark:[15,20,35,30,45,50,48]})}
    ${statCard('flame','7','Дней подряд','var(--amber)','var(--amber-soft)',null,{spark:[40,50,55,60,70,80,95]})}
  </div>
  <div class="g g2">
    <div class="panel"><h3>${ico('pin')} Задачи на сегодня</h3><div class="ps">3 задачи</div>
      <div class="list">
        ${li(ico('puzzle'),"Досдать «A/B-тест платного онбординга»","дедлайн через 6 ч","")}
        ${li(ico('doc'),"Отправить резюме в Ozon","Data Analyst Intern","")}
        ${li(ico('chat'),"Ответить Марии (Сбер)","приглашение на интервью","")}
      </div>
    </div>
    <div class="panel"><h3>${ico('target')} Активные симуляции</h3><div class="ps">В работе</div>
      <div class="list">
        ${simLi("A/B-тест платного онбординга",78,"6 ч")}
        ${simLi("Анализ retention e-commerce",45,"3 дн.")}
        ${simLi("Landing для SaaS-стартапа",20,"5 дн.")}
      </div>
    </div>
  </div>
  <div class="g g2" style="margin-top:16px">
    <div class="panel"><h3>${ico('calendar')} Ближайшие события</h3><div class="ps"></div>
      <div class="list">
        ${li(ico('dot','ok'),"Интервью в Ozon","12 июл · 14:00 · Zoom","")}
        ${li(ico('dot','danger'),"Дедлайн A/B симуляции","13 июл · 23:59","")}
        ${li(ico('dot','info'),"Вебинар «Как пройти скрининг»","15 июл · 18:00","")}
      </div>
    </div>
    <div class="panel"><h3>${ico('trophy')} Достижения</h3><div class="ps">3 из 4 открыто</div>
      <div class="g g2" style="gap:10px">
        ${ach(ico('flame'),"7 дней подряд",true)}${ach(ico('brain'),"AI-мастер",true)}
        ${ach(ico('chart'),"Аналитик",true)}${ach(ico('target'),"Первый оффер",false)}
      </div>
    </div>
  </div>`,

"student:path":()=>{
  const {st,done,total,xp,xpTotal,curIdx}=pathProgress();
  const pct=Math.round(done/total*100);
  const xpPct=Math.round(xp/xpTotal*100);
  const cur=PATH_STEPS[curIdx];
  const rr=42,cc=2*Math.PI*rr,off=cc-(pct/100)*cc;
  /* rough estimate: each remaining step ≈ 1 week of unhurried work */
  const weeksLeft=Math.max(1,(total-done));
  const MILESTONES={3:'Базовый уровень пройден — открылись симуляции',6:'Портфолио собрано — вы заметны работодателям'};

  return ph("Персональная траектория","Путь от нуля до первой стажировки — шаги открываются по мере прогресса")+`

  <div class="tj-hero">
    <div class="tj-top">
      <div class="tj-ring">
        <svg width="96" height="96" viewBox="0 0 96 96">
          <circle cx="48" cy="48" r="${rr}" fill="none" stroke="rgba(255,255,255,.22)" stroke-width="8"/>
          <circle cx="48" cy="48" r="${rr}" fill="none" stroke="#fff" stroke-width="8" stroke-linecap="round"
                  stroke-dasharray="${cc.toFixed(1)}" stroke-dashoffset="${off.toFixed(1)}"/>
        </svg>
        <div class="r-v"><div class="r-n">${pct}%</div><div class="r-l">пути</div></div>
      </div>
      <div class="tj-info">
        <h2>${done===total?'Путь пройден':`Сейчас: ${cur.t}`}</h2>
        <p>${done===total?'Все шаги закрыты — вы готовы к рынку.':cur.why}</p>
        <div class="tj-bars">
          <div class="tj-bar"><div class="b-l">Шагов</div><div class="b-v">${done} / ${total}</div></div>
          <div class="tj-bar"><div class="b-l">Опыт</div><div class="b-v">${xp} XP</div></div>
          <div class="tj-bar"><div class="b-l">Симуляций</div><div class="b-v">${st._sims}</div></div>
          <div class="tj-bar"><div class="b-l">Осталось</div><div class="b-v">~${weeksLeft} нед</div></div>
        </div>
        <div class="xp-track" title="${xp} из ${xpTotal} XP"><i style="width:${Math.max(2,xpPct)}%"></i></div>
      </div>
      ${done<total?`<div class="tj-cta"><button class="btn" onclick="go('${cur.go}')">${ico('spark')} ${cur.t} →</button></div>`:''}
    </div>
  </div>

  <div class="road">
    ${PATH_STEPS.map((s,i)=>{
      const isDone=st[s.k], isCur=(i===curIdx), locked=pathLocked(i);
      const cls=isDone?'done':isCur?'cur':locked?'locked':'';
      const badge=isDone?'<span class="tj-badge done">Завершено</span>'
                 :isCur?'<span class="tj-badge cur">Текущий шаг</span>'
                 :'<span class="tj-badge lock">Откроется позже</span>';
      const sub=pathSubProgress(s.k,st);
      const flag=MILESTONES[i] && isDone ? `<div class="tj-flag">${ico('trophy')}${MILESTONES[i]}</div>` : '';
      return `<div class="tj-step ${cls}" onclick="${locked?`pathLockedHint(${i})`:`go('${s.go}')`}">
        <div class="tj-node">${isDone?ico('check'):(locked?ico('ban'):ico(s.ic))}</div>
        <div class="tj-card">
          <div class="tj-h"><span class="tj-t">${i+1}. ${s.t}</span>${badge}</div>
          <div class="tj-d">${s.d}</div>
          <div class="tj-meta">
            <span class="xp">${ico('spark')}+${s.xp} XP</span>
            ${s.time!=='—'?`<span>${ico('clock')}${s.time}</span>`:''}
          </div>
          ${(isCur&&!isDone)?`<div class="tj-why">${ico('spark')}<span>${s.why}</span></div>`:''}
          ${(!locked&&!isDone)?`<div class="tj-act">
            ${sub?`<div class="tj-progress"><div class="pt"><i style="width:${sub.pct}%"></i></div><div class="pl">${sub.label}</div></div>`:''}
            <button class="btn ${isCur?'btn-primary':'btn-ghost'}" onclick="event.stopPropagation();go('${s.go}')">${isCur?'Продолжить':'Открыть'} →</button>
          </div>`:''}
        </div>
      </div>${flag}`;
    }).join('')}
  </div>`;
},

"student:diagnostics":()=>diagRender(),

"student:simulations":()=>{
  profileInit();
  const done=MOCK.profile.doneSims||[];
  const f=state._simFilter||'Все';
  const cats=['Все','Рекомендовано','Сданные',...[...new Set(SIMS.map(s=>s.cat))]];
  let list=SIMS.slice();
  if(f==='Рекомендовано') list=list.filter(s=>matchFor(s)>=65);
  else if(f==='Сданные')  list=list.filter(s=>done.includes(s.id));
  else if(f!=='Все')      list=list.filter(s=>s.cat===f);
  list.sort((a,b)=>matchFor(b)-matchFor(a));

  const xpEarned=SIMS.filter(s=>done.includes(s.id)).reduce((a,s)=>a+s.xp,0);
  const xpTotal=SIMS.reduce((a,s)=>a+s.xp,0);

  const count=c=>c==='Все'?SIMS.length
    :c==='Рекомендовано'?SIMS.filter(s=>matchFor(s)>=65).length
    :c==='Сданные'?done.length
    :SIMS.filter(s=>s.cat===c).length;

  return `<div class="sim-hero">
    <div class="sh-b">
      <h2>${ico('puzzle')} Симуляции</h2>
      <p>Реальные бизнес-кейсы от компаний. Решённые попадают в портфолио, которое видят работодатели.</p>
      <div class="sh-stats">
        <div class="sh-s"><div class="v">${done.length} / ${SIMS.length}</div><div class="l">Сдано</div></div>
        <div class="sh-s"><div class="v">${xpEarned} XP</div><div class="l">Заработано из ${xpTotal}</div></div>
        <div class="sh-s"><div class="v">${SIMS.filter(s=>matchFor(s)>=65).length}</div><div class="l">Подходят вам</div></div>
      </div>
    </div>
  </div>

  <div class="sim-filters">
    ${cats.map(c=>`<div class="sf ${f===c?'on':''}" onclick="setSimFilter(${JSON.stringify(c).replace(/"/g,'&quot;')})">${c} · ${count(c)}</div>`).join('')}
  </div>

  ${list.length===0?`<div class="empty" style="padding:50px 20px"><div class="ei">${ico('puzzle')}</div><h3>Здесь пока пусто</h3><p>Смените фильтр или загляните позже</p></div>`
  :`<div class="sims-grid">
    ${list.map(s=>{const m=matchFor(s),isDone=done.includes(s.id);return `
      <div class="simcard2 ${isDone?'done':''}" onclick="openSim(${s.id})">
        ${isDone?`<span class="s2-done">${ico('check')}Сдано</span>`:''}
        <div class="s2-head">
          <div class="s2-logo" style="background:${s.color}">${s.logo}</div>
          <div class="s2-tt"><div class="s2-t">${s.t}</div><div class="s2-co">${s.co} · ${s.role}</div></div>
        </div>
        <div class="s2-meta">
          <span class="s2-pill">${ico('user')}${s.lvl}</span>
          <span class="s2-pill">${ico('clock')}${s.dur}</span>
          <span class="s2-pill">${ico('calendar')}до ${s.dl}</span>
        </div>
        <div class="s2-brief">${s.brief}</div>
        <div class="s2-tags">${s.tags.map(t=>`<span class="s2-tag">${t}</span>`).join('')}</div>
        <div class="s2-foot">
          <div class="s2-match"><div class="s2-bar"><i style="width:${m}%"></i></div><span class="s2-mv">${m}%</span></div>
          <span class="s2-xp">+${s.xp} XP</span>
        </div>
      </div>`;}).join('')}
  </div>`}`;
},

"student:jobs":()=>{
  const f=state._jobFilter||'Все';
  const cf=state._courseFilter||'Все';
  const q=(state._jobQuery||'').toLowerCase().trim();
  const view=state._jobView||'cards';
  const filters=['Все','IT','Маркетинг','Продажи','Дизайн','HR','Финансы'];
  /* course groups combine WITH the field chips, they don't replace them */
  const COURSE_GROUPS={'Все':null,'1–2 курс':[1,2],'3–4 курс':[3,4],'Выпускники':[5]};
  const inCourse=j=>{
    const g=COURSE_GROUPS[cf];
    if(!g) return true;
    return (j.courses||[]).some(c=>g.includes(c));
  };
  let list=JOBS.filter(j=>(f==='Все'||j.field===f) && inCourse(j));
  // сегмент: местные / зарубежные (как career.edu.uz)
  const seg=state._jobSeg||'local';
  list=list.filter(j=> seg==='abroad' ? j.abroad : !j.abroad);
  // доп-фильтры в стиле career.edu.uz: формат места, тип занятости, уровень
  const ff=state._jobFmt||'', ft=state._jobType||'', fl=state._jobLvl||'';
  if(ff) list=list.filter(j=>j.fmt===ff);
  if(ft) list=list.filter(j=>j.type===ft);
  if(fl) list=list.filter(j=>j.lvl===fl);
  if(q) list=list.filter(j=>(j.t+' '+j.co+' '+j.team+' '+j.tags.join(' ')+' '+j.field).toLowerCase().includes(q));
  /* nearest deadline first; expired sink to the bottom regardless of match */
  list=list.sort((a,b)=>{
    const pa=isPast(a.deadline), pb=isPast(b.deadline);
    if(pa!==pb) return pa?1:-1;
    return String(a.deadline).localeCompare(String(b.deadline));
  });
  const countIn=(grp)=>JOBS.filter(j=>{const g=COURSE_GROUPS[grp];return !g||(j.courses||[]).some(c=>g.includes(c));}).length;

  const cardHtml=j=>{const m=matchFor(j);const closed=isPast(j.deadline);return `
      <div class="jobcard${closed?' closed':''}" onclick="openJob(${j.id})">
        ${j.new&&!closed?`<span class="jc-new">Новое</span>`:''}
        <div class="jc-head">
          <div class="jc-logo" style="background:${j.color}">${j.logo}</div>
          <div class="jc-tt"><div class="jc-title">${j.t}</div><div class="jc-co">${j.co} · ${j.team}</div></div>
        </div>
        <div class="jc-meta">
          <span class="jc-pill">${ico('pin')}${j.loc}</span>
          <span class="jc-pill">${ico('briefcase')}${j.fmt}</span>
          <span class="jc-pill">${ico('student')}${coursesText(j.courses)}</span>
          ${deadlinePill(j)}
        </div>
        <div class="jc-about">${j.about}</div>
        <div class="jc-tags">${j.tags.map(t=>`<span class="jc-tag">${t}</span>`).join('')}</div>
        <div class="jc-foot">
          <div class="jc-match"><div class="jc-mbar"><i style="width:${m}%"></i></div><span class="jc-mval">${m}%</span></div>
          <span class="jc-sal">${j.sal}</span>
        </div>
      </div>`;};
  const rowHtml=j=>{const m=matchFor(j);const closed=isPast(j.deadline);return `
      <div class="jobrow${closed?' closed':''}" onclick="openJob(${j.id})">
        <div class="jr-logo" style="background:${j.color}">${j.logo}</div>
        <div class="jr-main">
          <div class="jr-title">${j.t}${j.new&&!closed?`<span class="jc-new">Новое</span>`:''}</div>
          <div class="jr-sub"><span>${ico('company')}${j.co}</span><span>${ico('pin')}${j.loc}</span><span>${ico('student')}${coursesText(j.courses)}</span></div>
        </div>
        <div class="jr-tags">${deadlinePill(j)}</div>
        <div class="jr-right">
          <div class="jr-match"><div class="jr-mbar"><i style="width:${m}%"></i></div><span class="jr-mval">${m}%</span></div>
          <div class="jr-sal">${j.sal}</div>
        </div>
      </div>`;};

  return `<div class="onb-banner" style="margin-bottom:18px"><h2>${ico('briefcase')} ${JOBS.length} стажировок и вакансий</h2><p>Сначала те, у кого ближе дедлайн. Отклик — в один клик.</p></div>
  <div class="job-seg">
    <button class="js-tab ${seg==='local'?'on':''}" onclick="setJobSeg('local')">${ico('pin')} Местные · ${JOBS.filter(j=>!j.abroad).length}</button>
    <button class="js-tab ${seg==='abroad'?'on':''}" onclick="setJobSeg('abroad')">${ico('globe')} Зарубежные · ${JOBS.filter(j=>j.abroad).length}</button>
  </div>
  <div class="jobs-toolbar">
    <div class="jobs-search">${ico('search')}<input placeholder="Поиск по названию, компании, навыкам…" value="${state._jobQuery||''}" oninput="setJobQuery(this.value)" autofocus></div>
    <div class="view-toggle">
      <button class="${view==='cards'?'on':''}" onclick="setJobView('cards')" title="Карточки">${ico('puzzle')}</button>
      <button class="${view==='list'?'on':''}" onclick="setJobView('list')" title="Список">${ico('list')}</button>
    </div>
  </div>
  <div class="job-filters">
    ${filters.map(x=>`<div class="jf ${f===x?'on':''}" onclick="setJobFilter('${x}')">${x}${x!=='Все'?` · ${JOBS.filter(j=>j.field===x).length}`:` · ${JOBS.length}`}</div>`).join('')}
  </div>
  <div class="job-filters" style="margin-top:-4px">
    ${Object.keys(COURSE_GROUPS).map(x=>`<div class="jf ${cf===x?'on':''}" onclick="setCourseFilter('${x}')">${x} · ${countIn(x)}</div>`).join('')}
    <span style="margin-left:auto;align-self:center;font-size:12.5px;color:var(--muted)">Найдено: ${list.length}</span>
  </div>
  <div class="job-selects">
    <select class="jsel" onchange="setJobExtra('_jobFmt',this.value)">
      <option value="">Любое место</option>
      ${[...new Set(JOBS.map(j=>j.fmt))].map(v=>`<option value="${v}"${ff===v?' selected':''}>${v}</option>`).join('')}
    </select>
    <select class="jsel" onchange="setJobExtra('_jobType',this.value)">
      <option value="">Любой тип</option>
      ${[...new Set(JOBS.map(j=>j.type))].map(v=>`<option value="${v}"${ft===v?' selected':''}>${v}</option>`).join('')}
    </select>
    <select class="jsel" onchange="setJobExtra('_jobLvl',this.value)">
      <option value="">Любой уровень</option>
      ${[...new Set(JOBS.map(j=>j.lvl))].map(v=>`<option value="${v}"${fl===v?' selected':''}>${v}</option>`).join('')}
    </select>
    ${(ff||ft||fl)?`<button class="jsel-reset" onclick="clearJobExtra()">Сбросить</button>`:''}
  </div>
  ${list.length===0?`<div class="empty" style="padding:50px 20px"><div class="ei">${ico('search')}</div><h3>Ничего не найдено</h3><p>Измените запрос или фильтр</p></div>`
    : view==='cards' ? `<div class="jobs-grid">${list.map(cardHtml).join('')}</div>`
    : `<div class="jobs-list">${list.map(rowHtml).join('')}</div>`}`;
},

"student:resume":()=>FEATURES.resumeBuilder?resumeBuilder():featureOff("AI-резюме","Конструктор резюме временно скрыт: сейчас приоритет — то, что видит работодатель."),

"student:messages":()=>{
  profileInit();
  /* every company you applied to gets a thread — the list is derived, not hardcoded */
  const applied=(MOCK.profile.appliedJobs||[]).map(id=>JOBS.find(j=>j.id===id)).filter(Boolean);
  const seen=new Set();
  const fromApps=applied.filter(j=>{ if(seen.has(j.co))return false; seen.add(j.co); return true; })
    .map(j=>[`${j.co} Careers`, 'Компания · '+j.t, appStage(j.id)==='interview'?'Приглашаем на интервью':'Ваш отклик получен']);
  const base=[["Куратор ВУЗа","Наставник","Отличный прогресс по траектории!"]];
  const threads=[...fromApps,...base];
  /* if the student clicked "Написать в X", surface that thread first */
  const w=state._chatWith;
  if(w){ threads.sort((a,b)=>(b[0].startsWith(w)?1:0)-(a[0].startsWith(w)?1:0)); }
  return chatUI(threads.length?threads:[["Пока никого","—","Откликнитесь на вакансию, чтобы начать переписку"]]);
},

/* ---------- UNIVERSITY ---------- */
"university:home":()=>`<div class="onb-banner" style="margin-bottom:18px"><h2>${ico('university')} Обзор ВУЗа</h2><p>342 студента · 8 когорт · средняя готовность 61% · 47 офферов</p></div>`+`
  <div class="g g4" style="margin-bottom:16px">
    ${stat("342","Активных студента","up","+24")}
    ${stat("8","Когорт")}
    ${stat("61%","Средняя готовность","up","+5%")}
    ${stat("47","Офферов получено","up","+12")}
  </div>
  <div class="g g2">
    <div class="panel"><h3>Прогресс когорт</h3><div class="ps">Топ по готовности</div>
      ${cohortRow("Аналитика данных · 2025",78)}
      ${cohortRow("Продуктовый менеджмент",64)}
      ${cohortRow("Дизайн-мышление",52)}
      ${cohortRow("Digital-маркетинг",41)}
    </div>
    <div class="panel"><h3>Требуют внимания</h3><div class="ps">Студенты с застоем</div>
      <div class="list">
        ${li(ico('alert'),"12 студентов","не заходили 7+ дней","")}
        ${li(ico('chart'),"Когорта «Маркетинг»","прогресс ниже плана","")}
        ${li(ico('target'),"5 студентов","готовы к офферу — свяжите с HR","")}
      </div>
    </div>
  </div>`,

"university:cohorts":()=>ph("Когорты","Управление группами студентов",`<button class="btn btn-primary btn-sm" onclick="toast('Создание когорты — в демо недоступно')">＋ Новая когорта</button>`)+`
  <div class="cards">
    ${COHORTS.map((c,i)=>`
      <div class="simcard" onclick="openCohort(${i})">
        <div class="sc-t">${c.name}</div>
        <div class="sc-meta">${c.count} студентов</div>
        <div style="margin-top:6px"><div class="progress"><i style="width:${c.ready}%"></i></div></div>
        <div class="sc-foot"><span class="badge b-teal">${c.ready}% готовность</span><span class="sc-meta">→ открыть</span></div>
      </div>`).join('')}
  </div>`,

"university:students":()=>ph("Студенты","Реестр студентов всех когорт")+`
  <div class="panel" style="padding:0;overflow:hidden">
    <table class="tbl">
      <thead><tr><th>Студент</th><th>Когорта</th><th>Шаг</th><th>Готовность</th><th>Статус</th></tr></thead>
      <tbody>
      ${STUDENTS.map((s,i)=>`
        <tr onclick="openStudent(${i})" style="cursor:pointer">
          <td class="nm">${s.name}</td><td>${s.cohort}</td><td>${s.step}</td>
          <td><div style="display:flex;align-items:center;gap:8px"><div class="progress" style="width:60px"><i style="width:${s.ready}"></i></div>${s.ready}</div></td>
          <td>${statusBadge(s.status)}</td>
        </tr>`).join('')}
      </tbody>
    </table>
  </div>`,

"university:gaps":()=>ph("Gap-матрица","Компетенции × уровни. Тёмные ячейки — сильные пробелы.")+`
  <div class="panel">
    ${gapMatrix()}
    <div style="display:flex;gap:14px;margin-top:16px;font-size:12px;color:var(--muted)">
      <span style="display:flex;align-items:center;gap:6px"><span style="width:14px;height:14px;border-radius:4px;background:#0F9E75"></span>Сильно</span>
      <span style="display:flex;align-items:center;gap:6px"><span style="width:14px;height:14px;border-radius:4px;background:#9FE1CB"></span>Средне</span>
      <span style="display:flex;align-items:center;gap:6px"><span style="width:14px;height:14px;border-radius:4px;background:#E24B4A"></span>Пробел</span>
    </div>
  </div>`,

"university:reports":()=>ph("Отчёты","Готовые пресеты + экспорт в CSV / PDF")+`
  <div class="g g2">
    ${['Готовность когорт','Динамика прогресса','Gap-анализ по направлениям','Воронка «студент → оффер»'].map(r=>`
      <div class="panel" style="display:flex;align-items:center;gap:14px">
        <div class="li-ic" style="width:44px;height:44px;font-size:20px">${ico('list')}</div>
        <div style="flex:1"><div style="font-weight:600;font-size:14px">${r}</div><div class="ps" style="margin:0">Пресет отчёта</div></div>
        <button class="btn btn-ghost btn-sm" onclick="toast('Экспорт «'+r+'» — CSV/PDF (демо)')">Экспорт</button>
      </div>`).join('')}
  </div>`,

"university:team":()=>ph("Команда кураторов","Приглашайте кураторов по email",`<button class="btn btn-primary btn-sm" onclick="toast('Приглашение отправлено (демо)')">＋ Пригласить</button>`)+`
  <div class="panel" style="padding:0;overflow:hidden">
    <table class="tbl"><thead><tr><th>Куратор</th><th>Email</th><th>Роль</th><th>Когорты</th></tr></thead><tbody>
    ${[["Иванов И.И.","ivanov@uni.uz","Владелец","все"],["Петрова А.С.","petrova@uni.uz","Куратор","3"],["Садыков Р.","sadykov@uni.uz","Куратор","2"]].map(t=>
      `<tr><td class="nm">${t[0]}</td><td class="mono" style="font-size:12px">${t[1]}</td><td>${statusBadge(t[2]==='Владелец'?'offer':'active',t[2])}</td><td>${t[3]}</td></tr>`).join('')}
    </tbody></table>
  </div>`,

/* ---------- COMPANY ---------- */
"company:home":()=>{
  const nw=CANDS.new.length, sc=CANDS.screen.length, iv=CANDS.interview.length, of=CANDS.offer.length;
  const total=nw+sc+iv+of;
  /* a funnel is read against its widest stage, not against the sum of all stages */
  const mx=Math.max(nw,sc,iv,of,1);
  return `<div class="onb-banner" style="margin-bottom:18px"><h2>${ico('company')} Обзор компании</h2><p>${total} ${plural(total,'кандидат','кандидата','кандидатов')} в воронке · ${INTERNSHIPS.length} ${plural(INTERNSHIPS.length,'стажировка','стажировки','стажировок')} · средний match ${avgMatch()}% · ${of} ${plural(of,'оффер','оффера','офферов')}</p></div>`+`
  <div class="g g4" style="margin-bottom:16px">
    ${stat(INTERNSHIPS.length,"Открытых стажировок")}
    ${stat(total,plural(total,"Кандидат в воронке","Кандидата в воронке","Кандидатов в воронке"),"up")}
    ${stat(avgMatch()+"%","Средний match","up","+4%")}
    ${stat(of,plural(of,"Оффер","Оффера","Офферов"))}
  </div>
  <div class="g g2">
    <div class="panel"><h3>Воронка найма</h3><div class="ps">${FEATURES.recruiterKanban?`<a onclick="go('candidates')" style="cursor:pointer;color:var(--accent)">Открыть Kanban →</a>`:'Сводка по этапам отбора'}</div>
      ${funnelRow("Новые",nw,nw/mx*100)}${funnelRow("Скрининг",sc,sc/mx*100)}${funnelRow("Интервью",iv,iv/mx*100)}${funnelRow("Оффер",of,of/mx*100)}
    </div>
    <div class="panel"><h3>Топ-кандидаты недели</h3><div class="ps">По совпадению</div>
      <div class="list">
        ${li(ico('user'),"Тимур Б.","Data Analyst · 95%","→")}
        ${li(ico('user'),"Нилуфар А.","Product · 88%","→")}
        ${li(ico('user'),"Анна К.","Data Analyst · 92%","→")}
      </div>
    </div>
  </div>`;},

"company:internships":()=>ph("Стажировки","Опубликованные вакансии-стажировки",`<button class="btn btn-primary btn-sm" onclick="go('internship-new')">＋ Новая стажировка</button>`)+`
  <div class="cards">
    ${INTERNSHIPS.map((j,i)=>`
      <div class="simcard" onclick="openInternship(${i})">
        <div class="sc-top"><div class="sc-t">${j.name}</div>${statusBadge(j.status==='Черновик'?'stalled':'active',j.status)}</div>
        <div class="sc-meta">${j.apps} откликов</div>
        <div class="sc-foot">${FEATURES.recruiterKanban?`<span class="badge b-amber">Kanban воронка</span>`:`<span class="badge">${j.status}</span>`}<span class="sc-meta">→ открыть</span></div>
      </div>`).join('')}
  </div>`,

"company:candidates":()=>!FEATURES.recruiterKanban?featureOff("Кандидаты","Воронка найма появится, когда в ней будут реальные кандидаты."):ph("Кандидаты","Воронка найма Kanban · перетаскивайте карточки между этапами")+`
  <div class="kanban">
    ${kcol("Новые",CANDS.new,'new')}
    ${kcol("Скрининг",CANDS.screen,'screen')}
    ${kcol("Интервью",CANDS.interview,'interview')}
    ${kcol("Оффер",CANDS.offer,'offer')}
  </div>`,

"company:messages":()=>chatUI([
  ["Тимур Б.","Data Analyst · 95%","Спасибо за приглашение!"],
  ["Нилуфар А.","Product · 88%","Готова к интервью в четверг"],
  ["Анна К.","Data Analyst · 92%","Отправила тестовое задание"],
]),

/* Mirrors `company-detail` field for field. Previously this asked for four
   strings while the public page promised three figures, programmes and a
   selection stepper — the employer could not fill in what students would see.
   Leaving a figure blank is fine: the public block disappears rather than
   showing a "нет данных" placeholder. */
"company:company":()=>{
  const me=COMPANIES[0];   /* the signed-in company, mocked as Uzum */
  return ph("Профиль компании","Публичная страница, которую видят кандидаты",
    `<button class="btn btn-ghost btn-sm" style="width:auto;margin-right:8px" onclick="openCompany(0)">Посмотреть как кандидат</button>
     <button class="btn btn-primary btn-sm" onclick="toast('Изменения сохранены (демо)')">Сохранить</button>`)+`

  <div class="panel" style="margin-bottom:16px">
    <h3>Основное</h3>
    <div class="split" style="margin-top:12px">
      <div class="field"><label>Название</label><input value="${me.name}"></div>
      <div class="field"><label>Отрасль</label><input value="${me.industry}"></div>
    </div>
    <div class="split">
      <div class="field"><label>Город</label><input value="${me.city}"></div>
      <div class="field"><label>Размер</label><input value="${me.size}"></div>
    </div>
    <div class="field"><label>О компании</label><textarea rows="3" style="width:100%">${me.about}</textarea></div>
  </div>

  <div class="panel" style="margin-bottom:16px">
    <h3>Цифры</h3>
    <div class="ps">Единственный аргумент, который работает. Пустое поле — блок просто не покажется</div>
    <div class="g g3" style="margin-top:12px">
      <div class="field"><label>% стажёров с оффером</label><input type="number" value="${me.stats.offerRate??''}" placeholder="—"></div>
      <div class="field"><label>Стажёров за год</label><input type="number" value="${me.stats.internsHired??''}" placeholder="—"></div>
      <div class="field"><label>Средний путь до оффера</label><input value="${me.stats.avgTimeToOffer??''}" placeholder="—"></div>
    </div>
  </div>

  <div class="panel" style="margin-bottom:16px">
    <h3>Программы для студентов</h3>
    <div class="ps">Что вы предлагаете тем, у кого пока нет опыта</div>
    <div class="co-progs">
      ${me.programs.map(pr=>`
        <div class="co-prog">
          <div class="cp-head">
            <div class="cp-title">${pr.title}</div>
            <button class="btn btn-ghost btn-sm" style="width:auto;padding:0 12px;height:28px" onclick="toast('Редактирование — в демо недоступно')">Изменить</button>
          </div>
          <div class="cp-meta">
            <span class="jc-pill">${ico('clock')}${pr.duration}</span>
            <span class="jc-pill">${ico('student')}${coursesText(pr.courses)}</span>
            ${pr.offerRate!=null?`<span class="jc-pill" style="background:var(--green-soft);color:var(--green-ink)">${pr.offerRate}% оффер</span>`:''}
          </div>
        </div>`).join('')}
    </div>
    <button class="btn btn-ghost btn-sm" style="width:auto;margin-top:12px" onclick="toast('Добавление программы — в демо недоступно')">＋ Добавить программу</button>
  </div>

  <div class="panel">
    <h3>Шаги отбора</h3>
    <div class="ps">Прозрачный процесс — то, чего студенту не хватает больше всего</div>
    <div class="field" style="margin-top:12px"><label>Через запятую</label><input value="${me.hiringSteps.join(', ')}"></div>
    ${hiringStepper(me.hiringSteps)}
  </div>`;
},

"company:team":()=>ph("HR-команда","Роли: Owner / Recruiter / Viewer",`<button class="btn btn-primary btn-sm" onclick="toast('Приглашение отправлено (демо)')">＋ Пригласить</button>`)+`
  <div class="panel" style="padding:0;overflow:hidden">
    <table class="tbl"><thead><tr><th>Сотрудник</th><th>Email</th><th>Роль</th></tr></thead><tbody>
    ${[["Азиз Ю.","aziz@uzum.uz","Owner"],["Камола Т.","kamola@uzum.uz","Recruiter"],["Бекзод С.","bekzod@uzum.uz","Viewer"]].map(t=>
      `<tr><td class="nm">${t[0]}</td><td class="mono" style="font-size:12px">${t[1]}</td><td>${statusBadge(t[2]==='Owner'?'offer':t[2]==='Recruiter'?'active':'stalled',t[2])}</td></tr>`).join('')}
    </tbody></table>
  </div>`,

/* ---------- SHARED ---------- */
"notifications":()=>ph("Уведомления","События из вашего кабинета · демо",NOTIFICATIONS.length?`<button class="btn btn-ghost btn-sm" onclick="markAllRead()">Прочитать всё</button>`:'')+
  (NOTIFICATIONS.length?NOTIFICATIONS.map(n=>notif(ico(n.icon),n.title,n.text,n.time,n.unread)).join('')
  :emptyState('bell','Пока нет уведомлений','Здесь появятся события: подтверждение часов ментором, статусы задач и договоров, приглашения.')),

"help":()=>{
  const guides=helpGuides();
  const faq=HELP_FAQ[state.role]||[];
  const roleName=(ROLE_META[state.role]||{}).label||'вашей роли';
  return ph("Как пользоваться платформой",`Гайды по разделам, ответы на частые вопросы и обучающий тур для ${roleName}`)+`
  <div class="panel help-hero" style="margin-bottom:16px">
    <div class="row" style="align-items:center;gap:14px">
      <div class="help-hero-ic">${ico('bot')}</div>
      <div style="flex:1"><h3 style="margin:0">Не знаете, с чего начать?</h3><div class="sd">Пройдите короткий интерактивный тур — он проведёт по ключевым разделам прямо на живых экранах.</div></div>
      <button class="btn btn-primary btn-sm" style="width:auto" onclick="startTour()">${ico('spark')} Запустить тур</button>
    </div>
  </div>

  <h3 style="margin:18px 4px 10px">Разделы платформы</h3>
  <div class="help-guides">
    ${guides.map(g=>`<div class="help-card" onclick="go('${g.page}')">
      <div class="help-card-ic">${ico(g.ic)}</div>
      <div style="flex:1;min-width:0">
        <div class="help-card-t">${g.title}</div>
        <div class="help-card-x">${g.text}</div>
        ${g.tip?`<div class="help-card-tip">${ico('spark')} ${g.tip}</div>`:''}
      </div>
      <span class="help-card-go">${ico('compass')}</span>
    </div>`).join('')}
  </div>

  ${faq.length?`<h3 style="margin:22px 4px 10px">Частые вопросы</h3>
  <div class="help-faq">
    ${faq.map((f,i)=>`<div class="help-q" onclick="toggleHelpFaq(${i})">
      <div class="help-q-h"><span>${f.q}</span><span class="help-q-ch" id="help-ch-${i}">${state._helpFaq===i?'−':'+'}</span></div>
      ${state._helpFaq===i?`<div class="help-q-a">${f.a}</div>`:''}
    </div>`).join('')}
  </div>`:''}

  <div class="panel" style="margin-top:22px"><h3>Нужна помощь?</h3>
    <div class="sd" style="margin-bottom:10px">Если что-то не работает или непонятно — напишите нам, ответим в Telegram.</div>
    <button class="btn btn-ghost btn-sm" style="width:auto" onclick="toast('Поддержка — в демо недоступна')">${ico('chat')} Связаться с поддержкой</button>
  </div>`;
},

"settings":()=>{
  const tab=state._setTab||'appearance';
  const tabs=[['appearance','Оформление'],['notifications','Уведомления'],['privacy','Приватность'],['account','Аккаунт'],['data','Данные']];
  const bytes=storageBytes(), kb=(bytes/1024).toFixed(1);
  const quotaPct=Math.min(100, Math.round(bytes/(5*1024*1024)*100));
  const push=pushState();

  const body={
    appearance:()=>`
      <div class="panel" style="margin-bottom:16px"><h3>Тема и цвет</h3><div class="ps">Применяется сразу, сохраняется на этом устройстве</div>
        ${sRow('moon','Тема оформления','«Авто» следует за настройкой системы.',
          sSeg('theme',[['light','Светлая'],['dark','Тёмная'],['auto','Авто']]))}
        ${sRow('palette','Акцентный цвет','Влияет на кнопки, ссылки и выделения.',
          sSwatches('accent',[['blue','#3F5BF6','Синий'],['teal','#0F9E75','Бирюзовый'],['violet','#6C4DD6','Фиолетовый'],['amber','#B9791A','Янтарный']]))}
      </div>
      <div class="panel" style="margin-bottom:16px"><h3>Читаемость</h3><div class="ps">Подстройте интерфейс под себя</div>
        ${sRow('list','Плотность интерфейса','«Компактно» уменьшает отступы — на экран влезает больше.',
          sSeg('density',[['comfortable','Просторно'],['compact','Компактно']]))}
        ${sRow('compass','Свернуть боковое меню','Оставить только иконки — больше места под контент (на десктопе).',
          sToggle('sidebarCollapsed'))}
        ${sRow('doc','Размер шрифта','От 90% до 120% от базового.',
          sRange('fontScale',90,120,5,'%'))}
        ${sRow('spark','Анимации и переходы','Отключите, если укачивает или тормозит.',
          sToggle('motion'))}
      </div>
      <div class="panel"><h3>Язык и звук</h3><div class="ps"></div>
        ${sRow('globe','Язык интерфейса','В прототипе переключается только атрибут страницы.',
          sSeg('language',[['ru','Русский'],['uz','Oʻzbekcha']]), 'частично')}
        ${sRow('bell','Звуки интерфейса','Короткий сигнал при важных событиях.',
          sToggle('sounds'), 'демо')}
      </div>`,

    notifications:()=>`
      <div class="panel" style="margin-bottom:16px"><h3>Браузерные уведомления</h3><div class="ps">Единственный канал, который работает по-настоящему</div>
        ${sRow('bell','Push в браузере',
          push==='granted' ? 'Разрешение выдано. Отправим тестовое уведомление при включении.'
          : push==='denied' ? 'Заблокировано в настройках браузера — снимите блокировку там.'
          : push==='unsupported' ? 'Этот браузер не поддерживает уведомления.'
          : 'Потребуется разрешение браузера.',
          push==='granted'
            ? sToggle('pushEnabled')
            : `<button class="btn btn-primary btn-sm" style="width:auto" onclick="requestPush()" ${push==='denied'||push==='unsupported'?'disabled':''}>Разрешить</button>`)}
      </div>
      <div class="panel"><h3>Почта и дайджесты</h3><div class="ps">Требуют сервера — в прототипе только сохраняют выбор</div>
        ${sRow('mail','Дайджест раз в неделю','Сводка новых вакансий и прогресса.', sToggle('emailDigest'), 'нужен сервер')}
        ${sRow('target','Совпадения вакансий','Письмо, когда появляется позиция под ваш профиль.', sToggle('jobAlerts'), 'нужен сервер')}
      </div>`,

    privacy:()=>`
      <div class="panel" style="margin-bottom:16px"><h3>Видимость профиля</h3><div class="ps">Кто видит ваше резюме и результаты</div>
        ${sRow('user','Открытый профиль','Работодатели могут найти вас в поиске кандидатов. Выключите — вас увидят только те, кому вы откликнулись.',
          sToggle('profilePublic'))}
        ${sRow('university','Делиться диагностикой с ВУЗом','Куратор увидит ваш профиль компетенций и прогресс.',
          sToggle('shareDiag'))}
      </div>
      <div class="panel"><h3>Hero и данные</h3><div class="ps"></div>
        ${sRow('bot','История чата с Hero','Хранится только в этом браузере, никуда не отправляется.',
          `<button class="btn btn-ghost btn-sm" style="width:auto" onclick="clearHeroChat()">Очистить</button>`)}
        ${sRow('compass','Обучающий тур','Пройти вводный тур по разделам заново.',
          `<button class="btn btn-ghost btn-sm" style="width:auto" onclick="replayTour()">Запустить</button>`)}
      </div>`,

    account:()=>{
      const r=MOCK.reg||{};
      const name=[r.first,r.last].filter(Boolean).join(' ')||'Студент';
      return `
      <div class="panel" style="margin-bottom:16px;display:flex;align-items:center;gap:16px">
        <div style="width:56px;height:56px;border-radius:16px;overflow:hidden;background:var(--accent-soft);color:var(--accent-ink);display:flex;align-items:center;justify-content:center;flex:none">
          ${MOCK.users.photo?`<img src="${MOCK.users.photo}" style="width:100%;height:100%;object-fit:cover">`:ico('user')}
        </div>
        <div style="flex:1;min-width:0">
          <div style="font-weight:700;font-size:16px">${name}</div>
          <div class="ps" style="margin:0">${(r.code||'+998')} ${r.phone||'—'} · роль: ${ROLE_META[state.role].label}</div>
        </div>
        <button class="btn btn-ghost btn-sm" style="width:auto" onclick="uploadPhoto()">${ico('upload')} Фото</button>
      </div>
      <div class="panel" style="margin-bottom:16px"><h3>Основные данные</h3><div class="ps">Меняются в резюме и профиле</div>
        ${sRow('user','Имя и фамилия',name,`<button class="btn btn-ghost btn-sm" style="width:auto" onclick="go('resume')">Изменить</button>`)}
        ${sRow('phone','Номер телефона',`${(r.code||'+998')} ${r.phone||'не указан'}`,`<span class="badge b-gray">основной вход</span>`)}
        ${sRow('university','Учебное заведение',r.university||'не указано',`<button class="btn btn-ghost btn-sm" style="width:auto" onclick="go('resume')">Изменить</button>`)}
      </div>
      <div class="panel" style="margin-bottom:16px"><h3>Безопасность</h3><div class="ps"></div>
        ${sRow('check','Автосохранение','Изменения в резюме сохраняются мгновенно.', sToggle('autosave'))}
        ${sRow('ban','Двухфакторная аутентификация','Код подтверждения при входе с нового устройства.',
          `<button class="btn btn-ghost btn-sm" style="width:auto" onclick="toast('2FA требует сервера — в прототипе недоступна')">Настроить</button>`,'нужен сервер')}
      </div>
      <div class="panel"><h3>Сессия</h3><div class="ps"></div>
        ${sRow('compass','Выйти из аккаунта','Данные останутся на этом устройстве.',
          `<button class="btn btn-ghost btn-sm" style="width:auto" onclick="doLogout()">Выйти</button>`)}
      </div>`;},

    data:()=>{
      const acts=trackSummary();
      return `
      <div class="panel" style="margin-bottom:16px"><h3>${ico('chart')} Активность в этой сессии</h3><div class="ps">Демо-трекинг: какие разделы вы открывали. Ничего не отправляется — только для показа аналитики.</div>
        ${acts.length?acts.map(([name,n])=>{const mx=acts[0][1]||1;return `<div class="set-row"><div class="st" style="flex:1">${name}</div><div style="display:flex;align-items:center;gap:10px;width:160px"><div class="progress" style="flex:1"><i style="width:${Math.round(n/mx*100)}%"></i></div><span class="sd" style="width:24px;text-align:right">${n}</span></div></div>`;}).join(''):`<div class="sd">Пока нет данных — походите по разделам, и здесь появится статистика посещений.</div>`}
      </div>
      <div class="panel" style="margin-bottom:16px"><h3>Локальное хранилище</h3><div class="ps">Всё живёт в этом браузере — сервера у прототипа нет</div>
        <div class="storage-bar"><i style="width:${Math.max(2,quotaPct)}%"></i></div>
        <div class="ps" style="margin:0">Занято ${kb} КБ из ~5 МБ (${quotaPct}%)</div>
        <div style="margin-top:14px">
          ${sRow('upload','Выгрузить мои данные','Файл JSON: профиль, резюме, диагностика, настройки.',
            `<button class="btn btn-ghost btn-sm" style="width:auto" onclick="exportData()">Скачать</button>`)}
          ${sRow('doc','Загрузить из файла','Восстановит состояние из ранее выгруженного JSON.',
            `<button class="btn btn-ghost btn-sm" style="width:auto" onclick="importData()">Выбрать файл</button>`)}
          ${sRow('gear','Сбросить настройки','Тема, цвет, плотность и прочее — к значениям по умолчанию.',
            `<button class="btn btn-ghost btn-sm" style="width:auto" onclick="resetPrefs()">Сбросить</button>`)}
        </div>
      </div>
      <div class="panel danger"><h3>${ico('alert')} Опасная зона</h3><div class="ps">Действие необратимо</div>
        ${sRow('ban','Удалить все данные','Профиль, резюме, диагностика, настройки, история Hero. Восстановить будет нельзя.',
          `<button class="btn btn-danger btn-sm" style="width:auto" onclick="wipeData()">Удалить всё</button>`)}
      </div>`;},
  };

  return ph("Настройки","Всё, что здесь переключается, действительно работает")+`
  <div class="set-nav">
    ${tabs.map(t=>`<button class="${tab===t[0]?'on':''}" onclick="setSettingsTab('${t[0]}')">${t[1]}</button>`).join('')}
  </div>
  ${(body[tab]||body.appearance)()}`;
},

"profile":()=>{
  profileInit();
  const r=MOCK.reg||{}, p=MOCK.profile, d=MOCK.resumeData||{};
  const name=[r.first,r.last].filter(Boolean).join(' ')||'Без имени';
  const photo=MOCK.users.photo;
  const c=profileChecklist();
  const doneN=c.filter(x=>x.done).length;
  const pct=Math.round(doneN/c.length*100);
  const views=Math.round(pct/100*42);
  const diagDone=!!(state._diag&&state._diag.done);
  const nextGap=c.find(x=>!x.done);

  const STATUS=[
    ['active','Активно ищу','var(--green)','Работодатели видят вас первыми в поиске'],
    ['open','Открыт к предложениям','var(--amber)','Не ищу активно, но рассмотрю интересное'],
    ['closed','Не ищу','var(--faint)','Профиль скрыт из поиска работодателей'],
  ];
  const st=STATUS.find(x=>x[0]===p.jobStatus)||STATUS[0];

  const skills=(r.skillsArr||[]);
  const lv=(r.langLevels||{});
  const langs=Object.keys(lv);

  const applied=(p.appliedJobs||[]).map(id=>JOBS.find(j=>j.id===id)).filter(Boolean);
  const rr=42, cc=2*Math.PI*rr, off=cc-(pct/100)*cc;
  const slug=[r.first,r.last].filter(Boolean).join('-').toLowerCase().replace(/[^a-zа-я0-9-]/gi,'')||'student';

  const SUGGEST=[['github','GitHub','code'],['linkedin','LinkedIn','briefcase'],['t.me','Telegram','chat'],['behance','Behance','palette']];

  return ph("Профиль","Так вас видят работодатели",
    `<button class="btn btn-ghost btn-sm" style="width:auto" onclick="go('resume')">${ico('resume')} Резюме</button>`)+`

  <div class="pf-hero">
    <div class="pf-cover">
      <span class="pf-status-pill"><span class="status-dot" style="background:${st[2]}"></span>${st[1]}</span>
    </div>
    <div class="pf-body">
      <div class="pf-ava">
        ${photo?`<img src="${photo}" alt="">`:ico('user')}
        <div class="pf-cam" onclick="uploadPhoto()">Изменить</div>
      </div>
      <div class="pf-id">
        <div class="pf-name">${name}
          <span class="pf-verified ${p.phoneVerified?'':'pf-unverified'}" ${p.phoneVerified?'':'onclick="verifyPhone()"'}>
            ${ico(p.phoneVerified?'check':'alert')}${p.phoneVerified?'Подтверждён':'Подтвердить телефон'}
          </span>
        </div>
        <div class="pf-role">${r.goal||r.direction||'Направление не указано'}</div>
        <div class="pf-tags">
          ${r.university?`<span class="pf-tag">${ico('university')}${r.university.length>30?r.university.slice(0,28)+'…':r.university}</span>`:''}
          ${r.course?`<span class="pf-tag">${ico('student')}${r.course}</span>`:''}
          ${r.city?`<span class="pf-tag">${ico('pin')}${r.city}</span>`:''}
          ${r.format?`<span class="pf-tag">${ico('briefcase')}${r.format}</span>`:''}
        </div>
        <div class="pf-link">
          <span class="pl-ic">${ico('globe')}</span>
          <code>z2h.uz/r/${slug}</code>
          <button onclick="copyProfileLink('${slug}')">${ico('doc')} Копировать</button>
        </div>
      </div>
      <div class="pf-side">
        ${photo
          ? `<button class="btn btn-ghost btn-sm" style="width:auto" onclick="removePhoto()">Удалить фото</button>`
          : `<button class="btn btn-primary btn-sm" style="width:auto" onclick="uploadPhoto()">${ico('upload')} Фото</button>`}
      </div>
    </div>
  </div>

  <div class="g g2" style="margin-bottom:16px">
    <div class="panel">
      <h3>${ico('target')} Заполненность профиля</h3><div class="ps">Полные профили получают в 3 раза больше приглашений</div>
      <div class="pf-meter" style="margin-top:16px">
        <div class="pm-ring">
          <svg width="74" height="74" viewBox="0 0 96 96">
            <circle cx="48" cy="48" r="${rr}" fill="none" stroke="var(--hair2)" stroke-width="9"/>
            <circle cx="48" cy="48" r="${rr}" fill="none" stroke="var(--accent)" stroke-width="9" stroke-linecap="round"
                    stroke-dasharray="${cc.toFixed(1)}" stroke-dashoffset="${off.toFixed(1)}"/>
          </svg>
          <span>${pct}%</span>
        </div>
        <div class="pm-b">
          <div class="pm-t">${doneN} из ${c.length} пунктов</div>
          <div class="pm-d">${nextGap?`Следующий шаг: <b>${nextGap.t}</b>`:'Профиль полностью заполнен — отлично!'}</div>
        </div>
      </div>
      <div class="check-list">
        ${c.map(x=>`<div class="check-item ${x.done?'done':''}" onclick="${x.action}">
          <span class="ci-box">${ico('check')}</span>
          <span class="ci-t">${x.t}</span>
          ${x.done?'':`<span class="ci-go">Заполнить →</span>`}
        </div>`).join('')}
      </div>
    </div>

    <div class="panel">
      <h3>${ico('chart')} Активность</h3><div class="ps">Ваш след на платформе</div>
      <div class="act-grid" style="margin-top:16px">
        <div class="act" onclick="go('diagnostics')">
          <div class="a-ic" style="background:var(--blue-soft);color:var(--blue)">${ico('brain')}</div>
          <div class="a-v" style="font-size:${diagDone?'15px':'22px'};color:${diagDone?'var(--green)':'var(--faint)'}">${diagDone?'Пройдена':'—'}</div>
          <div class="a-l">Диагностика</div>
        </div>
        <div class="act" onclick="go('simulations')">
          <div class="a-ic" style="background:var(--purple-soft);color:var(--purple)">${ico('puzzle')}</div>
          <div class="a-v">${p.simsDone}</div><div class="a-l">Симуляций сдано</div>
        </div>
        <div class="act" onclick="go('jobs')">
          <div class="a-ic" style="background:var(--teal-soft);color:var(--teal)">${ico('briefcase')}</div>
          <div class="a-v">${p.applications}</div><div class="a-l">Откликов</div>
        </div>
        <div class="act">
          <div class="a-ic" style="background:var(--amber-soft);color:var(--amber)">${ico('user')}</div>
          <div class="a-v">${views}</div><div class="a-l" title="Оценка: растёт с заполненностью профиля">Просмотров · оценка</div>
        </div>
      </div>
      <div style="margin-top:18px">
        <div class="section-label" style="margin:0 0 9px">Статус поиска работы</div>
        <div class="status-pick">
          ${STATUS.map(x=>`<div class="status-opt ${p.jobStatus===x[0]?'on':''}" onclick="setProfile('jobStatus','${x[0]}')">
            <div class="so-h"><span class="status-dot" style="background:${x[2]}"></span>${x[1]}</div>
            <div class="so-d">${x[3]}</div>
          </div>`).join('')}
        </div>
      </div>
    </div>
  </div>

  <div class="panel" style="margin-bottom:16px">
    <h3>${ico('user')} Личные данные</h3>
    <div class="ps">Сохраняются автоматически<span class="saved-hint" id="pf-saved">${ico('check')}сохранено</span></div>

    <div class="pf-sub">Кто вы</div>
    <div class="pf-grid">
      <div class="pf-field"><label>${ico('user')}Имя</label>
        <input value="${(r.first||'').replace(/"/g,'&quot;')}" oninput="setReg('first',this.value)" placeholder="Бекзод"></div>
      <div class="pf-field"><label>${ico('user')}Фамилия</label>
        <input value="${(r.last||'').replace(/"/g,'&quot;')}" oninput="setReg('last',this.value)" placeholder="Азимбоев"></div>
      <div class="pf-field"><label>${ico('calendar')}Дата рождения</label>
        <input type="date" min="1950-01-01" max="2012-12-31" value="${r.birth||''}" oninput="clampBirth(this,'reg')" onchange="clampBirth(this,'reg')"></div>
      <div class="pf-field"><label>${ico('pin')}Город</label>
        <input value="${(r.city||'').replace(/"/g,'&quot;')}" oninput="setReg('city',this.value)" placeholder="Ташкент"></div>
    </div>

    <div class="pf-sub">Как с вами связаться</div>
    <div class="pf-grid">
      <div class="pf-field locked"><label>${ico('phone')}Телефон<span class="pf-lock">${ico('ban')}нельзя изменить</span></label>
        <input value="${(r.code||'+998')} ${r.phone||''}" disabled>
        <div class="pf-note">Используется для входа в аккаунт</div></div>
      <div class="pf-field"><label>${ico('mail')}Email</label>
        <input type="email" value="${(p.email||'').replace(/"/g,'&quot;')}" oninput="setProfileEmail(this.value)" placeholder="you@mail.uz">
        <div class="pf-note">Работодатели напишут сюда</div></div>
    </div>

    <div class="pf-sub">Образование</div>
    <div class="pf-grid">
      <div class="pf-field" style="grid-column:1/-1"><label>${ico('university')}Учебное заведение</label>
        <input value="${(r.university||'').replace(/"/g,'&quot;')}" oninput="setReg('university',this.value)" placeholder="Университет"></div>
      <div class="pf-field"><label>${ico('student')}Курс</label>
        <input value="${(r.course||'').replace(/"/g,'&quot;')}" oninput="setReg('course',this.value)" placeholder="3-й курс"></div>
      <div class="pf-field"><label>${ico('target')}Направление</label>
        <input value="${(r.direction||'').replace(/"/g,'&quot;')}" oninput="setReg('direction',this.value)" placeholder="Аналитика данных"></div>
    </div>
  </div>

  <div class="g g2" style="margin-bottom:16px">
    <div class="panel">
      <h3>${ico('code')} Навыки и языки</h3><div class="ps">Редактируются в резюме</div>
      <div style="margin-top:14px">
        <div class="section-label" style="margin:0 0 8px">Навыки</div>
        <div class="pf-chips">
          ${skills.length?skills.map(sk=>{
            const lvl=((d.skillLevels||{})[sk])||'';
            return `<span class="pf-chip">${sk}${lvl?`<span class="lvl">${lvl}</span>`:''}</span>`;
          }).join(''):`<span class="ps">Пока не добавлены</span>`}
        </div>
        <div class="section-label" style="margin:16px 0 8px">Языки</div>
        <div class="pf-chips">
          ${langs.length?langs.map(l=>`<span class="pf-chip plain" title="${langDesc(lv[l])}">${l}<span class="lvl">${lv[l]==='Родной'?'родной':langLabel(lv[l])}</span></span>`).join(''):`<span class="ps">Пока не добавлены</span>`}
        </div>
      </div>
      <button class="btn btn-ghost btn-sm" style="width:auto;margin-top:16px" onclick="go('resume')">${ico('resume')} Изменить в резюме</button>
    </div>

    <div class="panel">
      <h3>${ico('globe')} Ссылки и портфолио</h3><div class="ps">Их видят работодатели</div>
      <div style="margin-top:10px">
        ${p.links.length?p.links.map((l,i)=>`<div class="link-row">
          <span class="lr-ic">${ico(linkIcon(l.url))}</span>
          <input value="${(l.url||'').replace(/"/g,'&quot;')}" oninput="setLink(${i},this.value)" placeholder="https://github.com/username">
          <button class="lr-x" onclick="removeProfileLink(${i})" title="Удалить">✕</button>
        </div>`).join(''):`<div class="ps" style="padding:6px 0">Пока ничего не добавлено</div>`}
      </div>
      <div class="link-suggest">
        ${SUGGEST.map(sg=>`<button onclick="addProfileLink('https://${sg[0]}/')">${ico(sg[2])}${sg[1]}</button>`).join('')}
        <button onclick="addProfileLink('')">${ico('plus')}Другое</button>
      </div>
    </div>
  </div>

  ${applied.length?`<div class="panel" style="margin-bottom:16px">
    <h3>${ico('briefcase')} История откликов</h3><div class="ps">${applied.length} ${applied.length===1?'отклик':'откликов'}</div>
    <div style="margin-top:10px">
      ${applied.map(j=>`<div class="app-row" onclick="openJob(${j.id})" style="cursor:pointer">
        <div class="ar-logo" style="background:${j.color}">${j.logo}</div>
        <div class="ar-b"><div class="ar-t">${j.t}</div><div class="ar-d">${j.co} · ${j.loc}</div></div>
        <span class="ar-s">На рассмотрении</span>
      </div>`).join('')}
    </div>
  </div>`:''}

  <div class="panel">
    <h3>${ico('ban')} Приватность и согласия</h3><div class="ps">Кто видит ваши данные</div>
    <div style="margin-top:8px">
      ${sRow('user','Открытый профиль','Работодатели могут найти вас в поиске кандидатов.',sToggle('profilePublic'))}
      ${sRow('university','Делиться диагностикой с ВУЗом','Куратор увидит ваш профиль компетенций.',sToggle('shareDiag'))}
      ${sRow('mail','Согласие на обработку данных','Дано при регистрации. Отзыв означает удаление аккаунта.',
        `<button class="btn btn-ghost btn-sm" style="width:auto" onclick="setSettingsTab('data');go('settings')">Управлять данными</button>`)}
    </div>
  </div>`;
},

"search":()=>ph("Поиск","Симуляции, вакансии, кандидаты и разделы в одном месте")+`
  <div class="field" style="max-width:520px;margin-bottom:20px"><input placeholder="Введите запрос…" oninput="filterSearch(this.value)" autofocus></div>
  <div id="search-out">
    <div class="section-label">Симуляции</div>
    ${SIMS.slice(0,2).map(s=>li(ico('puzzle'),s.t,s.role+" · "+s.match+"%","→")).join('')}
    <div class="section-label">Вакансии</div>
    ${JOBS.slice(0,2).map(j=>li(ico('briefcase'),j.t,j.co+" · "+j.match+"%","→")).join('')}
    <div class="section-label">Разделы</div>
    ${li(ico('compass'),"Траектория","перейти в раздел","")}
    ${li(ico('doc'),"AI-резюме","перейти в раздел","")}
  </div>`,

"university:settings":()=>ph("Настройки организации","Профиль ВУЗа, брендинг и SSO")+`
  <div class="panel" style="margin-bottom:16px"><h3>Профиль организации</h3><div class="ps"></div>
    <div class="split">
      <div class="field"><label>Название</label><input value="Национальный университет Узбекистана"></div>
      <div class="field"><label>Регион</label><input value="Ташкент"></div>
      <div class="field"><label>Ответственный</label><input value="Иванов И. И."></div>
      <div class="field"><label>Домен для приглашений</label><input value="@nuu.uz"></div>
    </div>
  </div>
  <div class="panel" style="margin-bottom:16px"><h3>Брендинг</h3><div class="ps">Логотип и цвет в кабинетах студентов</div>
    ${setRow("Логотип ВУЗа","Отображается в шапке студентов",true,"Загружен")}
    ${setRow("Акцентный цвет","Фирменный цвет организации",true,"Бирюзовый")}
  </div>
  <div class="panel"><h3>SSO</h3><div class="ps">Единый вход через учётную систему ВУЗа</div>
    ${setRow("SAML / SSO","Вход студентов по корпоративному аккаунту",false)}
    ${setRow("Автозачисление","Новые студенты попадают в когорту по домену",true)}
  </div>`,

"company:settings":()=>ph("Настройки","Биллинг, интеграции и роли")+`
  <div class="panel" style="margin-bottom:16px"><h3>Биллинг</h3><div class="ps"></div>
    <div class="set-row"><div><div class="st">Тариф «Компания»</div><div class="sd">от 25 000 сум/мес · до 6 стажировок</div></div><button class="btn btn-ghost btn-sm" onclick="toast('Биллинг — в демо недоступен')">Управлять</button></div>
    <div class="set-row"><div><div class="st">Способ оплаты</div><div class="sd">Карта •••• 4242</div></div><button class="btn btn-ghost btn-sm" onclick="toast('Биллинг — в демо недоступен')">Изменить</button></div>
  </div>
  <div class="panel" style="margin-bottom:16px"><h3>Интеграции</h3><div class="ps"></div>
    ${setRow("Telegram-бот","Уведомления о новых кандидатах",true)}
    ${setRow("Экспорт в ATS","Выгрузка кандидатов в вашу систему найма",false)}
    ${setRow("Webhook откликов","POST при новом отклике",false)}
  </div>
  <div class="panel"><h3>Роли и доступ</h3><div class="ps"></div>
    ${setRow("Recruiter может публиковать","Создание стажировок без Owner",true)}
    ${setRow("Viewer видит контакты","Доступ к email кандидатов",false)}
  </div>`,

/* ============================================================
   CORE 1 — ДНЕВНИК ПРАКТИКИ [FEATURES.internship_diary]
   Студент ведёт, ментор подтверждает, вуз видит статус.
   ============================================================ */
"admin:home":()=>{
  const signed=CONTRACTS.filter(c=>c.status==='signed').length;
  const _kf=kpiFaculties();
  const totalEmployed=_kf.reduce((s,f)=>s+f.employed,0);
  const totalIntern=_kf.reduce((s,f)=>s+f.onInternship,0);
  return `<div class="onb-banner" style="margin-bottom:18px"><h2>${ico('gear')} Панель администратора платформы</h2><p>Сводка по вузам, договорам и трудоустройству · демо-данные</p></div>`+`
  <div class="cards">
    <div class="simcard"><div class="sc-t" style="font-size:26px">${CONTRACTS.length}</div><div class="sc-meta">договоров практики (${signed} подписано)</div></div>
    <div class="simcard"><div class="sc-t" style="font-size:26px">${totalIntern}</div><div class="sc-meta">студентов на практике</div></div>
    <div class="simcard"><div class="sc-t" style="font-size:26px">${totalEmployed}</div><div class="sc-meta">трудоустроено</div></div>
    <div class="simcard"><div class="sc-t" style="font-size:26px">${HTD_ORDERS.length}</div><div class="sc-meta">активных заказов на кадры</div></div>
  </div>
  <div class="sd" style="margin-top:14px">Все показатели — демо-данные, не реальные метрики.</div>`;
},

"student:diary":()=>{
  const done=DIARY.entries.filter(e=>e.status==='approved').reduce((s,e)=>s+e.hours,0);
  const pct=Math.min(100,Math.round(done/DIARY.goalHours*100));
  const overdue=DIARY.entries.filter(e=>e.status==='overdue').length;
  const hasEntries=DIARY.entries.length>0;
  return ph("Дневник практики",`${DIARY.company} · ${DIARY.role} · ментор ${DIARY.mentor}`,`<button class="btn btn-primary btn-sm" onclick="toast('Новая запись — в демо недоступна')">＋ Запись за неделю</button>`)+`
  <div class="panel" style="margin-bottom:16px">
    <div class="row" style="align-items:center">
      <div><div class="st">Прогресс по часам</div><div class="sd">${done} из ${DIARY.goalHours} ч подтверждено · демо-данные</div></div>
      <div style="font-family:var(--disp);font-weight:800;font-size:26px">${pct}%</div>
    </div>
    <div class="progress" style="margin-top:10px"><i style="width:${pct}%"></i></div>
    ${overdue?`<div class="ps"></div><div class="badge b-red">${ico('bell')} ${overdue} просроченная запись — сдайте, чтобы вуз зачёл часы</div>`:''}
  </div>
  ${hasEntries?practiceSchedule(myPractice()):''}
  <div class="panel" style="padding:${hasEntries?'0':'0'};overflow:hidden">
    ${hasEntries?`<table class="tbl">
      <thead><tr><th>Неделя</th><th>Дата</th><th>Часы</th><th>Задачи</th><th>Статус</th></tr></thead>
      <tbody>
      ${DIARY.entries.map((e,i)=>`
        <tr onclick="openDiaryEntry(${i})" style="cursor:pointer">
          <td class="nm">Неделя ${e.week}</td><td>${e.date}</td><td>${e.hours||'—'}</td>
          <td>${e.task}</td><td>${diaryBadge(e)}</td>
        </tr>`).join('')}
      </tbody>
    </table>`:emptyState('list','Записей пока нет','Практика ещё не началась или первая запись не добавлена. Добавьте отчёт за неделю — ментор подтвердит часы, и вуз зачтёт практику.',{label:'＋ Первая запись',onclick:"toast('Новая запись — в демо недоступна')"})}
  </div>
  ${DIARY.criteria.length?`<div class="panel" style="margin-top:16px"><h3>Оценка ментора</h3>
    <div class="sd" style="margin-bottom:10px">${DIARY.mentor} · ${DIARY.company} · демо-оценка</div>
    ${DIARY.criteria.map(c=>`<div class="set-row"><div class="st">${c.name}</div><div style="display:flex;gap:3px">${[1,2,3,4,5].map(n=>`<span style="width:9px;height:9px;border-radius:50%;background:${n<=c.score?'var(--accent)':'var(--hair2)'}"></span>`).join('')}</div></div>`).join('')}
  </div>`:`<div class="panel" style="margin-top:16px"><h3>Оценка ментора</h3>${emptyState('user','Ментор ещё не оценил','Оценка появится, когда ментор проверит ваши первые записи. Регулярно заполняйте дневник, чтобы получить обратную связь.')}</div>`}
  ${hasEntries?`<div style="margin-top:16px">${practiceThread(myPractice())}</div>`:''}`;
},

"diary-entry":()=>{
  const e=DIARY.entries[state._diary||0]||DIARY.entries[0];
  return back('diary','Дневник практики')+ph(`Неделя ${e.week}`,`${e.date} · ${DIARY.company}`)+`
  <div class="panel" style="margin-bottom:16px">
    <div class="set-row"><div class="st">Статус</div>${diaryBadge(e)}</div>
    <div class="set-row"><div class="st">Часы за неделю</div><div>${e.hours||0} ч</div></div>
    ${e.grade?`<div class="set-row"><div class="st">Оценка ментора</div><span class="badge b-green">${e.grade}</span></div>`:''}
    ${e.due?`<div class="set-row"><div class="st">Срок сдачи</div><span class="badge b-red">до ${e.due}</span></div>`:''}
  </div>
  <div class="panel" style="margin-bottom:16px"><h3>Что сделано</h3><div class="ps"></div><p style="line-height:1.6">${e.task}</p></div>
  <div class="panel"><h3>Вложения</h3><div class="ps"></div>
    <div class="set-row"><div><div class="st">${ico('folder')} отчёт_неделя${e.week}.pdf</div><div class="sd">заглушка · файл не загружается в демо</div></div><button class="btn btn-ghost btn-sm" onclick="toast('Загрузка файлов — в демо недоступна')">Открыть</button></div>
  </div>`;
},

/* ============================================================
   CORE 2 — ТРЁХСТОРОННИЙ ДОГОВОР ПРАКТИКИ [FEATURES.tripartite_contract]
   Вуз + студент + компания. E-imzo — MOCK. Реестр в кабинете вуза/админа.
   ============================================================ */
"university:contracts":()=>contractsList("university"),
"admin:contracts":()=>contractsList("admin"),
"contract-detail":()=>{
  const c=CONTRACTS[state._contract||0]||CONTRACTS[0];
  const parties=[["Вуз","uni"],["Студент","student"],["Компания","company"]];
  const st=CONTRACT_STATUS[c.status]||['b-gray',c.status];
  return back('contracts','Реестр договоров')+ph(`Договор ${c.id}`,`${c.program} · демо`)+`
  <div class="panel" style="margin-bottom:16px">
    <div class="set-row"><div class="st">Студент</div><div>${c.student}</div></div>
    <div class="set-row"><div class="st">Компания</div><div>${c.company}</div></div>
    <div class="set-row"><div class="st">Факультет</div><div>${c.faculty}</div></div>
    <div class="set-row"><div class="st">Статус</div><span class="badge ${st[0]}">${st[1]}</span></div>
  </div>
  <div class="panel" style="margin-bottom:16px"><h3>Стороны и подписи</h3><div class="ps"></div>
    ${parties.map(p=>`<div class="set-row"><div class="st">${p[0]}</div>${c.signed[p[1]]?`<span class="badge b-green">${ico('check')} Подписано</span>`:`<span class="badge b-amber">Ожидает</span>`}</div>`).join('')}
  </div>
  ${(()=>{ const p=practiceByContract(c.id); if(!p) return '';
    const hrs=practiceHours(p); const pct=Math.min(100,Math.round(hrs/p.goalHours*100));
    const done=p.entries.filter(e=>e.status==='approved').length;
    return `<div class="panel" style="margin-bottom:16px"><h3>Практика по договору</h3>
    <div class="sd" style="margin-bottom:10px">Тот же студент виден в дневнике практики и в KPI деканата · демо</div>
    <div class="set-row"><div class="st">Ментор от компании</div><div>${p.mentor}</div></div>
    <div class="set-row"><div class="st">Подтверждено часов</div><div>${hrs} из ${p.goalHours} ч</div></div>
    <div class="set-row"><div class="st">Записей в дневнике</div><div>${p.entries.length} (${done} подтверждено)</div></div>
    <div class="progress" style="margin-top:10px"><i style="width:${pct}%"></i></div>
    ${p.entries.length===0?`<div class="sd" style="margin-top:10px">${ico('alert')} Практика ещё не началась — договор не подписан всеми сторонами.</div>`:''}
    </div>`;})()}
  <div class="panel" style="margin-bottom:16px"><h3>Шаблон договора</h3><div class="ps"></div>
    <p style="line-height:1.6;color:var(--muted);font-size:13px">Договор о квалификационной практике между образовательной организацией, обучающимся и организацией-базой практики. Предмет: прохождение практики в объёме ${c.program.match(/\d+ ч/)?c.program.match(/\d+ ч/)[0]:'—'}, руководство со стороны компании, зачёт со стороны вуза. <span class="mono">— демо-текст, не юридический документ</span></p>
  </div>
  ${c.status!=='signed'?`<button class="btn btn-primary" onclick="signContract()">${ico('check')} Подписать через E-imzo (ЭЦП)</button><div class="sd" style="text-align:center;margin-top:8px">MOCK: реальной интеграции с E-imzo нет</div>`:`<div class="empty" style="padding:30px"><div class="ei">${ico('check')}</div><h3>Договор подписан всеми сторонами</h3></div>`}`;
},

/* ============================================================
   CORE 3 — KPI ДЕКАНАТА [FEATURES.uni_kpi_dashboard]
   Аналитика трудоустройства под гос-KPI. Все числа — демо.
   ============================================================ */
"university:kpi":()=>kpiDashboard("university"),
"admin:kpi":()=>kpiDashboard("admin"),

/* ============================================================
   CORE 4 — HIRE-TRAIN-DEPLOY [FEATURES.htd]
   Компания заказывает кадры → трек обучения → витрина → deploy.
   ============================================================ */
"company:htd":()=>{
  const t={applied:0,enrolled:0,training:0,deployed:0};
  HTD_ORDERS.forEach(o=>{for(const k in t)t[k]+=o.funnel[k];});
  const stageColor={recruit:'#3F5BF6',train:'#7C3AED',deploy:'#10B981',done:'#888'};
  return ph("Заказ на кадры","Hire-Train-Deploy · обучение под ваш спрос",`<button class="btn btn-primary btn-sm" onclick="go('order-new')">＋ Новый заказ</button>`)+
  (HTD_ORDERS.length?`
  <div class="htd-stats">
    <div class="htd-stat"><b>${HTD_ORDERS.length}</b><span>активных заказов</span></div>
    <div class="htd-stat"><b>${t.enrolled}</b><span>студентов набрано</span></div>
    <div class="htd-stat"><b>${t.training}</b><span>обучаются сейчас</span></div>
    <div class="htd-stat"><b style="color:var(--green)">${t.deployed}</b><span>трудоустроено</span></div>
  </div>
  <div class="sd" style="margin-bottom:14px">Сформируйте заказ — под него соберётся учебный трек, студенты пройдут обучение и попадут в витрину верифицированных кандидатов. Демо-данные.</div>
  <div class="cards">
    ${HTD_ORDERS.map((o,i)=>{
      const s=HTD_STAGE[o.stage]||['b-gray',o.stage];
      const hc=stageColor[o.stage]||'#3F5BF6';
      const overdue=o.deadline<dOffset(0);
      const segs=[["applied"],["enrolled"],["training"],["deployed"]];
      const mx=Math.max(...segs.map(x=>o.funnel[x[0]]))||1;
      return `
      <div class="htd-card" style="--hc:${hc}" onclick="openHtd(${i})">
        <div class="htd-card-h"><div class="htd-card-t">${o.role}</div><span class="badge ${s[0]}">${s[1]}</span></div>
        <div class="htd-card-meta">${o.company} · ${o.id} · ${o.count} чел. · ${o.track}</div>
        <div class="htd-skills">${o.skills.map(sk=>`<span class="htd-skill">${sk}</span>`).join('')}</div>
        <div class="htd-mini">${segs.map(x=>`<div class="htd-mini-seg"><i style="width:${Math.round(o.funnel[x[0]]/mx*100)}%"></i></div>`).join('')}</div>
        <div class="htd-card-foot"><span style="${overdue?'color:var(--red)':''}">${ico('calendar')} срок: ${o.deadline}${overdue?' · просрочен':''}</span><span>${ico('chart')} ${o.funnel.deployed}/${o.count} готово →</span></div>
      </div>`;}).join('')}
  </div>`
  :emptyState('puzzle','Заказов на кадры пока нет','Создайте первый заказ: укажите роль, нужные навыки и количество. Под заказ соберётся учебный трек, а обученные студенты попадут в витрину.',{label:'＋ Новый заказ',onclick:"go('order-new')"}));

},
"company:order-new":()=>{
  const draft=state._orderDraft||(state._orderDraft={skills:[]});
  const skillPool=["SQL","Python","Дашборды (BI)","A/B-тесты","Аналитика данных","Go","PostgreSQL","REST","Docker","JavaScript","HTML/CSS","Дизайн","Figma","Коммуникация","ML","Excel","Финмодели"];
  return back('htd','Заказ на кадры')+ph("Новый заказ на кадры","Опишите спрос — под него соберётся трек подготовки, а готовые студенты попадут в витрину")+`
  <div class="panel" style="max-width:660px">
    <div class="field" style="margin-top:4px"><label>Направление / роль</label><input id="ord-role" value="${draft.role||''}" placeholder="Напр. Data Analyst"></div>
    <div class="split">
      <div class="field"><label>Количество мест</label><input id="ord-count" type="number" min="1" value="${draft.count||5}"></div>
      <div class="field"><label>Срок (дней от сегодня)</label><input id="ord-days" type="number" min="1" value="${draft.days||45}"></div>
    </div>
    <div class="field"><label>Название трека подготовки</label><input id="ord-track" value="${draft.track||''}" placeholder="Напр. Аналитика данных · 8 модулей"><div class="sd" style="margin-top:5px">Это подготовка под ваш заказ, а не курс — навыки собираются под требования.</div></div>
    <div class="field"><label>Требуемые навыки</label>
      <div class="sd" style="margin-bottom:8px">Отметьте навыки — по ним студенты ранжируются в витрине (Match Score).</div>
      <div class="ord-skills">
        ${skillPool.map(s=>`<span class="ord-skill ${draft.skills.includes(s)?'on':''}" onclick="toggleOrderSkill('${s.replace(/'/g,"\\'")}')">${draft.skills.includes(s)?ico('check'):''}${s}</span>`).join('')}
      </div>
    </div>
    ${draft.skills.length?`<div class="sd" style="margin:2px 0 12px">Выбрано: ${draft.skills.join(', ')}</div>`:`<div class="sd" style="margin:2px 0 12px" >Навыки не выбраны — добавьте хотя бы один.</div>`}
    <button class="btn btn-primary" onclick="submitOrder()">Опубликовать заказ</button>
    <button class="btn btn-ghost btn-sm" style="width:auto;margin-left:8px" onclick="state._orderDraft=null;go('htd')">Отмена</button>
    <div class="sd" style="margin-top:12px">MOCK: заказ добавляется в демо-модель этой сессии — появится в списке заказов, в витрине для ранжирования и у студентов в «Заказах на кадры».</div>
  </div>`;
},
"htd-detail":()=>{
  const o=HTD_ORDERS[state._htd||0]||HTD_ORDERS[0];
  const s=HTD_STAGE[o.stage]||['b-gray',o.stage];
  const stages=[["applied","Отклики","#3F5BF6","#5B72F8"],["enrolled","Набрано","#6D4AED","#8B6EF2"],["training","Обучаются","#C2410C","#EA580C"],["deployed","Трудоустроены","#059669","#10B981"]];
  const max=Math.max(...stages.map(x=>o.funnel[x[0]]))||1;
  const pipe=[["recruit","users","Hire","Набор кандидатов"],["train","puzzle","Train","Обучение по треку"],["deploy","trophy","Deploy","Трудоустройство"]];
  const stageIdx={recruit:0,train:1,deploy:2,done:3}[o.stage]??0;
  return back('htd','Заказ на кадры')+ph(`${o.role} · ${o.count} чел.`,`${o.company} · ${o.id} · демо`,`<span class="badge ${s[0]}">${s[1]}</span>`)+`
  <div class="htd-pipe">
    ${pipe.map((p,i)=>`<div class="htd-pipe-cell ${i===stageIdx?'on':''}"><div class="htd-pipe-ic">${ico(p[1])}</div><div class="htd-pipe-t">${p[2]}</div><div class="htd-pipe-d">${p[3]}</div></div>`).join('')}
  </div>
  <div class="panel" style="margin-bottom:16px">
    <div class="set-row"><div class="st">Срок</div><div>${o.deadline}${o.deadline<dOffset(0)?` <span class="badge b-red">просрочен</span>`:''}</div></div>
    <div class="set-row"><div class="st">Учебный трек</div><div>${o.track}</div></div>
    <div class="set-row"><div class="st">Требуемые навыки</div><div style="text-align:right">${o.skills.map(sk=>`<span class="htd-skill">${sk}</span>`).join(' ')}</div></div>
  </div>
  <div class="panel" style="margin-bottom:16px"><h3>Воронка Hire-Train-Deploy</h3><div class="sd" style="margin-bottom:14px">демо-данные · конверсия между ступенями</div>
    <div class="htd-funnel">
      ${stages.map((x,i)=>{
        const val=o.funnel[x[0]];
        const w=Math.max(6,Math.round(val/max*100));
        const conv = i>0 ? (o.funnel[stages[i-1][0]]? Math.round(val/o.funnel[stages[i-1][0]]*100):0) : null;
        return `${conv!==null?`<div class="htd-fconv">↓ ${conv}% перешло дальше</div>`:''}
        <div class="htd-fstep"><div class="htd-fbar" style="width:${w}%;--fc1:${x[2]};--fc2:${x[3]}"></div>
          <div class="htd-frow"><span class="htd-flabel"><span class="htd-fdot">${i+1}</span>${x[1]}</span><span class="htd-fnum">${val}</span></div>
        </div>`;}).join('')}
    </div>
  </div>
  <div class="panel" style="margin-bottom:16px"><h3>Учебный трек · ${o.modules.length} ${plural(o.modules.length,'модуль','модуля','модулей')}</h3><div class="sd" style="margin-bottom:12px">Собран под требования заказа · демо</div>
    <div class="htd-modules">
      ${o.modules.map((m,i)=>`<div class="htd-mod"><span class="htd-mod-n">${i+1}</span><span>${m}</span></div>`).join('')}
    </div>
  </div>
  ${(()=>{const trk=trackByOrder(o.id);if(!trk||!trk.enrolled.length)return `<div class="panel" style="margin-bottom:16px"><h3>Студенты на треке</h3>${emptyState('users','Пока никто не зачислен','Как только студенты запишутся на трек подготовки под этот заказ, здесь появится их прогресс.')}</div>`;
    return `<div class="panel" style="margin-bottom:16px"><h3>Студенты на треке · ${trk.enrolled.length}</h3>
      <div class="sd" style="margin-bottom:10px">Прогресс подготовки под требования заказа · демо</div>
      ${trk.enrolled.map(sid=>{const info=trackModulesFor(trk,sid);const ready=info.percent>=100;return `
        <div class="trk-enr">
          <div class="trk-enr-av">${(trk.names[sid]||sid).split(' ').map(w=>w[0]).join('').slice(0,2)}</div>
          <div style="flex:1;min-width:0"><div class="trk-enr-n">${trk.names[sid]||sid}</div>
            <div class="progress" style="margin-top:5px"><i style="width:${info.percent}%"></i></div></div>
          <div class="trk-enr-p">${info.percent}%${ready?` · <span style="color:var(--green)">в витрине</span>`:''}</div>
        </div>`;}).join('')}
    </div>`;})()}
  <button class="btn btn-primary" onclick="go('talent-showcase')">${ico('users')} Открыть витрину под заказ</button>`;
},

/* ============================================================
   BRIDGE — ВИТРИНА ВЕРИФИЦИРОВАННЫХ СТУДЕНТОВ [FEATURES.talent_showcase]
   Навыки подтверждены дневником практики и HTD-треками (не самозаявка).
   Контакты — за premium-пейволлом. MOCK: оплаты и разблокировки нет.
   ============================================================ */
"company:talent-showcase":()=>{
  const unlocked=state._talentUnlocked||[];
  const isPremium=!!state._talentPremium;
  // выбор HTD-заказа для ранжирования по Match Score
  const orderId=state._showcaseOrder;
  const order=orderId!=null?HTD_ORDERS.find(o=>o.id===orderId):null;
  let list=TALENT.filter(c=>c.sims>0 && c.score>=70);
  if(order){
    list=list.map(c=>({c,m:talentMatch(c,order)})).sort((a,b)=>b.m.score-a.m.score);
  } else {
    list=list.sort((a,b)=>b.score-a.score).map(c=>({c,m:null}));
  }
  return ph("Витрина талантов","Студенты с навыками, подтверждёнными практикой и HTD-треками",
    isPremium?`<span class="badge b-green">${ico('check')} Premium активен</span>`:`<button class="btn btn-primary btn-sm" onclick="talentBuyPremium()">${ico('card')} Premium-доступ</button>`)+`
  <div class="panel" style="margin-bottom:16px;padding:14px 16px">
    <div class="row" style="align-items:center;gap:12px">
      <div style="flex:1"><div class="st">Ранжировать под заказ</div><div class="sd">Выберите HTD-заказ — кандидаты отсортируются по соответствию его требованиям с объяснением пробела</div></div>
      <select class="ms-order-sel" onchange="setShowcaseOrder(this.value)">
        <option value="">По общему рейтингу</option>
        ${HTD_ORDERS.map(o=>`<option value="${o.id}"${orderId===o.id?' selected':''}>${o.id} · ${o.role} (${o.company})</option>`).join('')}
      </select>
    </div>
    ${order?`<div class="sd" style="margin-top:10px">${ico('target')} Требования заказа <b>${order.id}</b>: ${order.skills.join(', ')}</div>`:''}
  </div>
  <div class="ai-note" style="margin-bottom:16px">${ico('alert')}<span>Навыки в витрине <b>верифицированы</b>: подтверждены ментором в дневнике практики и HTD-треками, а не самозаявкой студента. Демо-данные.</span></div>
  <div class="cand-grid">
    ${list.map(({c,m})=>{
      const open=isPremium||unlocked.includes(c.id);
      const st=c.status==='active'?['var(--green)','Активно ищет']:['var(--amber)','Открыт к предложениям'];
      const skills = c.id===0 ? verifiedSkills().map(s=>s.name) : c.skills;
      const fitCls=m?(m.score>=80?'ms-hi':m.score>=50?'ms-mid':'ms-lo'):'';
      return `<div class="candcard">
        <div class="cc-head">
          <div class="cc-ava">${c.n.split(' ').map(w=>w[0]).join('')}</div>
          <div style="flex:1;min-width:0">
            <div class="cc-n">${open?c.n:'Студент #'+(c.id+1)}</div>
            <div class="cc-u">${c.u} · ${c.course}</div>
          </div>
          ${m?`<div class="ms-ring ${fitCls}" style="width:48px;height:48px;border-width:2.5px"><b style="font-size:14px">${m.score}%</b></div>`:`<span class="cc-fit">${c.score}</span>`}
        </div>
        <div class="cc-skills">
          ${skills.map(s=>{
            const isGap=m&&m.gap.includes(s);
            return `<span class="cc-sk"><span class="pf-verified" style="padding:2px 7px">${ico('check')}</span> ${s}</span>`;}).join('')}
        </div>
        ${m&&m.gap.length?`<div class="sd" style="margin-top:8px;color:var(--amber)">${ico('spark')} Не хватает под ${order.id}: ${m.gap.join(', ')}</div>`:m?`<div class="sd" style="margin-top:8px;color:var(--green)">${ico('check')} Полное соответствие заказу ${order.id}</div>`:''}
        <div class="cc-foot">
          <span>${ico('puzzle')}${c.sims} ${plural(c.sims,'кейс','кейса','кейсов')}</span>
          <span>${ico('pin')}${c.city}</span>
          <span><span class="status-dot" style="background:${st[0]}"></span>${st[1]}</span>
        </div>
        ${c.id===0?`<div class="sd" style="margin-top:8px">${ico('check')} ${practiceHours(myPractice())} ч практики в ${myPractice().company} · подтверждено ментором</div>`:''}
        ${open
          ? `<button class="btn btn-ghost btn-sm" style="margin-top:10px" onclick="openTalent(${c.id})">Открыть профиль и контакты →</button>`
          : `<button class="btn btn-primary btn-sm" style="margin-top:10px" onclick="talentUnlock(${c.id})">${ico('card')} Разблокировать контакты</button>`}
      </div>`;}).join('')}
  </div>
  <div class="sd" style="margin-top:14px">MOCK: пейволл имитирован, оплата и передача контактов не происходят.</div>`;
},

/* ============================================================
   TASKS — компания/ментор: список с воронкой, создание, проверка
   ============================================================ */
"company:tasks":()=>{
  const list=tasksVisible().filter(t=>t.companyId===0); // демо: кабинет компании Uzum (id 0)
  const fn={open:0,applied:0,in_progress:0,submitted:0,closed:0};
  list.forEach(t=>{
    if(t.status==='open') fn.open++;
    fn.applied+=t.applicants.length;
    if(t.status==='in_progress') fn.in_progress++;
    if(t.status==='submitted') fn.submitted++;
    if(['accepted','rejected'].includes(t.status)) fn.closed++;
  });
  return ph("Задачи","Микрозадачи под ваш кадровый заказ — тест кандидата или учебный проект",`<button class="btn btn-primary btn-sm" onclick="go('company:task-new')">＋ Новая задача</button>`)+`
  <div class="tk-funnel">
    <div class="tk-fcell"><b>${fn.open}</b><span>открыто</span></div>
    <div class="tk-fcell"><b>${fn.applied}</b><span>откликов</span></div>
    <div class="tk-fcell"><b>${fn.in_progress}</b><span>в работе</span></div>
    <div class="tk-fcell"><b>${fn.submitted}</b><span>на проверке</span></div>
    <div class="tk-fcell"><b>${fn.closed}</b><span>закрыто</span></div>
  </div>
  ${list.length?`<div class="cards">${list.map(t=>{
    const ts=TASK_STATUS[t.status],tt=TASK_TYPE[t.type];
    return `<div class="tk-card" onclick="openTaskReview('${t.id}')">
      <div class="tk-card-h"><div class="tk-card-t">${t.title}</div><span class="badge ${ts[0]}">${ts[1]}</span></div>
      <div class="tk-card-meta">${tt[1]}${t.htdOrderId?' · заказ '+t.htdOrderId:' · standalone'} · ${t.applicants.length} откл.</div>
      <div class="tk-skills">${t.skills.map(s=>`<span class="tk-skill">${s}</span>`).join('')}</div>
      <div class="tk-card-foot"><span class="${taskOverdue(t)?'tk-over':''}">${ico('calendar')} ${t.deadline}${taskOverdue(t)?' · просрочено':''}</span><span>${t.status==='submitted'?'проверить →':t.status==='open'?'назначить →':'открыть →'}</span></div>
    </div>`;}).join('')}</div>`
  :emptyState('list','Задач пока нет','Создайте первую задачу под кадровый заказ: студенты выполнят её, а ментор оценит. Результат попадёт в паспорт и витрину.',{label:'＋ Новая задача',onclick:"go('company:task-new')"})}`;
},
"company:task-new":()=>{
  return back('tasks','К задачам')+ph("Новая задача","Форма создания — MOCK, реальной публикации нет")+`
  <div class="panel" style="max-width:640px">
    <div class="field" style="margin-top:4px"><label>Название</label><input placeholder="Напр. SQL-выгрузка топ-категорий"></div>
    <div class="field"><label>Описание</label><textarea rows="3" placeholder="Что нужно сделать, формат результата…"></textarea></div>
    <div class="field"><label>Привязка к HTD-заказу (опционально)</label>
      <select><option value="">Без привязки (standalone)</option>${HTD_ORDERS.map(o=>`<option>${o.id} · ${o.role}</option>`).join('')}</select></div>
    <div class="field"><label>Навыки (через запятую)</label><input placeholder="SQL, Аналитика данных"></div>
    <div class="split">
      <div class="field"><label>Тип</label><select><option value="project">Учебный проект</option><option value="test">Тест кандидата</option></select></div>
      <div class="field"><label>Дедлайн (дней от сегодня)</label><input type="number" value="10" min="1"></div>
    </div>
    <div class="field"><label>Оплата</label><select><option value="none">Без оплаты</option><option value="stipend">Стипендия по договору практики (вне платформы)</option></select></div>
    <div class="sd" style="margin:2px 0 14px">${ico('alert')} Платформа денег не держит. Оплата — только через договор практики, вне Z2H.</div>
    <button class="btn btn-primary" onclick="toast('Задача создана (демо) — публикация не происходит');go('company:tasks')">Опубликовать задачу</button>
  </div>`;
},
"company:task-review":()=>{
  const t=taskById(state._taskReview); if(!t) return back('tasks','К задачам')+ph("Проверка","Задача не выбрана");
  const ts=TASK_STATUS[t.status],tt=TASK_TYPE[t.type];
  // назначение исполнителя (open + есть отклики)
  if(t.status==='open'){
    return back('tasks','К задачам')+ph(t.title,`${tt[1]} · выбор исполнителя`)+`
    <div class="panel" style="margin-bottom:16px"><p style="line-height:1.6">${t.description}</p></div>
    <div class="panel"><h3>Откликнувшиеся</h3>
    ${t.applicants.length?`<div class="sd" style="margin-bottom:10px">Назначьте исполнителя — задача перейдёт «в работу».</div>
      ${t.applicants.map(sid=>`<div class="set-row"><div class="st">${sid===MY_STUDENT_ID?'Анна Каримова':sid}</div><button class="btn btn-primary btn-sm" style="width:auto" onclick="taskAssign('${t.id}','${sid}')">Назначить</button></div>`).join('')}`
      :emptyState('users','Откликов пока нет','Как только студенты откликнутся, вы сможете назначить исполнителя.')}
    </div>`;
  }
  // проверка сданной работы
  if(t.status==='submitted'){
    const h=state._tkHard||0, s=state._tkSoft||0;
    return back('tasks','К задачам')+ph(t.title,`${tt[1]} · проверка работы`)+`
    <div class="tk-review-box"><div class="st" style="margin-bottom:6px">Решение исполнителя</div>
      <p style="line-height:1.6">${t.submission.text}</p>
      <div class="sd" style="margin-top:8px">Вложения: ${t.submission.attachments.join(', ')} · сдано ${t.submission.submittedAt}</div>
    </div>
    <div class="panel"><h3>Оценка</h3>
      <div class="tk-score"><label>Hard skills</label><div class="tk-score-btns">${[1,2,3,4,5].map(n=>`<button class="${h===n?'on':''}" onclick="setTaskScore('hard',${n})">${n}</button>`).join('')}</div></div>
      <div class="tk-score"><label>Soft skills</label><div class="tk-score-btns">${[1,2,3,4,5].map(n=>`<button class="${s===n?'on':''}" onclick="setTaskScore('soft',${n})">${n}</button>`).join('')}</div></div>
      <div class="field" style="margin:8px 0"><textarea id="tk-rev-c" rows="3" placeholder="Комментарий ментора…"></textarea></div>
      <div style="display:flex;gap:10px;flex-wrap:wrap">
        <button class="btn btn-primary btn-sm" style="width:auto" onclick="submitTaskReview('${t.id}','accepted')">${ico('check')} Принять</button>
        <button class="btn btn-ghost btn-sm" style="width:auto" onclick="submitTaskReview('${t.id}','rework')">Вернуть на доработку</button>
        <button class="btn btn-danger btn-sm" style="width:auto" onclick="submitTaskReview('${t.id}','rejected')">Отклонить</button>
      </div>
      <div class="sd" style="margin-top:10px">Принятие запишет навыки в паспорт студента и обновит витрину${t.htdOrderId?', а также воронку заказа '+t.htdOrderId:''}.</div>
    </div>`;
  }
  // уже завершённые / в работе
  return back('tasks','К задачам')+ph(t.title,`${tt[1]} · ${ts[1]}`)+`
  <div class="panel" style="margin-bottom:16px"><div class="tk-badges" style="margin-bottom:10px"><span class="badge ${ts[0]}">${ts[1]}</span>${taskOverdue(t)?`<span class="badge b-red">просрочено</span>`:''}</div><p style="line-height:1.6">${t.description}</p></div>
  ${t.submission?`<div class="tk-review-box"><div class="st">Решение</div><p style="line-height:1.6;margin-top:6px">${t.submission.text}</p></div>`:''}
  ${t.review?`<div class="panel"><h3>Оценка ментора</h3><div class="sd" style="margin:6px 0">${t.review.mentorId} · hard ${t.review.scores.hard}/5 · soft ${t.review.scores.soft}/5</div><p style="line-height:1.6">${t.review.comment}</p></div>`:`<div class="sd">Задача «${ts[1]}» — на этом этапе действий проверки нет.</div>`}`;
},

/* TASKS — вуз: сводка (только чтение), сигнал к KPI */
"university:tasks":()=>{
  const all=tasksVisible();
  const accepted=all.filter(t=>t.status==='accepted');
  const inWork=all.filter(t=>['in_progress','submitted'].includes(t.status));
  const skills=[...new Set(accepted.flatMap(t=>t.skills))];
  return ph("Задачи студентов","Мониторинг участия в задачах компаний — дополнительный сигнал к KPI")+`
  <div class="cards" style="margin-bottom:16px">
    <div class="simcard"><div class="sc-t" style="font-size:26px">${inWork.length}</div><div class="sc-meta">задач в работе у студентов</div></div>
    <div class="simcard"><div class="sc-t" style="font-size:26px">${accepted.length}</div><div class="sc-meta">задач принято компаниями</div></div>
    <div class="simcard"><div class="sc-t" style="font-size:26px">${skills.length}</div><div class="sc-meta">навыков подтверждено</div></div>
  </div>
  ${accepted.length?`<div class="panel" style="padding:0;overflow:hidden"><table class="tbl">
    <thead><tr><th>Задача</th><th>Компания</th><th>Навыки</th><th>Оценка</th></tr></thead>
    <tbody>${accepted.map(t=>`<tr><td class="nm">${t.title}</td><td>${taskCompany(t)}</td><td>${t.skills.join(', ')}</td><td>${t.review?`${t.review.scores.hard}+${t.review.scores.soft}/10`:'—'}</td></tr>`).join('')}</tbody>
  </table></div>
  <div class="sd" style="margin-top:12px">Принятые задачи усиливают паспорт навыков студентов и учитываются как сигнал трудоустройства в KPI деканата. Демо-данные, только чтение.</div>`
  :emptyState('list','Пока нет принятых задач','Когда студенты вуза начнут выполнять и сдавать задачи компаний, здесь появится сводка навыков и результатов.')}`;
},
/* TASKS — админ: модерация (скрыть/вернуть) */
"admin:tasks":()=>{
  return ph("Модерация задач","Скрытие задач с публикации — MOCK, как у banked-вакансий",`<span class="badge b-gray">${TASKS.length} задач всего</span>`)+
  (TASKS.length?`<div class="panel" style="padding:0;overflow:hidden"><table class="tbl">
    <thead><tr><th>ID</th><th>Задача</th><th>Компания</th><th>Статус</th><th>Публикация</th><th></th></tr></thead>
    <tbody>${TASKS.map(t=>{const ts=TASK_STATUS[t.status];const hidden=!!TASK_HIDDEN[t.id];return `
      <tr><td class="mono">${t.id}</td><td class="nm">${t.title}</td><td>${taskCompany(t)}</td>
      <td><span class="badge ${ts[0]}">${ts[1]}</span></td>
      <td>${hidden?`<span class="badge b-red">Скрыта</span>`:`<span class="badge b-green">Опубликована</span>`}</td>
      <td><button class="btn btn-ghost btn-sm" style="width:auto;padding:4px 12px" onclick="toggleTaskHidden('${t.id}')">${hidden?'Вернуть':'Скрыть'}</button></td></tr>`;}).join('')}</tbody>
  </table></div>`
  :emptyState('list','Задач нет','Опубликованные компаниями задачи появятся здесь для модерации.'));
},

"forbidden":()=>`<div class="empty" style="padding:90px 20px">
    <div class="ei">${ico('ban')}</div>
    <h3>Доступ запрещён</h3>
    <p style="max-width:360px;margin:0 auto 18px">Этот раздел доступен другой роли. Вернитесь на обзор своего кабинета.</p>
    <button class="btn btn-primary btn-sm" style="width:auto;margin:0 auto" onclick="go('home')">← На обзор</button>
  </div>`,

/* ============================================================
   ПАСПОРТ НАВЫКОВ [FEATURES.skills_passport]
   Показывает, откуда каждый навык подтверждён. Верифицированные —
   те, что видит работодатель в витрине талантов.
   ============================================================ */
"student:orders":()=>{
  const orders=HTD_ORDERS;
  return ph("Заказы на кадры","Компании ищут специалистов под конкретные требования. Ваш % соответствия и что дообучить — рядом.")+
  (orders.length?`<div class="cards">${orders.map((o,i)=>{
    const m=myMatchForOrder(o);
    const cls=m.score>=80?'ms-hi':m.score>=50?'ms-mid':'ms-lo';
    return `<div class="ms-card" onclick="openStudentOrder(${i})">
      <div class="ms-card-h">
        <div><div class="ms-card-t">${o.role}</div><div class="ms-card-meta">${o.company} · ${o.id} · ${o.count} мест</div></div>
        <div class="ms-ring ${cls}"><b>${m.score}%</b><span>match</span></div>
      </div>
      <div class="ms-skills">${o.skills.map(s=>{const has=m.covered.includes(s);const half=m.half.includes(s);return `<span class="ms-chip ${has?'ms-ok':half?'ms-half':'ms-gap'}">${has?ico('check'):''}${s}</span>`;}).join('')}</div>
      <div class="ms-expl">${m.gap.length?`Покрыто ${m.coveredCount} из ${m.total}. Дообучить: <b>${m.gap.join(', ')}</b>`:`Полное соответствие — вы готовы к этому заказу`}</div>
    </div>`;}).join('')}</div>`
  :emptyState('puzzle','Открытых заказов нет','Компании пока не разместили заказы под ваши навыки. Загляните позже.'));
},
"student:order-detail":()=>{
  const o=HTD_ORDERS[state._sOrder]; if(!o) return ph("Заказ","Не найден");
  const m=myMatchForOrder(o);
  const cls=m.score>=80?'ms-hi':m.score>=50?'ms-mid':'ms-lo';
  return back('orders','Заказы')+ph(o.role,`${o.company} · ${o.id} · ${o.count} мест · срок ${o.deadline}`)+`
  <div class="panel ms-detail" style="margin-bottom:16px">
    <div class="row" style="align-items:center">
      <div><h3 style="margin:0">Ваше соответствие</h3><div class="sd">Считается прозрачно: verified-навык = полный вес, заявленный = половина, отсутствует = 0</div></div>
      <div class="ms-ring ms-ring-lg ${cls}"><b>${m.score}%</b><span>match</span></div>
    </div>
    <div class="ms-bars" style="margin-top:14px">
      ${o.skills.map(s=>{const has=m.covered.includes(s);const half=m.half.includes(s);return `
        <div class="ms-bar-row"><span class="ms-bar-l">${s}</span>
          <span class="badge ${has?'b-green':half?'b-amber':'b-gray'}">${has?'подтверждён':half?'заявлен':'нет'}</span></div>`;}).join('')}
    </div>
    ${m.gap.length?`<div class="ms-gap-box">${ico('spark')} <b>Чтобы дойти до 100%:</b> дообучите ${m.gap.join(', ')}. Под этот заказ собран трек подготовки — навыки закроются на практике.</div>`:`<div class="ms-gap-box ms-gap-ok">${ico('check')} Вы полностью соответствуете требованиям. Можно откликаться.</div>`}
  </div>
  <div class="panel" style="margin-bottom:16px"><h3>Трек подготовки под заказ</h3>
    <div class="sd" style="margin-bottom:10px">${o.track} · навыки под требования компании (не курс — подготовка под конкретный заказ)</div>
    <div class="tk-portf">${(o.modules||[]).map((mod,idx)=>`<div class="tk-portf-item">${idx+1}. ${mod}</div>`).join('')}</div>
  </div>
  <button class="btn btn-primary" onclick="go('track')">${m.gap.length?'Записаться на трек подготовки':'Перейти к треку'}</button>`;
},
"student:track":()=>{
  const t=myTrack();
  const o=t.order;
  const gapSkills=myMatchForOrder(o).gap;
  return ph("Мой трек подготовки",`Под заказ ${o.company} · ${o.role} — навыки под требования, не курс`,`<button class="btn btn-ghost btn-sm" onclick="go('orders')">${ico('target')} К заказам</button>`)+`
  <div class="panel" style="margin-bottom:16px">
    <div class="row" style="align-items:center">
      <div><div class="st">Прогресс по треку</div><div class="sd">${t.doneN} из ${t.total} модулей · ${o.track} · демо</div></div>
      <div style="font-family:var(--disp);font-weight:800;font-size:26px">${t.percent}%</div>
    </div>
    <div class="progress" style="margin-top:10px"><i style="width:${t.percent}%"></i></div>
  </div>
  <div class="panel" style="margin-bottom:16px"><h3>Модули трека</h3>
    <div class="trk-mods" style="margin-top:10px">
      ${t.modules.map((m,i)=>`<div class="trk-mod ${m.done?'done':m.current?'cur':''}">
        <div class="trk-mod-ic">${m.done?ico('check'):m.current?`<span class="trk-dot"></span>`:i+1}</div>
        <div style="flex:1"><div class="trk-mod-t">${m.title}</div><div class="sd">${m.done?'пройдено':m.current?'сейчас в работе':'впереди'}</div></div>
        ${m.current?`<button class="btn btn-primary btn-sm" style="width:auto" onclick="toast('Продолжение модуля — в демо недоступно')">Продолжить</button>`:''}
      </div>`).join('')}
    </div>
  </div>
  <div class="panel" style="margin-bottom:16px"><h3>Навыки под заказ</h3>
    <div class="sd" style="margin-bottom:10px">Трек закрывает требования заказа ${o.id}. Пройденные модули подтверждают навыки в паспорте.</div>
    <div class="ms-bars">
      ${o.skills.map(s=>{const closed=!gapSkills.includes(s);return `
        <div class="ms-bar-row"><span class="ms-bar-l">${s}</span><span class="badge ${closed?'b-green':'b-amber'}">${closed?'закрыт':'в процессе'}</span></div>`;}).join('')}
    </div>
  </div>
  ${t.percent<100?`<div class="ms-gap-box">${ico('spark')} Осталось ${t.total-t.doneN} ${plural(t.total-t.doneN,'модуль','модуля','модулей')} до завершения трека. После защиты навыки станут верифицированными и вы попадёте в витрину для работодателя.</div>`:`<div class="ms-gap-box ms-gap-ok">${ico('check')} Трек пройден — навыки подтверждены, вы в витрине талантов.</div>`}`;
},
"student:passport":()=>{
  const sp=skillsPassport();
  const verified=sp.skills.filter(s=>SKILL_SOURCE[s.source].verified);
  return ph("Паспорт навыков",`Навыки подтверждаются практикой, симуляциями и обучением — не просто заявлены`,`<button class="btn btn-ghost btn-sm" onclick="go('talent-showcase')">${ico('trophy')} Как видит работодатель</button>`)+`
  <div class="cards" style="margin-bottom:16px">
    <div class="simcard"><div class="sc-t" style="font-size:26px">${verified.length}<span style="font-size:15px;color:var(--muted)">/${sp.skills.length}</span></div><div class="sc-meta">навыков верифицировано</div></div>
    <div class="simcard"><div class="sc-t" style="font-size:26px">${sp.hrs}<span style="font-size:15px;color:var(--muted)"> ч</span></div><div class="sc-meta">практики в ${sp.company}</div></div>
    <div class="simcard"><div class="sc-t" style="font-size:26px">${sp.mentorGrade}%</div><div class="sc-meta">оценка ментора</div></div>
  </div>
  <div class="ai-note" style="margin-bottom:16px">${ico('alert')}<span>Верифицированные навыки видны работодателям в <b>витрине талантов</b>. Заявленные (только диагностика) — нет, пока не подтвердите их практикой или кейсом. Демо-данные.</span></div>
  <div class="panel">
    ${sp.skills.map(s=>{const src=SKILL_SOURCE[s.source];return `
      <div class="set-row" style="align-items:flex-start">
        <div style="flex:1">
          <div style="display:flex;align-items:center;gap:8px;margin-bottom:4px">
            <span class="st">${s.name}</span>
            ${src.verified?`<span class="pf-verified" style="padding:2px 8px">${ico('check')} ${src.label}</span>`:`<span class="badge b-gray">${src.label}</span>`}
          </div>
          <div class="progress" style="max-width:280px"><i style="width:${s.level}%"></i></div>
          <div class="sd" style="margin-top:5px">${s.evidence}</div>
        </div>
        <div style="font-family:var(--disp);font-weight:800;font-size:18px;width:44px;text-align:right">${s.level}%</div>
      </div>`;}).join('')}
  </div>
  <div class="sd" style="margin-top:14px">Источники: ${Object.values(SKILL_SOURCE).map(s=>`${s.label} — ${s.note}`).join(' · ')}</div>`;
},

/* ============================================================
   TASKS — студент: лента открытых задач, карточка, мои задачи
   ============================================================ */
"student:tasks":()=>{
  const f=state._taskFilter||{};
  let list=tasksForStudentFeed();
  if(f.type) list=list.filter(t=>t.type===f.type);
  if(f.skill) list=list.filter(t=>t.skills.includes(f.skill));
  if(f.company) list=list.filter(t=>String(t.companyId)===f.company);
  const allSkills=[...new Set(tasksForStudentFeed().flatMap(t=>t.skills))];
  const allCos=[...new Set(tasksForStudentFeed().map(t=>t.companyId))];
  return ph("Задачи","Реальные микрозадачи компаний — опыт и навыки в паспорт, не просто халтура",`<button class="btn btn-ghost btn-sm" onclick="go('my-tasks')">${ico('list')} Мои задачи</button>`)+`
  <div class="tk-filters">
    <select onchange="setTaskFilter('type',this.value)"><option value="">Все типы</option><option value="test"${f.type==='test'?' selected':''}>Тест кандидата</option><option value="project"${f.type==='project'?' selected':''}>Учебный проект</option></select>
    <select onchange="setTaskFilter('skill',this.value)"><option value="">Все навыки</option>${allSkills.map(s=>`<option value="${s}"${f.skill===s?' selected':''}>${s}</option>`).join('')}</select>
    <select onchange="setTaskFilter('company',this.value)"><option value="">Все компании</option>${allCos.map(c=>`<option value="${c}"${f.company===String(c)?' selected':''}>${(COMPANIES.find(x=>x.id===c)||{}).name||c}</option>`).join('')}</select>
    ${(f.type||f.skill||f.company)?`<button class="btn btn-ghost btn-sm" style="width:auto" onclick="clearTaskFilter()">Сбросить</button>`:''}
  </div>
  ${list.length?`<div class="cards">${list.map(t=>taskCard(t)).join('')}</div>`
    :emptyState('list','Открытых задач нет','Пока нет задач под ваши фильтры. Загляните позже или сбросьте фильтры — компании публикуют новые задачи под кадровые заказы.')}`;
},
"student:task-detail":()=>{
  const t=taskById(state._task); if(!t) return ph("Задача","Не найдена");
  const applied=t.applicants.includes(MY_STUDENT_ID);
  const isMine=t.assigneeId===MY_STUDENT_ID;
  const tt=TASK_TYPE[t.type], ts=TASK_STATUS[t.status];
  return back('tasks','Все задачи')+ph(t.title,`${taskCompany(t)}${t.htdOrderId?' · заказ '+t.htdOrderId:''}`)+`
  <div class="panel" style="margin-bottom:16px">
    <div class="tk-badges" style="margin-bottom:12px">
      <span class="badge ${tt[0]}">${tt[1]}</span>
      <span class="badge ${ts[0]}">${ts[1]}</span>
      ${taskOverdue(t)?`<span class="badge b-red">${ico('bell')} просрочено</span>`:''}
    </div>
    <p style="line-height:1.6;margin-bottom:14px">${t.description}</p>
    <div class="set-row"><div class="st">Тип</div><div>${tt[1]}</div></div>
    <div class="set-row"><div class="st">Дедлайн</div><div class="${taskOverdue(t)?'tk-over':''}">${t.deadline}</div></div>
    <div class="set-row"><div class="st">Что даёт</div><div>Навыки в паспорт: ${t.skills.join(', ')}</div></div>
    ${taskIsPaid(t)?`<div class="set-row"><div class="st">Оплата</div><div><b>${fmtMoney(t.reward.price)}</b> · ${t.reward.note}</div></div>`:`<div class="set-row"><div class="st">Оплата</div><div>Без оплаты · опыт и портфолио</div></div>`}
  </div>
  ${FEATURES.tasks_payments && taskIsPaid(t)?`<div class="panel tk-escrow" style="margin-bottom:16px">
    <div class="row" style="align-items:center;margin-bottom:8px"><h3 style="margin:0">${ico('card')} Безопасная сделка</h3><span class="badge ${ESCROW_STATUS[t.payment.escrow][0]}">${ESCROW_STATUS[t.payment.escrow][1]}</span></div>
    <div class="tk-escrow-steps">
      <div class="tk-es ${['held','released'].includes(t.payment.escrow)?'done':''}">Заморозка</div>
      <div class="tk-es ${t.payment.escrow==='released'?'done':''}">Работа</div>
      <div class="tk-es ${t.payment.escrow==='released'?'done':''}">Выплата</div>
    </div>
    <div class="sd" style="margin-top:10px">${
      t.payment.escrow==='held'?`Сумма ${fmtMoney(t.payment.amount)} условно заморожена. Будет выплачена исполнителю после приёмки работы.`
      :t.payment.escrow==='released'?`Выплачено исполнителю: ${fmtMoney(t.payment.amount)}.`
      :t.payment.escrow==='disputed'?`Открыт спор — сумма удержана до решения арбитража.`
      :t.payment.escrow==='refunded'?`Средства возвращены заказчику (работа не принята).`
      :`Оплата замораживается при назначении исполнителя.`
    }</div>
    <div class="sd" style="margin-top:8px;color:var(--faint)">${ico('alert')} Демонстрация контура оплаты. Платформа <b>не проводит реальных денег</b>: для продакшена нужен внешний провайдер (Payme/Click) и юридическая лицензия. Фактическая оплата — по договору практики, вне Z2H.</div>
    ${t.payment.escrow==='held'&&t.assigneeId===MY_STUDENT_ID?`<button class="btn btn-ghost btn-sm" style="width:auto;margin-top:10px" onclick="escrowDispute('${t.id}')">Открыть спор</button>`:''}
  </div>`:''}
  <div class="panel" style="margin-bottom:16px"><h3>Требуемые навыки</h3>
    <div class="tk-skills" style="margin-top:10px">${t.skills.map(s=>`<span class="tk-skill">${s}</span>`).join('')}</div>
  </div>
  ${isMine&&t.status==='in_progress'?`<div class="panel"><h3>Сдать работу</h3>
    <div class="sd" style="margin-bottom:10px">Вы назначены исполнителем. Опишите решение и приложите файлы (заглушка).</div>
    <div class="field"><textarea id="tk-sub" rows="4" placeholder="Опишите решение…"></textarea></div>
    <button class="btn btn-primary btn-sm" onclick="taskSubmit('${t.id}',document.getElementById('tk-sub').value)">${ico('spark')} Отправить на проверку</button>
  </div>`
  :isMine&&t.status==='submitted'?`<div class="panel">${emptyState('clock','Работа на проверке','Ментор компании проверит решение и выставит оценку. Результат появится в «Моих задачах».')}</div>`
  :isMine&&t.status==='accepted'?`<div class="panel"><h3>${ico('check')} Задача принята</h3><div class="sd">Навыки добавлены в паспорт. ${t.review?`Оценка: hard ${t.review.scores.hard}/5, soft ${t.review.scores.soft}/5. «${t.review.comment}»`:''}</div></div>`
  :t.status==='open'&&!applied?`<button class="btn btn-primary" onclick="taskApply('${t.id}')">Откликнуться на задачу</button>`
  :t.status==='open'&&applied?`<div class="panel">${emptyState('check','Отклик отправлен','Компания рассмотрит отклик и назначит исполнителя. Следите за статусом в «Моих задачах».')}</div>`
  :`<div class="sd">Статус: ${ts[1]}. Действия недоступны на этом этапе.</div>`}`;
},
"student:my-tasks":()=>{
  const list=myTasks();
  return ph("Мои задания","Задания, на которые вы откликнулись или которые выполняете",`<button class="btn btn-ghost btn-sm" onclick="go('freelancer')">${ico('user')} Мой профиль исполнителя</button>`)+
  (list.length?`<div class="cards">${list.map(t=>{
    const ts=TASK_STATUS[t.status];const over=taskOverdue(t);
    const soon=!over && t.deadline<dOffset(3) && !['accepted','rejected'].includes(t.status);
    return `<div class="tk-card" onclick="openTask('${t.id}')">
      <div class="tk-card-h"><div class="tk-card-t">${t.title}</div><span class="badge ${ts[0]}">${ts[1]}</span></div>
      <div class="tk-card-meta">${taskCompany(t)}${t.htdOrderId?' · '+t.htdOrderId:''}${taskIsPaid(t)?' · '+fmtMoney(t.reward.price):''}</div>
      <div class="tk-card-foot"><span class="${over?'tk-over':''}">${ico('calendar')} ${t.deadline}${over?' · просрочено':soon?' · скоро дедлайн':''}</span><span>${t.status==='accepted'&&t.review?`оценка ${t.review.scores.hard}+${t.review.scores.soft}/10`:'подробнее →'}</span></div>
    </div>`;}).join('')}</div>`
  :emptyState('list','Вы пока не брали заданий','Откликнитесь на задание из ленты фриланса — оно появится здесь с текущим статусом и дедлайном.',{label:'К ленте фриланса',onclick:"go('tasks')"}));
},
/* ============================================================
   FREELANCE — каталог исполнителей (Fiverr-стиль) и профиль
   ============================================================ */
"student:freelancers":()=>freelancersPage('student'),
"company:freelancers":()=>freelancersPage('company'),
"student:freelancer":()=>{ state._freelancer=state._freelancer||MY_STUDENT_ID; return freelancerPage(); },
"company:freelancer":()=>freelancerPage(),

/* ============================================================
   РОЛЬ МЕНТОРА — узкий доступ: подтверждение часов и оценки.
   Ментор компании видит только своих практикантов.
   ============================================================ */
"mentor:home":()=>{
  const list=mentorPractices();
  const pending=mentorPendingEntries().length;
  return `<div class="onb-banner" style="margin-bottom:18px"><h2>${ico('check')} Кабинет ментора</h2><p>${CURRENT_MENTOR} · ${list.length} ${plural(list.length,'практикант','практиканта','практикантов')}${pending?` · ${pending} на проверку`:''} · демо</p></div>`+`
  ${pending?`<div class="ai-note" style="margin-bottom:16px">${ico('alert')}<span>У вас <b>${pending}</b> ${plural(pending,'запись','записи','записей')} на проверку. Подтвердите часы, чтобы студент получил зачёт.</span> <button class="btn btn-primary btn-sm" style="width:auto;margin-left:auto" onclick="go('review')">Проверить →</button></div>`:''}
  <div class="cards">
    ${list.length?list.map(p=>{const hrs=practiceHours(p);const pct=Math.min(100,Math.round(hrs/p.goalHours*100));const pend=p.entries.filter(e=>e.status==='submitted'||e.status==='overdue').length;return `
      <div class="simcard" onclick="openMentorStudent('${p.id}')">
        <div class="row" style="align-items:center"><div class="sc-t">${p.student}</div>${pend?`<span class="badge b-amber">${pend} на проверку</span>`:`<span class="badge b-green">${ico('check')} всё сдано</span>`}</div>
        <div class="sc-meta">${p.company} · ${p.role} · ${p.faculty}</div>
        <div style="margin-top:10px"><div class="row"><span class="sd">${hrs} из ${p.goalHours} ч</span><span class="sd">${pct}%</span></div><div class="progress" style="margin-top:5px"><i style="width:${pct}%"></i></div></div>
      </div>`;}).join(''):emptyState('users','Пока нет практикантов','Компания ещё не закрепила за вами студентов. Когда договор практики подпишут, практикант появится здесь.')}
  </div>`;
},
"mentor:review":()=>{
  const pending=mentorPendingEntries();
  if(!pending.length) return ph("На проверку","Записи практикантов, ожидающие подтверждения")+emptyState('check','Всё проверено','Нет записей, ожидающих подтверждения. Практиканты получат зачёт за подтверждённые часы.');
  return ph("На проверку",`${pending.length} ${plural(pending.length,'запись','записи','записей')} ждёт подтверждения часов`)+`
  <div class="cards">
    ${pending.map(({p,e,i})=>`
      <div class="simcard" style="cursor:default">
        <div class="row" style="align-items:center"><div class="sc-t">${p.student} · неделя ${e.week}</div>${e.status==='overdue'?`<span class="badge b-red">просрочено</span>`:`<span class="badge b-amber">на проверке</span>`}</div>
        <div class="sc-meta">${e.date} · ${e.hours} ч · ${p.company}</div>
        <p style="margin:10px 0;line-height:1.5">${e.task}</p>
        <div style="display:flex;gap:8px;flex-wrap:wrap;align-items:center">
          <span class="sd">Оценка:</span>
          ${['A','B','C'].map(g=>`<button class="btn btn-ghost btn-sm" style="width:auto;padding:6px 14px" onclick="mentorApprove('${p.id}',${i},'${g}')">${g}</button>`).join('')}
          <button class="btn btn-primary btn-sm" style="width:auto;margin-left:auto" onclick="mentorApprove('${p.id}',${i},null)">${ico('check')} Подтвердить часы</button>
        </div>
      </div>`).join('')}
  </div>
  <div class="sd" style="margin-top:12px">MOCK: подтверждение меняет статус записи в демо-модели, реального уведомления студенту нет.</div>`;
},
"mentor-student":()=>{
  const p=PRACTICE.find(x=>x.id===state._mentorStudent)||mentorPractices()[0];
  if(!p) return ph("Практикант","Нет данных");
  const hrs=practiceHours(p);const pct=Math.min(100,Math.round(hrs/p.goalHours*100));
  return back('home','Мои практиканты')+ph(p.student,`${p.company} · ${p.role} · ${p.faculty}`)+`
  <div class="panel" style="margin-bottom:16px">
    <div class="set-row"><div class="st">Подтверждено часов</div><div>${hrs} из ${p.goalHours} ч</div></div>
    <div class="progress" style="margin-top:8px"><i style="width:${pct}%"></i></div>
  </div>
  ${p.entries.length?practiceSchedule(p):''}
  <div class="panel" style="padding:0;overflow:hidden;margin-bottom:16px"><table class="tbl">
    <thead><tr><th>Неделя</th><th>Дата</th><th>Часы</th><th>Задачи</th><th>Статус</th></tr></thead>
    <tbody>
    ${p.entries.map((e,i)=>`<tr><td class="nm">Неделя ${e.week}</td><td>${e.date}</td><td>${e.hours||'—'}</td><td>${e.task}</td>
      <td>${(e.status==='submitted'||e.status==='overdue')?`<button class="btn btn-primary btn-sm" style="width:auto;padding:4px 12px" onclick="mentorApprove('${p.id}',${i},null)">Подтвердить</button>`:diaryBadge(e)}</td></tr>`).join('')}
    </tbody>
  </table></div>
  ${practiceThread(p)}`;
},

/* ============================================================
   РЕЕСТРЫ ПАРТНЁРОВ [связь сторон договора]
   Вуз выбирает компанию, компания выбирает вуз.
   ============================================================ */
"university:partners":()=>{
  const active=PARTNER_COMPANIES.filter(c=>c.status==='active').length;
  return ph("Компании-партнёры","Базы практики для ваших студентов — стороны договора",`<button class="btn btn-primary btn-sm" onclick="toast('Приглашение компании — в демо недоступно')">＋ Пригласить компанию</button>`)+`
  <div class="cards" style="margin-bottom:16px">
    <div class="simcard"><div class="sc-t" style="font-size:26px">${active}</div><div class="sc-meta">активных партнёров</div></div>
    <div class="simcard"><div class="sc-t" style="font-size:26px">${PRACTICE.length}</div><div class="sc-meta">совместных практик</div></div>
    <div class="simcard"><div class="sc-t" style="font-size:26px">${PARTNER_COMPANIES.length}</div><div class="sc-meta">компаний в реестре</div></div>
  </div>
  <div class="panel" style="padding:0;overflow:hidden">
    <table class="tbl">
      <thead><tr><th>Компания</th><th>Сфера</th><th>Город</th><th>Практик</th><th>Статус</th><th></th></tr></thead>
      <tbody>
      ${PARTNER_COMPANIES.map(c=>{const st=PARTNER_STATUS[c.status];const np=companyPractices(c.name);return `
        <tr>
          <td class="nm">${c.name}</td><td>${c.field}</td><td>${c.city}</td><td>${np||'—'}</td>
          <td><span class="badge ${st[0]}">${st[1]}</span></td>
          <td>${c.status==='active'?`<button class="btn btn-ghost btn-sm" style="width:auto;padding:4px 12px" onclick="toast('Новый договор с ${c.name} — в демо недоступен')">Договор</button>`:c.status==='invited'?`<span class="sd">ожидает ответа</span>`:''}</td>
        </tr>`;}).join('')}
      </tbody>
    </table>
  </div>
  <div class="sd" style="margin-top:12px">Из этого реестра вуз выбирает компанию при создании договора практики. Демо-данные.</div>`;
},
"university:career-sync":()=>{
  const recs=careerEduRecords();
  const synced=recs.filter(r=>r.synced).length;
  return ph("Синхронизация с career.edu.uz","Обязательные данные уходят в госплатформу автоматически")+`
  <div class="panel ce-hero" style="margin-bottom:16px">
    <div class="row" style="align-items:flex-start;gap:12px">
      <div class="ce-ic">${ico('globe')}</div>
      <div style="flex:1">
        <h3 style="margin:0 0 4px">Z2H дополняет career.edu.uz, а не заменяет её</h3>
        <div class="sd">career.edu.uz помогает найти работу и обязательна по постановлению. Z2H доводит студента до работодателя — практика, договор, KPI — и <b>отдаёт обязательные данные в госсистему</b>. Вуз не ведёт два учёта: заполняет у нас, госплатформа получает автоматически.</div>
      </div>
    </div>
  </div>
  <div class="cards" style="margin-bottom:16px">
    <div class="simcard"><div class="sc-t" style="font-size:26px">${synced}</div><div class="sc-meta">записей выгружено</div></div>
    <div class="simcard"><div class="sc-t" style="font-size:26px">${recs.length-synced}</div><div class="sc-meta">ожидают выгрузки</div></div>
    <div class="simcard"><div class="sc-t" style="font-size:15px;padding-top:6px">${CAREER_EDU_SYNC.lastSyncedAt}</div><div class="sc-meta">последняя синхронизация</div></div>
  </div>
  <div class="panel" style="margin-bottom:16px">
    <div class="row" style="align-items:center;margin-bottom:6px"><h3 style="margin:0">Записи к выгрузке</h3><button class="btn btn-primary btn-sm" style="width:auto" onclick="toast('Синхронизация запущена (демо) — реальной передачи нет')">${ico('upload')} Синхронизировать</button></div>
    <div class="sd" style="margin-bottom:10px">Данные вытекают из практик и договоров — единый источник, без двойного ввода. ДЕМО-данные.</div>
    <div class="panel" style="padding:0;overflow:hidden;border:1px solid var(--hair)"><table class="tbl">
      <thead><tr><th>Студент</th><th>Практика</th><th>Договор</th><th>Трудоустройство</th><th>Статус</th></tr></thead>
      <tbody>${recs.map(r=>`<tr>
        <td class="nm">${r.student}</td><td>${r.internship}</td><td>${r.contract}</td>
        <td>${r.employed?'да':'—'}</td>
        <td>${r.synced?`<span class="badge b-green">${ico('check')} выгружено</span>`:`<span class="badge b-gray">ожидает</span>`}</td>
      </tr>`).join('')}</tbody>
    </table></div>
  </div>
  <div class="panel" style="margin-bottom:16px"><h3>Маппинг полей</h3>
    <div class="sd" style="margin-bottom:10px">Как наши данные ложатся на поля госплатформы</div>
    <div class="panel" style="padding:0;overflow:hidden;border:1px solid var(--hair)"><table class="tbl">
      <thead><tr><th>Поле Z2H</th><th>Поле career.edu.uz</th><th>Примечание</th></tr></thead>
      <tbody>${CAREER_EDU_MAP.map(m=>`<tr><td class="nm">${m.ours}</td><td class="mono">${m.gov}</td><td class="sd">${m.note}</td></tr>`).join('')}</tbody>
    </table></div>
  </div>
  <div class="panel ce-priv"><h3>${ico('ban')} Персональные данные</h3>
    <div class="sd">Вуз не передаёт персональные данные студентов в Z2H — регистрация и хранение на стороне платформы. В госсистему уходят только обязательные учётные факты (статус практики, договор, трудоустройство), а не документы и не персональные данные.</div>
  </div>
  <div class="sd" style="margin-top:12px">MOCK-интеграция. Реальная синхронизация требует официального API career.edu.uz и, возможно, регистрации договора практики на госплатформе (постановление КМ №615) — проверить до продакшена.</div>`;
},
"university:subscription":()=>{
  const plans=[
    {name:"Базовый", price:"Бесплатно", cur:"", tag:['b-gray','Текущий'], feats:[
      ["KPI-дашборд под «Индекс качества выпускника»",true],
      ["Дневник практики и зачёт часов",true],
      ["Реестр договоров практики",true],
      ["Выгрузка в career.edu.uz",true],
      ["Расширенная аналитика по факультетам",false],
      ["Приоритетная выгрузка и API-доступ",false],
      ["Персональный менеджер и обучение команды",false],
    ]},
    {name:"Карьерный центр+", price:"12 000 000", cur:"сум/год", tag:['b-green','Расширенный'], feats:[
      ["KPI-дашборд под «Индекс качества выпускника»",true],
      ["Дневник практики и зачёт часов",true],
      ["Реестр договоров практики",true],
      ["Выгрузка в career.edu.uz",true],
      ["Расширенная аналитика по факультетам",true],
      ["Приоритетная выгрузка и API-доступ",true],
      ["Персональный менеджер и обучение команды",true],
    ]},
  ];
  return ph("Подписка вуза","Базовый функционал бесплатен. Расширенная аналитика и поддержка — по подписке.")+`
  <div class="sd" style="margin-bottom:16px;max-width:640px">Операционка практики, KPI и выгрузка в госплатформу доступны бесплатно — чтобы снять барьер входа. Подписка открывает углублённую аналитику и сопровождение. ДЕМО-данные.</div>
  <div class="split">
    ${plans.map((p,i)=>`<div class="panel sub-plan ${i===1?'sub-hl':''}">
      <div class="row" style="align-items:center"><h3 style="margin:0">${p.name}</h3><span class="badge ${p.tag[0]}">${p.tag[1]}</span></div>
      <div class="sub-price">${p.price}<span> ${p.cur}</span></div>
      <div class="sub-feats">${p.feats.map(f=>`<div class="sub-feat ${f[1]?'on':'off'}">${f[1]?ico('check'):ico('ban')} <span>${f[0]}</span></div>`).join('')}</div>
      ${i===1?`<button class="btn btn-primary btn-sm" style="margin-top:14px" onclick="toast('Оформление подписки — в демо недоступно')">Оформить подписку</button>`:`<button class="btn btn-ghost btn-sm" style="margin-top:14px" disabled>Текущий план</button>`}
    </div>`).join('')}
  </div>
  <div class="sd" style="margin-top:14px">MOCK: оплата и биллинг не подключены. Цена — демонстрационная.</div>`;
},
"company:partners":()=>{
  const active=PARTNER_UNIS.filter(u=>u.status==='active').length;
  const totalStud=PARTNER_UNIS.reduce((s,u)=>s+u.students,0);
  return ph("ВУЗы-партнёры","Источники кандидатов и стороны договора практики",`<button class="btn btn-primary btn-sm" onclick="toast('Заявка вузу — в демо недоступна')">＋ Добавить ВУЗ</button>`)+`
  <div class="cards" style="margin-bottom:16px">
    <div class="simcard"><div class="sc-t" style="font-size:26px">${active}</div><div class="sc-meta">активных ВУЗов</div></div>
    <div class="simcard"><div class="sc-t" style="font-size:26px">${totalStud}</div><div class="sc-meta">студентов в охвате</div></div>
    <div class="simcard"><div class="sc-t" style="font-size:26px">${PARTNER_UNIS.length}</div><div class="sc-meta">ВУЗов в реестре</div></div>
  </div>
  <div class="cards">
    ${PARTNER_UNIS.map(u=>{const st=PARTNER_STATUS[u.status];return `
      <div class="simcard" style="cursor:default">
        <div class="row" style="align-items:center"><div class="sc-t">${u.name}</div><span class="badge ${st[0]}">${st[1]}</span></div>
        <div class="sc-meta">${u.full}</div>
        <div class="sc-foot" style="margin-top:10px"><span class="sc-meta">${ico('users')} ${u.students} студентов</span><span class="sc-meta">${ico('pin')} ${u.city}</span></div>
      </div>`;}).join('')}
  </div>
  <div class="sd" style="margin-top:12px">Из этого реестра компания выбирает ВУЗ при создании договора практики. Демо-данные.</div>`;
},

"invite":()=>`<div class="empty" style="padding:70px 20px">
    <div class="ei">${ico('mail','stub-mail')}</div>
    <h3>Приглашение в когорту</h3>
    <p style="max-width:400px;margin:0 auto 6px">Куратор ВУЗа приглашает вас в когорту <b>«Аналитика данных · 2025»</b>.</p>
    <p style="max-width:400px;margin:0 auto 18px;font-size:12px" class="mono">/invite/a1b2c3-token</p>
    <div style="display:flex;gap:10px;justify-content:center">
      <button class="btn btn-primary btn-sm" style="width:auto" onclick="toast('Вы вступили в когорту (демо)');go('home')">Принять</button>
      <button class="btn btn-ghost btn-sm" style="width:auto" onclick="go('home')">Отклонить</button>
    </div>
  </div>`,

/* ---------- DETAIL / DYNAMIC ($id) SCREENS ---------- */
"sim-detail":()=>{
  const s=SIMS[state._sim||0];
  profileInit();
  const isDone=simDone(s.id);
  const draft=simDraft(s.id);
  const review=simReview(s.id);
  const words=countWords(draft);
  const MIN=40;

  const stage = isDone?2:(draft.trim()?1:0);
  const stages=[['Изучите бриф',0],['Напишите решение',1],['AI-разбор',2]];

  return back('simulations','Симуляции')+`
  <div class="panel" style="margin-bottom:16px">
    <div class="sim-head">
      <div class="sd-logo" style="background:${s.color}">${s.logo}</div>
      <div style="flex:1;min-width:220px">
        <h2 style="font-size:21px;font-weight:700;letter-spacing:-.02em">${s.t}</h2>
        <div style="color:var(--muted);font-size:13.5px;margin-top:3px">${s.co} · ${s.role}</div>
        <div class="s2-meta" style="margin-top:12px;margin-bottom:0">
          <span class="s2-pill">${ico('user')}${s.lvl}</span>
          <span class="s2-pill">${ico('clock')}${s.dur}</span>
          <span class="s2-pill">${ico('calendar')}до ${s.dl}</span>
          <span class="s2-pill" style="background:var(--accent-soft);color:var(--accent-ink)">${ico('spark')}+${s.xp} XP</span>
        </div>
      </div>
      <div style="flex:none">
        ${isDone
          ? `<span class="pf-verified">${ico('check')}Сдано</span>`
          : `<div class="s2-match" style="justify-content:flex-end"><div class="s2-bar"><i style="width:${matchFor(s)}%"></i></div><span class="s2-mv">${matchFor(s)}% совпадение</span></div>`}
      </div>
    </div>
    <div class="sim-steps">
      ${stages.map((st,i)=>`<div class="sim-stp ${stage>i?'ok':(stage===i?'on':'')}">
        <span class="n">${stage>i?ico('check'):(i+1)}</span>${st[0]}
      </div>${i<stages.length-1?`<div class="sim-line ${stage>i?'ok':''}"></div>`:''}`).join('')}
    </div>
  </div>

  ${review?aiReviewBlock(s,review):''}

  <div class="split">
    <div>
      <div class="panel" style="margin-bottom:16px"><h3>${ico('list')} Бриф от компании</h3>
        <p style="font-size:13.5px;color:var(--ink);line-height:1.65;margin-top:8px">${s.brief}</p></div>
      <div class="panel" style="margin-bottom:16px"><h3>${ico('data')} Что у вас есть</h3>
        <p style="font-size:13.5px;color:var(--muted);line-height:1.6;margin-top:8px">${s.data}</p></div>
      <div class="panel"><h3>${ico('check')} Что нужно сдать</h3>
        <ul style="margin:10px 0 0;padding-left:18px;font-size:13.5px;color:var(--muted);line-height:1.9">
          ${s.deliver.map(d=>`<li>${d}</li>`).join('')}</ul></div>
    </div>

    <div>
      <div class="panel" style="margin-bottom:16px;background:var(--accent-soft);border-color:transparent">
        <h3 style="color:var(--accent-ink)">${ico('user')} Совет наставника</h3>
        <p style="font-size:13.5px;color:var(--accent-ink);line-height:1.6;margin-top:8px">${s.tip}</p></div>

      <div class="panel" style="margin-bottom:16px"><h3>${ico('chart')} Как оценивают</h3><div class="ps">Веса критериев</div>
        <div style="margin-top:10px">
          ${s.rubric.map(r=>`<div class="rubric-row">
            <span class="rb-n">${r[0]}</span>
            <div class="rb-bar"><i style="width:${r[1]*2.5}%"></i></div>
            <span class="rb-w">${r[1]}%</span>
          </div>`).join('')}
        </div>
      </div>

      <div class="panel">
        <h3>${ico('doc')} Ваше решение</h3>
        <div class="ps">${isDone?'Решение отправлено — ниже разбор от AI':'Черновик сохраняется автоматически'}</div>
        <textarea class="answer-box" style="margin-top:12px" ${isDone?'readonly':''}
          placeholder="Опишите вывод, гипотезы и метрики…"
          oninput="saveSimDraft(${s.id},this.value)">${draft.replace(/</g,'&lt;')}</textarea>
        <div class="answer-meta">
          <span id="sim-words" class="${words>=MIN?'ok':'warn'}">${words} ${plural(words,'слово','слова','слов')}</span>
          <span>·</span>
          <span>${words>=MIN?'достаточно для сдачи':`минимум ${MIN} — осталось ${MIN-words}`}</span>
        </div>
        ${isDone?'':`<button class="btn btn-primary" style="width:100%;margin-top:14px" onclick="submitSim(${s.id})">
          ${ico('spark')} Сдать на AI-разбор</button>`}
        ${isDone?`<button class="btn btn-ghost" style="width:100%;margin-top:14px" onclick="resetSim(${s.id})">Пересдать</button>`:''}
      </div>
    </div>
  </div>`;
},

"student:applications":()=>{
  profileInit();
  const ids=MOCK.profile.appliedJobs||[];

  if(!ids.length) return ph("Мои отклики","Здесь появятся вакансии, на которые вы откликнулись")+`
    <div class="folio-empty">
      <div class="fe-ic">${ico('briefcase')}</div>
      <h3>Вы ещё никуда не откликались</h3>
      <p>Найдите вакансию с высоким совпадением и отправьте резюме — мы будем показывать здесь каждый этап: скрининг, интервью, оффер.</p>
      <button class="btn btn-primary" style="width:auto;margin:20px auto 0" onclick="go('jobs')">${ico('briefcase')} Смотреть вакансии</button>
    </div>`;

  const f=state._appFilter||'all';
  const sort=state._appSort||'recent';
  const q=(state._appQuery||'').toLowerCase().trim();
  const showArch=!!state._appArchived;

  let all=ids.map(id=>({job:JOBS.find(j=>j.id===id),stage:appStage(id),meta:appMeta(id),id})).filter(x=>x.job);
  const active=all.filter(x=>!x.meta.archived);
  const archived=all.filter(x=>x.meta.archived);
  const pool=showArch?archived:active;

  const stats=appStats(active.map(x=>x.id));
  const count=k=>k==='all'?pool.length:pool.filter(x=>x.stage===k).length;

  let list=f==='all'?pool.slice():pool.filter(x=>x.stage===f);
  if(q) list=list.filter(x=>(x.job.t+' '+x.job.co+' '+x.job.loc+' '+(x.meta.note||'')).toLowerCase().includes(q));

  const rank={offer:0,interview:1,screening:2,sent:3,rejected:4};
  if(sort==='recent')      list.sort((a,b)=>(b.meta.appliedAt||0)-(a.meta.appliedAt||0));
  else if(sort==='oldest') list.sort((a,b)=>(a.meta.appliedAt||0)-(b.meta.appliedAt||0));
  else if(sort==='stage')  list.sort((a,b)=>rank[a.stage]-rank[b.stage]);
  else if(sort==='match')  list.sort((a,b)=>matchFor(b.job)-matchFor(a.job));

  /* the nearest upcoming interview gets pinned to the top of the page */
  const upcoming=active.filter(x=>x.meta.interview && new Date(x.meta.interview)>Date.now())
                       .sort((a,b)=>new Date(a.meta.interview)-new Date(b.meta.interview))[0];

  return ph("Мои отклики",`${active.length} ${plural(active.length,'активный отклик','активных отклика','активных откликов')}${archived.length?` · ${archived.length} в архиве`:''}`)+`

  ${upcoming?(()=>{const cd=interviewCountdown(upcoming.meta.interview);
    return `<div class="iv-banner ${cd&&cd.soon?'soon':''}" style="margin-bottom:16px">
      <div class="iv-ic">${ico('calendar')}</div>
      <div class="iv-b">
        <div class="iv-t">Ближайшее интервью · ${upcoming.job.co}</div>
        <div class="iv-d">${fmtDateTime(upcoming.meta.interview)}${cd?` · ${cd.t}`:''}</div>
      </div>
      <button class="btn btn-primary" onclick="exportInterviewICS(${upcoming.id})">${ico('calendar')} В календарь</button>
    </div>`;})():''}

  <div class="app-stats">
    ${statCard('briefcase',stats.total,'Активных откликов','var(--blue)','var(--blue-soft)')}
    ${statCard('chat',stats.interviews,'Дошли до интервью','var(--purple)','var(--purple-soft)',null,{hint:`${stats.toInterview}% конверсия`})}
    ${statCard('trophy',stats.offers,'Офферов','var(--green)','var(--green-soft)',null,{hint:stats.offers?`${stats.toOffer}% конверсия`:'Пока ни одного'})}
    ${statCard('clock',stats.avgDays,'Дней в среднем','var(--amber)','var(--amber-soft)',null,{hint:'С момента отклика'})}
  </div>

  <div class="app-stages">
    <div class="app-stage ${f==='all'?'on':''}" style="--as-c:var(--ink)" onclick="setAppFilter('all')">
      <div class="as-d" style="background:var(--ink)"></div><div class="as-v">${pool.length}</div><div class="as-l">Все</div></div>
    ${APP_STAGES.map(st=>`<div class="app-stage ${f===st[0]?'on':''}" style="--as-c:${st[2]}" onclick="setAppFilter('${st[0]}')">
      <div class="as-d"></div><div class="as-v">${count(st[0])}</div><div class="as-l">${st[1]}</div></div>`).join('')}
  </div>

  <div class="app-toolbar">
    <div class="app-search">${ico('search')}
      <input placeholder="Поиск по вакансии, компании, заметке…" value="${(state._appQuery||'').replace(/"/g,'&quot;')}" oninput="setAppQuery(this.value)">
    </div>
    <div class="arch-toggle ${showArch?'on':''}" onclick="state._appArchived=${!showArch};state._appOpen=null;go('applications')">
      ${ico('folder')}${showArch?'Показать активные':`Архив${archived.length?` · ${archived.length}`:''}`}
    </div>
    <select class="sort-sel" onchange="setAppSort(this.value)">
      <option value="recent" ${sort==='recent'?'selected':''}>Сначала новые</option>
      <option value="oldest" ${sort==='oldest'?'selected':''}>Сначала старые</option>
      <option value="stage"  ${sort==='stage'?'selected':''}>По этапу</option>
      <option value="match"  ${sort==='match'?'selected':''}>По совпадению</option>
    </select>
  </div>

  <div id="app-list">
  ${list.length===0?`<div class="empty" style="padding:40px 20px"><div class="ei">${ico('briefcase')}</div>
      <h3>${q?'Ничего не найдено':showArch?'Архив пуст':'На этом этапе пока пусто'}</h3>
      ${q?`<p>Измените запрос</p>`:''}</div>`
  :list.map(({job,stage,meta,id})=>{
    const m=stageMeta(stage);
    const next=appNextAction(id);
    const nudge=appNudge(id,stage);
    const cd=interviewCountdown(meta.interview);
    return `<div class="appcard${meta.archived?' archived':''}" id="app-${id}">
      <div style="display:flex;align-items:center;gap:14px;width:100%" onclick="toggleApp(${id})">
        <div class="ac-logo" style="background:${job.color}">${job.logo}</div>
        <div class="ac-b">
          <div class="ac-t">${job.t} ${meta.archived?'<span class="arch-badge">в архиве</span>':''}</div>
          <div class="ac-d">${job.co} · ${job.loc}</div>
          <div class="ac-meta">
            <span>${ico('calendar')}Отклик ${fmtAgo(meta.appliedAt)}</span>
            <span>${ico('target')}${matchFor(job)}% совпадение</span>
            ${meta.interview?`<span style="color:var(--purple)">${ico('clock')}${cd?cd.t:fmtDateTime(meta.interview)}</span>`:''}
            ${meta.note?`<span>${ico('doc')}Заметка</span>`:''}
          </div>
        </div>
        <div class="ac-right" style="display:flex;align-items:center;gap:10px">
          <span class="stage-pill" style="background:${m[2]}1f;color:${m[2]}">
            <span class="d" style="background:${m[2]}"></span>${m[1]}</span>
          <span class="ac-chev">${ico('compass')}</span>
        </div>
      </div>

      <div class="app-body hidden" id="app-body-${id}">
        ${nudge?`<div class="nudge">${ico('alert')}<span><b>${nudge.t}.</b> ${nudge.d}</span></div>`:''}

        ${meta.interview?`<div class="iv-banner ${cd&&cd.past?'past':(cd&&cd.soon?'soon':'')}">
          <div class="iv-ic">${ico('calendar')}</div>
          <div class="iv-b"><div class="iv-t">Интервью назначено</div>
            <div class="iv-d">${fmtDateTime(meta.interview)}${cd?` · ${cd.t}`:''}</div></div>
          <button class="btn btn-ghost" onclick="event.stopPropagation();exportInterviewICS(${id})">${ico('calendar')} .ics</button>
        </div>`:''}

        <div class="ps" style="margin:0 0 4px">${m[3]}</div>
        <div class="tl">
          ${appHistory(id).map((r,i,arr)=>`<div class="tl-row ${i<arr.length-1?'done':'cur'}">
            <div class="tl-t">${r.t}</div><div class="tl-d">${r.d}</div></div>`).join('')}
        </div>

        <div class="ai-note" style="margin-top:12px">${ico('spark')}<span><b>${next.t}</b></span></div>

        <div class="iv-set" onclick="event.stopPropagation()">
          <span class="lbl">${ico('calendar')}Дата интервью:</span>
          <input type="datetime-local" value="${meta.interview||''}" onchange="setInterview(${id},this.value)">
          ${meta.interview?`<button class="btn btn-ghost btn-sm" style="width:auto;height:38px" onclick="setInterview(${id},'')">Убрать</button>`:''}
        </div>

        <div style="margin-top:14px" onclick="event.stopPropagation()">
          <div class="note-head">${ico('doc')}Личная заметка<span class="note-saved" id="note-ok-${id}">сохранено</span></div>
          <textarea class="app-note" placeholder="Например: спросить про формат стажировки и наставника"
            oninput="saveAppNote(${id},this.value);flashNote(${id})">${(meta.note||'').replace(/</g,'&lt;')}</textarea>
        </div>

        <div class="slog" id="slog-${id}" onclick="event.stopPropagation()">
          <div class="slog-h" onclick="document.getElementById('slog-${id}').classList.toggle('open')">
            ${ico('compass')}История этапов · ${stageLog(id).length}
          </div>
          <div class="slog-body">
            ${stageLog(id).slice().reverse().map(e=>{const sm=stageMeta(e.stage);
              return `<div class="slog-row">
                <span class="sl-d" style="background:${sm[2]}"></span>
                <span class="sl-n">${sm[1]}</span>
                <span class="sl-t">${fmtAgo(e.at)}</span>
              </div>`;}).join('')}
          </div>
        </div>

        <div class="stage-move" onclick="event.stopPropagation()">
          <span class="sm-l">Обновить этап вручную:</span>
          ${APP_STAGES.map(st=>`<button class="${stage===st[0]?'on':''}" onclick="setAppStage(${id},'${st[0]}')">${st[1]}</button>`).join('')}
        </div>

        <div class="app-actions" onclick="event.stopPropagation()">
          <button class="btn btn-primary" onclick="go('${next.go}')">${next.b}</button>
          <button class="btn btn-ghost" onclick="openJob(${id})">Вакансия</button>
          <button class="btn btn-ghost" onclick="openChat(${JSON.stringify(job.co).replace(/"/g,'&quot;')})">${ico('chat')} Написать в ${job.co}</button>
          <button class="btn btn-ghost" onclick="toggleArchive(${id})">${ico('folder')}${meta.archived?'Вернуть':'В архив'}</button>
          <button class="btn-withdraw" style="margin-left:auto;height:34px;padding:0 13px;font-size:12.5px;font-weight:600" onclick="withdrawApp(${id})">Отозвать</button>
        </div>
      </div>
    </div>`;}).join('')}
  </div>

  <div class="ai-note" style="margin-top:16px">${ico('alert')}<span>Этапы <b>смоделированы</b> из полноты профиля и числа сданных симуляций — реальные приходили бы от компаний. Дату интервью и этап вы задаёте сами; файл календаря скачивается по-настоящему.</span></div>`;
},

"student:portfolio":()=>{
  const items=portfolioItems();
  const avg=portfolioScore();
  const totalXp=items.reduce((a,x)=>a+x.sim.xp,0);
  const skills=[...new Set(items.flatMap(x=>x.sim.tags))];
  const color=v=>v>=75?'var(--green)':v>=55?'var(--accent)':'var(--amber)';

  if(!items.length) return ph("Портфолио","Решённые кейсы, которые видят работодатели")+`
    <div class="folio-empty">
      <div class="fe-ic">${ico('puzzle')}</div>
      <h3>Портфолио пока пустое</h3>
      <p>Сдайте первую симуляцию — решённый кейс с оценкой попадёт сюда и станет доказательством ваших навыков.</p>
      <button class="btn btn-primary" style="width:auto;margin:20px auto 0" onclick="go('simulations')">${ico('puzzle')} Выбрать кейс</button>
    </div>`;

  return ph("Портфолио",`${items.length} ${plural(items.length,'решённый кейс','решённых кейса','решённых кейсов')} · так вас видит работодатель`,
    `<button class="btn btn-ghost btn-sm" style="width:auto" onclick="copyProfileLink('portfolio')">${ico('globe')} Поделиться</button>`)+`
  <div class="g g4" style="margin-bottom:18px">
    ${statCard('puzzle',items.length,'Кейсов решено','var(--purple)','var(--purple-soft)')}
    ${statCard('target',avg+'/100','Средняя оценка','var(--blue)','var(--blue-soft)',null,{hint:avg>=75?'Сильный результат':'Есть куда расти'})}
    ${statCard('spark',totalXp+' XP','Заработано','var(--amber)','var(--amber-soft)')}
    ${statCard('code',skills.length,'Навыков подтверждено','var(--teal)','var(--teal-soft)')}
  </div>

  ${skills.length?`<div class="panel" style="margin-bottom:18px">
    <h3>${ico('check')} Подтверждённые навыки</h3><div class="ps">Не заявленные, а показанные в решённых кейсах</div>
    <div class="pf-chips" style="margin-top:12px">${skills.map(s=>`<span class="pf-chip">${s}</span>`).join('')}</div>
  </div>`:''}

  <div class="pf-grid2">
    ${items.map(({sim,rev})=>`<div class="folio" onclick="state._sim=${sim.id};go('sim-detail')" style="cursor:pointer">
      <div class="fo-top">
        <div class="fo-logo" style="background:${sim.color}">${sim.logo}</div>
        <div style="flex:1;min-width:0"><div class="fo-t">${sim.t}</div><div class="fo-c">${sim.co} · ${sim.role}</div></div>
        ${rev?`<div class="fo-score"><div class="fo-sv" style="color:${color(rev.total)}">${rev.total}</div><div class="fo-sl">из 100</div></div>`:''}
      </div>
      <div class="fo-body">
        ${rev?`<div class="fo-bars">
          ${rev.scores.map(x=>`<div class="fo-bar">
            <span class="n">${x.name}</span>
            <div class="b"><i style="width:${x.value}%;background:${color(x.value)}"></i></div>
            <span class="v" style="color:${color(x.value)}">${x.value}</span>
          </div>`).join('')}
        </div>`:`<div class="ps" style="margin-bottom:12px">Оценка не сохранилась</div>`}
        <div class="fo-tags">${sim.tags.map(t=>`<span class="fo-tag">${t}</span>`).join('')}</div>
      </div>
    </div>`).join('')}
  </div>

  <div class="ai-note" style="margin-top:16px">${ico('alert')}<span>Оценки получены <b>демонстрационным разбором</b> по формальным признакам текста, а не по его смыслу.</span></div>`;
},

"company:candidate-search":()=>{
  const q=(state._candQuery||'').toLowerCase().trim();
  const picked=state._candSkills||[];
  const ALL_SKILLS=[...new Set(TALENT.flatMap(c=>c.skills))].slice(0,12);
  let list=TALENT.slice();
  if(q) list=list.filter(c=>(c.n+' '+c.u+' '+c.city+' '+c.skills.join(' ')+' '+c.field).toLowerCase().includes(q));
  if(picked.length) list=list.filter(c=>picked.some(s=>c.skills.some(x=>x.toLowerCase().includes(s.toLowerCase()))));
  list.sort((a,b)=>candFit(b)-candFit(a));

  return ph("Поиск кандидатов","Студенты с подтверждёнными навыками — не резюме, а решённые кейсы")+`
  <div class="cand-filters">
    <div class="cand-search">${ico('search')}
      <input placeholder="Имя, вуз, город, навык…" value="${(state._candQuery||'').replace(/"/g,'&quot;')}" oninput="setCandQuery(this.value)">
    </div>
    <span class="ps" style="margin:0">${list.length} ${plural(list.length,'кандидат','кандидата','кандидатов')}</span>
  </div>

  <div class="job-filters" style="margin-bottom:18px">
    ${ALL_SKILLS.map(s=>`<div class="jf ${picked.includes(s)?'on':''}" onclick="toggleCandSkill(${JSON.stringify(s).replace(/"/g,'&quot;')})">${s}</div>`).join('')}
    ${picked.length?`<div class="jf" onclick="state._candSkills=[];go('candidate-search')">✕ Сбросить</div>`:''}
  </div>

  ${list.length===0?`<div class="empty" style="padding:50px 20px"><div class="ei">${ico('search')}</div><h3>Никого не нашли</h3><p>Смягчите фильтры или измените запрос</p></div>`
  :`<div class="cand-grid">
    ${list.map(c=>{
      const fit=candFit(c);
      const st=c.status==='active'?['var(--green)','Активно ищет']:['var(--amber)','Открыт к предложениям'];
      return `<div class="candcard" onclick="openTalent(${c.id})">
        <div class="cc-head">
          <div class="cc-ava">${c.n.split(' ').map(w=>w[0]).join('')}</div>
          <div style="flex:1;min-width:0"><div class="cc-n">${c.n}</div><div class="cc-u">${c.u} · ${c.course}</div></div>
          <span class="cc-fit">${fit}%</span>
        </div>
        <div class="cc-skills">
          ${c.skills.map(s=>{const hit=picked.some(p=>s.toLowerCase().includes(p.toLowerCase()));
            return `<span class="cc-sk ${hit?'hit':''}">${s}</span>`;}).join('')}
        </div>
        <div class="cc-foot">
          <span>${ico('puzzle')}${c.sims} ${plural(c.sims,'кейс','кейса','кейсов')}</span>
          <span>${ico('pin')}${c.city}</span>
          <span><span class="status-dot" style="background:${st[0]}"></span>${st[1]}</span>
          <span class="cc-open">Открыть →</span>
        </div>
      </div>`;}).join('')}
  </div>`}

  <div class="ai-note" style="margin-top:16px">${ico('alert')}<span>Каталог кандидатов <b>демонстрационный</b>. Реальный поиск показывал бы студентов, давших согласие на открытый профиль.</span></div>`;
},

"university:placement":()=>{
  const f=PLACEMENT.funnel;
  const total=f[0][1], offers=f[f.length-1][1];
  const rate=Math.round(offers/total*100);
  const max=f[0][1];
  return ph("Трудоустройство","Куда дошли ваши студенты — результат, а не только пробелы")+`
  <div class="place-band">
    ${statCard('users',total,'Студентов в системе','var(--blue)','var(--blue-soft)')}
    ${statCard('trophy',offers,'Получили оффер','var(--green)','var(--green-soft)',null,{hint:`${rate}% от всех`})}
    ${statCard('briefcase',PLACEMENT.employers.length,'Компаний-партнёров','var(--teal)','var(--teal-soft)')}
    ${statCard('chart',Math.round(f[3][1]/f[1][1]*100)+'%','Доходят до отклика','var(--amber)','var(--amber-soft)')}
  </div>

  <div class="panel" style="margin-bottom:16px">
    <h3>${ico('compass')} Воронка трудоустройства</h3><div class="ps">Где студенты отваливаются</div>
    <div class="funnel-wrap">
      ${f.map((row,i)=>{
        const pct=Math.round(row[1]/max*100);
        const drop=i>0?Math.round((1-row[1]/f[i-1][1])*100):0;
        return `<div class="funnel-b">
          <span class="fb-n">${row[0]}</span>
          <div class="fb-t"><i style="width:${Math.max(12,pct)}%;background:${row[2]}">${row[1]}</i></div>
          <span class="fb-p">${i>0?`−${drop}%`:'100%'}</span>
        </div>`;}).join('')}
    </div>
    <div class="ai-note" style="margin-top:14px">${ico('spark')}<span>Самая большая потеря — между <b>«Сдали симуляции»</b> и <b>«Откликнулись»</b>. Студенты готовы, но не решаются подать заявку.</span></div>
  </div>

  <div class="g g2">
    <div class="panel">
      <h3>${ico('company')} Куда взяли</h3><div class="ps">Компании, принявшие ваших студентов</div>
      <div style="margin-top:10px">
        ${PLACEMENT.employers.map(e=>`<div class="emp-row">
          <div class="er-logo" style="background:${e[2]}">${e[1]}</div>
          <div class="er-b"><div class="er-n">${e[0]}</div><div class="er-d">${e[4]}</div></div>
          <span class="er-c">${e[3]}</span>
        </div>`).join('')}
      </div>
    </div>
    <div class="panel">
      <h3>${ico('folder')} По когортам</h3><div class="ps">Офферы относительно размера группы</div>
      <div style="margin-top:10px">
        ${PLACEMENT.byCohort.map(c=>{
          const pct=Math.round(c[2]/c[1]*100);
          return `<div style="padding:11px 0;border-bottom:1px solid var(--hair2)">
            <div style="display:flex;justify-content:space-between;font-size:13.5px;margin-bottom:7px">
              <span style="font-weight:600">${c[0]}</span>
              <span style="color:var(--muted)">${c[2]} из ${c[1]} · <b style="color:var(--accent-ink)">${pct}%</b></span>
            </div>
            <div class="progress"><i style="width:${pct}%"></i></div>
          </div>`;}).join('')}
      </div>
      <button class="btn btn-ghost btn-sm" style="width:100%;margin-top:14px" onclick="toast('Экспорт отчёта — демо')">${ico('doc')} Выгрузить отчёт</button>
    </div>
  </div>

  <div class="ai-note" style="margin-top:16px">${ico('alert')}<span>Данные <b>демонстрационные</b>. Реальные приходили бы от компаний при подтверждении оффера.</span></div>`;
},

"job-detail":()=>{const j=JOBS[state._job||0];
  const closed=isPast(j.deadline);
  const fields=(MOCK.workFields)||[]; const inField=j.field&&fieldMatches(j.field,fields);
  const diagDone=state._diag&&state._diag.done; const m=matchFor(j);
  const mySkills=(MOCK.reg&&MOCK.reg.skillsArr)||[];
  const lvlWeight={'Базовый':40,'Средний':65,'Продвинутый':85,'Эксперт':100};
  /* honest per-skill comparison: only claim a match when the profile actually has it */
  const skillRows=j.tags.map(t=>{
    const hit=mySkills.find(s=>{
      const a=s.toLowerCase(), b=t.toLowerCase();
      return a===b || a.includes(b) || b.includes(a);
    });
    const lvl=hit?(lvlWeight[(MOCK.resumeData&&MOCK.resumeData.skillLevels||{})[hit]]||65):0;
    return {tag:t,hit:!!hit,lvl};
  });
  const covered=skillRows.filter(r=>r.hit).length;
  const reasons=[
    [inField, `Совпадает с интересом «${j.field}»`],
    [covered>0, `Есть ${covered} из ${skillRows.length} требуемых навыков`],
    [diagDone, "Профиль уточнён диагностикой"],
    [!diagDone, "Пройдите диагностику, чтобы повысить точность", true],
    [!inField, `Добавьте «${j.field}» в интересы для лучшего совпадения`, true],
    [covered<skillRows.length, `Добавьте недостающие навыки в резюме`, true],
  ].filter(x=>x[0]).map(x=>`<li style="color:${x[2]?'var(--muted)':'var(--ink)'}">${x[2]?'○':'✓'} ${x[1]}</li>`).join('');

  const skillBlock = mySkills.length===0
    ? `<div class="empty" style="padding:26px 20px;text-align:center">
         <div class="ei">${ico('code')}</div>
         <h3 style="font-size:14px">В профиле пока нет навыков</h3>
         <p style="font-size:13px;color:var(--muted);margin-top:4px">Добавьте их в резюме — покажем честное сравнение с этой вакансией</p>
         <button class="btn btn-ghost btn-sm" style="width:auto;margin:12px auto 0" onclick="go('resume')">Заполнить резюме →</button>
       </div>`
    : `<div style="margin-top:12px;display:flex;flex-direction:column;gap:11px">
        ${skillRows.map(r=>`
        <div style="display:flex;align-items:center;gap:12px">
          <span style="font-size:13px;width:130px;flex:none">${r.tag}</span>
          <div style="flex:1;height:8px;background:var(--hair2);border-radius:4px;overflow:hidden"><i style="display:block;height:100%;width:${r.lvl}%;background:${r.hit?'var(--green)':'var(--hair)'};border-radius:4px"></i></div>
          <span style="font-size:11px;font-weight:600;color:${r.hit?'var(--green)':'var(--muted)'};width:78px;text-align:right">${r.hit?'есть навык':'нет в профиле'}</span>
        </div>`).join('')}
       </div>
       <div class="ps" style="margin-top:12px">Закрыто ${covered} из ${skillRows.length} требований</div>`;

  return back('jobs','Вакансии')+`
  <div class="panel" style="margin-bottom:16px">
    <div style="display:flex;gap:16px;align-items:flex-start;flex-wrap:wrap">
      <div class="jc-logo" style="background:${j.color};width:60px;height:60px;border-radius:16px;font-size:24px">${j.logo}</div>
      <div style="flex:1;min-width:220px">
        <h2 style="font-size:22px;font-weight:700;letter-spacing:-.02em">${j.t}</h2>
        <div style="color:var(--muted);font-size:14px;margin-top:2px">${j.co} · ${j.team}</div>
        <div class="jc-meta" style="margin-top:12px;margin-bottom:0">
          <span class="jc-pill">${ico('pin')}${j.loc}</span>
          <span class="jc-pill">${ico('briefcase')}${j.fmt}</span>
          <span class="jc-pill">${ico('user')}${j.lvl}</span>
          <span class="jc-pill">${ico('doc')}${j.type}</span>
          <span class="jc-pill">${ico('student')}${coursesText(j.courses)}</span>
          ${deadlinePill(j)}
          <span class="jc-pill" style="background:var(--green-soft);color:var(--green-ink)">${j.sal}</span>
        </div>
      </div>
    </div>
    <div style="display:flex;align-items:center;gap:16px;margin-top:18px;padding-top:16px;border-top:1px solid var(--hair2);flex-wrap:wrap">
      <div class="match" style="font-size:14px"><div class="mbar" style="width:100px"><i style="width:${m}%"></i></div>${m}% совпадение</div>
      ${appliedTo(j.id)
        ? `<span class="pf-verified" style="margin-left:auto">${ico('check')}Вы откликнулись</span>`
        : closed
          ? `<button class="btn btn-ghost btn-sm" style="width:auto;margin-left:auto" disabled>Набор закрыт</button>`
          : `<button class="btn btn-primary btn-sm" style="width:auto;margin-left:auto" onclick="applyToJob(${j.id})">Откликнуться →</button>`}
    </div>
  </div>

  ${!closed&&j.deadline?`<div class="panel cd-panel" style="margin-bottom:16px">
    <div class="cd-label">${ico('clock')} До окончания приёма откликов</div>
    <div class="cd-timer" id="cd-timer" data-deadline="${j.deadline}">—</div>
  </div>`:''}

  <div class="panel" style="margin-bottom:16px"><h3>О позиции</h3>
    <p style="font-size:13.5px;color:var(--muted);line-height:1.6;margin-top:6px">${j.about}</p>
    <div class="jc-tags" style="margin:14px 0 0">${j.tags.map(t=>`<span class="jc-tag">${t}</span>`).join('')}</div>
  </div>

  ${(()=>{const steps=jobSteps(j);return steps.length?`
  <div class="panel" style="margin-bottom:16px"><h3>Как проходит отбор</h3><div class="ps">${steps.length} ${plural(steps.length,'шаг','шага','шагов')} от анкеты до решения${j.hiringSteps?'':' · процесс компании '+j.co}</div>
    ${hiringStepper(steps)}
  </div>`:''})()}

  ${FEATURES.skillMatchChart?`
  <div class="panel" style="margin-bottom:16px"><h3>Соответствие по навыкам</h3><div class="ps">Ваш профиль против требований вакансии</div>
    ${skillBlock}
  </div>

  <div class="panel" style="margin-bottom:16px"><h3>Почему такой процент</h3><div class="ps">Как считается совпадение</div>
    <ul style="list-style:none;margin:8px 0 0;padding:0;font-size:13px;line-height:2">${reasons}</ul>
  </div>`:''}

  <div class="split">
    <div class="panel"><h3>Задачи</h3>
      <ul style="margin:8px 0 0;padding-left:18px;font-size:13.5px;color:var(--muted);line-height:1.8">${(j.duties||[]).map(x=>`<li>${x}</li>`).join('')}</ul></div>
    <div class="panel"><h3>Требования</h3>
      <ul style="margin:8px 0 0;padding-left:18px;font-size:13.5px;color:var(--muted);line-height:1.8">${(j.reqs||[]).map(x=>`<li>${x}</li>`).join('')}<li>${j.lvl}-уровень, желание расти</li></ul></div>
  </div>`;},

/* The student card shows a deadline, a course range and the selection steps.
   The form had no way to enter any of them — the employer could not fill in
   what the platform promised to display. */
"internship-new":()=>back('internships','Стажировки')+ph("Новая стажировка","Форма создания вакансии",`<button class="btn btn-primary btn-sm" onclick="toast('Стажировка опубликована (демо)');go('internships')">Опубликовать</button>`)+`
  <div class="panel" style="max-width:640px">
    <h3>Основное</h3>
    <div class="field" style="margin-top:12px"><label>Название позиции</label><input placeholder="Data Analyst Intern"></div>
    <div class="split">
      <div class="field"><label>Формат</label><select><option>Гибрид</option><option>Офис</option><option>Удалённо</option></select></div>
      <div class="field"><label>Стипендия</label><input placeholder="350–500 $"></div>
    </div>
    <div class="field"><label>Требуемые навыки</label><input placeholder="SQL, Python, A/B"></div>
    <div class="field"><label>Описание</label><input placeholder="Кратко о роли и задачах"></div>
  </div>

  <div class="panel" style="max-width:640px;margin-top:16px">
    <h3>Кого берём и до какого числа</h3>
    <div class="ps">Эти два поля студент видит на карточке первыми</div>
    <div class="split" style="margin-top:12px">
      <div class="field"><label>Приём заявок до</label><input type="date" value="2026-08-20"></div>
      <div class="field"><label>Мест</label><input type="number" placeholder="5" min="1"></div>
    </div>
    <div class="field"><label>Курс</label>
      <div class="job-filters" style="margin-top:6px">
        ${[["1–2 курс",false],["3–4 курс",true],["Выпускники",false]].map(x=>
          `<div class="jf ${x[1]?'on':''}" onclick="this.classList.toggle('on')">${x[0]}</div>`).join('')}
      </div>
    </div>
  </div>

  <div class="panel" style="max-width:640px;margin-top:16px">
    <h3>Как проходит отбор</h3>
    <div class="ps">Прозрачные шаги снимают главный страх кандидата — «что будет дальше»</div>
    <div class="field" style="margin-top:12px"><label>Шаги через запятую</label>
      <input value="Анкета, Тестовое задание, Интервью, Выбор команды"></div>
    ${hiringStepper(["Анкета","Тестовое задание","Интервью","Выбор команды"])}
  </div>

  <div class="panel" style="max-width:640px;margin-top:16px">
    <h3>Связанная симуляция</h3>
    <div class="ps">Необязательно. Решённый кейс заменяет тестовое задание</div>
    <div class="field" style="margin-top:12px"><select><option>— не связывать —</option><option>Анализ retention e-commerce</option><option>A/B-тест онбординга</option></select></div>
  </div>`,

"cohort-detail":()=>{const c=COHORTS[state._cohort||0];const roster=STUDENTS.filter(s=>c.name.startsWith(s.cohort)).concat(STUDENTS).slice(0,4);return back('cohorts','Когорты')+ph(c.name,`${c.count} студентов · ${c.ready}% средняя готовность`)+`
  <div class="g g3" style="margin-bottom:16px">${stat(c.count,"Студентов")}${stat(c.ready+"%","Готовность","up")}${stat(c.offers,"Офферов")}</div>
  <div class="panel" style="padding:0;overflow:hidden">
    <table class="tbl"><thead><tr><th>Студент</th><th>Шаг</th><th>Готовность</th><th>Статус</th></tr></thead><tbody>
    ${roster.map(s=>
      `<tr><td class="nm">${s.name}</td><td>${s.step}</td><td>${s.ready}</td><td>${statusBadge(s.status)}</td></tr>`).join('')}
    </tbody></table>
  </div>`;},

"student-detail":()=>{const s=STUDENTS[state._student||0];return back('students','Студенты')+ph(s.name,`Когорта «${s.cohort}» · шаг ${s.step}`)+`
  <div class="g g3" style="margin-bottom:16px">${stat(s.ready,"Готовность","up")}${stat(s.sims,"Симуляций сдано")}${stat(s.apps,"Отклика")}</div>
  <div class="g g2">
    <div class="panel"><h3>Компетенции</h3><div class="ps"></div>${['Аналитика данных','Продукт','Коммуникация','SQL'].map(c=>compRow(c)).join('')}</div>
    <div class="panel"><h3>Активность</h3><div class="ps"></div>
      <div class="list">${li(ico('puzzle'),"Сдала «Анализ retention»","оценка 92%","")}${li(ico('doc'),"Обновила AI-резюме","вчера","")}${li(ico('chat'),s.status==='interview'?"Приглашена на интервью":"Откликнулась на вакансию","Ozon","")}</div>
    </div>
  </div>`;},

"internship-detail":()=>{const j=INTERNSHIPS[state._intern||0];
  const total=CANDS.new.length+CANDS.screen.length+CANDS.interview.length+CANDS.offer.length;
  return back('internships','Стажировки')+ph(j.name,`${total} в воронке · перетаскивайте кандидатов между этапами`)+`
  <div class="g g4" style="margin-bottom:16px">
    ${stat(CANDS.new.length,"Новые")}${stat(CANDS.screen.length,"Скрининг")}${stat(CANDS.interview.length,"Интервью")}${stat(CANDS.offer.length,"Оффер","up")}
  </div>
  <div class="kanban">${kcol("Новые",CANDS.new,'new')}${kcol("Скрининг",CANDS.screen,'screen')}${kcol("Интервью",CANDS.interview,'interview')}${kcol("Оффер",CANDS.offer,'offer')}</div>`;},

/* ---------- TALENT PROFILE (what the employer actually came for) ---------- */
"talent-detail":()=>{
  const c=TALENT.find(x=>x.id===state._talent)||TALENT[0];
  const fit=candFit(c);
  const st=c.status==='active'?['var(--green)','Активно ищет']:['var(--amber)','Открыт к предложениям'];
  const initials=c.n.split(' ').map(w=>w[0]).join('');
  return back('candidate-search','Поиск кандидатов')+`
  <div class="panel" style="margin-bottom:16px">
    <div style="display:flex;gap:16px;align-items:flex-start;flex-wrap:wrap">
      <div class="tp-ava">${initials}</div>
      <div style="flex:1;min-width:220px">
        <h2 style="font-size:22px;font-weight:700;letter-spacing:-.02em">${c.n}</h2>
        <div style="color:var(--muted);font-size:14px;margin-top:2px">${c.u} · ${c.course}</div>
        <div class="jc-meta" style="margin-top:12px;margin-bottom:0">
          <span class="jc-pill">${ico('pin')}${c.city}</span>
          <span class="jc-pill">${ico('briefcase')}${c.field}</span>
          <span class="jc-pill"><span class="status-dot" style="background:${st[0]}"></span>${st[1]}</span>
        </div>
      </div>
      <div style="text-align:right;flex:none">
        <div class="tp-fit">${fit}%</div>
        <div class="tp-fit-l">совпадение</div>
      </div>
    </div>
    <div style="display:flex;gap:10px;margin-top:18px;padding-top:16px;border-top:1px solid var(--hair2);flex-wrap:wrap">
      <button class="btn btn-primary btn-sm" style="width:auto" onclick="toast('Приглашение отправлено (демо)')">Пригласить на интервью →</button>
      <button class="btn btn-ghost btn-sm" style="width:auto" onclick="go('messages')">Написать</button>
    </div>
  </div>

  <div class="co-stats" style="margin:0 0 16px">
    <div class="co-stat"><div class="cs-v">${c.sims}</div><div class="cs-l">${plural(c.sims,'решённый кейс','решённых кейса','решённых кейсов')}</div></div>
    <div class="co-stat"><div class="cs-v">${c.score}%</div><div class="cs-l">средний балл по кейсам</div></div>
    <div class="co-stat"><div class="cs-v">${c.skills.length}</div><div class="cs-l">${plural(c.skills.length,'подтверждённый навык','подтверждённых навыка','подтверждённых навыков')}</div></div>
  </div>

  <div class="panel" style="margin-bottom:16px"><h3>Навыки</h3>
    <div class="ps">Подтверждены решёнными кейсами, а не самооценкой</div>
    <div class="tp-skills">${c.skills.map(x=>`<span class="tp-sk">${x}</span>`).join('')}</div>
  </div>

  <div class="panel"><h3>Решённые кейсы</h3>
    <div class="ps">То, что заменяет строчку в резюме</div>
    <div class="list" style="margin-top:8px">
      ${Array.from({length:c.sims}).map((_,i)=>li(ico('puzzle'),
        `Кейс ${i+1} · ${c.field}`,
        `Оценка ${Math.max(60,c.score-i*4)}% · сдан`,'')).join('')}
    </div>
  </div>`;
},

/* ---------- COMPANIES (public content, no contract required) ---------- */
"companies":()=>{
  const q=(state._coQuery||'').toLowerCase().trim();
  let list=COMPANIES.slice();
  if(q) list=list.filter(c=>(c.name+' '+c.industry+' '+c.city+' '+c.about).toLowerCase().includes(q));
  list.sort((a,b)=>b.openPositions-a.openPositions);
  const card=c=>{
    /* one headline figure, and only if it exists */
    const head = c.stats.offerRate!=null
      ? `<div class="co-fig"><b>${c.stats.offerRate}%</b><span>стажёров получают оффер</span></div>`
      : c.stats.internsHired!=null
        ? `<div class="co-fig"><b>${c.stats.internsHired}</b><span>стажёров за год</span></div>`
        : '';
    return `<div class="co-card" onclick="openCompany(${c.id})">
      <div class="co-top">
        <div class="co-logo" style="background:${c.color}">${c.initials}</div>
        ${c.openPositions>0?`<span class="co-open">${c.openPositions} ${plural(c.openPositions,'позиция','позиции','позиций')}</span>`:`<span class="co-open muted">Набора нет</span>`}
      </div>
      <div class="co-name">${c.name}</div>
      <div class="co-sub">${c.industry}</div>
      <div class="co-meta"><span>${ico('pin')}${c.city}</span><span>${ico('users')}${c.size}</span></div>
      ${head}
    </div>`;
  };
  return ph("Компании","Кто берёт студентов, на каких условиях и с каким шансом на оффер")+`
  <div class="jobs-toolbar" style="margin-bottom:14px">
    <div class="jobs-search">${ico('search')}<input placeholder="Поиск по названию, отрасли…" value="${state._coQuery||''}" oninput="setCoQuery(this.value)"></div>
  </div>
  ${list.length===0
    ? `<div class="empty" style="padding:50px 20px"><div class="ei">${ico('search')}</div><h3>Ничего не найдено</h3><p>Измените запрос</p></div>`
    : `<div class="co-grid">${list.map(card).join('')}</div>`}`;
},

"company-detail":()=>{
  const c=COMPANIES[state._co||0];
  const jobs=JOBS.filter(j=>j.co===c.name);

  /* stats block renders only if there is at least one real number */
  const figs=[
    [c.stats.offerRate!=null, `${c.stats.offerRate}%`, "стажёров получают оффер"],
    [c.stats.internsHired!=null, `${c.stats.internsHired}`, "стажёров наняли за год"],
    [!!c.stats.avgTimeToOffer, `${c.stats.avgTimeToOffer}`, "средний путь до оффера"],
  ].filter(x=>x[0]);
  const statsBlock = figs.length
    ? `<div class="co-stats">${figs.map(f=>`<div class="co-stat"><div class="cs-v">${f[1]}</div><div class="cs-l">${f[2]}</div></div>`).join('')}</div>`
    : '';

  const steps=(c.hiringSteps||[]);
  const stepper = steps.length
    ? `<div class="panel" style="margin-bottom:16px"><h3>Как проходит отбор</h3><div class="ps">${steps.length} ${plural(steps.length,'шаг','шага','шагов')} от анкеты до решения</div>
        ${hiringStepper(steps)}
       </div>` : '';

  const progs = (c.programs||[]).map(p=>`
    <div class="co-prog">
      <div class="cp-head">
        <div class="cp-title">${p.title}</div>
        ${p.paid?`<span class="cp-paid">${ico('check')}Оплачивается</span>`:''}
      </div>
      <div class="cp-meta">
        <span class="jc-pill">${ico('clock')}${p.duration}</span>
        <span class="jc-pill">${ico('student')}${coursesText(p.courses)}</span>
        ${p.offerRate!=null?`<span class="jc-pill" style="background:var(--green-soft);color:var(--green-ink)">${p.offerRate}% оффер</span>`:''}
      </div>
    </div>`).join('');

  return back('companies','Компании')+`
  <div class="panel" style="margin-bottom:16px">
    <div style="display:flex;gap:16px;align-items:flex-start;flex-wrap:wrap">
      <div class="co-logo" style="background:${c.color};width:60px;height:60px;border-radius:16px;font-size:20px">${c.initials}</div>
      <div style="flex:1;min-width:220px">
        <h2 style="font-size:22px;font-weight:700;letter-spacing:-.02em">${c.name}</h2>
        <div style="color:var(--muted);font-size:14px;margin-top:2px">${c.industry}</div>
        <div class="jc-meta" style="margin-top:12px;margin-bottom:0">
          <span class="jc-pill">${ico('pin')}${c.city}</span>
          <span class="jc-pill">${ico('users')}${c.size}</span>
          ${c.openPositions>0?`<span class="jc-pill" style="background:var(--blue-soft);color:var(--blue-ink)">${ico('briefcase')}${c.openPositions} ${plural(c.openPositions,'открытая позиция','открытые позиции','открытых позиций')}</span>`:''}
        </div>
      </div>
    </div>
    ${statsBlock}
  </div>

  <div class="panel" style="margin-bottom:16px"><h3>О компании</h3>
    <p style="font-size:13.5px;color:var(--muted);line-height:1.6;margin-top:6px">${c.about}</p>
  </div>

  ${progs?`<div class="panel" style="margin-bottom:16px"><h3>Программы для студентов</h3><div class="ps">Что компания предлагает тем, у кого пока нет опыта</div>
    <div class="co-progs">${progs}</div></div>`:''}

  ${stepper}

  ${jobs.length?`<div class="panel"><h3>Открытые вакансии</h3><div class="ps">${jobs.length} ${plural(jobs.length,'позиция','позиции','позиций')} прямо сейчас</div>
    <div class="jobs-list" style="margin-top:12px">${jobs.map(j=>`
      <div class="jobrow" onclick="openJob(${j.id})">
        <div class="jr-logo" style="background:${j.color}">${j.logo}</div>
        <div class="jr-main">
          <div class="jr-title">${j.t}</div>
          <div class="jr-sub"><span>${ico('pin')}${j.loc}</span><span>${ico('briefcase')}${j.fmt}</span>${deadlinePill(j)}</div>
        </div>
        <div class="jr-right"><div class="jr-sal">${j.sal}</div></div>
      </div>`).join('')}</div></div>`
   :`<div class="panel"><h3>Открытые вакансии</h3>
      <div class="empty" style="padding:26px 20px;text-align:center">
        <div class="ei">${ico('briefcase')}</div>
        <div style="font-size:14px;font-weight:600;margin-top:6px">Сейчас набора нет</div>
        <p style="font-size:13px;color:var(--muted);margin-top:4px">Следите за событиями компании — там появляются анонсы</p>
      </div></div>`}`;
},

/* ---------- EVENTS ---------- */
"events":()=>{
  const f=state._evFilter||'Все';
  const types=['Все',...Object.keys(EV_TYPE)];
  let list=EVENTS.filter(e=>f==='Все'||e.type===f);
  list.sort((a,b)=>a.date.localeCompare(b.date));
  const card=e=>{
    const c=COMPANIES[e.company];
    const t=EV_TYPE[e.type]||{soft:'var(--hair2)',ink:'var(--muted)'};
    const pct=Math.round(e.seatsTaken/e.seats*100);
    const closed=isPast(e.deadline);
    const left=daysLeft(e.deadline);
    return `<div class="ev-card${closed?' ev-closed':''}">
      <div class="ev-top">
        <span class="ev-type" style="background:${t.soft};color:${t.ink}">${e.type}</span>
        <span class="ev-fmt">${ico(e.format==='Онлайн'?'globe':'pin')}${e.format}</span>
      </div>
      <div class="ev-title">${e.title}</div>
      <div class="ev-co">
        <span class="ev-logo" style="background:${c.color}">${c.initials}</span>
        <span>${c.name}</span>
        ${e.university?`<span class="ev-uni">${ico('university')}${e.university}</span>`:''}
      </div>
      <div class="ev-desc">${e.description}</div>
      <div class="ev-seats">
        <div class="ev-bar"><i style="width:${pct}%"></i></div>
        <span>${e.seatsTaken} из ${e.seats} мест</span>
      </div>
      <div class="ev-foot">
        <span class="ev-date">${ico('calendar')}${fmtDate(e.date)}</span>
        ${closed
          ? `<span class="ev-dl closed">Регистрация закрыта</span>`
          : left<=7
            ? `<span class="ev-dl urgent">Осталось ${left} ${plural(left,'день','дня','дней')}</span>`
            : `<span class="ev-dl">до ${fmtDate(e.deadline)}</span>`}
      </div>
      <button class="btn btn-primary btn-sm" style="width:100%;margin-top:12px" ${closed?'disabled':''} onclick="toast('Заявка отправлена (демо)')">${closed?'Набор закрыт':'Зарегистрироваться'}</button>
    </div>`;
  };
  return ph("События","Встречи, мастер-классы и чемпионаты от работодателей")+`
  <div class="job-filters" style="margin-bottom:16px">
    ${types.map(x=>`<div class="jf ${f===x?'on':''}" onclick="setEvFilter('${x}')">${x}${x!=='Все'?` · ${EVENTS.filter(e=>e.type===x).length}`:` · ${EVENTS.length}`}</div>`).join('')}
  </div>
  ${list.length===0
    ? `<div class="empty" style="padding:50px 20px"><div class="ei">${ico('calendar')}</div><h3>Событий не найдено</h3><p>Выберите другой тип</p></div>`
    : `<div class="ev-grid">${list.map(card).join('')}</div>`}`;
},
};

/* ============================================================
   COMPONENT HELPERS
   ============================================================ */
function stat(v,l,dir,d){return `<div class="stat"><div class="sv">${v}</div><div class="sl">${l}</div>${d?`<div class="sd ${dir||''}">${dir==='up'?'↑ ':dir==='down'?'↓ ':''}${d}</div>`:''}</div>`;}
function progressRing(pct,label){
  const r=42,c=2*Math.PI*r,off=c-(pct/100)*c;
  return `<div class="ov-ring">
    <svg width="96" height="96" viewBox="0 0 96 96">
      <circle cx="48" cy="48" r="${r}" fill="none" stroke="var(--hair2)" stroke-width="8"/>
      <circle cx="48" cy="48" r="${r}" fill="none" stroke="var(--accent)" stroke-width="8" stroke-linecap="round" stroke-dasharray="${c}" stroke-dashoffset="${off}"/>
    </svg>
    <div class="ov-ring-v"><div class="ov-ring-num">${pct}%</div><div class="ov-ring-lbl">${label}</div></div>
  </div>`;
}
function statCard(icon,val,label,color,soft,delta,opts){
  opts=opts||{};
  const isZero = String(val)==='0' || String(val)==='0%';
  const spark = opts.spark ? `<div class="sc-spark">${opts.spark.map(h=>`<i style="height:${Math.max(12,h)}%"></i>`).join('')}</div>` : '';
  return `<div class="statcard ${isZero?'zero':''}" style="--sc-color:${color};--sc-soft:${soft}">
    <div class="sc-ic" style="background:${soft};color:${color}">${ico(icon)}</div>
    <div class="sc-v">${val}</div>
    <div class="sc-l">${label}</div>
    ${delta?`<div class="sc-delta">↑ ${delta}</div>`:''}
    ${(!delta&&opts.hint)?`<div class="sc-hint">${opts.hint}</div>`:''}
    ${spark}
  </div>`;
}
function li(ic,t,d,r){return `<div class="li"><div class="li-ic">${ic}</div><div class="li-b"><div class="li-t">${t}</div><div class="li-d">${d}</div></div>${r?`<div class="li-r">${r}</div>`:''}</div>`;}
function simLi(t,p,due){return `<div class="li"><div class="li-b"><div class="li-t">${t}</div><div style="margin-top:6px"><div class="progress"><i style="width:${p}%"></i></div></div></div><div class="li-r">${due}</div></div>`;}
function ach(e,t,on){return `<div style="text-align:center;padding:12px;border:1px solid var(--hair);border-radius:11px;opacity:${on?1:.4}"><div style="font-size:24px">${e}</div><div style="font-size:11.5px;font-weight:600;margin-top:4px">${t}</div><div style="font-size:10px;color:var(--muted)">${on?'Открыто':'Заблокировано'}</div></div>`;}
const COMP_SCORES={"Аналитика данных":72,"Продукт":58,"Коммуникация":81,"Маркетинг":44,"SQL":76,"Python":63};
function compRow(c){const p=COMP_SCORES[c]??60;return `<div style="display:flex;align-items:center;gap:10px;padding:8px 0"><span style="font-size:13px;width:130px;flex:none">${c}</span><div class="progress" style="flex:1"><i style="width:${p}%"></i></div><span style="font-size:12px;color:var(--muted);width:34px;text-align:right">${p}%</span></div>`;}
function cohortRow(n,p){return `<div style="padding:10px 0;border-bottom:1px solid var(--hair2)"><div style="display:flex;justify-content:space-between;margin-bottom:6px"><span style="font-size:13.5px;font-weight:500">${n}</span><span style="font-size:12px;color:var(--muted)">${p}%</span></div><div class="progress"><i style="width:${p}%"></i></div></div>`;}
/* Takes the already-computed percent. The old signature said `max` and divided
   again, so every bar came out at ~6% and the funnel never narrowed. */
/* Was hardcoded at 73%. Read it off the candidate pool the screen actually shows. */
function avgMatch(){
  if(typeof TALENT==='undefined' || !TALENT.length) return 0;
  const v=TALENT.map(c=>candFit(c));
  return Math.round(v.reduce((a,b)=>a+b,0)/v.length);
}

function funnelRow(n,v,pct){const p=Math.max(2,Math.round(pct));return `<div style="padding:9px 0"><div style="display:flex;justify-content:space-between;margin-bottom:5px"><span style="font-size:13px">${n}</span><span style="font-size:12px;color:var(--muted);font-weight:600">${v}</span></div><div class="progress"><i style="width:${p}%"></i></div></div>`;}
function statusBadge(s,txt){const map={active:['b-blue','В работе'],interview:['b-purple','Интервью'],offer:['b-green','Оффер'],stalled:['b-red','Застой']};const[cls,def]=map[s]||['b-gray',s];return `<span class="badge ${cls}">${txt||def}</span>`;}
function kcol(title,items,key){return `<div class="kcol" data-stage="${key}" ondragover="event.preventDefault();this.style.background='var(--accent-soft)'" ondragleave="this.style.background=''" ondrop="dropCand(event,'${key}')"><h4>${title}<span class="kcount">${items.length}</span></h4>${items.map((c,ci)=>`<div class="kcard" draggable="true" ondragstart="dragCand(event,'${key}',${ci})" onclick="toast('Кандидат: ${c[0]} — ${c[1]}')"><div class="kn">${c[0]}</div><div class="kr">${c[1]}</div><div class="kfoot"><span class="badge b-gray">портфолио</span></div></div>`).join('')}</div>`;}
function dragCand(e,fromKey,idx){ e.dataTransfer.setData('text/plain',''); window._drag={from:fromKey,idx:idx}; }
function dropCand(e,toKey){
  e.preventDefault();
  const d=window._drag; if(!d||d.from===toKey){ document.querySelectorAll('.kcol').forEach(c=>c.style.background=''); return; }
  const card=CANDS[d.from].splice(d.idx,1)[0];   // move in shared model
  if(card) CANDS[toKey].push(card);
  window._drag=null;
  /* recompute internship applications = total in pipeline, then re-render whole detail */
  if(typeof INTERNSHIPS!=='undefined' && state._intern!=null && INTERNSHIPS[state._intern]){
    INTERNSHIPS[state._intern].apps = CANDS.new.length+CANDS.screen.length+CANDS.interview.length+CANDS.offer.length;
    INTERNSHIPS[state._intern].offers = CANDS.offer.length;
  }
  go(state.page||'internship-detail');   // re-render current board → counts/funnel update
  toast("Кандидат перемещён: "+(card?card[0]:''));
}
function notif(ic,t,d,tm,unread){return `<div class="notif ${unread?'unread':''}"><div class="ni" style="background:var(--accent-soft)">${ic}</div><div style="flex:1"><div style="font-size:14px;font-weight:600">${t}</div><div style="font-size:12.5px;color:var(--muted);margin-top:2px">${d}</div></div><div style="font-size:11.5px;color:var(--faint)">${tm}</div></div>`;}
/* ============================================================
   PROFILE — real data, saved as you type, no fake "Save" button
   ============================================================ */
function profileInit(){
  if(!MOCK.profile || typeof MOCK.profile!=='object') MOCK.profile={};
  const p=MOCK.profile;
  if(typeof p.email!=='string') p.email='';
  if(!Array.isArray(p.links)) p.links=[];
  if(typeof p.jobStatus!=='string') p.jobStatus='active';
  if(typeof p.phoneVerified!=='boolean') p.phoneVerified=false;
  if(!Array.isArray(p.doneSims)) p.doneSims=[];
  if(!p.appMeta||typeof p.appMeta!=='object') p.appMeta={};
  if(!p.simDrafts||typeof p.simDrafts!=='object') p.simDrafts={};
  if(!p.simReviews||typeof p.simReviews!=='object') p.simReviews={};
  p.simsDone=p.doneSims.length;
  if(!Array.isArray(p.appliedJobs)) p.appliedJobs=[];
  p.applications=p.appliedJobs.length;
  if(typeof p.views!=='number') p.views=0;
  return p;
}
/* write-through: persist silently so typing never loses focus */
let _saveFlash=null;
function flashSaved(){
  const el=document.getElementById('pf-saved'); if(!el) return;
  el.classList.add('on');
  clearTimeout(_saveFlash);
  _saveFlash=setTimeout(()=>el.classList.remove('on'),1200);
}
/* debounce writes: one keystroke should not hit localStorage every time */
let _regSave=null;
function setReg(field,val){
  MOCK.reg[field]=val;
  clearTimeout(_regSave);
  _regSave=setTimeout(()=>{ persistState(); flashSaved(); },350);
}
/* Дата рождения: жёстко ограничиваем год 4 цифрами и разумным диапазоном.
   type="date" в части браузеров позволяет набрать 5-6-значный год — обрезаем. */
function clampBirth(el,field){
  let v=el.value||'';                       // формат YYYY-MM-DD (год может быть длиннее)
  const m=v.match(/^(\d+)-(\d{2})-(\d{2})$/);
  if(m){
    let y=m[1];
    if(y.length>4) y=y.slice(0,4);          // обрезаем год до 4 цифр
    let yn=parseInt(y,10);
    if(y.length===4){                        // валидируем диапазон только для полного года
      if(yn<1950) y='1950';
      if(yn>2012) y='2012';
    }
    v=`${y}-${m[2]}-${m[3]}`;
    if(v!==el.value) el.value=v;
  }
  if(field==='reg') setReg('birth',el.value); else MOCK.reg.birth=el.value;
}
function setProfileQuiet(field,val){ profileInit(); MOCK.profile[field]=val; persistState(); }
/* used by controls that need the page to redraw (status pick, links) */
function setProfile(field,val){
  profileInit(); MOCK.profile[field]=val; persistState();
  if(field==='email') return;           // typing → no redraw
  go('profile');
}
let _linkSave=null;
function setLink(i,url){
  profileInit();
  if(!MOCK.profile.links[i]) return;
  MOCK.profile.links[i].url=url;
  clearTimeout(_linkSave);
  _linkSave=setTimeout(()=>{ persistState(); flashSaved(); },350);
}
function addProfileLink(prefill){ profileInit(); MOCK.profile.links.push({url:prefill||''}); persistState(); go('profile'); }
function removeProfileLink(i){ profileInit(); MOCK.profile.links.splice(i,1); persistState(); go('profile'); }
function linkIcon(url){
  const u=(url||'').toLowerCase();
  if(u.includes('github')) return 'code';
  if(u.includes('linkedin')) return 'briefcase';
  if(u.includes('t.me')||u.includes('telegram')) return 'chat';
  if(u.includes('behance')||u.includes('dribbble')) return 'palette';
  return 'globe';
}
/* phone verification — mock SMS, any code passes (same rule as onboarding) */
function verifyPhone(){
  const code=prompt('Мы отправили код на ваш номер (демо — подойдёт любой):','1234');
  if(code==null) return;
  setProfileQuiet('phoneVerified',true);
  toast('Телефон подтверждён');
  go('profile');
}
/* email setter that does not redraw while typing */
let _emailSave=null;
function setProfileEmail(v){
  profileInit(); MOCK.profile.email=v;
  clearTimeout(_emailSave);
  _emailSave=setTimeout(()=>{ persistState(); flashSaved(); },350);
}

function profileChecklist(){
  const r=MOCK.reg||{}, p=profileInit(), d=MOCK.resumeData||{};
  const diagDone=!!(state._diag&&state._diag.done);
  const skills=(r.skillsArr||[]).length>0;
  return [
    {t:'Имя и фамилия', done:!!(r.first&&r.last), action:"toast('Заполните поля ниже')"},
    {t:'Фото профиля', done:!!MOCK.users.photo, action:"uploadPhoto()"},
    {t:'Телефон подтверждён', done:!!p.phoneVerified, action:"verifyPhone()"},
    {t:'Учебное заведение и курс', done:!!(r.university&&r.course), action:"toast('Заполните поля ниже')"},
    {t:'Пройдена диагностика', done:diagDone, action:"go('diagnostics')"},
    {t:'Раздел «О себе» в резюме', done:!!(d.about&&d.about.trim()), action:"go('resume')"},
    {t:'Указаны навыки', done:skills, action:"go('resume')"},
    {t:'Добавлена хотя бы одна ссылка', done:(p.links||[]).some(l=>l.url&&l.url.trim()), action:"addProfileLink()"},
  ];
}

/* public profile link — real clipboard copy, with a fallback */
function copyProfileLink(slug){
  const url='https://z2h.uz/r/'+slug;
  const done=()=>toast('Ссылка скопирована: '+url);
  try{
    if(navigator.clipboard && navigator.clipboard.writeText){ navigator.clipboard.writeText(url).then(done,()=>fallbackCopy(url,done)); }
    else fallbackCopy(url,done);
  }catch(e){ fallbackCopy(url,done); }
}
function fallbackCopy(text,cb){
  try{
    const ta=document.createElement('textarea');
    ta.value=text; ta.style.position='fixed'; ta.style.opacity='0';
    document.body.appendChild(ta); ta.select(); document.execCommand('copy'); ta.remove(); cb();
  }catch(e){ toast('Не удалось скопировать'); }
}

/* ---- simulations: drafts, submission, mock review — all persisted ---- */
function simDone(id){ profileInit(); return (MOCK.profile.doneSims||[]).includes(id); }
function simDraft(id){ profileInit(); return (MOCK.profile.simDrafts||{})[id]||''; }
function simReview(id){ profileInit(); return (MOCK.profile.simReviews||{})[id]||null; }
function countWords(t){ return (t||'').trim().split(/\s+/).filter(Boolean).length; }
function setSimFilter(f){ state._simFilter=f; go('simulations'); }

let _simSave=null;
function saveSimDraft(id,text){
  profileInit();
  if(!MOCK.profile.simDrafts) MOCK.profile.simDrafts={};
  MOCK.profile.simDrafts[id]=text;
  /* live word counter without redrawing the textarea */
  const el=document.getElementById('sim-words');
  if(el){
    const n=countWords(text);
    el.textContent=`${n} ${plural(n,'слово','слова','слов')}`;
    el.className = n>=40?'ok':'warn';
  }
  clearTimeout(_simSave);
  _simSave=setTimeout(()=>{ if(typeof persistState==='function') persistState(); },400);
}

/* A deterministic mock: the "score" is derived from the answer, not random.
   It is NOT a real AI review — the UI says so plainly. */
function buildSimReview(sim,text){
  const words=countWords(text);
  const lower=(text||'').toLowerCase();
  const hasNumbers=/\d/.test(text);
  const hasStructure=/\n|•|-\s|\d\./.test(text);
  const mentionsMetric=/метрик|конверси|процент|%|ltv|cac|retention|удержан/.test(lower);
  const mentionsHypo=/гипотез|предполаг|версия|проверить/.test(lower);

  const scores=sim.rubric.map(([name,weight])=>{
    let v=45;
    if(words>=80) v+=15; else if(words>=40) v+=8;
    if(hasNumbers) v+=10;
    if(hasStructure) v+=8;
    if(mentionsMetric) v+=10;
    if(mentionsHypo) v+=8;
    v=Math.min(95,v);
    return {name,weight,value:v};
  });
  const total=Math.round(scores.reduce((a,x)=>a+x.value*x.weight,0)/100);

  const strengths=[];
  const gaps=[];
  if(hasNumbers) strengths.push('Есть конкретные цифры — это то, что ценят'); else gaps.push('Добавьте цифры: без них выводы звучат как мнение');
  if(mentionsHypo) strengths.push('Сформулированы проверяемые гипотезы'); else gaps.push('Не хватает гипотез — что именно вы предлагаете проверить?');
  if(mentionsMetric) strengths.push('Указаны метрики успеха'); else gaps.push('Не названы метрики, по которым поймём, что сработало');
  if(hasStructure) strengths.push('Структурированный ответ, легко читать'); else gaps.push('Разбейте текст на пункты — сплошной абзац трудно оценивать');
  if(words>=80) strengths.push('Достаточно развёрнуто'); else if(words<60) gaps.push('Ответ короткий — раскройте рассуждение');

  return {total,scores,strengths:strengths.slice(0,3),gaps:gaps.slice(0,3),words,at:new Date().toISOString()};
}

function submitSim(id){
  const sim=SIMS.find(x=>x.id===id); if(!sim) return;
  const text=simDraft(id);
  const words=countWords(text);
  if(words<40){ toast(`Напишите хотя бы 40 слов — сейчас ${words}`); return; }

  profileInit();
  if(!Array.isArray(MOCK.profile.doneSims)) MOCK.profile.doneSims=[];
  if(!MOCK.profile.simReviews) MOCK.profile.simReviews={};
  if(!MOCK.profile.doneSims.includes(id)) MOCK.profile.doneSims.push(id);
  MOCK.profile.simReviews[id]=buildSimReview(sim,text);
  MOCK.profile.simsDone=MOCK.profile.doneSims.length;
  if(typeof persistState==='function') persistState();
  toast(`Решение принято · +${sim.xp} XP`);
  go('sim-detail');
}
function resetSim(id){
  if(!confirm('Пересдать? Текущая оценка будет удалена, решение сохранится.')) return;
  profileInit();
  MOCK.profile.doneSims=(MOCK.profile.doneSims||[]).filter(x=>x!==id);
  if(MOCK.profile.simReviews) delete MOCK.profile.simReviews[id];
  MOCK.profile.simsDone=MOCK.profile.doneSims.length;
  if(typeof persistState==='function') persistState();
  go('sim-detail');
}

function aiReviewBlock(sim,rev){
  const color=v=>v>=75?'var(--green)':v>=55?'var(--accent)':'var(--amber)';
  return `<div class="ai-review">
    <div class="ar-top">
      ${ico('bot')}
      <span class="ar-t">Разбор решения</span>
      <span class="ar-score">${rev.total}<span style="font-size:14px;opacity:.7">/100</span></span>
    </div>
    <div class="ar-body">
      ${rev.scores.map(x=>`<div class="ai-score-row">
        <span class="as-n">${x.name}<span style="color:var(--faint);font-size:11px"> · вес ${x.weight}%</span></span>
        <div class="as-bar"><i style="width:${x.value}%;background:${color(x.value)}"></i></div>
        <span class="as-v" style="color:${color(x.value)}">${x.value}</span>
      </div>`).join('')}

      <div style="margin-top:16px">
        <div class="section-label" style="margin:0 0 8px;color:var(--green)">Что удалось</div>
        <ul style="margin:0;padding-left:18px;font-size:13px;color:var(--ink);line-height:1.8">
          ${rev.strengths.map(x=>`<li>${x}</li>`).join('')||'<li style="color:var(--muted)">Пока нечего отметить</li>'}
        </ul>
      </div>
      <div style="margin-top:14px">
        <div class="section-label" style="margin:0 0 8px;color:var(--amber-ink)">Что улучшить</div>
        <ul style="margin:0;padding-left:18px;font-size:13px;color:var(--muted);line-height:1.8">
          ${rev.gaps.map(x=>`<li>${x}</li>`).join('')||'<li>Хороший ответ, замечаний нет</li>'}
        </ul>
      </div>

      <div class="ai-note">${ico('alert')}<span>Это <b>демонстрационный разбор</b>: оценка выводится из формальных признаков текста (длина, структура, наличие цифр и метрик), а не из его смысла. Настоящая проверка требует языковой модели.</span></div>
    </div>
  </div>`;
}

/* ============================================================
   APPLICATIONS — a real funnel: stage, history, next action
   ============================================================ */
const APP_STAGES=[
  ['sent',      'Отправлен',   'var(--faint)',  'Компания ещё не открывала отклик'],
  ['screening', 'Скрининг',    'var(--accent)', 'Резюме на рассмотрении у рекрутёра'],
  ['interview', 'Интервью',    'var(--purple)', 'Назначена встреча'],
  ['offer',     'Оффер',       'var(--green)',  'Вам предложили место'],
  ['rejected',  'Отказ',       'var(--red)',    'В этот раз не сложилось'],
];
function stageMeta(k){ return APP_STAGES.find(x=>x[0]===k)||APP_STAGES[0]; }
/* Deterministic mock progression: the stage depends on how complete the profile is
   and on the job id — the same student always sees the same picture. */
function appStage(jobId){
  profileInit();
  const custom=(MOCK.profile.appStages||{})[jobId];
  if(custom) return custom;
  const c=profileChecklist().filter(x=>x.done).length;   // 0..8
  const done=(MOCK.profile.doneSims||[]).length;
  const strength=c+done*2;
  if(strength>=11 && jobId%4===0) return 'offer';
  if(strength>=8  && jobId%3===0) return 'interview';
  if(strength>=5) return 'screening';
  if(strength<3 && jobId%5===4) return 'rejected';
  return 'sent';
}
function appHistory(jobId){
  const st=appStage(jobId);
  const order=['sent','screening','interview','offer'];
  const idx=order.indexOf(st);
  const rows=[{k:'sent',t:'Отклик отправлен',d:'Резюме и портфолио ушли рекрутёру'}];
  if(st==='rejected'){ rows.push({k:'rejected',t:'Отказ',d:'Компания выбрала другого кандидата'}); return rows; }
  if(idx>=1) rows.push({k:'screening',t:'Резюме просмотрено',d:'Рекрутёр открыл ваш профиль'});
  if(idx>=2) rows.push({k:'interview',t:'Приглашение на интервью',d:'Свяжутся для согласования времени'});
  if(idx>=3) rows.push({k:'offer',t:'Оффер',d:'Осталось обсудить условия'});
  return rows;
}
function appNextAction(jobId){
  const st=appStage(jobId);
  if(st==='sent')      return {t:'Усильте профиль, пока ждёте',go:'resume',b:'Дополнить резюме'};
  if(st==='screening') return {t:'Рекрутёр смотрит профиль — добавьте портфолио',go:'portfolio',b:'Открыть портфолио'};
  if(st==='interview') return {t:'Подготовьтесь к интервью',go:'simulations',b:'Потренироваться на кейсе'};
  if(st==='offer')     return {t:'Поздравляем — обсудите условия',go:'messages',b:'Написать компании'};
  return {t:'Не сдавайтесь — откликнитесь на похожую вакансию',go:'jobs',b:'Смотреть вакансии'};
}
function setAppStage(jobId,stage){
  profileInit();
  if(!MOCK.profile.appStages) MOCK.profile.appStages={};
  MOCK.profile.appStages[jobId]=stage;
  logStage(jobId,stage);         // keep the history instead of overwriting it
  if(typeof persistState==='function') persistState();
  state._appOpen=jobId;          // keep the card expanded across the redraw
  go('applications');
}
function setAppFilter(f){ state._appFilter=f; go('applications'); }

/* ============================================================
   PORTFOLIO — built from submitted simulations, nothing invented
   ============================================================ */
function portfolioItems(){
  profileInit();
  const done=MOCK.profile.doneSims||[];
  return done.map(id=>{
    const sim=SIMS.find(s=>s.id===id);
    const rev=simReview(id);
    return sim?{sim,rev}:null;
  }).filter(Boolean);
}
function portfolioScore(){
  const items=portfolioItems().filter(x=>x.rev);
  if(!items.length) return 0;
  return Math.round(items.reduce((a,x)=>a+x.rev.total,0)/items.length);
}

/* ============================================================
   CANDIDATE SEARCH (company) — a searchable talent pool
   ============================================================ */
const TALENT=[
  {id:0,n:'Анна Каримова',   u:'ТУИТ',            course:'4-й курс', skills:['SQL','Python','Дашборды','Аналитика'],   sims:4, score:88, city:'Ташкент',   field:'IT',        status:'active'},
  {id:1,n:'Игорь Петров',    u:'Вестминстер',      course:'3-й курс', skills:['Продукт','A/B','Аналитика'],             sims:3, score:81, city:'Ташкент',   field:'IT',        status:'active'},
  {id:2,n:'Мария Соколова',  u:'ТГЭУ',             course:'4-й курс', skills:['SMM','Копирайтинг','CRO'],               sims:2, score:74, city:'Ташкент',   field:'Маркетинг', status:'open'},
  {id:3,n:'Дилшод Рахимов',  u:'ТУИТ',             course:'2-й курс', skills:['SQL','Excel','Аналитика'],               sims:2, score:71, city:'Самарканд', field:'IT',        status:'active'},
  {id:4,n:'Нилуфар Азимова', u:'Инха',             course:'4-й курс', skills:['Figma','UX','Прототипы'],                sims:3, score:85, city:'Ташкент',   field:'Дизайн',    status:'active'},
  {id:5,n:'Тимур Бобоев',    u:'ТУИТ',             course:'4-й курс', skills:['SQL','Python','ML','Дашборды'],          sims:5, score:92, city:'Ташкент',   field:'IT',        status:'active'},
  {id:6,n:'Севара Юсупова',  u:'Финансовый инст.', course:'3-й курс', skills:['Excel','Финмодели','Отчётность'],        sims:2, score:78, city:'Бухара',    field:'Финансы',   status:'open'},
  {id:7,n:'Азиз Турсунов',   u:'Туринский политех',course:'3-й курс', skills:['Тестирование','API','Автотесты'],        sims:3, score:80, city:'Ташкент',   field:'IT',        status:'active'},
  {id:8,n:'Камола Хасанова', u:'ТГПУ',             course:'2-й курс', skills:['Рекрутинг','Онбординг','Коммуникация'],  sims:1, score:69, city:'Наманган',  field:'HR',        status:'open'},
];
function candFit(c){
  const q=(state._candSkills||[]);
  if(!q.length) return c.score;
  const hits=q.filter(s=>c.skills.some(x=>x.toLowerCase().includes(s.toLowerCase()))).length;
  return Math.min(99, Math.round(c.score*0.6 + (hits/q.length)*40));
}
/* Match Score кандидата витрины под HTD-заказ.
   Навыки кандидата в витрине считаем верифицированными (source='mentor'),
   т.к. витрина по определению показывает только подтверждённые навыки. */
function talentMatch(c, order){
  if(!order) return null;
  const skills=(c.id===0?verifiedSkills().map(s=>s.name):c.skills).map(name=>({name,source:'mentor'}));
  return matchScore(order.skills, skills);
}
function setShowcaseOrder(id){ state._showcaseOrder = id||null; go('talent-showcase'); }
function toggleCandSkill(s){
  const a=state._candSkills||(state._candSkills=[]);
  const i=a.indexOf(s); if(i>-1)a.splice(i,1); else a.push(s);
  go('candidate-search');
}
function setCandQuery(q){
  state._candQuery=q;
  const c=document.getElementById('content'); if(!c) return;
  const wrap=document.createElement('div'); wrap.innerHTML=PAGES['company:candidate-search']();
  const fresh=wrap.querySelector('.cand-grid, .empty');
  const cur=c.querySelector('.cand-grid, .empty');
  if(fresh&&cur) cur.replaceWith(fresh); else go('candidate-search');
}

/* ============================================================
   PLACEMENT (university) — where the students actually landed
   ============================================================ */
const PLACEMENT={
  funnel:[['Всего студентов',342,'var(--faint)'],['Прошли диагностику',287,'var(--accent)'],
          ['Сдали симуляции',196,'var(--purple)'],['Откликнулись',134,'var(--teal)'],
          ['Получили интервью',71,'var(--amber)'],['Получили оффер',47,'var(--green)']],
  employers:[['Ozon','O','#005BFF',12,'Аналитика, разработка'],['Uzum','U','#7000FF',9,'Продукт, фронтенд'],
             ['EPAM','E','#38B049',8,'QA, дизайн'],['Payme','P','#12A5A0',7,'Продажи, тестирование'],
             ['TBC Bank','T','#00AEEF',6,'Финансы'],['Click','C','#00A6D6',5,'Маркетинг']],
  byCohort:[['Аналитика данных · 2025',48,14],['Продуктовый менеджмент · 2025',36,9],
            ['Дизайн · 2025',29,8],['Маркетинг · 2025',41,11],['Финансы · 2025',33,5]],
};

/* applications are real: they persist and drive the profile counter */
function appliedTo(id){ profileInit(); return (MOCK.profile.appliedJobs||[]).includes(id); }
function applyToJob(id){
  profileInit();
  if(!Array.isArray(MOCK.profile.appliedJobs)) MOCK.profile.appliedJobs=[];
  if(!MOCK.profile.appliedJobs.includes(id)){
    MOCK.profile.appliedJobs.push(id);
    MOCK.profile.applications=MOCK.profile.appliedJobs.length;
    appMeta(id).appliedAt=Date.now();          // remember when, so we can show "3 дня назад"
    persistState();
  }
  toast('Отклик отправлен — смотрите этапы в «Мои отклики»');
  go('job-detail');
}
/* per-application metadata: date, note, interview slot, archive, stage history */
function appMeta(id){
  profileInit();
  if(!MOCK.profile.appMeta||typeof MOCK.profile.appMeta!=='object') MOCK.profile.appMeta={};
  const m=MOCK.profile.appMeta[id] || (MOCK.profile.appMeta[id]={});
  if(typeof m.appliedAt!=='number') m.appliedAt=Date.now();
  if(typeof m.note!=='string')      m.note='';
  if(typeof m.archived!=='boolean') m.archived=false;
  if(typeof m.interview!=='string') m.interview='';       // ISO datetime, set by the student
  if(!Array.isArray(m.log))         m.log=[{stage:'sent',at:m.appliedAt}];
  return m;
}
/* ---- stage history: every change is recorded, nothing is silently overwritten ---- */
function logStage(id,stage){
  const m=appMeta(id);
  const last=m.log[m.log.length-1];
  if(last && last.stage===stage) return;
  m.log.push({stage,at:Date.now()});
}
function stageLog(id){ return appMeta(id).log||[]; }

/* ---- interview scheduling ---- */
function setInterview(id,iso){
  appMeta(id).interview=iso;
  if(iso && appStage(id)!=='interview'){ /* scheduling implies the stage */ }
  if(typeof persistState==='function') persistState();
  state._appOpen=id; go('applications');
}
function fmtDateTime(iso){
  if(!iso) return '';
  const d=new Date(iso);
  if(isNaN(d)) return '';
  const days=['вс','пн','вт','ср','чт','пт','сб'];
  const mm=['янв','фев','мар','апр','мая','июн','июл','авг','сен','окт','ноя','дек'];
  return `${days[d.getDay()]}, ${d.getDate()} ${mm[d.getMonth()]} · ${String(d.getHours()).padStart(2,'0')}:${String(d.getMinutes()).padStart(2,'0')}`;
}
function interviewCountdown(iso){
  if(!iso) return null;
  const diff=new Date(iso)-Date.now();
  if(isNaN(diff)) return null;
  if(diff<0) return {past:true,t:'Интервью прошло'};
  const h=Math.round(diff/3600000);
  if(h<1)  return {soon:true,t:'Меньше часа!'};
  if(h<24) return {soon:true,t:`Через ${h} ${plural(h,'час','часа','часов')}`};
  const d=Math.round(h/24);
  return {t:`Через ${d} ${plural(d,'день','дня','дней')}`};
}
/* real .ics file — opens in any calendar app */
function exportInterviewICS(id){
  const m=appMeta(id); const job=JOBS.find(j=>j.id===id);
  if(!m.interview||!job){ toast('Сначала укажите дату интервью'); return; }
  const start=new Date(m.interview);
  const end=new Date(start.getTime()+60*60000);
  const fmt=d=>d.toISOString().replace(/[-:]/g,'').split('.')[0]+'Z';
  const ics=['BEGIN:VCALENDAR','VERSION:2.0','PRODID:-//Zero-to-Hero//RU','BEGIN:VEVENT',
    `UID:z2h-${id}-${Date.now()}@z2h.uz`,
    `DTSTAMP:${fmt(new Date())}`,`DTSTART:${fmt(start)}`,`DTEND:${fmt(end)}`,
    `SUMMARY:Интервью · ${job.co} · ${job.t}`,
    `DESCRIPTION:${(m.note||'Собеседование по вакансии '+job.t).replace(/\n/g,' ')}`,
    `LOCATION:${job.loc}`,'END:VEVENT','END:VCALENDAR'].join('\r\n');
  try{
    const blob=new Blob([ics],{type:'text/calendar'});
    const a=document.createElement('a');
    a.href=URL.createObjectURL(blob);
    a.download=`interview-${job.co.toLowerCase()}.ics`;
    document.body.appendChild(a); a.click(); a.remove();
    setTimeout(()=>URL.revokeObjectURL(a.href),1000);
    toast('Файл календаря скачан');
  }catch(e){ toast('Не удалось создать файл'); }
}

/* ---- archive: rejections stop cluttering the active list ---- */
function toggleArchive(id){
  const m=appMeta(id);
  m.archived=!m.archived;
  if(typeof persistState==='function') persistState();
  toast(m.archived?'Отклик в архиве':'Возвращён в активные');
  state._appOpen=null; go('applications');
}
function setAppQuery(q){
  state._appQuery=q;
  const c=document.getElementById('content'); if(!c) return;
  const wrap=document.createElement('div'); wrap.innerHTML=PAGES['student:applications']();
  const fresh=wrap.querySelector('#app-list');
  const cur=c.querySelector('#app-list');
  if(fresh&&cur) cur.replaceWith(fresh); else go('applications');
}
/* jump straight into a conversation with this employer */
function openChat(companyName){
  state._chatWith=companyName;
  go('messages');
  toast(`Переписка с ${companyName}`);
}
function withdrawApp(id){
  const job=JOBS.find(j=>j.id===id);
  if(!confirm(`Отозвать отклик на «${job?job.t:'вакансию'}»? Вернуть его будет нельзя.`)) return;
  profileInit();
  MOCK.profile.appliedJobs=(MOCK.profile.appliedJobs||[]).filter(x=>x!==id);
  MOCK.profile.applications=MOCK.profile.appliedJobs.length;
  if(MOCK.profile.appMeta) delete MOCK.profile.appMeta[id];
  if(MOCK.profile.appStages) delete MOCK.profile.appStages[id];
  persistState();
  toast('Отклик отозван');
  go('applications');
}
let _noteSave=null;
function saveAppNote(id,text){
  appMeta(id).note=text;
  clearTimeout(_noteSave);
  _noteSave=setTimeout(()=>{ if(typeof persistState==='function') persistState(); },400);
}
/* days since the application was sent */
function daysAgo(ts){
  if(!ts) return 0;
  return Math.max(0, Math.floor((Date.now()-ts)/86400000));
}
function fmtAgo(ts){
  const d=daysAgo(ts);
  if(d===0) return 'сегодня';
  if(d===1) return 'вчера';
  return `${d} ${plural(d,'день','дня','дней')} назад`;
}
/* a nudge when an application has been sitting untouched */
function appNudge(id,stage){
  const d=daysAgo(appMeta(id).appliedAt);
  if(stage==='offer'||stage==='rejected') return null;
  if(stage==='sent' && d>=7)      return {t:`Тишина ${d} ${plural(d,'день','дня','дней')}`,d:'Компании чаще отвечают тем, у кого заполнено портфолио'};
  if(stage==='screening' && d>=10) return {t:'Долгий скрининг',d:'Можно вежливо напомнить о себе в сообщениях'};
  return null;
}
/* funnel conversion, computed from the real list */
function appStats(ids){
  const stages=ids.map(id=>appStage(id));
  const n=stages.length||1;
  const past=k=>{
    const order=['sent','screening','interview','offer'];
    const i=order.indexOf(k);
    return stages.filter(s=>s!=='rejected'&&order.indexOf(s)>=i).length;
  };
  const offers=stages.filter(s=>s==='offer').length;
  const interviews=past('interview');
  const rejected=stages.filter(s=>s==='rejected').length;
  const avgDays=ids.length?Math.round(ids.reduce((a,id)=>a+daysAgo(appMeta(id).appliedAt),0)/ids.length):0;
  return {
    total:stages.length, offers, interviews, rejected,
    toInterview:Math.round(interviews/n*100),
    toOffer:Math.round(offers/n*100),
    avgDays,
  };
}
function setAppSort(v){ state._appSort=v; go('applications'); }

/* Expand/collapse in place — no page redraw, so the scroll position stays put.
   (The old version called go('applications') and jumped the user to the top.) */
function toggleApp(id){
  const card=document.getElementById('app-'+id);
  const body=document.getElementById('app-body-'+id);
  if(!card||!body) return;
  const opening=body.classList.contains('hidden');
  /* accordion: only one open at a time keeps the list scannable */
  document.querySelectorAll('.appcard.open').forEach(c=>{
    if(c!==card){ c.classList.remove('open'); const b=c.querySelector('.app-body'); if(b) b.classList.add('hidden'); }
  });
  body.classList.toggle('hidden',!opening);
  card.classList.toggle('open',opening);
  state._appOpen = opening?id:null;
}
function flashNote(id){
  const el=document.getElementById('note-ok-'+id); if(!el) return;
  el.classList.add('on');
  clearTimeout(el._t);
  el._t=setTimeout(()=>el.classList.remove('on'),1200);
}
/* after a redraw, reopen whatever the user had expanded */
function restoreAppOpen(){
  const id=state._appOpen;
  if(id==null) return;
  const card=document.getElementById('app-'+id), body=document.getElementById('app-body-'+id);
  if(card&&body){ body.classList.remove('hidden'); card.classList.add('open'); }
}

/* legacy row (still used by university/company pages) */
function setRow(t,d,on,val,action){return `<div class="set-row"><div><div class="st">${t}</div><div class="sd">${d}</div></div><div class="set-ctl">${val?`<span class="badge b-gray">${val}</span>`:`<div class="toggle ${on?'on':''}" onclick="this.classList.toggle('on');${action||''}"></div>`}</div></div>`;}

/* ---- settings controls: every one writes into PREFS and applies live ---- */
function sRow(icon,title,desc,ctl,warn){
  return `<div class="set-row">
    <div><div class="st">${icon?ico(icon):''}${title}${warn?`<span class="set-warn">${warn}</span>`:''}</div><div class="sd">${desc}</div></div>
    <div class="set-ctl">${ctl}</div>
  </div>`;
}
function sToggle(key,extra){
  const on=!!PREFS[key];
  return `<div class="toggle ${on?'on':''}" onclick="setPref('${key}',${!on});${extra||''}"></div>`;
}
function sSeg(key,opts){
  return `<div class="seg-ctl">${opts.map(o=>`<button class="${PREFS[key]===o[0]?'on':''}" onclick="setPref('${key}','${o[0]}')">${o[1]}</button>`).join('')}</div>`;
}
function sSwatches(key,opts){
  return `<div class="sw-row">${opts.map(o=>`<div class="sw ${PREFS[key]===o[0]?'on':''}" style="background:${o[1]}" title="${o[2]}" onclick="setPref('${key}','${o[0]}')"></div>`).join('')}</div>`;
}
function sRange(key,min,max,step,suffix){
  return `<div class="set-range">
    <input type="range" min="${min}" max="${max}" step="${step}" value="${PREFS[key]}"
           oninput="previewFontScale(this.value)" onchange="setPref('${key}',+this.value)">
    <span class="rv" id="rv-${key}">${PREFS[key]}${suffix||''}</span>
  </div>`;
}
/* live preview while dragging, before the value is committed */
function previewFontScale(v){
  document.body.style.setProperty('--font-scale', v/100);
  const el=document.getElementById('rv-fontScale'); if(el) el.textContent=v+'%';
}
function setSettingsTab(t){ state._setTab=t; go('settings'); }

/* ---- real browser push permission (this one genuinely works) ---- */
async function requestPush(){
  if(!('Notification' in window)){ toast('Браузер не поддерживает уведомления'); return; }
  if(Notification.permission==='denied'){ toast('Уведомления заблокированы в настройках браузера'); return; }
  try{
    const p = Notification.permission==='granted' ? 'granted' : await Notification.requestPermission();
    if(p==='granted'){
      setPref('pushEnabled',true);
      new Notification('Zero-to-Hero',{body:'Уведомления включены. Сообщим о новых вакансиях.'});
    }else{ setPref('pushEnabled',false); toast('Разрешение не выдано'); }
  }catch(e){ toast('Не удалось запросить разрешение'); }
}
function pushState(){
  if(!('Notification' in window)) return 'unsupported';
  return Notification.permission; // default | granted | denied
}

/* ---- data management: export / import / wipe (all real) ---- */
/* enumerate our keys reliably (Object.keys on Storage is not universal) */
function z2hKeys(){
  const out=[];
  try{ for(let i=0;i<localStorage.length;i++){ const k=localStorage.key(i); if(k&&k.startsWith('z2h_')) out.push(k); } }catch(e){}
  return out;
}
function storageBytes(){
  let n=0;
  z2hKeys().forEach(k=>{ try{ n+=(localStorage.getItem(k)||'').length; }catch(e){} });
  return n;
}
function exportData(){
  const dump={};
  z2hKeys().forEach(k=>{ try{ dump[k]=localStorage.getItem(k); }catch(e){} });
  const blob=new Blob([JSON.stringify(dump,null,2)],{type:'application/json'});
  const a=document.createElement('a');
  a.href=URL.createObjectURL(blob);
  a.download='z2h-my-data.json';
  document.body.appendChild(a); a.click(); a.remove();
  setTimeout(()=>URL.revokeObjectURL(a.href),1000);
  toast('Данные выгружены');
}
function importData(){
  let inp=document.getElementById('z2h-import');
  if(!inp){
    inp=document.createElement('input'); inp.type='file'; inp.accept='application/json'; inp.id='z2h-import'; inp.style.display='none';
    inp.addEventListener('change',()=>{
      const f=inp.files&&inp.files[0]; if(!f) return;
      const r=new FileReader();
      r.onload=()=>{
        try{
          const obj=JSON.parse(r.result);
          Object.keys(obj).filter(k=>k.startsWith('z2h_')).forEach(k=>localStorage.setItem(k,obj[k]));
          toast('Данные загружены — перезагружаю');
          setTimeout(()=>location.reload(),700);
        }catch(e){ toast('Файл повреждён'); }
      };
      r.readAsText(f); inp.value='';
    });
    document.body.appendChild(inp);
  }
  inp.click();
}
function wipeData(){
  if(!confirm('Удалить все локальные данные: профиль, резюме, диагностику, настройки? Это необратимо.')) return;
  z2hKeys().forEach(k=>{ try{ localStorage.removeItem(k); }catch(e){} });
  toast('Всё удалено — перезагружаю');
  setTimeout(()=>location.reload(),700);
}
function resetPrefs(){
  if(!confirm('Сбросить настройки к значениям по умолчанию?')) return;
  PREFS={...PREFS_DEFAULT}; savePrefs(); applyPrefs(); go('settings'); toast('Настройки сброшены');
}
function replayTour(){
  toast('Тур запущен');
  setTimeout(()=>{ go('home'); setTimeout(tourBegin,250); },300);
}
function clearHeroChat(){
  if(typeof heroReset==='function'){ heroReset(); heroShowFab(); }
  toast('История Hero очищена');
}
function doLogout(){
  if(!confirm('Выйти из аккаунта? Данные останутся на этом устройстве.')) return;
  clearState(); show('scr-public');
}
function gapMatrix(){
  const comps=['SQL','Python','A/B-тесты','Коммуникация','Продукт','Маркетинг'];
  const lvls=['Junior','Middle','Senior'];
  const colors=['#0F9E75','#9FE1CB','#E24B4A'];
  const glyph=['●●●','●●','●'];
  /* fixed matrix: 0=сильно 1=средне 2=пробел — растёт к Senior */
  const GRID=[
    [0,1,2],[0,1,2],[1,2,2],
    [0,0,1],[1,1,2],[1,2,2],
  ];
  let html=`<div class="matrix" style="grid-template-columns:120px repeat(3,1fr)">`;
  html+=`<div class="mhead"></div>`+lvls.map(l=>`<div class="mhead">${l}</div>`).join('');
  comps.forEach((c,ri)=>{
    html+=`<div class="mrow-label">${c}</div>`;
    lvls.forEach((_,ci)=>{const i=GRID[ri][ci];html+=`<div class="mcell" style="background:${colors[i]}">${glyph[i]}</div>`;});
  });
  html+=`</div>`;return html;
}
function chatUI(convos){
  return ph("Сообщения","Прямое общение — студент, куратор, HR")+`
  <div class="chat">
    <div class="chat-side">
      ${convos.map((c,i)=>`<div class="chat-c ${i===0?'on':''}" onclick="document.querySelectorAll('.chat-c').forEach(x=>x.classList.remove('on'));this.classList.add('on')"><div class="cn">${c[0]}</div><div class="cp">${c[1]} · ${c[2]}</div></div>`).join('')}
    </div>
    <div class="chat-main">
      <div class="chat-msgs">
        <div class="msg them">${convos[0][2]}</div>
        <div class="msg me">Здравствуйте! Да, мне удобно.</div>
        <div class="msg them">Отлично, тогда до встречи ${ico('check')}</div>
      </div>
      <div class="chat-input"><input placeholder="Сообщение…" onkeydown="if(event.key==='Enter'&&this.value){const m=document.querySelector('.chat-msgs');m.insertAdjacentHTML('beforeend','<div class=&quot;msg me&quot;>'+this.value+'</div>');this.value='';m.scrollTop=m.scrollHeight;}"><button class="btn btn-primary btn-sm" onclick="chatSend(this)">Отпр.</button></div>
    </div>
  </div>`;
}

/* ---- detail openers ---- */
function openSim(id){state._sim=id;go('sim-detail');}
function openJob(id){state._job=id;go('job-detail');}
/* живой обратный отсчёт до дедлайна вакансии (как career.edu.uz).
   Дата дедлайна детерминирована (от TODAY), тикаем к ней от реального «сейчас». */
let _cdTimer=null;
function startCountdown(){
  if(_cdTimer){ clearInterval(_cdTimer); _cdTimer=null; }
  const el=document.getElementById('cd-timer'); if(!el) return;
  const deadline=el.getAttribute('data-deadline'); if(!deadline) return;
  const end=new Date(deadline+'T23:59:59').getTime();
  const tick=()=>{
    const now=Date.now();
    let diff=Math.max(0, end-now);
    const days=Math.floor(diff/86400000); diff-=days*86400000;
    const h=Math.floor(diff/3600000); diff-=h*3600000;
    const m=Math.floor(diff/60000); diff-=m*60000;
    const s=Math.floor(diff/1000);
    const pad=n=>String(n).padStart(2,'0');
    const cur=document.getElementById('cd-timer');
    if(!cur){ if(_cdTimer){clearInterval(_cdTimer);_cdTimer=null;} return; }
    cur.innerHTML=`<b>${days}</b> ${plural(days,'день','дня','дней')} <span class="cd-sep">|</span> <b>${pad(h)}:${pad(m)}:${pad(s)}</b>`;
  };
  tick(); _cdTimer=setInterval(tick,1000);
}
function openCompany(id){state._co=id;go('company-detail');}
function openTalent(id){state._talent=id;go('talent-detail');}
/* ===== BRIDGE: пейволл витрины талантов (MOCK) ===== */
function talentUnlock(id){ // MOCK: разблокировка контактов одного студента
  state._talentUnlocked=[...(state._talentUnlocked||[]),id];
  toast('Контакты разблокированы (демо — оплаты нет)');
  go('talent-showcase');
}
function talentBuyPremium(){ // MOCK: premium-подписка компании
  state._talentPremium=true;
  toast('Premium-доступ активирован (демо — биллинга нет)');
  go('talent-showcase');
}
function setCoQuery(q){
  state._coQuery=q;
  go('companies');
  const inp=document.querySelector('.jobs-search input');
  if(inp){ inp.focus(); inp.setSelectionRange(q.length,q.length); }
}
function setEvFilter(f){state._evFilter=f;go('events');}
function setCourseFilter(c){state._courseFilter=c;go('jobs');}
function setJobFilter(f){state._jobFilter=f;go('jobs');}
function setJobExtra(key,val){ state[key]=val||''; go('jobs'); }
function setJobSeg(s){ state._jobSeg=s; go('jobs'); }
function clearJobExtra(){ state._jobFmt=state._jobType=state._jobLvl=''; go('jobs'); }
function setJobView(v){state._jobView=v;go('jobs');}
function setJobQuery(q){
  state._jobQuery=q;
  /* re-render only the results area to preserve input focus */
  const c=document.getElementById('content'); if(!c) return;
  const wrap=document.createElement('div'); wrap.innerHTML=PAGES['student:jobs']();
  const newRes=wrap.querySelector('.jobs-grid, .jobs-list, .empty');
  const cur=c.querySelector('.jobs-grid, .jobs-list, .empty');
  if(newRes&&cur) cur.replaceWith(newRes); else go('jobs');
}
function openCohort(i){state._cohort=i;go('cohort-detail');}
function openStudent(i){state._student=i||0;go('student-detail');}

/* ===== CORE helpers ===== */
function diaryBadge(e){
  const map={approved:['b-green','Подтверждено'],submitted:['b-amber','На проверке'],overdue:['b-red','Просрочено'],draft:['b-gray','Черновик']};
  const [cls,txt]=map[e.status]||['b-gray',e.status];
  return `<span class="badge ${cls}">${txt}</span>`;
}
/* график практики по неделям: прошедшие/текущая/просроченные/будущие + ближайший дедлайн.
   Строится из записей дневника (даты) и цели по часам. Демо. */
function practiceSchedule(p){
  const entries=p.entries||[];
  if(!entries.length) return '';
  // ближайшая несданная запись = ближайший дедлайн
  const pending=entries.filter(e=>e.status==='submitted'||e.status==='overdue');
  const overdue=entries.find(e=>e.status==='overdue');
  const totalWeeks=Math.ceil(p.goalHours/32); // ~32 ч/нед — оценка длительности
  const cells=[];
  for(let w=1;w<=totalWeeks;w++){
    const e=entries.find(x=>x.week===w);
    let cls='future',label='';
    if(e){
      if(e.status==='approved') cls='done';
      else if(e.status==='overdue') cls='overdue';
      else if(e.status==='submitted') cls='cur';
      label=e.date.slice(5); // MM-DD
    }
    cells.push(`<div class="psch-w ${cls}"><div class="psch-bar" title="Неделя ${w}${e?' · '+e.task:''}">${w}</div>${label?`<div class="psch-d">${label}</div>`:''}</div>`);
  }
  const nextDue = overdue ? `<span class="badge b-red">${ico('bell')} просрочена запись за неделю ${overdue.week} (срок ${overdue.due||overdue.date})</span>`
    : pending.length ? `<span class="badge b-amber">${ico('clock')} ${pending.length} ${plural(pending.length,'запись','записи','записей')} на проверке у ментора</span>`
    : `<span class="badge b-green">${ico('check')} все записи в срок</span>`;
  return `<div class="panel" style="margin-bottom:16px"><h3>${ico('calendar')} График практики</h3>
    <div class="sd" style="margin-bottom:6px">${entries.length} из ~${totalWeeks} недель · ${p.company} · демо</div>
    <div class="psch">${cells.join('')}</div>
    <div class="psch-legend">
      <span><i style="background:var(--green)"></i>сдано</span>
      <span><i style="background:var(--accent)"></i>на проверке</span>
      <span><i style="background:var(--red)"></i>просрочено</span>
      <span><i style="background:var(--hair2);border:1.5px dashed var(--hair)"></i>впереди</span>
    </div>
    <div style="margin-top:12px">${nextDue}</div>
  </div>`;
}
function openDiaryEntry(i){ state._diary=i; go('diary-entry'); }
function openHtd(i){ state._htd=i; go('htd-detail'); }
function openStudentOrder(i){ state._sOrder=i; go('order-detail'); }
/* ---- создание HTD-заказа (демо, пишет в HTD_ORDERS этой сессии) ---- */
function captureOrderDraft(){
  const d=state._orderDraft||(state._orderDraft={skills:[]});
  const g=id=>{const el=document.getElementById(id);return el?el.value:undefined;};
  const role=g('ord-role'); if(role!==undefined) d.role=role;
  const count=g('ord-count'); if(count!==undefined) d.count=+count;
  const days=g('ord-days'); if(days!==undefined) d.days=+days;
  const track=g('ord-track'); if(track!==undefined) d.track=track;
  return d;
}
function toggleOrderSkill(s){
  const d=captureOrderDraft();
  const i=d.skills.indexOf(s); if(i>-1) d.skills.splice(i,1); else d.skills.push(s);
  go('order-new');
}
function submitOrder(){
  const d=captureOrderDraft();
  if(!d.role||!d.role.trim()){ toast('Укажите роль'); return; }
  if(!d.skills.length){ toast('Выберите хотя бы один навык'); return; }
  const n=HTD_ORDERS.length+1;
  const id='HTD-'+String(20+n).padStart(2,'0');
  HTD_ORDERS.unshift({ // MOCK: no backend — живёт в памяти сессии
    id, company:(ROLE_META.company?'Ваша компания':'Компания'), role:d.role.trim(),
    count:d.count||5, deadline:dOffset(d.days||45),
    skills:d.skills.slice(), stage:'recruit',
    funnel:{applied:0, enrolled:0, training:0, deployed:0},
    track:d.track||`${d.role.trim()} · трек подготовки`,
    modules:d.skills.map(s=>`Модуль: ${s}`)
  });
  state._orderDraft=null;
  toast('Заказ '+id+' опубликован (демо)');
  go('htd');
}
/* сквозная переписка по практике: студент ↔ ментор ↔ куратор вуза. MOCK. */
function practiceThread(p){
  const cur='#3B7D22', stu='#3F5BF6', uni='#0F9E75';
  const msgs=[
    {n:p.mentor,role:'ментор · '+p.company,c:cur,t:'2 дня назад',x:`${p.student.split(' ')[0]}, по неделе 4 всё отлично. Дашборд retention можно показать команде.`},
    {n:p.student,role:'практикант',c:stu,t:'2 дня назад',x:'Спасибо! Загрузил отчёт в дневник, жду подтверждения часов.'},
    {n:'Куратор ВУЗа',role:'вуз · '+p.faculty,c:uni,t:'вчера',x:'Вижу прогресс в системе. Напоминаю: к концу месяца нужно закрыть 240 ч для зачёта практики.'},
  ];
  const ini=n=>n.split(' ').map(w=>w[0]).join('').slice(0,2);
  return `<div class="panel" style="margin-bottom:16px"><h3>${ico('chat')} Переписка по практике</h3>
    <div class="sd" style="margin-bottom:12px">Студент ↔ ментор ↔ куратор ВУЗа — в одном месте · демо, отправка не работает</div>
    <div class="pthread">
      ${msgs.map(m=>`<div class="pmsg">
        <div class="pmsg-av" style="background:${m.c}">${ini(m.n)}</div>
        <div class="pmsg-b"><div class="pmsg-h"><span class="pmsg-n">${m.n}</span><span class="pmsg-role">${m.role}</span><span class="pmsg-t">${m.t}</span></div><div class="pmsg-x">${m.x}</div></div>
      </div>`).join('')}
    </div>
    <div class="pthread-foot">
      <input placeholder="Написать ментору и куратору…" onkeydown="if(event.key==='Enter')toast('Отправка сообщений — в демо недоступна')">
      <button class="btn btn-primary btn-sm" style="width:auto" onclick="toast('Отправка сообщений — в демо недоступна')">${ico('spark')} Отправить</button>
    </div>
  </div>`;
}
function openMentorStudent(id){ state._mentorStudent=id; go('mentor-student'); }
/* ---- TASKS UI helpers ---- */
function taskCard(t){
  const tt=TASK_TYPE[t.type];
  const paid=taskIsPaid(t);
  return `<div class="tk-card" onclick="openTask('${t.id}')">
    <div class="tk-card-h"><div class="tk-card-t">${t.title}</div><span class="badge ${tt[0]}">${tt[1]}</span></div>
    <div class="tk-card-meta">${taskCompany(t)}${t.htdOrderId?' · заказ '+t.htdOrderId:''}</div>
    <div class="tk-skills">${t.skills.map(s=>`<span class="tk-skill">${s}</span>`).join('')}</div>
    <div class="tk-card-foot">
      <span class="${taskOverdue(t)?'tk-over':''}">${ico('calendar')} до ${t.deadline}${taskOverdue(t)?' · просрочено':''}</span>
      ${paid?`<span class="tk-price">${fmtMoney(t.reward.price)}</span>`:`<span>${t.applicants.length?t.applicants.length+' откл.':'без оплаты'}</span>`}
    </div>
  </div>`;
}
function openTask(id){ state._task=id; go('task-detail'); }
/* ---- FREELANCE UI ---- */
function stars(n){ let s=''; for(let i=1;i<=5;i++) s+=`<span class="tk-star ${i<=Math.round(n)?'on':''}">★</span>`; return s; }
function openFreelancer(id){ state._freelancer=id; go('freelancer'); }
function freelancersPage(role){
  const sub = role==='company' ? 'Наймите проверенного исполнителя под задание' : 'Рейтинг исполнителей платформы — и ваш профиль';
  const right = role==='student' ? `<button class="btn btn-primary btn-sm" onclick="openFreelancer(MY_STUDENT_ID)">${ico('user')} Мой профиль</button>` : '';
  const sorted=[...FREELANCERS].sort((a,b)=>b.rating-a.rating||b.done-a.done);
  return ph("Исполнители", sub, right)+
  (sorted.length?`<div class="cards">${sorted.map(f=>{const lv=FL_LEVEL[f.level];return `
    <div class="tk-fl-card" onclick="openFreelancer('${f.id}')">
      <div class="tk-fl-h">
        <div class="tk-fl-av">${f.name.split(' ').map(w=>w[0]).join('').slice(0,2)}</div>
        <div style="flex:1;min-width:0"><div class="tk-fl-name">${f.name}${f.id===MY_STUDENT_ID?' · вы':''}</div><div class="tk-fl-title">${f.title}</div></div>
        <span class="badge ${lv[0]}">${lv[1]}</span>
      </div>
      <div class="tk-fl-rate"><span class="tk-stars">${stars(f.rating)}</span><b>${f.rating}</b><span class="sd">(${f.reviews} отзывов · ${f.done} заданий)</span></div>
      <div class="tk-skills" style="margin-top:8px">${f.skills.slice(0,4).map(s=>`<span class="tk-skill">${s}</span>`).join('')}</div>
      <div class="tk-card-foot"><span class="sd">${ico('pin')} ${f.city} · ${f.from}</span><span>профиль →</span></div>
    </div>`;}).join('')}</div>`
  :emptyState('users','Пока нет исполнителей','Профили появятся, когда студенты начнут выполнять задания.'));
}
function freelancerPage(){
  const f=freelancerById(state._freelancer)||myFreelancer();
  if(!f) return ph("Профиль исполнителя","Не найден");
  const lv=FL_LEVEL[f.level];const mine=f.id===MY_STUDENT_ID;
  return back('freelancers','Исполнители')+ph(f.name+(mine?' · ваш профиль':''),f.title)+`
  <div class="panel" style="margin-bottom:16px">
    <div class="tk-fl-h" style="margin-bottom:12px">
      <div class="tk-fl-av" style="width:56px;height:56px;font-size:20px">${f.name.split(' ').map(w=>w[0]).join('').slice(0,2)}</div>
      <div style="flex:1"><div class="tk-fl-rate"><span class="tk-stars">${stars(f.rating)}</span><b>${f.rating}</b><span class="sd">${f.reviews} отзывов</span></div>
      <div class="sd" style="margin-top:4px">${ico('pin')} ${f.city} · ${f.from} · ${f.done} выполненных заданий</div></div>
      <span class="badge ${lv[0]}">${lv[1]}</span>
    </div>
    <div class="tk-skills">${f.skills.map(s=>`<span class="tk-skill">${s}</span>`).join('')}</div>
    ${(state.role==='company')?`<button class="btn btn-primary btn-sm" style="width:auto;margin-top:14px" onclick="toast('Приглашение на задание отправлено (демо)')">Пригласить на задание</button>`:''}
  </div>
  <div class="panel" style="margin-bottom:16px"><h3>Портфолио</h3>
    <div class="tk-portf">${f.portfolio.map(p=>`<div class="tk-portf-item">${ico('folder')} ${p}</div>`).join('')}</div>
  </div>
  <div class="panel"><h3>Отзывы</h3>
    ${f.feedback.length?f.feedback.map(r=>`<div class="tk-review-box" style="margin-bottom:10px">
      <div class="row" style="align-items:center"><b>${r.by}</b><span class="tk-stars">${stars(r.stars)}</span></div>
      <p style="margin-top:6px;line-height:1.5">${r.text}</p>
    </div>`).join(''):emptyState('chat','Отзывов пока нет','Отзывы появятся после первых принятых заданий.')}
  </div>`;
}
function openTaskReview(id){ state._taskReview=id; state._tkHard=0; state._tkSoft=0; go('company:task-review'); }
function setTaskFilter(k,v){ state._taskFilter={...(state._taskFilter||{})}; if(v) state._taskFilter[k]=v; else delete state._taskFilter[k]; go('tasks'); }
function clearTaskFilter(){ state._taskFilter={}; go('tasks'); }
function setTaskScore(kind,n){ if(kind==='hard') state._tkHard=n; else state._tkSoft=n; go('company:task-review'); }
function submitTaskReview(id,decision){
  const c=(document.getElementById('tk-rev-c')||{}).value||'';
  const h=state._tkHard||3, s=state._tkSoft||3;
  if(decision==='rework'){ const t=taskById(id); if(t){ t.status='in_progress'; toast('Возвращено на доработку (демо)'); notifyTask(t,'Задача возвращена на доработку: '+t.title);} go('company:tasks'); return; }
  taskReview(id,h,s,c,decision);
}
function toggleTaskHidden(id){ TASK_HIDDEN[id]=!TASK_HIDDEN[id]; toast(TASK_HIDDEN[id]?'Задача скрыта (демо)':'Задача возвращена (демо)'); go('admin:tasks'); }
function openContract(i){ state._contract=i; go('contract-detail'); }
function openContractById(cid){ const i=CONTRACTS.findIndex(c=>c.id===cid); if(i>=0){ state._contract=i; go('contract-detail'); } }
function signContract(){ // MOCK E-imzo — реалистичный флоу вместо мгновенной подписи
  const c=CONTRACTS[state._contract||0]; if(!c) return;
  const role=state.role;
  // какая сторона подписывает и не подписала ли уже
  const side = role==='university'?'uni':role==='student'?'student':role==='company'?'company':'uni';
  if(c.signed[side]){ toast('Вы уже подписали этот договор'); return; }
  openEimzoFlow(c, side);
}
/* MOCK E-imzo. Реальная реализация — через внешнего оператора ЭДО с API (E-DOCS/Faktura),
   НЕ самописная криптография. Юр-риск: постановление КМ №615 может требовать регистрацию
   договора практики на госплатформе — проверить монополию до продакшена. */
const EIMZO_CERTS=[
  {label:"O'ZBEKISTON RESPUBLIKASI · ЭЦП физического лица", who:"ключ на токене"},
  {label:"DSKEY · мобильная ЭЦП", who:"по номеру телефона"},
];
function openEimzoFlow(c, side){
  const ov=document.createElement('div'); ov.className='overlay'; ov.id='eimzo-ov';
  ov.onclick=(e)=>{ if(e.target===ov) ov.remove(); };
  ov.innerHTML=`<div class="success-modal" style="text-align:left;max-width:420px">
    <div class="row" style="align-items:center;margin-bottom:4px"><h2 class="title" style="margin:0">Подписание через E-imzo</h2></div>
    <p class="subtitle" style="margin:2px 0 16px">Договор ${c.id} · сторона: ${side==='uni'?'ВУЗ':side==='student'?'Студент':'Компания'}</p>
    <div id="eimzo-body"></div>
  </div>`;
  document.body.appendChild(ov);
  eimzoStepCert(c, side);
}
function eimzoStepCert(c, side){
  const b=document.getElementById('eimzo-body'); if(!b) return;
  b.innerHTML=`<div class="sd" style="margin-bottom:10px">Выберите сертификат ключа</div>
    ${EIMZO_CERTS.map((cert,i)=>`<div class="eimzo-cert" onclick="eimzoStepConnect('${c.id}','${side}',${i})">
      <div>${ico('card')}</div><div style="flex:1"><div style="font-weight:600;font-size:13px">${cert.label}</div><div class="sd">${cert.who}</div></div><span>${ico('compass')}</span>
    </div>`).join('')}
    <button class="btn btn-ghost btn-sm" style="margin-top:12px" onclick="document.getElementById('eimzo-ov').remove()">Отмена</button>`;
}
function eimzoStepConnect(cid, side, certIdx){
  const b=document.getElementById('eimzo-body'); if(!b) return;
  b.innerHTML=`<div style="text-align:center;padding:20px 0">
    <div class="eimzo-spin"></div>
    <div style="margin-top:14px;font-weight:600">Подключение к E-imzo…</div>
    <div class="sd" style="margin-top:4px">${EIMZO_CERTS[certIdx].label}</div>
  </div>`;
  setTimeout(()=>eimzoConfirm(cid, side), 1400); // имитация задержки соединения с провайдером
}
function eimzoConfirm(cid, side){
  const c=CONTRACTS.find(x=>x.id===cid)||CONTRACTS[state._contract||0]; if(!c) return;
  c.signed[side]=true;
  if(c.signed.uni&&c.signed.student&&c.signed.company) c.status='signed';
  else if(!c.signed.student) c.status='awaiting_student';
  else if(!c.signed.company) c.status='awaiting_company';
  const p=practiceByContract(c.id); if(p) p.contractStatus=c.status; // синхрон с единой моделью
  notify('doc','Договор', c.status==='signed'?`Договор ${c.id} подписан всеми сторонами — практика активна`:`Ваша подпись в договоре ${c.id} поставлена`);
  // mock-хеш подписи + метка времени
  const hash='0x'+Array.from({length:8},()=>Math.floor(Math.random()*16).toString(16)).join('')+'…';
  c.signatures=c.signatures||{}; c.signatures[side]={at:new Date().toISOString().slice(0,16).replace('T',' '), hash};
  const b=document.getElementById('eimzo-body');
  if(b) b.innerHTML=`<div style="text-align:center">
    <div class="si" style="width:56px;height:56px;font-size:26px;margin:0 auto 12px">✓</div>
    <div style="font-weight:700;font-size:15px">Подпись поставлена</div>
    <div class="sd" style="margin:8px 0 2px">${c.signatures[side].at}</div>
    <div class="mono" style="font-size:11px;color:var(--muted)">хеш: ${hash}</div>
    <div class="sd" style="margin:12px 0 14px">${c.status==='signed'?'Все три стороны подписали — договор вступил в силу, дневник практики открыт.':'Ожидаются подписи остальных сторон.'}</div>
    <button class="btn btn-primary btn-sm" onclick="document.getElementById('eimzo-ov').remove();go('contract-detail')">Готово</button>
  </div>`;
  else { toast('Подписано через E-imzo (демо)'); go('contract-detail'); }
}
function contractsList(role){
  const title = role==='admin' ? 'Реестр договоров' : 'Договоры практики';
  return ph(title,"Трёхсторонние договоры · вуз + студент + компания",`<button class="btn btn-primary btn-sm" onclick="toast('Новый договор — в демо недоступен')">＋ Новый договор</button>`)+
  (CONTRACTS.length?`
  <div class="panel" style="padding:0;overflow:hidden">
    <table class="tbl">
      <thead><tr><th>№ договора</th><th>Студент</th><th>Компания</th><th>Факультет</th><th>Статус</th></tr></thead>
      <tbody>
      ${CONTRACTS.map((c,i)=>{const st=CONTRACT_STATUS[c.status]||['b-gray',c.status];return `
        <tr onclick="openContract(${i})" style="cursor:pointer">
          <td class="nm mono">${c.id}</td><td>${c.student}</td><td>${c.company}</td>
          <td>${c.faculty}</td><td><span class="badge ${st[0]}">${st[1]}</span></td>
        </tr>`;}).join('')}
      </tbody>
    </table>
  </div>
  <div class="sd" style="margin-top:12px">MOCK: подписание имитирует E-imzo, реальной интеграции нет.</div>`
  :emptyState('list','Договоров пока нет','Создайте первый трёхсторонний договор практики — выберите студента, компанию-партнёра и программу. Стороны подпишут его через E-imzo.',{label:'＋ Новый договор',onclick:"toast('Новый договор — в демо недоступен')"}));
}
function kpiDashboard(role){
  const title = role==='admin' ? 'Сводный KPI по вузам' : 'KPI деканата';
  const KF=kpiFaculties();
  const totalStud=KF.reduce((s,f)=>s+f.students,0);
  const totalIntern=KF.reduce((s,f)=>s+f.onInternship,0);
  const totalEmp=KF.reduce((s,f)=>s+f.employed,0);
  const empRate=Math.round(totalEmp/totalStud*100);
  /* «Индекс качества выпускника» — mock-расчёт: трудоустройство*0.5 + практика*0.3 + оценки*0.2 */
  const qIdx=Math.round((empRate*0.5 + (totalIntern/totalStud*100)*0.3 + (KF.reduce((s,f)=>s+f.avgGrade,0)/KF.length/5*100)*0.2));
  const cst={signed:['b-green','договор подписан'],awaiting_company:['b-amber','ждёт компанию'],awaiting_student:['b-amber','ждёт студента'],draft:['b-gray','черновик']};
  return ph(title,"Аналитика трудоустройства под гос-KPI по занятости выпускников",`<button class="btn btn-primary btn-sm" onclick="toast('Экспорт отчёта — демо (реальной выгрузки нет)')">${ico('list')} Экспорт</button>`)+`
  <div class="cards" style="margin-bottom:16px">
    <div class="simcard"><div class="sc-t" style="font-size:26px">${empRate}%</div><div class="sc-meta">трудоустройство выпускников</div></div>
    <div class="simcard"><div class="sc-t" style="font-size:26px">${totalIntern}</div><div class="sc-meta">на практике сейчас</div></div>
    <div class="simcard"><div class="sc-t" style="font-size:26px">${qIdx}</div><div class="sc-meta">Индекс качества выпускника (демо)</div></div>
  </div>
  <div class="panel" style="padding:0;overflow:hidden;margin-bottom:16px">
    <table class="tbl">
      <thead><tr><th>Факультет</th><th>Студентов</th><th>На практике</th><th>Трудоустроено</th><th>Ср. балл</th><th>% занятости</th></tr></thead>
      <tbody>
      ${KF.map(f=>{const r=Math.round(f.employed/f.students*100);return `
        <tr><td class="nm">${f.name}</td><td>${f.students}</td><td>${f.onInternship}</td><td>${f.employed}</td><td>${f.avgGrade}</td>
        <td><div style="display:flex;align-items:center;gap:8px"><div class="progress" style="width:60px"><i style="width:${r}%"></i></div>${r}%</div></td></tr>`;}).join('')}
      </tbody>
    </table>
  </div>
  <div class="panel"><h3>Студенты на практике</h3><div class="sd" style="margin-bottom:12px">Те же студенты видны в реестре договоров и дневниках практики · демо</div>
    <div class="htd-modules">
      ${PRACTICE.map(p=>{const hrs=practiceHours(p);const st=cst[p.contractStatus]||['b-gray',p.contractStatus];return `
        <div class="htd-mod" style="cursor:pointer" onclick="openContractById('${p.contractId}')">
          <span class="htd-mod-n">${p.student.split(' ').map(w=>w[0]).join('')}</span>
          <div style="flex:1"><div style="font-weight:600">${p.student}</div><div class="sd">${p.faculty} · ${p.company} · ${p.role} · ${hrs}/${p.goalHours} ч</div></div>
          <span class="badge ${st[0]}">${st[1]}</span>
        </div>`;}).join('')}
    </div>
  </div>
  <div class="sd" style="margin-top:12px">Все числа — демо-данные. Формулировки привязаны к гос-KPI по занятости выпускников.</div>`;
}
function openInternship(i){state._intern=i;go('internship-detail');}

/* override crumb labels for detail pages */
const _go=go;
go=function(p){
  const detailLabels={'sim-detail':'Симуляция','job-detail':'Вакансия','internship-new':'Новая стажировка','cohort-detail':'Когорта','student-detail':'Студент','internship-detail':'Стажировка'};
  _go(p);
  if(detailLabels[p]) document.getElementById('crumb').innerHTML=`<b>${detailLabels[p]}</b>`;
};

function filterSearch(q){
  const ql=q.toLowerCase();
  const sims=SIMS.filter(s=>s.t.toLowerCase().includes(ql));
  const jobs=JOBS.filter(j=>j.t.toLowerCase().includes(ql)||j.co.toLowerCase().includes(ql));
  document.getElementById('search-out').innerHTML=
    (sims.length?`<div class="section-label">Симуляции</div>`+sims.map(s=>li(ico('puzzle'),s.t,s.role+" · "+s.match+"%","→")).join(''):'')
    +(jobs.length?`<div class="section-label">Вакансии</div>`+jobs.map(j=>li(ico('briefcase'),j.t,j.co+" · "+j.match+"%","→")).join(''):'')
    +(!sims.length&&!jobs.length?`<div class="empty"><div class="ei">${ico('search')}</div><h3>Ничего не найдено</h3><p>Попробуйте другой запрос.</p></div>`:'');
}

/* ============================================================
   PUBLIC / MARKETING PAGES
   ============================================================ */
function pubGo(p){
  document.getElementById('pub-body').innerHTML = PUB[p] ? PUB[p]() : PUB.home();
  window.scrollTo(0,0);
  /* the landing carries interactive motion; other pages just add reveals */
  if(typeof initLandingMotion==='function') initLandingMotion();
}
const AUDIENCES=[
  ["student",ico('student'),"Студентам","Диагностика, персональная траектория из 10 шагов и реальные симуляции вместо абстрактных лекций — до первой стажировки.","for-students",'var(--blue-soft)'],
  ["university",ico('university'),"ВУЗам","Кабинет куратора: когорты, аналитика компетенций, gap-матрица и отчёты по готовности студентов.","for-universities",'var(--teal-soft)'],
  ["company",ico('company'),"Компаниям","Прогрев и подбор кандидатов через симуляции, воронка найма Kanban и прямые сообщения.","for-companies",'var(--amber-soft)'],
];
/* ============================================================
   ЛОКАЛИЗАЦИЯ RU / UZ (латиница). t('ключ') возвращает текст текущего языка.
   Язык хранится в PREFS.lang; переключение перерисовывает публичные страницы.
   ============================================================ */
const I18N={
  ru:{
    nav_students:'Студентам', nav_universities:'ВУЗам', nav_companies:'Компаниям', nav_pricing:'Тарифы', nav_about:'О нас', nav_help:'Помощь',
    login:'Войти', start:'Начать',
    hero_eyebrow:'Карьерная платформа · Узбекистан',
    hero_lead:'Компании говорят, кого ищут. Мы готовим студента под этот спрос, проводим практику и доводим до оффера — быстрее и точнее, чем кто-либо. Не резюме в пустоту, а путь до работы.',
    mini_demand:'Спрос', mini_demand_d:'Компания задаёт, кого ищет',
    mini_profile:'Профиль', mini_profile_d:'Определяем ваши навыки',
    mini_prep:'Подготовка', mini_prep_d:'Докручиваем недостающее',
    mini_cert:'Сертификат', mini_cert_d:'Подтверждаем соответствие',
    mini_offer:'Оффер', mini_offer_d:'Направляем в компанию',
    journey_note:'Курс не важен — путь открыт с 1-го. Важно соответствие тому, что ищет работодатель.',
    stat_students:'студентов', stat_universities:'вузов', stat_companies:'работодателей',
    stat_note:'Цели на первый учебный год — платформа готовится к запуску',
    bignum_title:'Масштаб задачи', bignum_sub:'Один показатель — реальный размер рынка, остальные — наши цели на первый учебный год. Без придуманных цифр.',
    bignum_1:'студентов вузов в Узбекистане', bignum_2:'студентов — цель первого года', bignum_3:'вузов-партнёров — цель', bignum_4:'работодателей — цель',
    bignum_market:'рынок', bignum_goal:'цель',
    role_student:'Студент', role_student_d:'Диагностика навыков и подготовка под реальные вакансии — до первого оффера', role_student_cta:'Пройти диагностику',
    role_univ:'ВУЗ', role_univ_d:'Когорты студентов, аналитика готовности и gap-матрица компетенций', role_univ_cta:'Открыть кабинет',
    role_company:'Компания', role_company_d:'Готовые кандидаты с подтверждёнными навыками, а не пустые резюме', role_company_cta:'Найти кандидатов',
    step_word:'Шаг', path_title:'Карьерный путь вместе с нами', path_sub:'Пять шагов от требований работодателя до оффера. Начать можно с любого курса.',
    step1:'Спрос компаний', step1_d:'Работодатели заранее говорят, какие навыки нужны для найма', step1_cta:'Смотреть вакансии',
    step2:'Ваш профиль', step2_d:'Определяем сильные стороны и чего не хватает под цель', step2_cta:'Пройти диагностику',
    step3:'Подготовка', step3_d:'Докручиваем недостающие навыки: кейсы, симуляции, тесты', step3_cta:'Начать обучение',
    step4:'Сертификат', step4_d:'Подтверждаем, что вы соответствуете требованиям компании', step4_cta:'Проверить себя',
    step5:'Оффер', step5_d:'Направляем готового кандидата напрямую работодателю', step5_cta:'Получить оффер',
    how_title:'Как это работает', how_sub:'Не доска вакансий. Работодатель — в начале пути, а не в конце.',
    how1:'Спрос впереди', how1_d:'Компания фиксирует, кого хочет нанять, ещё до вашего обучения. Вы готовитесь под реальную вакансию, а не в пустоту.',
    how2:'Профиль навыков', how2_d:'Диагностика за 20 минут показывает, что уже умеете и какого навыка не хватает под цель.',
    how3:'Подготовка', how3_d:'Докручиваете недостающее: кейсы и симуляции с AI-наставником, тесты на соответствие, сертификаты.',
    how4:'Направление в компанию', how4_d:'Готового кандидата направляем работодателю напрямую. Он видит подтверждённые навыки, а не резюме.',
    events_title:'Мы рекомендуем', events_all:'Все мероприятия', events_note:'Примеры формата — реальная афиша появится к запуску',
    jobs_title:'Живые вакансии и стажировки', jobs_sub:'Реальные позиции от работодателей — с требованиями, форматом и уровнем. Покажем ваш % соответствия под каждую.',
    lm_title:'Узнай свой шанс за 3 клика', lm_sub:'Выбери вакансию, отметь что уже умеешь — и увидь, насколько подходишь и что дообучить. Без регистрации.',
    lm_pick_vac:'1. Выбери вакансию', lm_pick_skills:'2. Отметь свои навыки',
    lm_gap:'Чтобы дойти до 100%, дообучи:', lm_full:'Полное соответствие — ты готов к этой вакансии!',
    lm_hint_gap:'Под эту вакансию соберётся трек подготовки — недостающие навыки закроются на практике.',
    lm_hint_ok:'Отправляй отклик — или собери паспорт навыков, чтобы работодатель увидел тебя в витрине.',
    lm_cta:'Построить мою траекторию →',
    noexp_badge:'Нет опыта? Это норма',
    noexp_title:'Тебя не берут из-за «нет опыта»? Мы заходим с другой стороны',
    noexp_sub:'Обычные площадки ждут, что ты уже готов. Мы наоборот: компания говорит, кого ищет, — а мы готовим тебя под это и доводим до оффера. Опыт ты получаешь в процессе, а не «до».',
    noexp_cta:'Начать без опыта →',
    noexp_short:'Обычные площадки ждут, что ты уже готов. Мы наоборот: готовим под конкретный заказ и доводим до оффера. Опыт — в процессе.',
    noexp_n1:'Спрос', noexp_n2:'Подготовка', noexp_n3:'Практика', noexp_n4:'Оффер',
    noexp_s1t:'Компания задаёт спрос', noexp_s1x:'Работодатель описывает, какие навыки ему нужны — конкретно, а не «вообще».',
    noexp_s2t:'Мы готовим под заказ', noexp_s2x:'Под требования собирается трек — ты закрываешь именно те навыки, что нужны.',
    noexp_s3t:'Практика и подтверждение', noexp_s3x:'Реальные задачи, ментор подтверждает часы и навыки — это и есть твой опыт.',
    noexp_s4t:'Оффер', noexp_s4x:'Готового кандидата видит работодатель в витрине — с подтверждёнными навыками.',
    uni_badge:'Для вузов и карьерных центров',
    uni_title:'Один кабинет вместо ручного учёта практики',
    uni_sub:'Дневник практики, зачёт часов, трёхсторонние договоры и KPI трудоустройства — в одном месте. Меньше рутины у карьерного центра, больше готовых выпускников.',
    uni_f1t:'KPI трудоустройства', uni_f1x:'Дашборд под «Индекс качества выпускника» — по факультетам.',
    uni_f2t:'Операционка практики', uni_f2x:'Дневник, зачёт часов, договор — без бумаги.',
    uni_f3t:'Подтверждённые навыки', uni_f3x:'Ментор заверяет часы и оценки — не «на словах».',
    uni_f4t:'Готовые выпускники', uni_f4x:'Подготовка под реальный спрос работодателей.',
    uni_cta:'Подключить вуз →',
    co_badge:'Для работодателей',
    co_title:'Не ищите готовых — готовьте под себя',
    co_sub:'Опишите, кого ищете, — под ваши требования соберётся трек, а студенты обучатся именно тому, что нужно. Вы получаете кандидатов, ранжированных по соответствию, с уже подтверждёнными навыками.',
    co_f1t:'Заказ на кадры (HTD)', co_f1x:'Опишите роль — под неё соберётся подготовка.',
    co_f2t:'Match Score под заказ', co_f2x:'Кандидаты ранжированы под ваши требования.',
    co_f3t:'Витрина готовых', co_f3x:'Навыки подтверждены практикой, не резюме.',
    co_f4t:'Задачи и микропроекты', co_f4x:'Оцените в деле до найма.',
    co_cta:'Разместить заказ →',
    jobs_more:'Подробнее', jobs_cta:'Смотреть все вакансии',
    ev_new_employer:'Работодатель нового поколения',
    ev1_type:'Стажировка', ev1_role:'Продуктовая аналитика', ev1_desc:'Стань профессионалом в аналитике с лидером рынка', ev1_date:'20 августа', ev1_place:'Ташкент',
    ev2_type:'Кейс-чемпионат', ev2_role:'Логистика последней мили', ev2_desc:'Сократи время доставки в Ташкенте на 20%', ev2_date:'25 августа', ev2_place:'Гибрид',
    ev3_type:'Мастер-класс', ev3_role:'Как пройти отбор в IT', ev3_desc:'Разбор тестового задания вживую', ev3_date:'29 августа', ev3_place:'Онлайн',
    ev4_type:'Стажировка', ev4_role:'Growth-маркетинг', ev4_desc:'Реальные кампании с первого дня', ev4_date:'1 сентября', ev4_place:'Ташкент',
    quotes_title:'Что говорят студенты', quotes_note:'Демо-контент: до публикации заменить реальными отзывами.',
    q1:'«Решил три кейса за месяц — на собеседовании показал их вместо резюме. Это сработало.»', q1_a:'Студент, ТУИТ · 4 курс',
    q2:'«Диагностика показала, что мне ближе аналитика, а не разработка. Сэкономила год.»', q2_a:'Студентка, Вестминстер · 3 курс',
    q3:'«Симуляция была сложнее реальной стажировки. Пришёл подготовленным.»', q3_a:'Студент, Инха · выпускник',
    faq_title:'Частые вопросы',
    faq1_q:'Это бесплатно?', faq1_a:'Для студентов базовый доступ бесплатный: диагностика, траектория и первые кейсы. Условия для вузов и компаний обсуждаются индивидуально.',
    faq2_q:'Чем это отличается от hh.uz?', faq2_a:'hh — это доска вакансий, где решает резюме. Здесь работодатель видит решённые кейсы: что вы умеете, а не что написали.',
    faq3_q:'Что такое симуляция?', faq3_a:'Реальная рабочая задача от компании — с данными, дедлайном и AI-наставником. Решение попадает в портфолио.',
    faq4_q:'Как компания видит мой профиль?', faq4_a:'Только с вашего согласия: навыки, решённые кейсы и оценки. Без телефона и почты до вашего отклика.',
    faq5_q:'Я на 1 курсе — мне рано?', faq5_a:'Нет. Первый шаг — диагностика и учебные кейсы, стажировки подключаются с 3 курса.',
    fin_eyebrow:'5 шагов · начать можно с любого курса',
    fin_h1:'Ваш путь до оффера', fin_h2:'начинается с одного шага',
    fin_sub:'Первый — диагностика на 20 минут. Она покажет, где вы уже сильны и что докрутить под спрос работодателей.',
    finrole_student:'Студент', finrole_univ:'ВУЗ', finrole_company:'Компания',
    finpane_student:'<b>Диагностика за 20 минут</b> — покажем сильные стороны и что докрутить под спрос.', fincta_student:'Пройти диагностику', finmeta_student:'Бесплатно · без резюме · результат сразу',
    finpane_univ:'<b>Кабинет куратора</b> — когорты, аналитика готовности и gap-матрица компетенций.', fincta_univ:'Открыть кабинет', finmeta_univ:'Демо · когорты · отчёты по студентам',
    finpane_company:'<b>Готовые кандидаты</b> с подтверждёнными навыками — воронка найма и прямые сообщения.', fincta_company:'Найти кандидатов', finmeta_company:'Подтверждённые навыки · без пустых резюме',
    wait_label:'Пока только присматриваетесь? Оставьте номер — напишем к запуску.', wait_cta:'Сообщить о запуске', wait_done:'Записали — напишем к запуску',
  },
  uz:{
    nav_students:'Talabalarga', nav_universities:'OTMlarga', nav_companies:'Kompaniyalarga', nav_pricing:'Tariflar', nav_about:'Biz haqimizda', nav_help:'Yordam',
    login:'Kirish', start:'Boshlash',
    hero_eyebrow:'Karьera platformasi · Oʻzbekiston',
    hero_lead:'Kompaniyalar kimni izlayotganini aytadi. Biz talabani shu talabga tayyorlaymiz, amaliyotdan oʻtkazamiz va offergacha yetkazamiz — har kimdan tez va aniqroq. Boʻshliqqa rezyume emas, ishgacha yoʻl.',
    mini_demand:'Talab', mini_demand_d:'Kompaniya kimni izlashini belgilaydi',
    mini_profile:'Profil', mini_profile_d:'Koʻnikmalaringizni aniqlaymiz',
    mini_prep:'Tayyorgarlik', mini_prep_d:'Yetishmaganini toʻldiramiz',
    mini_cert:'Sertifikat', mini_cert_d:'Mosligingizni tasdiqlaymiz',
    mini_offer:'Offer', mini_offer_d:'Kompaniyaga yoʻnaltiramiz',
    journey_note:'Kurs muhim emas — yoʻl 1-kursdan ochiq. Muhimi — ish beruvchi izlayotganiga mos kelish.',
    stat_students:'talaba', stat_universities:'OTM', stat_companies:'ish beruvchi',
    stat_note:'Birinchi oʻquv yili maqsadlari — platforma ishga tushishga tayyorlanmoqda',
    bignum_title:'Vazifa koʻlami', bignum_sub:'Bitta koʻrsatkich — bozorning real hajmi, qolganlari — birinchi oʻquv yili maqsadlarimiz. Oʻylab topilgan raqamlarsiz.',
    bignum_1:'Oʻzbekistonda OTM talabalari', bignum_2:'talaba — birinchi yil maqsadi', bignum_3:'hamkor OTM — maqsad', bignum_4:'ish beruvchi — maqsad',
    bignum_market:'bozor', bignum_goal:'maqsad',
    role_student:'Talaba', role_student_d:'Koʻnikma diagnostikasi va real vakansiyalarga tayyorgarlik — birinchi offergacha', role_student_cta:'Diagnostikadan oʻtish',
    role_univ:'OTM', role_univ_d:'Talabalar kogortasi, tayyorlik tahlili va kompetensiya gap-matritsasi', role_univ_cta:'Kabinetni ochish',
    role_company:'Kompaniya', role_company_d:'Tasdiqlangan koʻnikmali tayyor nomzodlar, boʻsh rezyume emas', role_company_cta:'Nomzod topish',
    step_word:'Qadam', path_title:'Karьera yoʻli biz bilan', path_sub:'Ish beruvchi talabidan offergacha besh qadam. Istalgan kursdan boshlash mumkin.',
    step1:'Kompaniyalar talabi', step1_d:'Ish beruvchilar qanday koʻnikma kerakligini oldindan aytadi', step1_cta:'Vakansiyalarni koʻrish',
    step2:'Sizning profilingiz', step2_d:'Kuchli tomonlaringiz va maqsadga nima yetishmasligini aniqlaymiz', step2_cta:'Diagnostikadan oʻtish',
    step3:'Tayyorgarlik', step3_d:'Yetishmagan koʻnikmalarni toʻldiramiz: keyslar, simulyatsiyalar, testlar', step3_cta:'Oʻqishni boshlash',
    step4:'Sertifikat', step4_d:'Kompaniya talablariga mosligingizni tasdiqlaymiz', step4_cta:'Oʻzingizni sinash',
    step5:'Offer', step5_d:'Tayyor nomzodni toʻgʻridan-toʻgʻri ish beruvchiga yoʻnaltiramiz', step5_cta:'Offer olish',
    how_title:'Bu qanday ishlaydi', how_sub:'Vakansiya doskasi emas. Ish beruvchi — yoʻl boshida, oxirida emas.',
    how1:'Talab oldinda', how1_d:'Kompaniya kimni yollashni siz oʻqishdan oldin belgilaydi. Siz boʻshliqqa emas, real vakansiyaga tayyorlanasiz.',
    how2:'Koʻnikma profili', how2_d:'20 daqiqalik diagnostika nimani bilishingiz va maqsadga qaysi koʻnikma yetishmasligini koʻrsatadi.',
    how3:'Tayyorgarlik', how3_d:'Yetishmaganini toʻldirasiz: AI-murabbiy bilan keys va simulyatsiyalar, moslik testlari, sertifikatlar.',
    how4:'Kompaniyaga yoʻnaltirish', how4_d:'Tayyor nomzodni ish beruvchiga toʻgʻridan-toʻgʻri yoʻnaltiramiz. U rezyumeni emas, tasdiqlangan koʻnikmani koʻradi.',
    events_title:'Biz tavsiya qilamiz', events_all:'Barcha tadbirlar', events_note:'Format namunalari — real afisha ishga tushishda paydo boʻladi',
    jobs_title:'Jonli vakansiyalar va amaliyotlar', jobs_sub:'Ish beruvchilardan real pozitsiyalar — talab, format va daraja bilan. Har biriga moslik %ingizni koʻrsatamiz.',
    lm_title:'3 bosishda imkoniyatingni bil', lm_sub:'Vakansiyani tanla, nimani bilishingni belgila — va qanchalik mos kelishingni hamda nimani oʻrganish kerakligini koʻr. Roʻyxatdan oʻtmasdan.',
    lm_pick_vac:'1. Vakansiyani tanla', lm_pick_skills:'2. Koʻnikmalaringni belgila',
    lm_gap:'100% ga yetish uchun oʻrgan:', lm_full:'Toʻliq moslik — sen bu vakansiyaga tayyorsan!',
    lm_hint_gap:'Bu vakansiya uchun tayyorlov treki yigʻiladi — yetishmayotgan koʻnikmalar amaliyotda yopiladi.',
    lm_hint_ok:'Ariza yubor — yoki koʻnikmalar pasportini yigʻ, ish beruvchi seni vitrinada koʻrsin.',
    lm_cta:'Trayektoriyamni tuzish →',
    noexp_badge:'Tajriba yoʻqmi? Bu normal',
    noexp_title:'«Tajriba yoʻq» deb olishmayaptimi? Biz boshqa tomondan kiramiz',
    noexp_sub:'Oddiy platformalar sen allaqachon tayyor boʻlishingni kutadi. Biz aksincha: kompaniya kimni izlayotganini aytadi — biz seni shunga tayyorlaymiz va offergacha yetkazamiz. Tajribani jarayonda olasan, «oldindan» emas.',
    noexp_cta:'Tajribasiz boshlash →',
    noexp_short:'Oddiy platformalar sen tayyor boʻlishingni kutadi. Biz aksincha: aniq buyurtma ostida tayyorlaymiz va offergacha yetkazamiz. Tajriba — jarayonda.',
    noexp_n1:'Talab', noexp_n2:'Tayyorlov', noexp_n3:'Amaliyot', noexp_n4:'Offer',
    noexp_s1t:'Kompaniya talabni belgilaydi', noexp_s1x:'Ish beruvchi qanday koʻnikmalar kerakligini aniq aytadi — «umuman» emas.',
    noexp_s2t:'Biz buyurtma ostida tayyorlaymiz', noexp_s2x:'Talab ostida trek yigʻiladi — aynan kerakli koʻnikmalarni yopasan.',
    noexp_s3t:'Amaliyot va tasdiqlash', noexp_s3x:'Real vazifalar, mentor soatlar va koʻnikmalarni tasdiqlaydi — bu sening tajribang.',
    noexp_s4t:'Offer', noexp_s4x:'Tayyor nomzodni ish beruvchi vitrinada koʻradi — tasdiqlangan koʻnikmalar bilan.',
    uni_badge:'OTM va karyera markazlari uchun',
    uni_title:'Amaliyotni qoʻlda hisoblash oʻrniga yagona kabinet',
    uni_sub:'Amaliyot kundaligi, soatlarni hisobga olish, uch tomonlama shartnomalar va ish bilan taʼminlash KPI — bir joyda. Karyera markazida kamroq rutina, koʻproq tayyor bitiruvchilar.',
    uni_f1t:'Ish bilan taʼminlash KPI', uni_f1x:'«Bitiruvchi sifat indeksi» dashboardi — fakultetlar boʻyicha.',
    uni_f2t:'Amaliyot operatsiyasi', uni_f2x:'Kundalik, soatlar, shartnoma — qogʻozsiz.',
    uni_f3t:'Tasdiqlangan koʻnikmalar', uni_f3x:'Mentor soat va baholarni tasdiqlaydi — «gapda» emas.',
    uni_f4t:'Tayyor bitiruvchilar', uni_f4x:'Ish beruvchilarning real talabiga tayyorlash.',
    uni_cta:'OTMni ulash →',
    co_badge:'Ish beruvchilar uchun',
    co_title:'Tayyorlarni izlamang — oʻzingizga tayyorlang',
    co_sub:'Kimni izlayotganingizni tavsiflang — talabingiz ostida trek yigʻiladi, talabalar aynan kerakli narsani oʻrganadi. Siz mosligi boʻyicha saralangan, koʻnikmalari tasdiqlangan nomzodlarni olasiz.',
    co_f1t:'Kadrlar buyurtmasi (HTD)', co_f1x:'Rolni tavsiflang — ostidan tayyorlov yigʻiladi.',
    co_f2t:'Buyurtma ostida Match Score', co_f2x:'Nomzodlar talabingiz boʻyicha saralangan.',
    co_f3t:'Tayyorlar vitrinasi', co_f3x:'Koʻnikmalar amaliyot bilan tasdiqlangan, rezyume emas.',
    co_f4t:'Vazifa va mikroloyihalar', co_f4x:'Ishga olishdan oldin baholang.',
    co_cta:'Buyurtma joylash →',
    jobs_more:'Batafsil', jobs_cta:'Barcha vakansiyalar',
    ev_new_employer:'Yangi avlod ish beruvchisi',
    ev1_type:'Amaliyot', ev1_role:'Mahsulot tahlili', ev1_desc:'Bozor lideri bilan tahlil sohasida professional boʻling', ev1_date:'20 avgust', ev1_place:'Toshkent',
    ev2_type:'Keys-chempionat', ev2_role:'Soʻnggi milya logistikasi', ev2_desc:'Toshkentda yetkazib berish vaqtini 20% ga qisqartiring', ev2_date:'25 avgust', ev2_place:'Gibrid',
    ev3_type:'Master-klass', ev3_role:'ITga qanday tanlovdan oʻtish', ev3_desc:'Test topshirigʻini jonli tahlil qilish', ev3_date:'29 avgust', ev3_place:'Onlayn',
    ev4_type:'Amaliyot', ev4_role:'Growth-marketing', ev4_desc:'Birinchi kundan real kampaniyalar', ev4_date:'1 sentabr', ev4_place:'Toshkent',
    quotes_title:'Talabalar nima deydi', quotes_note:'Demo-kontent: eʼlon qilishdan oldin real sharhlar bilan almashtirilsin.',
    q1:'«Bir oyda uchta keys yechdim — suhbatda ularni rezyume oʻrniga koʻrsatdim. Bu ishladi.»', q1_a:'Talaba, TATU · 4-kurs',
    q2:'«Diagnostika menga tahlil dasturlashdan koʻra yaqinroq ekanini koʻrsatdi. Bir yilni tejadi.»', q2_a:'Talaba, Vestminster · 3-kurs',
    q3:'«Simulyatsiya real amaliyotdan qiyinroq boʻldi. Tayyor holda keldim.»', q3_a:'Talaba, Inha · bitiruvchi',
    faq_title:'Koʻp beriladigan savollar',
    faq1_q:'Bu bepulmi?', faq1_a:'Talabalar uchun asosiy kirish bepul: diagnostika, trayektoriya va birinchi keyslar. OTM va kompaniyalar uchun shartlar alohida kelishiladi.',
    faq2_q:'hh.uz dan nimasi bilan farq qiladi?', faq2_a:'hh — rezyume hal qiladigan vakansiya doskasi. Bu yerda ish beruvchi yechilgan keyslarni koʻradi: nima yozganingizni emas, nima qila olishingizni.',
    faq3_q:'Simulyatsiya nima?', faq3_a:'Kompaniyaning real ish vazifasi — maʼlumotlar, muddat va AI-murabbiy bilan. Yechim portfelga tushadi.',
    faq4_q:'Kompaniya profilimni qanday koʻradi?', faq4_a:'Faqat sizning roziligingiz bilan: koʻnikmalar, yechilgan keyslar va baholar. Javobingizgacha telefon va pochta koʻrsatilmaydi.',
    faq5_q:'Men 1-kursdaman — erta emasmi?', faq5_a:'Yoʻq. Birinchi qadam — diagnostika va oʻquv keyslari, amaliyotlar 3-kursdan qoʻshiladi.',
    fin_eyebrow:'5 qadam · istalgan kursdan boshlash mumkin',
    fin_h1:'Offergacha yoʻlingiz', fin_h2:'bitta qadamdan boshlanadi',
    fin_sub:'Birinchisi — 20 daqiqalik diagnostika. U qayerda kuchli ekaningiz va ish beruvchilar talabiga nimani toʻldirish kerakligini koʻrsatadi.',
    finrole_student:'Talaba', finrole_univ:'OTM', finrole_company:'Kompaniya',
    finpane_student:'<b>20 daqiqalik diagnostika</b> — kuchli tomonlar va talabga nima toʻldirish kerakligini koʻrsatamiz.', fincta_student:'Diagnostikadan oʻtish', finmeta_student:'Bepul · rezyumesiz · natija darhol',
    finpane_univ:'<b>Kurator kabineti</b> — kogortalar, tayyorlik tahlili va kompetensiya gap-matritsasi.', fincta_univ:'Kabinetni ochish', finmeta_univ:'Demo · kogortalar · talabalar hisoboti',
    finpane_company:'<b>Tayyor nomzodlar</b> tasdiqlangan koʻnikmali — yollash voronkasi va toʻgʻridan-toʻgʻri xabarlar.', fincta_company:'Nomzod topish', finmeta_company:'Tasdiqlangan koʻnikma · boʻsh rezyumesiz',
    wait_label:'Hozircha faqat koʻrib turibsizmi? Raqamingizni qoldiring — ishga tushganda yozamiz.', wait_cta:'Ishga tushganda xabar berish', wait_done:'Qabul qilindi — ishga tushganda yozamiz',
  },
};
function curLang(){ try{ return (PREFS&&PREFS.language) || 'ru'; }catch(e){ return 'ru'; } }
function t(key){ const l=curLang(); return (I18N[l]&&I18N[l][key]) || (I18N.ru[key]) || key; }
function setLang(l){ if(!I18N[l]) return; setPref('language',l); applyStaticI18n(); const cc=document.getElementById('scr-public'); if(cc && !cc.classList.contains('hidden') && typeof pubGo==='function'){ pubGo('home'); } updateLangUI(); }
function toggleLang(){ setLang(curLang()==='ru'?'uz':'ru'); }
function updateLangUI(){ const b=document.getElementById('langBtn'); if(b) b.textContent = curLang()==='ru'?'UZ':'RU'; }
function applyStaticI18n(){ document.querySelectorAll('[data-i18n]').forEach(el=>{ const k=el.getAttribute('data-i18n'); const v=t(k); if(v) el.textContent=v; }); }

/* ============================================================
   ЛЕНДИНГ · интерактивный Match Score — «пощупай за 3 клика».
   Студент выбирает вакансию и отмечает свои навыки → видит % и что дообучить.
   Без регистрации. Демонстрирует главный дифференциатор прямо на входе.
   Переиспользует matchScore(). Отмеченные навыки считаем подтверждёнными.
   ============================================================ */
const LM_VACANCIES=[
  {id:0, role:"Data Analyst Intern", co:"Uzum", color:"#7C3AED", req:["SQL","Python","Дашборды","A/B-тесты","Аналитика"]},
  {id:1, role:"Frontend Intern", co:"Click", color:"#0EA5E9", req:["HTML/CSS","JavaScript","React","Git","Дизайн"]},
  {id:2, role:"Backend Junior", co:"Ozon", color:"#EF4444", req:["Python","SQL","REST","Docker","Git"]},
];
// пул навыков для выбора (объединение требований + пара «своих»)
const LM_SKILL_POOL=["SQL","Python","JavaScript","React","HTML/CSS","Дашборды","A/B-тесты","Аналитика","REST","Docker","Git","Дизайн"];
function lmState(){
  if(!window._lm){ window._lm={ vac:0, skills:new Set(["SQL","Python"]) }; }
  return window._lm;
}
function lmToggleSkill(s){
  const st=lmState();
  if(st.skills.has(s)) st.skills.delete(s); else st.skills.add(s);
  lmRender();
}
function lmSetVac(i){ lmState().vac=+i; lmRender(); }
function lmCompute(){
  const st=lmState();
  const vac=LM_VACANCIES[st.vac];
  const studentSkills=[...st.skills].map(name=>({name, source:'mentor'})); // отмеченные = подтверждённые
  return { vac, ...matchScore(vac.req, studentSkills) };
}
/* перерисовывает только внутренности виджета (не весь лендинг) */
function lmRender(){
  const host=document.getElementById('lm-widget'); if(!host) return;
  host.innerHTML=lmInner();
}
function lmInner(){
  const st=lmState();
  const r=lmCompute();
  const cls=r.score>=80?'ms-hi':r.score>=50?'ms-mid':'ms-lo';
  const ring=r.score>=80?'#22C55E':r.score>=50?'#E0A83A':'#8A8F98';
  return `
    <div class="lm-controls">
      <div class="lm-field">
        <label class="lm-lbl">${t('lm_pick_vac')}</label>
        <div class="lm-vacs">
          ${LM_VACANCIES.map((v,i)=>`<button class="lm-vac ${st.vac===i?'on':''}" onclick="lmSetVac(${i})"><span class="lm-vac-logo" style="background:${v.color}">${v.co[0]}</span>${v.role}<span class="lm-vac-co">${v.co}</span></button>`).join('')}
        </div>
      </div>
      <div class="lm-field">
        <label class="lm-lbl">${t('lm_pick_skills')}</label>
        <div class="lm-skills">
          ${LM_SKILL_POOL.map(s=>`<button class="lm-skill ${st.skills.has(s)?'on':''}" onclick="lmToggleSkill('${s.replace(/'/g,"\\'")}')">${st.skills.has(s)?'✓ ':''}${s}</button>`).join('')}
        </div>
      </div>
    </div>
    <div class="lm-result">
      <div class="lm-ring" style="--rc:${ring}">
        <svg viewBox="0 0 100 100"><circle class="lm-ring-bg" cx="50" cy="50" r="42"/><circle class="lm-ring-fg" cx="50" cy="50" r="42" style="stroke-dasharray:${r.score*2.64} 264"/></svg>
        <div class="lm-ring-num"><b>${r.score}%</b><span>match</span></div>
      </div>
      <div class="lm-expl">
        <div class="lm-expl-role">${r.vac.role} · ${r.vac.co}</div>
        ${r.gap.length
          ? `<div class="lm-gap">${t('lm_gap')} <b>${r.gap.join(', ')}</b></div><div class="lm-hint">${t('lm_hint_gap')}</div>`
          : `<div class="lm-ok">${t('lm_full')}</div><div class="lm-hint">${t('lm_hint_ok')}</div>`}
        <button class="cl-cta-btn lm-cta" onclick="startOnbAs('student')">${t('lm_cta')}</button>
      </div>
    </div>`;
}

const PUB = {
  home:()=>`
    <section class="cl-hero2">
      <canvas class="cl-hero-canvas" id="heroCanvas"></canvas>
      <div class="cl-orb cl-orb-1"></div>
      <div class="cl-orb cl-orb-2"></div>
      <div class="cl-orb cl-orb-3"></div>
      <div class="cl-hero2-inner">
        <div class="cl-badge reveal">${t('hero_eyebrow')}</div>
        <h1 class="cl-mega" id="megaTitle" aria-label="Zero to Hero">
          <span class="cl-mega-word">${'Zero'.split('').map((ch,i)=>`<i class="cl-ml" style="--li:${i}">${ch}</i>`).join('')}</span>
          <span class="cl-mega-arrow" id="megaArrow"><s style="--ai:0">›</s><s style="--ai:1">›</s><s style="--ai:2">›</s></span>
          <span class="cl-mega-word cl-mega-hero">${'Hero'.split('').map((ch,i)=>`<i class="cl-ml" style="--li:${i+5}">${ch}</i>`).join('')}</span>
        </h1>
        <p class="cl-lead reveal" data-d="2">${t('hero_lead')}</p>

        <div class="cl-journey reveal" data-d="3" id="journey">
          <svg class="cl-journey-svg" viewBox="0 0 1000 150" preserveAspectRatio="xMidYMid meet">
            <path id="jPath" class="cl-jline" d="M40 110 C 180 110, 200 40, 340 40 S 520 110, 620 90 S 800 30, 960 40" fill="none"/>
            <circle id="jTrail" class="cl-jtrail" r="14"/><circle id="jRunner" class="cl-jrunner" r="7"/>
          </svg>
          <div class="cl-journey-nodes">
            ${[
              [t('mini_demand'),t('mini_demand_d'),'var(--yy)'],
              [t('mini_profile'),t('mini_profile_d'),'var(--yy-pink)'],
              [t('mini_prep'),t('mini_prep_d'),'var(--yy-amber)'],
              [t('mini_cert'),t('mini_cert_d'),'var(--yy-cyan)'],
              [t('mini_offer'),t('mini_offer_d'),'var(--yy-green)'],
            ].map((n,i)=>`<button class="cl-jnode" style="--nc:${n[2]}" data-i="${i}" onclick="startOnbAs('student',{step:'${n[0]}'})"><span class="cl-jdot"></span><span class="cl-jlabel"><b>${n[0]}</b><em>${n[1]}</em></span></button>`).join('')}
          </div>
        </div>
        <div class="cl-journey-note reveal" data-d="3">${t('journey_note')}</div>

        <div class="cl-hero-stats reveal" data-d="4">
          ${[[STATS.students,t('stat_students')],[STATS.universities,t('stat_universities')],[STATS.companies,t('stat_companies')]].map(x=>`<div class="cl-hstat"><b class="cl-count" data-to="${x[0]}">0</b><span>${x[1]}</span></div>`).join('')}
        </div>

        <div class="cl-stat-note reveal" data-d="4">${t('stat_note')}</div>

        <div class="cl-roles reveal" data-d="4">
          ${[
            ['student',t('role_student'),t('role_student_d'),t('role_student_cta'),'var(--yy)'],
            ['university',t('role_univ'),t('role_univ_d'),t('role_univ_cta'),'var(--yy-green)'],
            ['company',t('role_company'),t('role_company_d'),t('role_company_cta'),'var(--yy-pink)'],
          ].map(r=>`
            <div class="cl-rolecard" style="--rc:${r[4]}" onclick="startOnbAs('${r[0]}')" role="button" tabindex="0">
              <div class="cl-rolecard-top">
                <div class="cl-rolecard-ic">${ico(r[0])}</div>
                <h3>${r[1]}</h3>
              </div>
              <p>${r[2]}</p>
              <span class="cl-rolecard-cta">${r[3]} <b>→</b></span>
            </div>`).join('')}
        </div>
      </div>
    </section>

    <div class="cl-logos">
      <div class="cl-logos-track">
        ${['Uzum','Ozon','Click','EPAM','Beeline','Payme','TBC Bank','Anor Bank','Artel','Korzinka','Uzum','Ozon','Click','EPAM','Beeline','Payme','TBC Bank','Anor Bank','Artel','Korzinka'].map((n,i)=>`<span class="cl-logo"><i style="--lc:${['#2B44FF','#10B981','#EC4899','#F59E0B','#06B6D4'][i%5]}">${n[0]}</i>${n}</span>`).join('')}
      </div>
    </div>

    <section class="cl-sec">
      <div class="cl-sec-head reveal"><h2 class="cl-h2">${t('path_title')}</h2>
        <p class="cl-sub">${t('path_sub')}</p></div>
      <div class="cl-path reveal">
        ${[
          [t('step_word')+' 1',t('step1'),t('step1_d'),t('step1_cta'),'linear-gradient(160deg,#2B44FF,#0E1330)'],
          [t('step_word')+' 2',t('step2'),t('step2_d'),t('step2_cta'),'linear-gradient(160deg,#7C3AED,#1E1040)'],
          [t('step_word')+' 3',t('step3'),t('step3_d'),t('step3_cta'),'linear-gradient(160deg,#EC4899,#3B0A24)',true],
          [t('step_word')+' 4',t('step4'),t('step4_d'),t('step4_cta'),'linear-gradient(160deg,#0891B2,#08203A)'],
          [t('step_word')+' 5',t('step5'),t('step5_d'),t('step5_cta'),'linear-gradient(160deg,#059669,#04241A)'],
        ].map((x,i)=>`
          <div class="cl-pcard${x[5]?' cl-pcard-hero':''}" style="--pg:${x[4]}">
            <div class="cl-pcard-course">${x[0]}</div>
            <div class="cl-pcard-scene">${pathScene(i)}</div>
            <div class="cl-glare"></div>
            <div class="cl-pcard-fill"></div>
            <div class="cl-pcard-body">
              <h3>${x[1]}</h3>
              <p>${x[2]}</p>
              <button class="cl-pcard-btn" onclick="startOnbAs('student',{step:'${x[1]}'})">${x[3]}</button>
            </div>
          </div>`).join('')}
      </div>
    </section>

    <section class="cl-sec">
      <div class="cl-sec-head reveal"><h2 class="cl-h2">${t('how_title')}</h2>
        <p class="cl-sub">${t('how_sub')}</p></div>
    </section>
    <div class="cl-howpin" id="howPin">
      <div class="cl-howpin-stage">
        <div class="cl-howstack" id="howStack">
          ${[
            ['01',t('how1'),t('how1_d'),'var(--yy)'],
            ['02',t('how2'),t('how2_d'),'#8B7CFF'],
            ['03',t('how3'),t('how3_d'),'#A99CFF'],
            ['04',t('how4'),t('how4_d'),'var(--yy-green)'],
          ].map((h,i)=>`
            <div class="cl-hcard" data-i="${i}" style="--hc:${h[3]}">
              <div class="cl-hcard-ghost">${h[0]}</div>
              <div class="cl-hcard-body">
                <div class="cl-hcard-col">
                  <div class="cl-hcard-num">${h[0]}</div>
                  <div class="cl-hcard-t">${h[1]}</div>
                </div>
                <div class="cl-hcard-d">${h[2]}</div>
              </div>
            </div>`).join('')}
        </div>
        <div class="cl-howdots" id="howDots">
          ${[0,1,2,3].map(i=>`<span data-i="${i}"></span>`).join('')}
        </div>
      </div>
      <!-- мобильный запасной список (без залипания) -->
      <div class="cl-how cl-how-mob">
        ${[
          ['01',t('how1'),t('how1_d'),'var(--yy)'],
          ['02',t('how2'),t('how2_d'),'#8B7CFF'],
          ['03',t('how3'),t('how3_d'),'#A99CFF'],
          ['04',t('how4'),t('how4_d'),'var(--yy-green)'],
        ].map((h,i)=>`
          <div class="cl-howstep reveal" data-d="${i+1}" style="--hc:${h[3]}">
            <div class="cl-hownum">${h[0]}</div>
            <div class="cl-howline"></div>
            <h3>${h[1]}</h3><p>${h[2]}</p>
          </div>`).join('')}
      </div>
    </div>

    <section class="cl-sec cl-lm-sec">
      <div class="cl-sec-head reveal"><h2 class="cl-h2">${t('lm_title')}</h2>
        <p class="cl-sub">${t('lm_sub')}</p></div>
      <div class="lm-card reveal" id="lm-widget">${lmInner()}</div>
    </section>

    <section class="cl-sec cl-noexp-sec">
      <div class="cl-noexp reveal">
        <div class="cl-noexp-left">
          <div class="cl-noexp-badge">${t('noexp_badge')}</div>
          <h2 class="cl-h2" style="text-align:left;margin:0 0 12px">${t('noexp_title')}</h2>
          <p class="cl-sub" style="text-align:left;margin:0 0 24px">${t('noexp_short')}</p>
          <button class="cl-cta-btn" onclick="startOnbAs('student')">${t('noexp_cta')}</button>
        </div>
        <div class="cl-flow">
          <div class="cl-flow-track"><div class="cl-flow-fill"></div><div class="cl-flow-dot"></div></div>
          <div class="cl-flow-nodes">
            ${[['target','noexp_n1'],['compass','noexp_n2'],['check','noexp_n3'],['trophy','noexp_n4']].map((s,i)=>`
              <div class="cl-flow-node" style="--fd:${i*0.35}s">
                <div class="cl-flow-ic">${ico(s[0])}</div>
                <div class="cl-flow-lbl">${t(s[1])}</div>
              </div>`).join('')}
          </div>
        </div>
      </div>
    </section>

    <section class="cl-sec">
      <div class="cl-sec-head reveal"><h2 class="cl-h2">${t('jobs_title')}</h2>
        <p class="cl-sub">${t('jobs_sub')}</p></div>
      <div class="cl-jobs reveal">
        ${JOBS.slice(0,6).map(j=>`
          <div class="cl-jobcard" onclick="startOnbAs('student')">
            <div class="cl-jc-top">
              <div class="cl-jc-logo" style="background:${j.color}">${j.logo}</div>
              <button class="cl-jc-fav" onclick="event.stopPropagation();toast&&toast('Войдите, чтобы сохранять вакансии')" aria-label="В избранное">${ico('trophy')}</button>
            </div>
            <div class="cl-jc-title">${j.t}</div>
            <div class="cl-jc-co">${j.co}</div>
            <div class="cl-jc-tags">
              <span class="cl-jc-tag">${j.loc}</span>
              <span class="cl-jc-tag">${j.fmt}</span>
              <span class="cl-jc-tag">${j.lvl}</span>
              <span class="cl-jc-tag">${j.type}</span>
            </div>
            <div class="cl-jc-foot"><span class="cl-jc-sal">${j.sal}</span><span class="cl-jc-more">${t('jobs_more')} →</span></div>
          </div>`).join('')}
      </div>
      <div style="text-align:center;margin-top:28px">
        <button class="cl-cta-btn" onclick="startOnbAs('student')">${t('jobs_cta')}</button>
      </div>
    </section>

    <section class="cl-sec cl-stats-sec">
      <div class="cl-sec-head reveal"><h2 class="cl-h2">${t('bignum_title')}</h2>
        <p class="cl-sub">${t('bignum_sub')}</p></div>
      <div class="cl-bignums reveal">
        <div class="cl-bignum"><b>700K+</b><span>${t('bignum_1')}</span><em class="cl-bn-tag cl-bn-market">${t('bignum_market')}</em></div>
        <div class="cl-bignum"><b>${STATS.students.toLocaleString('ru-RU')}</b><span>${t('bignum_2')}</span><em class="cl-bn-tag cl-bn-goal">${t('bignum_goal')}</em></div>
        <div class="cl-bignum"><b>${STATS.universities}</b><span>${t('bignum_3')}</span><em class="cl-bn-tag cl-bn-goal">${t('bignum_goal')}</em></div>
        <div class="cl-bignum"><b>${STATS.companies}</b><span>${t('bignum_4')}</span><em class="cl-bn-tag cl-bn-goal">${t('bignum_goal')}</em></div>
      </div>
    </section>

    <section class="cl-sec cl-uni-sec">
      <div class="cl-uni reveal">
        <div class="cl-uni-head">
          <div class="cl-uni-badge">${t('uni_badge')}</div>
          <h2 class="cl-h2" style="text-align:left;margin:0 0 12px">${t('uni_title')}</h2>
          <p class="cl-sub" style="text-align:left;margin:0">${t('uni_sub')}</p>
        </div>
        <div class="cl-uni-grid">
          ${[['chart','uni_f1t','uni_f1x'],['doc','uni_f2t','uni_f2x'],['check','uni_f3t','uni_f3x'],['users','uni_f4t','uni_f4x']].map(f=>`
            <div class="cl-uni-feat">
              <div class="cl-uni-ic">${ico(f[0])}</div>
              <div class="cl-uni-ft">${t(f[1])}</div>
              <div class="cl-uni-fx">${t(f[2])}</div>
            </div>`).join('')}
        </div>
        <button class="cl-cta-btn" onclick="startOnbAs('university')">${t('uni_cta')}</button>
      </div>
    </section>

    <section class="cl-sec cl-co-sec">
      <div class="cl-uni cl-co reveal">
        <div class="cl-uni-head">
          <div class="cl-uni-badge cl-co-badge">${t('co_badge')}</div>
          <h2 class="cl-h2" style="text-align:left;margin:0 0 12px">${t('co_title')}</h2>
          <p class="cl-sub" style="text-align:left;margin:0">${t('co_sub')}</p>
        </div>
        <div class="cl-uni-grid">
          ${[['target','co_f1t','co_f1x'],['compass','co_f2t','co_f2x'],['users','co_f3t','co_f3x'],['spark','co_f4t','co_f4x']].map(f=>`
            <div class="cl-uni-feat">
              <div class="cl-uni-ic cl-co-ic">${ico(f[0])}</div>
              <div class="cl-uni-ft">${t(f[1])}</div>
              <div class="cl-uni-fx">${t(f[2])}</div>
            </div>`).join('')}
        </div>
        <button class="cl-cta-btn" onclick="startOnbAs('company')">${t('co_cta')}</button>
      </div>
    </section>

    <section class="cl-sec">
      <div class="cl-sec-head cl-sec-head-row reveal">
        <h2 class="cl-h2">${t('events_title')}</h2>
        <button class="cl-link" onclick="startOnbAs('student')">${t('events_all')} →</button>
      </div>
      <p class="cl-demo-note reveal">${t('events_note')}</p>
      <div class="cl-events reveal">
        ${[
          ['Uzum',t('ev1_type'),t('ev1_role'),t('ev1_desc'),t('ev1_date'),t('ev1_place'),'var(--yy)',true],
          ['Ozon',t('ev2_type'),t('ev2_role'),t('ev2_desc'),t('ev2_date'),t('ev2_place'),'var(--yy-green)',true],
          ['EPAM',t('ev3_type'),t('ev3_role'),t('ev3_desc'),t('ev3_date'),t('ev3_place'),'var(--yy-cyan)',false],
          ['Click',t('ev4_type'),t('ev4_role'),t('ev4_desc'),t('ev4_date'),t('ev4_place'),'var(--yy-pink)',false],
        ].map(e=>`
          <div class="cl-event" onclick="startOnbAs('student')">
            <div class="cl-event-top" style="--ec:${e[6]}">
              <span class="cl-event-logo">${e[0][0]}</span>
              <span class="cl-event-co">${e[0]} · ${e[1]}</span>
            </div>
            <h4>${e[2]}</h4>
            <p>${e[3]}</p>
            <div class="cl-event-meta"><span>${ico('calendar')}${e[4]}</span><span>${ico('pin')}${e[5]}</span></div>
            ${e[7]?`<div class="cl-event-tag">${t('ev_new_employer')}</div>`:''}
          </div>`).join('')}
      </div>
    </section>

    <section class="cl-sec">
      <div class="cl-sec-head reveal"><h2 class="cl-h2">${t('quotes_title')}</h2>
        <p class="cl-sub">${t('quotes_note')}</p></div>
      <div class="cl-quotes">
        ${[
          [t('q1'),t('q1_a')],
          [t('q2'),t('q2_a')],
          [t('q3'),t('q3_a')],
        ].map((q,i)=>`
          <figure class="cl-quote reveal" data-d="${i+1}">
            <blockquote>${q[0]}</blockquote>
            <figcaption>${q[1]}</figcaption>
          </figure>`).join('')}
      </div>
    </section>

    <section class="cl-sec">
      <div class="cl-sec-head reveal"><h2 class="cl-h2">${t('faq_title')}</h2></div>
      <div class="cl-faq reveal">
        ${[
          [t('faq1_q'),t('faq1_a')],
          [t('faq2_q'),t('faq2_a')],
          [t('faq3_q'),t('faq3_a')],
          [t('faq4_q'),t('faq4_a')],
          [t('faq5_q'),t('faq5_a')],
        ].map(f=>`
          <details class="cl-faq-item"><summary>${f[0]}<span class="cl-faq-x">＋</span></summary><p>${f[1]}</p></details>`).join('')}
      </div>
    </section>

    <section class="cl-sec">
      <div class="cl-finale reveal" id="clFinale">
        <div class="cl-finale-glow"></div>
        <div class="cl-finale-glow2"></div>
        <div class="cl-finale-grid"></div>
        <div class="cl-finale-head">
          <div class="cl-finale-eyebrow">${t('fin_eyebrow')}</div>
          <h2 class="cl-finale-h">${t('fin_h1')}<br>${t('fin_h2')}</h2>
          <p class="cl-finale-sub">${t('fin_sub')}</p>
        </div>

        <div class="cl-finpath" id="clFinpath">
          <svg viewBox="0 0 760 40" preserveAspectRatio="none" aria-hidden="true">
            <defs>
              <linearGradient id="clPathGrad" x1="0" y1="0" x2="760" y2="0" gradientUnits="userSpaceOnUse">
                <stop offset="0" stop-color="#2B44FF"/><stop offset="0.28" stop-color="#7C3AED"/>
                <stop offset="0.52" stop-color="#EC4899"/><stop offset="0.76" stop-color="#06B6D4"/>
                <stop offset="1" stop-color="#10B981"/>
              </linearGradient>
            </defs>
            <line class="cl-finpath-track" x1="8" y1="20" x2="752" y2="20"/>
            <line class="cl-finpath-live" x1="8" y1="20" x2="752" y2="20" style="--len:744"/>
          </svg>
          <div class="cl-finpath-steps">
            ${[
              [t('mini_demand'),'#2B44FF'],[t('mini_profile'),'#7C3AED'],[t('mini_prep'),'#EC4899'],[t('mini_cert'),'#06B6D4'],[t('mini_offer'),'#10B981'],
            ].map((s,i)=>`<div class="cl-finstep" style="--c:${s[1]}" data-i="${i}"><span class="cl-findot"></span><span class="cl-finlabel">${s[0]}</span></div>`).join('')}
          </div>
        </div>

        <div class="cl-finale-act">
          <div class="cl-roletabs" role="tablist">
            <button class="cl-roletab on" style="--rc:#2B44FF" data-role="student" onclick="finaleRole('student')" role="tab">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 10 12 5 2 10l10 5 10-5Z"/><path d="M6 12v5c3 3 9 3 12 0v-5"/></svg>${t('finrole_student')}</button>
            <button class="cl-roletab" style="--rc:#10B981" data-role="university" onclick="finaleRole('university')" role="tab">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 21h18M5 21V7l7-4 7 4v14M9 9h.01M9 13h.01M9 17h.01M15 9h.01M15 13h.01M15 17h.01"/></svg>${t('finrole_univ')}</button>
            <button class="cl-roletab" style="--rc:#EC4899" data-role="company" onclick="finaleRole('company')" role="tab">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="4" y="3" width="16" height="18" rx="2"/><path d="M9 9h.01M9 13h.01M15 9h.01M15 13h.01M10 21v-4h4v4"/></svg>${t('finrole_company')}</button>
          </div>
          <div class="cl-rolepane" id="clRolePane">${t('finpane_student')}</div>
          <button class="cl-finale-primary" id="clRoleCta" style="--pc:#2B44FF" onclick="finaleGo()">${t('fincta_student')} <span class="cl-arr">→</span></button>
          <div class="cl-finale-meta" id="clRoleMeta">${t('finmeta_student')}</div>
          <div class="cl-finale-wait-label">${t('wait_label')}</div>
          <div class="cl-finale-wait" id="clWait">
            <div class="cl-cc" id="clCC">
              <button class="cl-cc-btn" id="clCCBtn" onclick="ccToggle()" type="button" aria-haspopup="listbox"><span class="cl-cc-flag" id="clCCFlag">🇺🇿</span><span id="clCCCode">+998</span><svg class="cl-cc-arr" viewBox="0 0 24 24" width="12" height="12" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="m6 9 6 6 6-6"/></svg></button>
              <div class="cl-cc-menu" id="clCCMenu" role="listbox">
                ${[['+998','🇺🇿','Узбекистан'],['+7','🇷🇺','Россия / Казахстан'],['+90','🇹🇷','Турция'],['+1','🇺🇸','США / Канада'],['+44','🇬🇧','Великобритания']].map(c=>`<button class="cl-cc-item" onclick="ccPick('${c[0]}','${c[1]}')" type="button" role="option"><span class="cl-cc-flag">${c[1]}</span><span class="cl-cc-name">${c[2]}</span><span class="cl-cc-num">${c[0]}</span></button>`).join('')}
              </div>
            </div>
            <input id="leadPhone" type="tel" inputmode="tel" placeholder="__ ___ __ __" oninput="waitMask(this);waitValidate()">
            <button id="clWaitBtn" onclick="saveLead()">${t('wait_cta')}</button>
            <span class="cl-finale-wait-ok"><span class="cl-wok-ic"><svg viewBox="0 0 24 24"><path d="M5 13l4 4L19 7"/></svg></span>${t('wait_done')}</span>
          </div>
        </div>
      </div>
    </section>`,

  pricing:()=>`<div class="pub-back" onclick="pubGo('home')">← На главную</div>
    <section class="pub-sec"><h2>Тарифы</h2><p class="lead">Для студентов — бесплатно навсегда. Для организаций — по подписке.</p>
      <div class="price-grid">
        ${priceCard("Студент","Бесплатно","Базовая траектория и первые симуляции",["Входная диагностика","Траектория из 10 шагов","3 симуляции в месяц","AI-резюме (базовое)","Отклик на вакансии"],false,"Начать бесплатно")}
        ${priceCard("ВУЗ","45 000 сум/мес","Кабинет для когорт и кураторов",["Неограниченно студентов","Аналитика и gap-матрица","Отчёты и экспорт","Кураторы и роли","Брендинг и SSO"],true,"Запросить демо")}
        ${priceCard("Компания","25 000 сум/мес","Поиск кандидатов через симуляции",["Публикация стажировок","AI-подбор кандидатов","Kanban воронка найма","Прямые сообщения","HR-роли"],false,"Купить")}
      </div>
    </section>`,

  about:()=>legalLike("О Zero-to-Hero","",
    [["Миссия","Мы сокращаем разрыв между университетом и первой работой в Узбекистане. Студент проходит путь от диагностики до оффера, а компания получает подготовленного кандидата с портфолио."],
     ["Как мы работаем","Модель hire-train-deploy: ВУЗ формирует когорты, студенты решают реальные симуляции от работодателей, компании видят готовых кандидатов и нанимают их."],
     ["Охват","Мы строим сеть по 170+ университетам Узбекистана и десяткам компаний-партнёров."]]),

  help:()=>`<div class="pub-back" onclick="pubGo('home')">← На главную</div>
    <section class="pub-sec"><h2>Центр помощи</h2><p class="lead">Ответы на частые вопросы по ролям.</p>
      <div style="max-width:680px;margin:0 auto">
        ${[["Как начать студенту?","Зарегистрируйтесь, выберите роль «Студент», пройдите диагностику — платформа построит траекторию."],["Как ВУЗу создать когорту?","В кабинете куратора: раздел «Когорты» → «Новая когорта» → пригласите студентов по email."],["Как компании опубликовать стажировку?","Кабинет компании → «Стажировки» → «Новая стажировка», привяжите симуляцию для отбора."],["Не приходит magic link","Проверьте папку спам; ссылка действует 15 минут. Можно войти по паролю."]].map(f=>`<details class="faq-item"><summary>${f[0]}</summary><p>${f[1]}</p></details>`).join('')}
      </div>
    </section>`,

  contact:()=>`<div class="pub-back" onclick="pubGo('home')">← На главную</div>
    <section class="pub-sec"><h2>Свяжитесь с нами</h2><p class="lead">Ответим в течение рабочего дня.</p>
      <div class="card" style="margin:0 auto">
        <div class="field"><label>Имя</label><input placeholder="Ваше имя"></div>
        <div class="field"><label>Email</label><input placeholder="you@example.com"></div>
        <div class="field"><label>Сообщение</label><input placeholder="Чем можем помочь?"></div>
        <button class="btn btn-primary" onclick="toast('Сообщение отправлено (демо)')">Отправить</button>
        <p class="hint">Или напишите на <b>hello@z2h.uz</b></p>
      </div>
    </section>`,

  "legal-terms":()=>legalLike("Условия использования","Обновлено: январь 2026",
    [["Общие положения","Регистрируясь, вы соглашаетесь с условиями обработки данных, правилами публикации контента и порядком разрешения споров."],
     ["Аккаунт","Вы отвечаете за сохранность учётных данных и за действия в рамках своей роли на платформе."],
     ["Контент","Материалы симуляций и решений используются для оценки и формирования портфолио."]]),

  "legal-privacy":()=>legalLike("Политика конфиденциальности","Обновлено: январь 2026",
    [["Какие данные мы обрабатываем","Профиль, результаты диагностики и симуляций, отклики. Данные используются для персонализации траектории и подбора вакансий."],
     ["Передача третьим лицам","Компаниям-работодателям доступны только данные кандидатов, которые сами откликнулись на их вакансии."],
     ["Ваши права","Вы можете запросить удаление данных в разделе «Настройки → Приватность»."]]),
};
/* The students page. Signature: a horizontal course-path ribbon where position
   encodes real sequence (1st year → offer), not decoration. Below it,
   FutureToday-style "doors" answer the first question a fresher has: is there
   anything here for me at my year? Yes. */
function coursesCount(group){
  return JOBS.filter(j=>(j.courses||[]).some(c=>group.includes(c))).length;
}
function studentsPage(){
  const path=[
    {y:"1 курс",t:"Диагностика",d:"Понять сильные стороны за 20 минут",ic:'target'},
    {y:"1–2 курс",t:"Первые кейсы",d:"Задачи компаний вместо лекций",ic:'puzzle'},
    {y:"2–3 курс",t:"Симуляции",d:"Рабочие ситуации с AI-наставником",ic:'bot'},
    {y:"3–4 курс",t:"Стажировка",d:"Отклик с портфолио кейсов",ic:'briefcase'},
    {y:"Выпускник",t:"Оффер",d:"Работодатель видит, что вы умеете",ic:'trophy'},
  ];
  const doors=[
    {g:"1–2 курс",n:coursesCount([1,2]),d:"Рано — но уже можно. Кейсы, мастер-классы, первые навыки."},
    {g:"3–4 курс",n:coursesCount([3,4]),d:"Основной сезон стажировок. Большинство программ здесь."},
    {g:"Выпускники",n:coursesCount([5]),d:"Полная занятость и graduate-программы работодателей."},
  ];
  return `<div class="pub-back" onclick="pubGo('home')">← На главную</div>
  <section class="hero" style="padding:52px 0 20px">
    <div class="hr-eyebrow" style="justify-content:center">${ico('student')} Студентам</div>
    <h1 style="font-size:38px">Не список вакансий. <span class="accent">Путь до оффера.</span></h1>
    <p>Платформа ведёт вас с первого курса: от «не знаю, что умею» до «работодатель сам зовёт».</p>
    <div class="cta-row"><button class="btn btn-primary" onclick="startOnbAs('student')">Начать бесплатно →</button></div>
  </section>

  <section class="pub-sec">
    <div class="sec-head"><span class="sec-eyebrow">Как это работает</span><h2>Пять шагов, а не пять курсов впустую</h2></div>
    <div class="cpath">
      ${path.map(x=>`
        <div class="cpath-step">
          <div class="cpath-year">${x.y}</div>
          <div class="cpath-dot">${ico(x.ic)}</div>
          <div class="cpath-t">${x.t}</div>
          <div class="cpath-d">${x.d}</div>
        </div>`).join('<div class="cpath-link"></div>')}
    </div>
  </section>

  <section class="pub-sec">
    <div class="sec-head"><span class="sec-eyebrow">С чего начать</span><h2>Найдите свою дверь</h2>
      <p class="sec-sub">Первый вопрос не «какая вакансия», а «берут ли вообще меня сейчас». Берут.</p></div>
    <div class="doors">
      ${doors.map(x=>`
        <div class="door" onclick="startOnbAs('student')">
          <div class="door-top"><span class="door-g">${x.g}</span><span class="door-n">${x.n} ${plural(x.n,'программа','программы','программ')}</span></div>
          <p class="door-d">${x.d}</p>
          <div class="door-go">Смотреть →</div>
        </div>`).join('')}
    </div>
  </section>

  <section class="pub-sec pub-sec-cta">
    <h2>Первый шаг — 20 минут и бесплатно</h2>
    <p class="sec-sub">Диагностика покажет, где вы сильны и какой путь короче.</p>
    <button class="btn btn-primary" onclick="startOnbAs('student')">Пройти диагностику →</button>
  </section>`;
}

/* Employer offer page. Agencies sell one expensive hire at a % of salary — maths
   that breaks for interns. Offer inverted: many pre-vetted students, cheap.
   Agency offer structure (hook → SLA → guarantee → flat price → fields), flipped. */
function companiesPage(){
  const fields=[
    {t:"Аналитика и данные",ic:'chart'},{t:"Разработка",ic:'code'},
    {t:"Маркетинг",ic:'megaphone'},{t:"Продажи",ic:'briefcase'},
    {t:"Дизайн",ic:'palette'},{t:"HR и рекрутинг",ic:'users'},
  ];
  const steps=[
    {t:"Публикуете задачу",d:"Реальный кейс или вакансию. Бесплатно."},
    {t:"Студенты решают",d:"Видно, кто как думает, а не кто как оформил резюме."},
    {t:"Выбираете лучших",d:"Пять отобранных вместо двухсот случайных откликов."},
  ];
  return `<div class="pub-back" onclick="pubGo('home')">← На главную</div>
  <section class="hero" style="padding:52px 0 24px">
    <div class="hr-eyebrow" style="justify-content:center">${ico('company')} Компаниям</div>
    <h1 style="font-size:38px"><span class="accent">${STATS.students.toLocaleString('ru-RU')} студентов</span><br>с решёнными кейсами, а не резюме</h1>
    <p>Не ищете одного идеального за процент от годовой зарплаты. Выбираете из тех, кто уже показал, как работает.</p>
    <div class="cta-row"><button class="btn btn-primary" onclick="startOnbAs('company')">Найти кандидатов →</button></div>
  </section>

  <section class="pub-sec">
    <div class="offer-grid">
      <div class="offer-card"><div class="offer-v">72 часа</div><div class="offer-l">до первых пяти кандидатов</div></div>
      <div class="offer-card"><div class="offer-v">Замена</div><div class="offer-l">бесплатно, если стажёр не подошёл</div></div>
      <div class="offer-card"><div class="offer-v">Фикс</div><div class="offer-l">фиксированная цена, не процент от зарплаты</div></div>
      <div class="offer-card"><div class="offer-v">${STATS.universities}</div><div class="offer-l">вузов в одном окне</div></div>
    </div>
  </section>

  <section class="pub-sec">
    <div class="sec-head"><span class="sec-eyebrow">Как это работает</span><h2>Кейс вместо кота в мешке</h2>
      <p class="sec-sub">Агентство приводит одного и берёт процент. Мы показываем многих, кто уже решил вашу задачу.</p></div>
    <div class="offer-steps">
      ${steps.map((x,i)=>`
        <div class="offer-step">
          <div class="offer-num">${i+1}</div>
          <div><div class="offer-st">${x.t}</div><div class="offer-sd">${x.d}</div></div>
        </div>`).join('')}
    </div>
  </section>

  <section class="pub-sec">
    <div class="sec-head"><span class="sec-eyebrow">Направления</span><h2>Кого можно найти</h2></div>
    <div class="fields-grid">
      ${fields.map(f=>`
        <div class="field-tile" onclick="startOnbAs('company')">
          <div class="field-ic">${ico(f.ic)}</div>
          <div class="field-t">${f.t}</div>
        </div>`).join('')}
    </div>
  </section>

  <section class="pub-sec pub-sec-cta">
    <h2>Первый кейс — бесплатно</h2>
    <p class="sec-sub">Опубликуйте задачу и посмотрите, кто её решит. Платите, только когда захотите нанять.</p>
    <button class="btn btn-primary" onclick="startOnbAs('company')">Опубликовать задачу →</button>
    <div class="offer-note">${ico('alert')} Цены и SLA демонстрационные. Финальные условия обсуждаются индивидуально.</div>
  </section>`;
}

function audiencePage(icon,title,sub,bg,features,price){
  return `<div class="pub-back" onclick="pubGo('home')">← На главную</div>
  <section class="hero" style="padding:56px 0 40px">
    <div class="ai" style="width:56px;height:56px;border-radius:14px;display:flex;align-items:center;justify-content:center;font-size:26px;background:${bg};margin:0 auto 18px">${icon}</div>
    <h1 style="font-size:36px">${title}</h1>
    <p>${sub}</p>
    <div class="cta-row"><button class="btn btn-primary" onclick="startOnb2()">Начать →</button></div>
  </section>
  <section class="pub-sec" style="padding-top:8px">
    <div style="max-width:520px;margin:0 auto">
      ${features.map(f=>`<div class="li" style="padding:14px 0"><div class="li-ic" style="background:${bg}">✓</div><div class="li-b"><div class="li-t">${f}</div></div></div>`).join('')}
      <div style="text-align:center;margin-top:24px"><span class="badge b-blue" style="font-size:13px;padding:6px 14px">${price}</span></div>
    </div>
  </section>`;
}
function priceCard(n,p,tag,feats,hot,cta){
  return `<div class="price ${hot?'hot':''}"><div class="pn">${n}</div><div class="pp">${p}</div><div class="ptag">${tag}</div><ul>${feats.map(f=>`<li>${f}</li>`).join('')}</ul><button class="btn ${hot?'btn-primary':'btn-ghost'}" onclick="startOnb2()">${cta}</button></div>`;
}
function legalLike(title,upd,sections){
  return `<div class="pub-back" onclick="pubGo('home')">← На главную</div>
  <div class="legal-doc"><h1>${title}</h1>${upd?`<div class="upd">${upd}</div>`:''}
    ${sections.map(s=>`<h3>${s[0]}</h3><p>${s[1]}</p>`).join('')}
  </div>`;
}

/* ============================================================
   COMMAND PALETTE
   ============================================================ */
function openPalette(){document.getElementById('palette').classList.remove('hidden');document.getElementById('pal-input').value='';renderPalette('');setTimeout(()=>document.getElementById('pal-input').focus(),50);}
function closePalette(){document.getElementById('palette').classList.add('hidden');}
function renderPalette(q){
  if(!state.role)return;
  const items=[...NAV[state.role].main,...NAV[state.role].foot].filter(x=>x[0]!=='__group' && pageEnabled(x[0]));
  const ql=q.toLowerCase();
  const filtered=items.filter(i=>i[2].toLowerCase().includes(ql));
  document.getElementById('pal-results').innerHTML=filtered.map(i=>
    `<div class="pres" onclick="closePalette();go('${i[0]}')"><span>${ico(i[1])}</span>${i[2]}<span class="pk">Перейти</span></div>`).join('')
    || `<div class="pres" style="color:var(--muted)">Ничего не найдено</div>`;
}
document.addEventListener('keydown',e=>{
  if((e.metaKey||e.ctrlKey)&&e.key==='k'){e.preventDefault();if(state.authed)openPalette();}
  if(e.key==='Escape')closePalette();
});

/* ============================================================
   ▼▼▼ NEW FEATURES — fully isolated, mock-only, removable ▼▼▼
   features/onboarding · features/ai · features/payment
   Nothing above this line is modified. To remove: delete this
   block, the #scr-onb2 markup, the new PAGES keys, and CSS.
   ============================================================ */

/* ---- mock/ (single object standing in for users.ts/resume.ts/ai.ts/companies.ts) ---- */
const MOCK = {
  users:   { phone:"", code:"", role:null, password:"", resumeCompleted:false, onbDeferred:false },
  resume:  { steps:["Личные данные","Опыт и навыки","Цель"], done:false },
  companies:[
    {role:"Junior Marketing", tag:"хайринг"},
    {role:"Sales Intern",      tag:"новое"},
    {role:"SMM Assistant",     tag:"хайринг"},
  ],
  ai: {
    voicePhrase:"Я хочу стать маркетологом.",
    voiceReply:"На основе ваших ответов рекомендуем пройти следующие шаги:\n• Создать резюме\n• Пройти диагностику\n• Изучить курс\n• Откликнуться на стажировки",
    canned:{
      "резюме":"Начните с раздела «Создать резюме» — я помогу заполнить его пошагово.",
      "стажировк":"Загляните в «Вакансии»: там есть стажировки с процентом совпадения под ваш профиль.",
      "диагностик":"Диагностика занимает ~5 минут и покажет ваши сильные стороны и пробелы.",
      "курс":"Рекомендую курс по основам маркетинга — он закрывает базовые пробелы.",
      "":"Расскажите, кем хотите стать — и я предложу конкретные шаги.",
    },
  },
};
/* ---- SVG icon set (no emoji per spec) ---- */


/* ---- mock reference books ---- */
const REF_UNIVERSITIES=["Национальный университет Узбекистана (НУУз)","Ташкентский университет информационных технологий (ТУИТ)","Университет Вестминстер в Ташкенте (WIUT)","Ташкентский государственный экономический университет (ТГЭУ)","Ташкентский финансовый институт","Университет Инха в Ташкенте (IUT)","Туринский политехнический университет в Ташкенте","Ташкентский государственный технический университет (ТашГТУ)","Ташкентский государственный юридический университет","Ташкентский государственный аграрный университет","Ташкентская медицинская академия","Ташкентский государственный педагогический университет","Ташкентский государственный транспортный университет","Ташкентский архитектурно-строительный университет","Ташкентский химико-технологический институт","Университет журналистики и массовых коммуникаций","Университет мировой экономики и дипломатии (УМЭД)","Банковско-финансовая академия","Ташкентский институт востоковедения","Узбекский государственный университет мировых языков","Узбекская государственная консерватория","Национальный институт художеств и дизайна им. Камолиддина Бехзода","Университет Амити в Ташкенте","Ташкентский филиал МГУ им. Ломоносова","Ташкентский филиал РЭУ им. Плеханова","Ташкентский филиал МГИМО","Филиал НИЯУ МИФИ в Ташкенте","Университет Аджу в Ташкенте","Университет Мичиган в Ташкенте","Central Asian University (CAU)","New Uzbekistan University","Самаркандский государственный университет","Самаркандский государственный медицинский университет","Самаркандский государственный институт иностранных языков","Бухарский государственный университет","Андижанский государственный университет","Наманганский государственный университет","Ферганский государственный университет","Каршинский государственный университет","Термезский государственный университет","Ургенчский государственный университет","Нукусский государственный педагогический институт","Каракалпакский государственный университет","Джизакский политехнический институт","Навоийский государственный горно-технологический университет","Гулистанский государственный университет"];
const REF_DIRECTIONS=["Информационные технологии","Программирование / Разработка","Аналитика данных","Искусственный интеллект","Кибербезопасность","Тестирование / QA","DevOps / Инфраструктура","Веб-разработка","Мобильная разработка","Дизайн","UX/UI дизайн","Графический дизайн","Маркетинг","SMM / Контент","PR / Коммуникации","Продажи","Продуктовый менеджмент","Проектный менеджмент","Финансы и экономика","Бухгалтерия / Аудит","Банковское дело","Управление персоналом (HR)","Логистика / Цепи поставок","Закупки","Юриспруденция","Образование / Преподавание","Медицина / Здравоохранение","Строительство / Архитектура","Производство / Инженерия","Туризм / Гостеприимство","Ритейл / E-commerce","Государственное управление","Журналистика / Медиа","Международные отношения","Сельское хозяйство","Энергетика","Транспорт","Психология","Химия / Биотехнологии","Предпринимательство"];
const REF_CITIES=["Ташкент","Самарканд","Бухара","Наманган","Андижан","Нукус","Фергана","Карши","Коканд","Термез","Ургенч","Джизак","Навои","Гулистан","Маргилан","Ангрен","Чирчик","Алмалык","Бекабад","Шахрисабз","Хива","Зарафшан","Учкудук","Денау","Каттакурган","Янгиюль","Асака","Кувасай","Шахрихан","Хазарасп"];
const REF_COURSES=["1-й курс","2-й курс","3-й курс","4-й курс","Магистратура","Выпускник"];
const REF_FORMATS=["Онлайн","Офлайн","Гибрид"];
const REF_ORG_TYPES=["ИТ-компания","Банк / финансы","Финтех","Телеком","Ритейл / e-commerce","Производство","Логистика","Маркетинговое агентство","Консалтинг","Образование","Медицина / фарма","Строительство / девелопмент","Энергетика","Сельское хозяйство","Туризм / гостеприимство","Медиа / развлечения","Госорганизация","НКО / фонд","Юридическая фирма","Стартап"];
const REF_REGIONS=["Ташкент","Ташкентская область","Самаркандская область","Бухарская область","Ферганская область","Андижанская область","Наманганская область","Республика Каракалпакстан","Другой регион"];
const WORK_FIELDS=[
  ["IT / Разработка","code"],
  ["Аналитика данных","chart"],
  ["Маркетинг","megaphone"],
  ["Продажи","briefcase"],
  ["Дизайн","palette"],
  ["HR / Персонал","users"],
  ["Финансы","card"],
  ["Бухгалтерия","doc"],
  ["Банкинг","company"],
  ["Продуктовый менеджмент","target"],
  ["Проектный менеджмент","list"],
  ["Логистика","compass"],
  ["Закупки","folder"],
  ["Юриспруденция","resume"],
  ["Тестирование / QA","check"],
  ["Кибербезопасность","ban"],
  ["Искусственный интеллект","brain"],
  ["DevOps","data"],
  ["Мобильная разработка","phone"],
  ["Веб-разработка","globe"],
  ["SMM / Контент","chat"],
  ["PR / Коммуникации","mic"],
  ["Образование","university"],
  ["Медицина","spark"],
  ["Строительство","home"],
  ["Производство","puzzle"],
  ["Туризм / Гостеприимство","pin"],
  ["Ритейл / E-commerce","card"],
  ["Госслужба","student"],
  ["Стартапы / Предпринимательство","flame"],
];

/* ---- persistence layer (mock, localStorage) ---- */
function saveRole(r){ try{ localStorage.setItem('z2h_role', r);}catch(e){} MOCK.users.role=r; }
function loadRole(){ try{ return localStorage.getItem('z2h_role'); }catch(e){ return null; } }
/* transient UI keys (search text, dropdown open state) must not be persisted */
function cleanReg(reg){
  if(!reg) return null;
  const out={};
  Object.keys(reg).forEach(k=>{ if(k[0]!=='_') out[k]=reg[k]; });
  return out;
}
/* ============================================================
   ВЕРСИЯ СХЕМЫ localStorage.
   Поднимайте SCHEMA_VERSION при несовместимых изменениях формата
   сохранённого состояния (новые поля state, смена структуры MOCK и т.п.).
   При несовпадении версии старое состояние безопасно сбрасывается —
   для демо чистый старт лучше, чем сломанный экран из устаревшего формата.
   На claude.ai localStorage запрещён (артефакты) — все вызовы в try/catch,
   поэтому падения не будет, просто состояние не сохранится между сессиями.
   ============================================================ */
const SCHEMA_VERSION=3;   // bump when z2h_state / MOCK shape changes incompatibly (v3: модуль задач)
function migrateStorageIfNeeded(){
  try{
    const v=parseInt(localStorage.getItem('z2h_schema_ver')||'0',10);
    if(v===SCHEMA_VERSION) return;
    // версия не совпала (или её нет) — чистим только наши ключи состояния,
    // настройки/тему/лиды сохраняем, они формат-независимы
    ['z2h_state','z2h_onb_draft','z2h_tour_done'].forEach(k=>{
      try{ localStorage.removeItem(k); }catch(e){}
    });
    localStorage.setItem('z2h_schema_ver', String(SCHEMA_VERSION));
  }catch(e){}
}
migrateStorageIfNeeded();

function persistState(){
  try{
    localStorage.setItem('z2h_schema_ver', String(SCHEMA_VERSION));
    localStorage.setItem('z2h_state', JSON.stringify({
      _schema: SCHEMA_VERSION,
      role: MOCK.users.role,
      active: MOCK.users.active||false,
      resumeCompleted: MOCK.users.resumeCompleted,
      fromMockFlow: MOCK.users.fromMockFlow||false,
      email: state.email,
      recsDone: Array.from(RECS_DONE||[]),
      reg: cleanReg(MOCK.reg),
      workFields: MOCK.workFields||[],
      diag: state._diag||null,
      photo: MOCK.users.photo||null,
      profile: MOCK.profile||null,
      resumeData: MOCK.resumeData||null,
    }));
  }catch(e){}
}
function restoreState(){
  try{
    const raw=localStorage.getItem('z2h_state'); if(!raw) return null;
    const s=JSON.parse(raw);
    // защита от устаревшего формата: если запись без версии или со старой — игнорируем
    if((s._schema||0)!==SCHEMA_VERSION){ try{ localStorage.removeItem('z2h_state'); }catch(e){} return null; }
    MOCK.users.role=s.role; MOCK.users.resumeCompleted=!!s.resumeCompleted;
    MOCK.users.fromMockFlow=!!s.fromMockFlow; MOCK.users.active=!!s.active;
    if(s.email) state.email=s.email;
    if(s.reg) MOCK.reg=s.reg;
    if(s.photo) MOCK.users.photo=s.photo;
    if(s.resumeData) MOCK.resumeData=s.resumeData;
    if(s.profile) MOCK.profile=s.profile;
    if(s.workFields) MOCK.workFields=s.workFields;
    if(s.diag){ state._diag=s.diag;
      if(s.diag.done && typeof COMP_SCORES!=='undefined' && typeof DIAG_Q!=='undefined'){
        /* re-derive the profile with the blended scorer, not the raw option value
           (test answers store 0/1, so writing them straight into COMP_SCORES was wrong) */
        if(typeof applyDiagScores==='function') applyDiagScores();
      }
    }
    if(s.recsDone && typeof RECS_DONE!=='undefined') s.recsDone.forEach(x=>RECS_DONE.add(x));
    return s;
  }catch(e){ return null; }
}
function clearState(){
  MOCK.users.active=false;
  try{ localStorage.removeItem('z2h_state'); localStorage.removeItem('z2h_role'); localStorage.removeItem('z2h_tour_done');
       localStorage.setItem('z2h_schema_ver', String(SCHEMA_VERSION)); }catch(e){}
  if(typeof heroReset==='function') heroReset();
}

/* ---- toast: single feedback pattern for all mock actions ---- */
function toast(msg){
  let t=document.getElementById('z2h-toast');
  if(!t){ t=document.createElement('div'); t.id='z2h-toast'; t.className='z2h-toast'; document.body.appendChild(t); }
  t.textContent=msg; t.classList.add('show');
  clearTimeout(window._toastT); window._toastT=setTimeout(()=>t.classList.remove('show'),2200);
}
/* ---- theme (applies app-wide, persisted) ---- */
/* ============================================================
   PREFERENCES — every setting here actually changes the app.
   Persisted in localStorage under z2h_prefs; applied via applyPrefs().
   ============================================================ */
const PREFS_DEFAULT={
  theme:'light',            // light | dark | auto
  density:'comfortable',    // comfortable | compact
  fontScale:100,            // 90..120
  motion:true,              // enable transitions/animations
  accent:'blue',            // blue | teal | violet | amber
  language:'ru',            // ru | uz
  autosave:true,
  sounds:false,
  profilePublic:true,       // employers can find your resume
  shareDiag:true,           // share diagnostics results with the university
  pushEnabled:false,        // real browser Notification permission
  emailDigest:true,         // mock (needs a server)
  jobAlerts:true,           // mock
  sidebarCollapsed:false,   // свёрнутый сайдбар (только иконки) на десктопе
};
let PREFS={...PREFS_DEFAULT};
function loadPrefs(){
  try{
    const raw=localStorage.getItem('z2h_prefs');
    if(raw) PREFS={...PREFS_DEFAULT,...JSON.parse(raw)};
  }catch(e){ PREFS={...PREFS_DEFAULT}; }
  /* migrate the old standalone theme key */
  try{
    const t=localStorage.getItem('z2h_theme');
    if(t && !localStorage.getItem('z2h_prefs')) PREFS.theme=t;
  }catch(e){}
  /* one-time reset: prototype experiments may have left theme:'dark'.
     Light is the product default, so clear that once. */
  try{
    if(!localStorage.getItem('z2h_theme_reset_v1')){
      if(PREFS.theme==='dark' || PREFS.theme==='auto') PREFS.theme='light';
      localStorage.setItem('z2h_theme_reset_v1','1');
      savePrefs();
    }
  }catch(e){}
  return PREFS;
}
function savePrefs(){ try{ localStorage.setItem('z2h_prefs', JSON.stringify(PREFS)); }catch(e){} }
function setPref(key,val){
  PREFS[key]=val; savePrefs(); applyPrefs();
  if(typeof state!=='undefined' && state.page==='settings' && typeof go==='function') go('settings');
}
function prefersDark(){
  try{ return window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches; }catch(e){ return false; }
}
function applyPrefs(){
  const b=document.body; if(!b) return;
  try{
    /* theme, incl. following the OS */
    /* honest theme: manual choice wins; "auto" follows the OS.
       Default stays light so a dark OS doesn't surprise-flip the landing. */
    const dark = PREFS.theme==='dark' || (PREFS.theme==='auto' && prefersDark());
    b.classList.toggle('dark', dark);
    /* density + reduced motion */
    b.classList.toggle('compact', PREFS.density==='compact');
    b.classList.toggle('no-motion', !PREFS.motion);
    /* typography scale */
    if(b.style && b.style.setProperty) b.style.setProperty('--font-scale', (PREFS.fontScale/100));
    /* accent colour + language attribute */
    if(b.setAttribute){ b.setAttribute('data-accent', PREFS.accent); b.setAttribute('lang', PREFS.language); }
    /* свёрнутый сайдбар (десктоп) */
    b.classList.toggle('sb-collapsed', !!PREFS.sidebarCollapsed);
  }catch(e){ /* never let a preference break the whole app */ }
}
/* keep "auto" honest: react to OS theme changes */
(function(){
  try{
    if(window.matchMedia){
      const mq=window.matchMedia('(prefers-color-scheme: dark)');
      const h=()=>{ if(PREFS.theme==='auto') applyPrefs(); };
      mq.addEventListener ? mq.addEventListener('change',h) : mq.addListener(h);
    }
  }catch(e){}
})();
/* legacy entry point used by the topbar moon button */
function toggleTheme(){
  const dark=document.body.classList.contains('dark');
  setPref('theme', dark?'light':'dark');
}
loadPrefs(); applyPrefs();
function openFullCabinet(){ MOCK.users.fromMockFlow=false; persistState(); go('home'); }

/* additively register new reachable pages in student nav (no existing entry changed) */
/* Hero is the floating assistant; the full-page chat stays reachable as "Hero" */
/* Hero is the floating assistant on every screen — no separate nav item,
   otherwise there would be two chats with different memories. */
/* Тарифы intentionally NOT added to student footer — students are on the free plan.
   The payment page stays reachable (command palette / direct nav) for upgrades. */

/* ============================================================
   STUDENT ONBOARDING v2 (spec-driven, mock, icon-based)
   role → [student: registration → SMS → resume choice → brief
           → AI resume → work fields → dashboard]
          [univ/company: registration-lite → SMS → dashboard]
   ============================================================ */
MOCK.reg={first:"",last:"",city:"",university:"",direction:"",course:"",birth:"",format:"Гибрид",phone:""};
MOCK.workFields=[];
let onbFlow={role:null,step:1};
/* Reset every trace of a previous attempt. Callers decide where to go next. */
function onbReset(role){
  onbFlow={role:role||null,step:role?2:1};
  MOCK.users={phone:"",code:"",role:null,password:"",resumeCompleted:false,onbDeferred:false};
  MOCK.reg={first:"",last:"",city:"",university:"",direction:"",course:"",birth:"",format:"Гибрид",phone:""};
  MOCK.workFields=[];
}
/* "Начать" without a role: the landing already asks the question, so don't
   ask it twice on a separate screen — take them to the cards and highlight them. */
/* ============================================================
   Landing motion: cursor particles, count-up stats, scroll reveals.
   Re-initialised each time the public home renders. Cheap, capped,
   respects prefers-reduced-motion. ============================================================ */
let _heroRAF=null, _heroParticles=[], _heroMouse={x:-999,y:-999};
function initHeroCanvas(){
  const c=document.getElementById('heroCanvas'); if(!c) return;
  if(window.matchMedia && window.matchMedia('(prefers-reduced-motion: reduce)').matches) return;
  if((navigator.hardwareConcurrency||8)<4 || window.innerWidth<760) return;
  const ctx=c.getContext('2d'); let w,h,dpr=Math.min(window.devicePixelRatio||1,2);
  function size(){ const r=c.getBoundingClientRect(); w=c.width=r.width*dpr; h=c.height=r.height*dpr; }
  size();
  const sec=c.closest('.cl-hero2');
  const N=Math.min(46, Math.floor((sec?sec.clientWidth:1200)/28));
  _heroParticles=Array.from({length:N},()=>({x:Math.random()*w,y:Math.random()*h,vx:(Math.random()-.5)*.25*dpr,vy:(Math.random()-.5)*.25*dpr,r:(Math.random()*1.6+.6)*dpr}));
  const dark=document.body.classList.contains('dark');
  const dot=dark?'rgba(180,190,255,':'rgba(123,92,255,';
  const line=dark?'rgba(150,160,255,':'rgba(123,92,255,';
  function step(){
    ctx.clearRect(0,0,w,h);
    const mx=_heroMouse.x*dpr, my=_heroMouse.y*dpr;
    for(const p of _heroParticles){
      p.x+=p.vx; p.y+=p.vy;
      if(p.x<0||p.x>w)p.vx*=-1; if(p.y<0||p.y>h)p.vy*=-1;
      // gentle pull toward cursor
      const dx=mx-p.x, dy=my-p.y, d=Math.hypot(dx,dy);
      if(d<160*dpr && d>0){ p.x+=dx/d*.5; p.y+=dy/d*.5; }
      ctx.beginPath(); ctx.arc(p.x,p.y,p.r,0,7); ctx.fillStyle=dot+'.6)'; ctx.fill();
    }
    // link nearby particles
    for(let i=0;i<_heroParticles.length;i++)for(let j=i+1;j<_heroParticles.length;j++){
      const a=_heroParticles[i],b=_heroParticles[j],dx=a.x-b.x,dy=a.y-b.y,d=Math.hypot(dx,dy);
      if(d<110*dpr){ ctx.beginPath(); ctx.moveTo(a.x,a.y); ctx.lineTo(b.x,b.y); ctx.strokeStyle=line+(0.14*(1-d/(110*dpr)))+')'; ctx.lineWidth=dpr; ctx.stroke(); }
    }
    _heroRAF=requestAnimationFrame(step);
  }
  cancelAnimationFrame(_heroRAF); step();
  if(sec && !sec._mouseBound){
    sec.addEventListener('mousemove',e=>{const r=sec.getBoundingClientRect();_heroMouse.x=e.clientX-r.left;_heroMouse.y=e.clientY-r.top;});
    sec.addEventListener('mouseleave',()=>{_heroMouse.x=-999;_heroMouse.y=-999;});
    window.addEventListener('resize',()=>{const c2=document.getElementById('heroCanvas');if(c2){const r=c2.getBoundingClientRect();c2.width=r.width*dpr;c2.height=r.height*dpr;}});
    sec._mouseBound=true;
  }
}
function runCountUp(){
  document.querySelectorAll('.cl-count').forEach(el=>{
    const to=parseInt(el.dataset.to,10)||0; if(el._done) return; el._done=true;
    const dur=1300, t0=performance.now();
    /* back-out easing: the number overshoots its target and springs back */
    function tick(t){ const k=Math.min(1,(t-t0)/dur);
      const c1=1.70158,c3=c1+1, e=1+c3*Math.pow(k-1,3)+c1*Math.pow(k-1,2);
      el.textContent=Math.max(0,Math.round(to*e)).toLocaleString('ru-RU'); if(k<1)requestAnimationFrame(tick); }
    requestAnimationFrame(tick);
  });
}
let _revObs=null;
function initReveals(){
  const els=document.querySelectorAll('.reveal:not(.in)');
  if(!('IntersectionObserver' in window)){ els.forEach(e=>e.classList.add('in')); runCountUp(); return; }
  if(!_revObs){
    _revObs=new IntersectionObserver((ents)=>{
      ents.forEach(en=>{ if(en.isIntersecting){ en.target.classList.add('in'); _revObs.unobserve(en.target);
        if(en.target.querySelector && en.target.querySelector('.cl-count')) runCountUp();
        if(en.target.classList.contains('cl-count')) runCountUp();
      }});
    },{threshold:.15});
  }
  els.forEach(e=>_revObs.observe(e));
  // stats may already be in view on load
  runCountUp();
}
/* animate the journey line drawing itself + a "student" dot running along it */
function initJourney(){
  const path=document.getElementById('jPath'), runner=document.getElementById('jRunner');
  if(!path||!runner) return;
  const len=path.getTotalLength();

  /* Place each node ON the line. Previously nodes were laid out by flexbox while
     the line was a hand-drawn bezier — two coordinate systems that didn't match,
     so the running dot appeared to float off the path. Now node centres are
     sampled from the same path via getPointAtLength and positioned in %. */
  const svg=path.ownerSVGElement;
  const nodesLayer=document.querySelector('.cl-journey-nodes');
  const nodes=[...document.querySelectorAll('.cl-jnode')];
  const n=nodes.length;

  /* Позиционируем ноды по РЕАЛЬНЫМ пиксельным координатам линии в отрендеренном
     SVG (через getBoundingClientRect), а не по процентам от viewBox. Это учитывает
     letterbox от preserveAspectRatio на любой высоте — поэтому на мобильном, где SVG
     ниже, точки остаются ровно на кривой. Пересчёт на resize. */
  function placeNodes(){
    if(!nodesLayer) return;
    const layerBox=nodesLayer.getBoundingClientRect();
    if(!layerBox.width||!layerBox.height) return;
    const pathBox=path.getBoundingClientRect();     // экранные координаты самой линии
    nodes.forEach((node,i)=>{
      const frac = n>1 ? i/(n-1) : 0;
      const pt=path.getPointAtLength(len*frac);
      /* доля точки внутри bbox линии → экранная позиция → % от слоя нод */
      const svgBox=svg.getBoundingClientRect();
      const vb=svg.viewBox.baseVal;
      const scaleX=svgBox.width/vb.width, scaleY=svgBox.height/vb.height;
      const scale=Math.min(scaleX,scaleY);          // meet: единый масштаб
      const drawnW=vb.width*scale, drawnH=vb.height*scale;
      const offX=svgBox.left+(svgBox.width-drawnW)/2;
      const offY=svgBox.top +(svgBox.height-drawnH)/2;
      const screenX=offX+pt.x*scale, screenY=offY+pt.y*scale;
      node.style.left=((screenX-layerBox.left)/layerBox.width*100)+'%';
      node.style.top =((screenY-layerBox.top )/layerBox.height*100)+'%';
    });
  }
  nodes.forEach((node,i)=>{
    const frac = n>1 ? i/(n-1) : 0;
    const pt=path.getPointAtLength(len*frac);
    /* Куда вынести подпись: сэмплируем линию чуть левее и правее точки.
       Если точка выше соседей (гребень) — подпись вверх, иначе вниз. */
    const d=Math.max(6,len*0.05);
    const a=path.getPointAtLength(Math.max(0,len*frac-d));
    const b=path.getPointAtLength(Math.min(len,len*frac+d));
    const neighbourY=(a.y+b.y)/2;
    node.classList.add(pt.y<=neighbourY ? 'up' : 'down');
  });
  placeNodes();
  if(!svg._placeBound){ svg._placeBound=true;
    let raf; addEventListener('resize',()=>{ cancelAnimationFrame(raf); raf=requestAnimationFrame(placeNodes); });
  }

  if(window.matchMedia && window.matchMedia('(prefers-reduced-motion: reduce)').matches){
    path.style.strokeDashoffset='0'; return;
  }
  path.classList.add('drawn');
  let t0=null, dur=2400;
  function run(ts){
    if(!t0)t0=ts; const k=Math.min(1,(ts-t0)/dur);
    const pt=path.getPointAtLength(len*k);
    runner.setAttribute('cx',pt.x); runner.setAttribute('cy',pt.y);
    const tr=document.getElementById('jTrail');
    if(tr){ const pt2=path.getPointAtLength(Math.max(0,len*k-26)); tr.setAttribute('cx',pt2.x); tr.setAttribute('cy',pt2.y); tr.style.opacity=k>0&&k<1?'.18':'0'; }
    runner.style.opacity = k>0&&k<1 ? '1':'0';
    if(k<1) requestAnimationFrame(run);
    else { // loop the runner softly
      let l0=null;
      /* don't burn frames when the hero is scrolled away */
      if(!window._heroVis){ window._heroVis={on:true};
        const hs=document.querySelector('.cl-hero2');
        if(hs && 'IntersectionObserver' in window){
          new IntersectionObserver(es=>{es.forEach(e=>{window._heroVis.on=e.isIntersecting;});},{threshold:0}).observe(hs);
        }
      }
      function loop(ts2){ if(!window._heroVis.on){ requestAnimationFrame(loop); return; }
        if(!l0)l0=ts2; const kk=((ts2-l0)/3200)%1; const p2=path.getPointAtLength(len*kk);
        runner.setAttribute('cx',p2.x); runner.setAttribute('cy',p2.y); runner.style.opacity='.9';
        const tr2=document.getElementById('jTrail');
        if(tr2){ const p3=path.getPointAtLength(Math.max(0,len*kk-26)); tr2.setAttribute('cx',p3.x); tr2.setAttribute('cy',p3.y); tr2.style.opacity='.18'; }
        requestAnimationFrame(loop); }
      requestAnimationFrame(loop);
    }
  }
  requestAnimationFrame(run);
}
/* mouse parallax: orbs + mega title drift subtly toward the cursor */
function initParallax(){
  const sec=document.querySelector('.cl-hero2'); if(!sec||sec._parBound) return;
  if(window.matchMedia&&window.matchMedia('(prefers-reduced-motion: reduce)').matches) return;
  const mega=document.getElementById('megaTitle');
  const orbs=[...sec.querySelectorAll('.cl-orb')];
  sec.addEventListener('mousemove',e=>{
    const r=sec.getBoundingClientRect();
    const nx=(e.clientX-r.left)/r.width-.5, ny=(e.clientY-r.top)/r.height-.5;
    if(mega) mega.style.transform=`translate(${nx*14}px,${ny*10}px)`;
    orbs.forEach((o,i)=>{ const k=(i+1)*10; o.style.transform=`translate(${nx*k}px,${ny*k}px)`; });
  });
  sec.addEventListener('mouseleave',()=>{ if(mega)mega.style.transform=''; orbs.forEach(o=>o.style.transform=''); });
  sec._parBound=true;
}
/* cursor-follow glare + 3D tilt on cards */
function initTiltGlare(){
  document.querySelectorAll('.cl-pcard').forEach(card=>{
    if(card._tiltBound) return; card._tiltBound=true;
    card.addEventListener('mousemove',e=>{
      const r=card.getBoundingClientRect();
      const x=e.clientX-r.left, y=e.clientY-r.top;
      card.style.setProperty('--gx',x+'px'); card.style.setProperty('--gy',y+'px');
      const rx=((y/r.height)-.5)*-8, ry=((x/r.width)-.5)*8;
      card.style.transform=`translateY(-10px) rotateX(${rx}deg) rotateY(${ry}deg) scale(1.02)`;
    });
    card.addEventListener('mouseleave',()=>{ card.style.transform=''; });
  });
  document.querySelectorAll('.cl-rolecard').forEach(card=>{
    if(card._glBound) return; card._glBound=true;
    card.addEventListener('mousemove',e=>{
      const r=card.getBoundingClientRect();
      card.style.setProperty('--gx',(e.clientX-r.left)+'px');
      card.style.setProperty('--gy',(e.clientY-r.top)+'px');
      const nx=(e.clientX-r.left)/r.width-.5;
      card.style.transform=`translateX(${nx*8}px) translateY(-4px)`;
    });
    card.addEventListener('mouseleave',()=>{ card.style.transform=''; });
  });
}
/* top scroll progress bar */
function initScrollBar(){
  let bar=document.getElementById('scrollBar');
  if(!bar){ bar=document.createElement('div'); bar.id='scrollBar'; document.body.appendChild(bar); }
  if(window._sbBound) return; window._sbBound=true;
  window.addEventListener('scroll',()=>{
    const h=document.documentElement;
    const k=h.scrollTop/((h.scrollHeight-h.clientHeight)||1);
    bar.style.width=(k*100)+'%';
  },{passive:true});
}
function initLandingMotion(){ requestAnimationFrame(()=>{ initHeroCanvas(); initReveals(); initJourney(); initParallax(); initTiltGlare(); initScrollBar(); initFinalePath(); initHowPin(); if(typeof waitValidate==='function') waitValidate(); if(typeof applyStaticI18n==='function'){ applyStaticI18n(); updateLangUI(); } }); }
/* pin-стек «Как это работает»: карточки сменяются по прогрессу скролла обёртки */
let _howRAF=0;
function initHowPin(){
  const pin=document.getElementById('howPin');
  const stack=document.getElementById('howStack');
  const dots=document.getElementById('howDots');
  if(!pin||!stack) return;
  const cards=[...stack.querySelectorAll('.cl-hcard')];
  const dotEls=dots?[...dots.querySelectorAll('span')]:[];
  const n=cards.length;
  if(!n) return;
  let active=-1;
  const layout=(idx)=>{
    cards.forEach((c,i)=>{
      const depth=i-idx;
      if(depth<0){ c.style.transform='translateY(-46px) scale(.93)'; c.style.opacity='0'; c.style.zIndex='0'; }
      else if(depth>3){ c.style.opacity='0'; c.style.zIndex='0'; }
      else { c.style.transform=`translateY(${depth*16}px) scale(${1-depth*.045})`; c.style.opacity = depth>2?'.35':'1'; c.style.zIndex=String(20-depth); }
    });
    dotEls.forEach((d,i)=>d.classList.toggle('on',i===idx));
  };
  const onScroll=()=>{
    if(_howRAF) return;
    _howRAF=requestAnimationFrame(()=>{
      _howRAF=0;
      const rect=pin.getBoundingClientRect();
      const vh=window.innerHeight;
      const total=pin.offsetHeight - vh; // прокручиваемая дистанция внутри pin
      const scrolled=Math.min(Math.max(-rect.top,0),total);
      const prog=total>0?scrolled/total:0; // 0..1
      const idx=Math.min(n-1,Math.floor(prog*n + 0.0001));
      if(idx!==active){ active=idx; layout(idx); }
    });
  };
  layout(0);
  window.addEventListener('scroll',onScroll,{passive:true});
  window.addEventListener('resize',onScroll,{passive:true});
  onScroll();
}

/* Финальный CTA с выбором роли: каждая роль меняет подводку, цвет кнопки и действие */
const FINALE_ROLES={
  student:{c:'#2B44FF',paneKey:'finpane_student',ctaKey:'fincta_student',metaKey:'finmeta_student'},
  university:{c:'#10B981',paneKey:'finpane_univ',ctaKey:'fincta_univ',metaKey:'finmeta_univ'},
  company:{c:'#EC4899',paneKey:'finpane_company',ctaKey:'fincta_company',metaKey:'finmeta_company'},
};
let _finaleRole='student';
function finaleRole(role){
  const r=FINALE_ROLES[role]; if(!r) return;
  _finaleRole=role;
  document.querySelectorAll('.cl-roletab').forEach(t=>t.classList.toggle('on',t.dataset.role===role));
  const pane=document.getElementById('clRolePane');
  const cta=document.getElementById('clRoleCta');
  const meta=document.getElementById('clRoleMeta');
  if(pane){ pane.style.opacity='0'; setTimeout(()=>{ pane.innerHTML=t(r.paneKey); pane.style.opacity='1'; },130); }
  if(cta){ cta.style.setProperty('--pc',r.c); cta.innerHTML=t(r.ctaKey)+' <span class="cl-arr">→</span>'; }
  if(meta) meta.textContent=t(r.metaKey);
}
function finaleGo(){ startOnbAs(_finaleRole); }

function initFinalePath(){
  const path=document.getElementById('clFinpath');
  if(!path || path.dataset.lit) return;
  const steps=[...path.querySelectorAll('.cl-finstep')];
  const run=()=>{
    if(path.dataset.lit) return;
    path.dataset.lit='1';
    path.classList.add('on');            // старт прочерчивания линии (CSS 2.1s)
    const reduce=matchMedia('(prefers-reduced-motion:reduce)').matches;
    steps.forEach((st,i)=>{
      const delay=reduce?0:i*380;        // синхронно с бегущей линией
      setTimeout(()=>{
        st.classList.add('lit');
        if(i===steps.length-1) st.classList.add('goal');
      }, delay);
    });
  };
  const io=new IntersectionObserver((es)=>{
    es.forEach(e=>{ if(e.isIntersecting){ run(); io.disconnect(); } });
  },{threshold:.4});
  io.observe(path);
}

/* Illustrated scene per career step — silhouette figures in context.
   Stands in for a photo without looking like a grey placeholder. */
function pathScene(i){
  const W='rgba(255,255,255,';
  // reusable silhouette person
  const person=(x,s,o)=>`<g transform="translate(${x},0) scale(${s})" opacity="${o}"><circle cx="0" cy="-26" r="9"/><path d="M-13 6 Q-13 -14 0 -14 Q13 -14 13 6 Z"/></g>`;
  const scenes=[
    // 1 freshman course — a lecture, one hand raised
    `<g fill="${W}.22)">${person(-34,1,.5)}${person(0,1.1,.7)}${person(34,1,.5)}</g><g fill="${W}.4)" transform="translate(60,-30)"><circle cx="0" cy="-30" r="7"/><path d="M-10 4 Q-10 -12 0 -12 Q10 -12 10 4 Z"/><rect x="6" y="-40" width="4" height="16" rx="2"/></g>`,
    // 2 case championship — a crowd / team
    `<g fill="${W}.2)">${person(-46,.85,.45)}${person(-16,1,.6)}${person(16,1,.6)}${person(46,.85,.45)}${person(0,1.15,.8)}</g>`,
    // 3 career events (hero) — audience facing a screen
    `<g fill="${W}.18)">${person(-40,.8,.4)}${person(-13,.9,.5)}${person(13,.9,.5)}${person(40,.8,.4)}</g><rect x="-46" y="-64" width="92" height="30" rx="4" fill="${W}.28)"/>`,
    // 4 internship — one focused person at a desk
    `<g fill="${W}.4)" transform="translate(0,4)"><circle cx="0" cy="-30" r="10"/><path d="M-15 8 Q-15 -14 0 -14 Q15 -14 15 8 Z"/></g><rect x="-30" y="14" width="60" height="6" rx="3" fill="${W}.25)"/>`,
    // 5 fulltime — two colleagues
    `<g fill="${W}.32)">${person(-18,1.05,.75)}${person(20,1.05,.65)}</g>`,
  ];
  return `<svg viewBox="-70 -80 140 120" preserveAspectRatio="xMidYMax slice" width="100%" height="100%">${scenes[i]||scenes[0]}</svg>`;
}

function startOnb2(){
  show('scr-public');
  if(typeof pubGo==='function') pubGo('home');   /* the role cards only live on home */
  requestAnimationFrame(()=>{
    const cards=document.querySelector('.cl-roles');
    if(!cards) return;
    cards.scrollIntoView({behavior:'smooth',block:'center'});
    cards.classList.add('cl-roles-pulse');
    setTimeout(()=>cards.classList.remove('cl-roles-pulse'),1500);
  });
}
/* role chosen on the landing → straight into registration, no intermediate step */
function startOnbAs(role,ctx){ state._onbCtx=ctx||null; onbReset(role); saveRole(role); show('scr-onb2'); renderOnb2();
  if(ctx&&(ctx.field||ctx.step)) toast('Выбрано: '+(ctx.field||ctx.step));
}
/* prototype lead capture: stores locally and says so */
let _waitCC='+998';
function ccToggle(){ const cc=document.getElementById('clCC'); if(cc) cc.classList.toggle('open'); }
function ccPick(code,flag){
  _waitCC=code;
  const codeEl=document.getElementById('clCCCode'), flagEl=document.getElementById('clCCFlag'), cc=document.getElementById('clCC');
  if(codeEl) codeEl.textContent=code;
  if(flagEl) flagEl.textContent=flag;
  if(cc) cc.classList.remove('open');
  const inp=document.getElementById('leadPhone');
  if(inp){ // плейсхолдер под длину номера выбранной страны
    const len=(typeof PHONE_LEN!=='undefined'&&PHONE_LEN[code])||10;
    inp.placeholder = len===9 ? '__ ___ __ __' : '___ ___ __ __';
    inp.value=''; waitMask(inp);
  }
  waitValidate();
}
/* закрываем меню кликом вне */
document.addEventListener('click',e=>{ const cc=document.getElementById('clCC'); if(cc&&cc.classList.contains('open')&&!cc.contains(e.target)) cc.classList.remove('open'); });

function waitMask(el){
  const code=_waitCC;
  const max=(typeof PHONE_LEN!=='undefined'&&PHONE_LEN[code])||10;
  let d=(el.value||'').replace(/\D/g,'').slice(0,max);
  el.value = (typeof formatPhone==='function') ? formatPhone(code,d) : d;
}
function waitValidate(){
  const inp=document.getElementById('leadPhone'), btn=document.getElementById('clWaitBtn');
  if(!inp||!btn) return;
  const max=(typeof PHONE_LEN!=='undefined'&&PHONE_LEN[_waitCC])||10;
  const digits=(inp.value||'').replace(/\D/g,'');
  btn.disabled = digits.length < max;
}
function saveLead(){
  const inp=document.getElementById('leadPhone'); if(!inp) return;
  const max=(typeof PHONE_LEN!=='undefined'&&PHONE_LEN[_waitCC])||10;
  const v=(inp.value||'').replace(/\D/g,'');
  if(v.length<max){ toast('Введите номер телефона'); inp.focus(); return; }
  const full=_waitCC+' '+inp.value;
  try{ const L=JSON.parse(localStorage.getItem('z2h_leads')||'[]'); L.push({phone:full,ts:Date.now()}); localStorage.setItem('z2h_leads',JSON.stringify(L)); }catch(e){}
  const wrap=document.getElementById('clWait');
  if(wrap){ wrap.classList.add('done'); }
  else { inp.value=''; toast('Записали! Прототип: заявка сохранена локально'); }
}

/* ---- phone mask (requirement 2) ---- */
const PHONE_LEN={'+998':9,'+7':10,'+90':10,'+1':10,'+44':10};
function phoneDigits(v){ return (v||'').replace(/\D/g,''); }
function formatPhone(code,digits){
  if(code==='+998'){ // XX XXX XX XX
    const p=[digits.slice(0,2),digits.slice(2,5),digits.slice(5,7),digits.slice(7,9)].filter(Boolean);
    return p.join(' ');
  }
  // generic grouping by 3-3-2-2
  const p=[digits.slice(0,3),digits.slice(3,6),digits.slice(6,8),digits.slice(8,10)].filter(Boolean);
  return p.join(' ');
}
function onbPhone(el){
  const code=MOCK.reg.code||'+998';
  const max=PHONE_LEN[code]||10;
  let d=phoneDigits(el.value).slice(0,max);
  MOCK.reg.phoneDigits=d;
  MOCK.reg.phone=formatPhone(code,d);
  el.value=MOCK.reg.phone;
  const wrap=el.closest('.phone-field');
  if(wrap){
    const ok=d.length===max;
    wrap.classList.toggle('err', d.length>0 && !ok);
    wrap.classList.toggle('ok', ok);
    const hint=wrap.querySelector('.phone-hint');
    if(hint) hint.textContent = ok ? 'Номер введён' : `${d.length} / ${max} цифр`;
  }
}
function phoneField(){
  const code=MOCK.reg.code||'+998';
  const max=PHONE_LEN[code]||10;
  const d=MOCK.reg.phoneDigits||phoneDigits(MOCK.reg.phone);
  const ok=d.length===max;
  return `<div class="phone-field ${d.length>0&&!ok?'err':''} ${ok?'ok':''}">
    <div class="pf-row">
      <select class="pf-code" onchange="MOCK.reg.code=this.value;MOCK.reg.phone='';MOCK.reg.phoneDigits='';renderOnb2()">
        ${Object.keys(PHONE_LEN).map(c=>`<option ${code===c?'selected':''}>${c}</option>`).join('')}
      </select>
      <input class="pf-input" type="tel" inputmode="numeric" value="${MOCK.reg.phone||''}" oninput="onbPhone(this)" placeholder="${code==='+998'?'90 123 45 67':'000 000 00 00'}">
      <span class="pf-status">${ok?ico('check'):''}</span>
    </div>
    <div class="phone-hint">${d.length?`${d.length} / ${max} цифр`:`Введите ${max} цифр`}</div>
  </div>`;
}
function onbGo(step){ onbFlow.step=step; renderOnb2(); }

/* flow definition per role */
const STUDENT_STEPS=["role","register","sms","resume-choice","brief","ai-resume","work","summary","done"];
const OTHER_STEPS=["role","register-lite","sms","summary","done"];
const STEP_LABELS={role:"Роль",register:"Данные","register-lite":"Данные",sms:"Телефон","resume-choice":"Резюме",brief:"Бриф","ai-resume":"AI",work:"Интересы",summary:"Проверка",done:"Готово"};
/* which steps are skippable (requirement 10) */
const SKIPPABLE={brief:true,work:true};
function onbSteps(){ return onbFlow.role==='student' ? STUDENT_STEPS : (onbFlow.role?OTHER_STEPS:["role"]); }

function onbStepper(){
  const steps=onbSteps(), cur=onbFlow.step-1;
  /* condensed stepper: show milestone steps, not every sub-step */
  const milestones = onbFlow.role==='student'
    ? [["role","Роль"],["register","Данные"],["sms","Телефон"],["brief","Резюме"],["summary","Готово"]]
    : [["role","Роль"],["register-lite","Данные"],["sms","Телефон"],["summary","Готово"]];
  const idxOf=k=>steps.indexOf(k);
  return `<div class="onb-stepper">${milestones.map((m,i)=>{
    const mi=idxOf(m[0]); const done=cur>mi; const isCur=cur>=mi && (i===milestones.length-1?cur>=mi:cur<idxOf(milestones[i+1][0]));
    const cls=done?'done':(isCur?'cur':'');
    return `<div class="step ${cls}"><div class="sdot">${done?ico('check'):(i+1)}</div><span>${m[1]}</span></div>${i<milestones.length-1?`<div class="sline ${done?'done':''}"></div>`:''}`;
  }).join('')}</div>`;
}

function renderOnb2(){
  const steps=onbSteps(), i=onbFlow.step-1, key=steps[Math.min(i,steps.length-1)];
  document.getElementById('onb2-stepper').innerHTML = key==='done' ? '' : onbStepper();
  document.getElementById('onb2-body').innerHTML=(ONB[key]||ONB.role)();
  document.getElementById('scr-onb2').querySelector('.card').style.maxWidth =
    (key==='role') ? '960px'
    : (key==='register'||key==='register-lite'||key==='ai-resume'||key==='brief'||key==='work'||key==='summary') ? '560px' : '440px';
  saveOnbDraft();
}

/* requirement 6: universal back navigation */
function onbBack(){
  /* step 2 with no role screen behind it → the landing is the real "back" */
  if(onbFlow.step===2 && !onbFlow._viaPicker){ show('scr-public'); return; }
  if(onbFlow.step>1){ onbFlow.step--; renderOnb2(); } else { show('scr-public'); }
}
/* requirement 10: skip optional step */
function onbSkip(){ const steps=onbSteps(); if(onbFlow.step<steps.length){ onbFlow.step++; renderOnb2(); } }

/* requirement 9: autosave & resume registration draft */
function saveOnbDraft(){ try{ localStorage.setItem('z2h_onb_draft', JSON.stringify({flow:onbFlow, reg:MOCK.reg, work:MOCK.workFields, consent:MOCK.reg.consent||false})); }catch(e){} }
function clearOnbDraft(){ try{ localStorage.removeItem('z2h_onb_draft'); }catch(e){} }
function resumeOnbDraft(){
  try{
    const raw=localStorage.getItem('z2h_onb_draft'); if(!raw) return false;
    const d=JSON.parse(raw);
    if(!d.flow||!d.flow.role||d.flow.step<2) return false;
    onbFlow=d.flow; MOCK.reg=d.reg||MOCK.reg; MOCK.workFields=d.work||[];
    show('scr-onb2'); renderOnb2(); return true;
  }catch(e){ return false; }
}

/* nav buttons helper: back + primary(+skip) */
function onbNav(primaryLabel, primaryAction, opts){
  opts=opts||{};
  return `<div class="onb-nav">
    <button class="btn btn-ghost" onclick="onbBack()">← Назад</button>
    <button class="btn btn-primary grow" onclick="${primaryAction}">${primaryLabel}</button>
  </div>${opts.skip?`<span class="skip-link" onclick="onbSkip()">Пропустить этот шаг →</span>`:''}`;
}

/* ---- Title formatter for name fields (spec #3) ---- */
function titleCase(v){ return v.replace(/\S+/g,w=>w.charAt(0).toUpperCase()+w.slice(1).toLowerCase()); }
function onbName(el,field){ const p=el.selectionStart; el.value=titleCase(el.value); MOCK.reg[field]=el.value; try{el.setSelectionRange(p,p);}catch(e){} }
/* reusable field bound to MOCK.reg[field].
   Short lists → <select>. Long lists (>15) → searchable <input list=datalist>,
   which lets the user type to filter instead of scrolling a native dropdown.
   Both allow a free-text value that isn't in the list. */
let _dlSeq=0;
function onbSelect(field,options,placeholder){
  const val=MOCK.reg[field]||'';
  if(options.length>15) return onbCombo(field,options,placeholder,val);
  const inList=options.includes(val);
  const isOther = val==='__other__' || (val && !inList);
  const opts=options.map(o=>`<option ${val===o?'selected':''}>${o}</option>`).join('');
  return `<select onchange="onbSelectChange('${field}',this.value)">
      <option value="">${placeholder}</option>
      ${opts}
      <option value="__other__" ${isOther?'selected':''}>Другое (ввести вручную)</option>
    </select>
    ${isOther?`<div class="other-row"><input placeholder="Впишите свой вариант" value="${(val==='__other__')?'':val}" oninput="MOCK.reg['${field}']=this.value"></div>`:''}`;
}
function onbCombo(field,options,placeholder,val){
  const id='dl-'+field+'-'+(++_dlSeq);
  const known=options.includes(val);
  return `<div class="combo">
    <input list="${id}" class="combo-input" placeholder="${placeholder} — начните вводить"
           value="${(val&&val!=='__other__')?val.replace(/"/g,'&quot;'):''}"
           oninput="MOCK.reg['${field}']=this.value;onbComboHint('${field}')"
           onchange="MOCK.reg['${field}']=this.value;renderOnb2()">
    <datalist id="${id}">${options.map(o=>`<option value="${o.replace(/"/g,'&quot;')}"></option>`).join('')}</datalist>
    <span class="combo-ic">${ico('search')}</span>
  </div>
  <div class="combo-hint" id="hint-${field}">${val?(known?'Выбрано из списка':'Свой вариант — так и сохраним'):`${options.length} вариантов · можно вписать свой`}</div>`;
}
function onbComboHint(field){
  const el=document.getElementById('hint-'+field); if(!el) return;
  const v=MOCK.reg[field]||'';
  el.textContent = v ? 'Свой вариант сохранится, если его нет в списке' : 'Можно вписать свой вариант';
}
function onbSelectChange(field,v){ MOCK.reg[field]=v; renderOnb2(); }

/* ---------- multi-select with search, chips and free-text ----------
   Values live in MOCK.reg[field+'Arr'] (array). A summary string is mirrored
   into MOCK.reg[field] so existing single-value readers (resume, preview) keep working. */
function mcState(field){
  if(!Array.isArray(MOCK.reg[field+'Arr'])) MOCK.reg[field+'Arr']=[];
  return MOCK.reg[field+'Arr'];
}
function mcSync(field){
  const arr=mcState(field);
  MOCK.reg[field]=arr[0]||'';          // primary value for single-value consumers
  if(typeof persistState==='function') persistState();
}
function onbMultiCombo(field,options,placeholder){
  const arr=mcState(field);
  const q=(MOCK.reg['_q'+field]||'');
  const open=!!MOCK.reg['_open'+field];
  return `<div class="mcombo" id="mc-${field}">
    <div class="mcombo-box" onclick="mcFocus('${field}')">
      ${arr.map(v=>`<span class="mchip"><span>${v}</span><button onclick="event.stopPropagation();mcRemove('${field}',${JSON.stringify(v).replace(/"/g,'&quot;')})" title="Убрать">✕</button></span>`).join('')}
      <input class="mcombo-input" id="mci-${field}" autocomplete="off"
             placeholder="${arr.length?'Добавить ещё…':placeholder}"
             value="${q.replace(/"/g,'&quot;')}"
             oninput="mcInput('${field}',this.value)"
             onfocus="mcOpen('${field}')"
             onkeydown="mcKey(event,'${field}')">
      <span class="mc-ic">${ico('search')}</span>
    </div>
    ${open?mcListHtml(field,options):''}
    <div class="mcombo-foot" id="mcf-${field}">${arr.length?`Выбрано: ${arr.length}`:`${options.length} вариантов · можно выбрать несколько или вписать свой`}</div>
  </div>`;
}
function mcListHtml(field,options){
  const arr=mcState(field);
  const raw=(MOCK.reg['_q'+field]||'').trim();      // original case, shown to the user
  const q=raw.toLowerCase();                        // normalised, used for matching
  const list=options.filter(o=>!q||o.toLowerCase().includes(q));
  const exact=options.some(o=>o.toLowerCase()===q)||arr.some(o=>o.toLowerCase()===q);
  return `<div class="mcombo-list" id="mcl-${field}">
    ${list.map(o=>{const on=arr.includes(o);return `<div class="mcombo-opt ${on?'on':''}" onmousedown="event.preventDefault();mcToggle('${field}',${JSON.stringify(o).replace(/"/g,'&quot;')})">
      <span class="mo-box">${ico('check')}</span>${o}</div>`;}).join('')}
    ${(raw&&!exact)?`<div class="mcombo-add" onmousedown="event.preventDefault();mcAddCustom('${field}')">${ico('plus')}Добавить «${raw}»</div>`:''}
    ${(!list.length&&!raw)?`<div class="mcombo-empty">Список пуст</div>`:''}
    ${(!list.length&&raw&&exact)?`<div class="mcombo-empty">Уже выбрано</div>`:''}
  </div>`;
}
/* re-render only the dropdown + footer so the input keeps focus and caret */
function mcRefresh(field,options){
  const root=document.getElementById('mc-'+field); if(!root){ renderOnb2(); return; }
  const oldList=document.getElementById('mcl-'+field);
  if(MOCK.reg['_open'+field]){
    const wrap=document.createElement('div'); wrap.innerHTML=mcListHtml(field,options);
    const fresh=wrap.firstElementChild;
    if(oldList) oldList.replaceWith(fresh); else root.insertBefore(fresh,document.getElementById('mcf-'+field));
  }else if(oldList){ oldList.remove(); }
  const foot=document.getElementById('mcf-'+field);
  if(foot){ const n=mcState(field).length; foot.textContent = n?`Выбрано: ${n}`:`${options.length} вариантов · можно выбрать несколько или вписать свой`; }
}
function mcOptions(field){ return field==='goal'?REF_DIRECTIONS:[]; }
function mcFocus(field){ const i=document.getElementById('mci-'+field); if(i)i.focus(); }
function mcOpen(field){ MOCK.reg['_open'+field]=true; mcRefresh(field,mcOptions(field)); }
function mcInput(field,v){ MOCK.reg['_q'+field]=v; MOCK.reg['_open'+field]=true; mcRefresh(field,mcOptions(field)); }
function mcToggle(field,val){
  const arr=mcState(field), i=arr.indexOf(val);
  if(i>-1) arr.splice(i,1); else arr.push(val);
  MOCK.reg['_q'+field]=''; mcSync(field);
  renderOnb2();  // chips changed → full redraw, then reopen
  MOCK.reg['_open'+field]=true; mcRefresh(field,mcOptions(field)); mcFocus(field);
}
function mcRemove(field,val){
  const arr=mcState(field), i=arr.indexOf(val);
  if(i>-1) arr.splice(i,1);
  mcSync(field); renderOnb2();
}
function mcAddCustom(field){
  const q=(MOCK.reg['_q'+field]||'').trim(); if(!q) return;
  const arr=mcState(field);
  if(!arr.includes(q)) arr.push(q);
  MOCK.reg['_q'+field]=''; mcSync(field); renderOnb2();
  MOCK.reg['_open'+field]=true; mcRefresh(field,mcOptions(field)); mcFocus(field);
}
function mcKey(e,field){
  const q=(MOCK.reg['_q'+field]||'').trim();
  if(e.key==='Enter'){ e.preventDefault();
    const opts=mcOptions(field);
    const hit=opts.find(o=>o.toLowerCase()===q.toLowerCase()) || opts.filter(o=>o.toLowerCase().includes(q.toLowerCase()))[0];
    if(hit) mcToggle(field,hit); else if(q) mcAddCustom(field);
  }else if(e.key==='Backspace' && !q){
    const arr=mcState(field); if(arr.length){ arr.pop(); mcSync(field); renderOnb2(); }
  }else if(e.key==='Escape'){ MOCK.reg['_open'+field]=false; mcRefresh(field,mcOptions(field)); }
}
/* close dropdown when clicking outside */
document.addEventListener('mousedown',e=>{
  ['goal'].forEach(f=>{
    if(!MOCK.reg||!MOCK.reg['_open'+f]) return;
    const root=document.getElementById('mc-'+f);
    if(root && !root.contains(e.target)){ MOCK.reg['_open'+f]=false; mcRefresh(f,mcOptions(f)); }
  });
});

/* ---- skills with proficiency, shared with the resume (MOCK.resumeData.skillLevels) ---- */
const SKILL_LVL_HINT={
  'Базовый':'Знаком, делал под присмотром',
  'Средний':'Решаю типовые задачи сам',
  'Продвинутый':'Работаю уверенно и быстро',
  'Эксперт':'Могу учить других',
};
function skillLevelsMap(){
  if(!MOCK.resumeData||typeof MOCK.resumeData!=='object') MOCK.resumeData={};
  if(!MOCK.resumeData.skillLevels||typeof MOCK.resumeData.skillLevels!=='object') MOCK.resumeData.skillLevels={};
  return MOCK.resumeData.skillLevels;
}
function skillChosen(){ return MOCK.reg.skillsArr||[]; }
function skillToggle(name){
  if(!Array.isArray(MOCK.reg.skillsArr)) MOCK.reg.skillsArr=[];
  const arr=MOCK.reg.skillsArr, lv=skillLevelsMap(), i=arr.indexOf(name);
  if(i>-1){ arr.splice(i,1); delete lv[name]; }
  else { arr.push(name); lv[name]='Средний'; }   // sensible default, not the lowest
  MOCK.reg.skills=arr.join(', ');
  if(typeof persistState==='function') persistState();
  renderOnb2();
}
function skillSetLevel(name,lvl){
  const lv=skillLevelsMap();
  lv[name]=lvl;
  if(typeof persistState==='function') persistState();
  renderOnb2();
}
function skillAddOther(){
  const v=(prompt('Какой навык добавить?')||'').trim();
  if(!v) return;
  if(!Array.isArray(MOCK.reg.skillsArr)) MOCK.reg.skillsArr=[];
  if(!MOCK.reg.skillsArr.includes(v)){ MOCK.reg.skillsArr.push(v); skillLevelsMap()[v]='Средний'; }
  MOCK.reg.skills=MOCK.reg.skillsArr.join(', ');
  if(typeof persistState==='function') persistState();
  renderOnb2();
}
function skillPicker(catalog){
  const chosen=skillChosen();
  const lv=skillLevelsMap();
  const all=[...catalog,...chosen.filter(c=>!catalog.includes(c))];   // custom skills go last
  const cards=all.filter(s=>chosen.includes(s));
  const chips=all.filter(s=>!chosen.includes(s));

  const card=name=>{
    const cur=lv[name]||'Средний';
    const idx=SKILL_LEVELS.indexOf(cur);
    return `<div class="skill-card">
      <div class="sk-head">
        <span class="sk-check">${ico('check')}</span>
        <span class="sk-name">${name}</span>
        <button class="sk-x" onclick="skillToggle(${JSON.stringify(name).replace(/"/g,'&quot;')})" title="Убрать">✕</button>
      </div>
      <div class="lvl-pick">
        ${SKILL_LEVELS.map((l,i)=>`<div class="lvl-seg ${i<=idx?'filled':''} ${i===idx?'active':''}"
             onclick="skillSetLevel(${JSON.stringify(name).replace(/"/g,'&quot;')},'${l}')" title="${SKILL_LVL_HINT[l]}">
          <div class="ls-bar"></div><div class="ls-t">${l}</div>
        </div>`).join('')}
      </div>
      <div class="lvl-hint">${ico('spark')}<span>${SKILL_LVL_HINT[cur]}</span></div>
    </div>`;
  };

  return `<div class="skill-grid">
      ${cards.map(card).join('')}
      ${chips.map(sName=>`<button class="skill-chip" onclick="skillToggle(${JSON.stringify(sName).replace(/"/g,'&quot;')})">
        <span class="sk-plus">${ico('plus')}</span>${sName}</button>`).join('')}
      <button class="skill-chip" onclick="skillAddOther()"><span class="sk-plus">${ico('plus')}</span>Другое</button>
    </div>
    ${chosen.length?`<div class="sk-summary">${ico('check')}<span>Выбрано <b>${chosen.length}</b> ${plural(chosen.length,'навык','навыка','навыков')} · уровень указан у каждого</span></div>`
                   :`<div class="sk-summary">${ico('spark')}<span>Отметьте навыки — затем укажите, насколько уверенно владеете</span></div>`}`;
}
/* "SQL · Продвинутый, Python · Средний" — used in the AI preview and the summary screen */
function skillSummary(){
  const arr=(MOCK.reg&&MOCK.reg.skillsArr)||[];
  const lv=(MOCK.resumeData&&MOCK.resumeData.skillLevels)||{};
  return arr.map(s=>lv[s]?`${s} · ${lv[s]}`:s).join(', ');
}
function plural(n,one,few,many){
  const m=n%100, d=n%10;
  if(m>=11&&m<=14) return many;
  if(d===1) return one;
  if(d>=2&&d<=4) return few;
  return many;
}


const ONB={
  /* STEP 1: role selection (spec #1 — role first) */
  role:()=>{
    const cards=[
      ["student","student","Студент","Пройдите путь от диагностики до первой стажировки",
        [["target","Персональная траектория"],["spark","Реальные бизнес-кейсы"],["briefcase","Отклик на вакансии"]]],
      ["company","company","Компания","Находите и нанимайте готовых кандидатов через симуляции",
        [["users","Готовые кандидаты"],["briefcase","Публикация стажировок"],["target","Воронка найма"]]],
      ["university","university","ВУЗ","Ведите когорты студентов и отслеживайте их прогресс",
        [["users","Управление когортами"],["target","Аналитика компетенций"],["doc","Отчёты по готовности"]]],
      ["mentor","check","Ментор","Подтверждайте часы практики и оценивайте своих практикантов",
        [["check","Подтверждение часов"],["users","Мои практиканты"],["target","Оценка навыков"]]],
      ["admin","gear","Админ","Панель администратора платформы: договоры, KPI, трудоустройство",
        [["doc","Реестр договоров"],["target","Сводный KPI по вузам"],["users","Мониторинг трудоустройства"]]],
    ];
    return `<div class="role-hero">
      <div class="rh-eyebrow">Карьерный центр · Узбекистан</div>
      <h1>С чего начнём?</h1>
      <p class="rh-sub">Выберите свою роль — интерфейс и возможности подстроятся под неё.</p>
      <div class="role-cards">
        ${cards.map(c=>`
          <div class="role-card${onbFlow.role===c[0]?' on':''}" onclick="onbChooseRole('${c[0]}')">
            <div class="rc-top">
              <div class="rc-ic">${IC[c[1]]}</div>
              <div class="rc-check">${IC.check}</div>
            </div>
            <h3>${c[2]}</h3>
            <div class="rc-desc">${c[3]}</div>
            <ul class="rc-feats">${c[4].map(f=>`<li>${IC[f[0]]}${f[1]}</li>`).join('')}</ul>
            <div class="rc-go">Продолжить как ${c[2].toLowerCase()} →</div>
          </div>`).join('')}
      </div>
    </div>`;
  },

  /* STEP 2 (student): full registration form (spec #2) */
  register:()=>`<h2 class="title">Регистрация студента</h2>
    <p class="subtitle">Заполните основные данные.</p>
    <div class="form-grid">
      <div class="field" id="f-first"><label>Имя *</label><input value="${MOCK.reg.first}" oninput="onbName(this,'first')" placeholder="Имя"><div class="field-err">Укажите имя</div></div>
      <div class="field" id="f-last"><label>Фамилия *</label><input value="${MOCK.reg.last}" oninput="onbName(this,'last')" placeholder="Фамилия"><div class="field-err">Укажите фамилию</div></div>
      <div class="field full" id="f-city"><label>Город проживания *</label>${onbSelect('city',REF_CITIES,'Выберите город')}<div class="field-err">Выберите город</div></div>
      <div class="field full"><label>Университет</label>${onbSelect('university',REF_UNIVERSITIES,'Выберите университет')}</div>
      <div class="field"><label>Направление</label>${onbSelect('direction',REF_DIRECTIONS,'Выберите направление')}</div>
      <div class="field"><label>Курс</label>${onbSelect('course',REF_COURSES,'Выберите курс')}</div>
      <div class="field full"><label>Дата рождения</label><input type="date" min="1950-01-01" max="2012-12-31" value="${MOCK.reg.birth}" oninput="clampBirth(this,'onb')" onchange="clampBirth(this,'onb')"></div>
      <div class="field full"><label>Формат стажировки</label>
        <div class="seg">
          ${REF_FORMATS.map(f=>`<button class="${MOCK.reg.format===f?'on':''}" onclick="MOCK.reg.format='${f}';renderOnb2()">${f}</button>`).join('')}
        </div></div>
      <div class="field full" id="f-phone"><label>Номер телефона *</label>${phoneField()}</div>
    </div>
    ${consentRow()}
    ${onbNav("Зарегистрироваться →","onbRegisterNext()")}`,

  /* STEP 2 (univ/company): full selectable registration */
  "register-lite":()=>`<h2 class="title">Регистрация организации</h2>
    <p class="subtitle">Укажите данные организации.</p>
    <div class="form-grid">
      <div class="field full" id="f-org"><label>Название организации *</label><input value="${MOCK.reg.org||''}" oninput="MOCK.reg.org=this.value" placeholder="Название"><div class="field-err">Укажите название</div></div>
      <div class="field" id="f-orgType"><label>Тип организации *</label>${onbSelect('orgType',REF_ORG_TYPES,'Выберите тип')}<div class="field-err">Выберите тип</div></div>
      <div class="field"><label>Регион</label>${onbSelect('region',REF_REGIONS,'Выберите регион')}</div>
      <div class="field full"><label>Сайт</label><input value="${MOCK.reg.site||''}" oninput="MOCK.reg.site=this.value" placeholder="https://..."></div>
      <div class="field full" id="f-contact"><label>Контактное лицо *</label><input value="${MOCK.reg.contact||''}" oninput="onbName(this,'contact')" placeholder="Имя Фамилия"><div class="field-err">Укажите контактное лицо</div></div>
      <div class="field full" id="f-phone"><label>Номер телефона *</label>${phoneField()}</div>
    </div>
    ${consentRow()}
    ${onbNav("Зарегистрироваться →","onbRegisterNext()")}`,

  /* STEP: SMS confirmation (any code ok) */
  sms:()=>`<div class="onb-banner"><h2>${IC.phone} Подтвердите телефон</h2><p>Код отправлен на ${(MOCK.reg.code||'+998')} ${MOCK.reg.phone||"ваш номер"}</p></div>
    <div class="field"><label>Код из SMS</label><input id="onb-code" inputmode="numeric" placeholder="0000" value="1234"></div>
    <div class="otp-note">Демо: любой код считается верным. SMS не отправляются.</div>
    ${onbNav("Подтвердить →","onbConfirmSms()")}
    ${onbFlow.role==='student'?`<p class="hint" style="margin-top:10px"><a onclick="onbSkipToApp()">Заполнить профиль позже — сразу в кабинет →</a></p>`:''}`,

  /* STEP (student): resume choice — create OR upload */
  "resume-choice":()=>`<h2 class="title">Резюме</h2>
    <p class="subtitle">Создайте новое или загрузите готовое.</p>
    <div class="big-choice">
      <div class="bc-card" onclick="onbGo(5)"><div class="bc-ic">${IC.doc}</div><h4>Создать резюме</h4><p>Ответьте на пару вопросов — соберём за вас</p></div>
      <div class="bc-card" onclick="onbUploadResume()"><div class="bc-ic">${IC.upload}</div><h4>Загрузить резюме</h4><p>PDF или DOCX с вашего устройства</p></div>
    </div>
    <div class="onb-nav"><button class="btn btn-ghost" onclick="onbBack()">← Назад</button></div>`,

  /* STEP (student): mini-brief — languages with level, skills, other options */
  brief:()=>{
    const skills=["Excel / таблицы","Презентации","Копирайтинг","SMM","SQL","Python","Дизайн (Figma)","Аналитика","Коммуникация","Работа в команде"];
    const exp=["Нет опыта","Учебные проекты","Волонтёрство","Подработка / фриланс","Стажировка","Постоянная работа"];
    return `<div class="onb-banner"><h2>${IC.spark} Мини-бриф</h2><p>Отметьте подходящее — AI соберёт черновик резюме</p></div>
    <div class="brief-q"><label>${IC.globe} Языки и уровень</label>${langLevels()}</div>
    <div class="brief-q"><label>${IC.briefcase} Есть ли опыт работы?</label>${onbSelect('exp',exp,'Выберите вариант')}</div>
    <div class="brief-q"><label>${IC.target} Чем хотите заниматься?</label>${onbMultiCombo('goal',REF_DIRECTIONS,'Выберите направления')}</div>
    <div class="brief-q"><label>${IC.spark} Что умеете делать?</label>
      ${skillPicker(skills)}</div>
    ${onbNav(ico('spark')+" Сформировать резюме","onbGenResume()",{skip:true})}`;
  },

  /* STEP (student): AI-generated preview (mock) */
  "ai-resume":()=>{const r=MOCK.reg;return `<h2 class="title">AI собрал резюме</h2>
    <p class="subtitle">Черновик на основе брифа. Отредактируете позже.</p>
    <div class="ai-preview">
      <span class="aip-badge">${IC.spark} Сформировано AI</span>
      <div class="rh">${(r.first||"Имя")+" "+(r.last||"Фамилия")}</div>
      <div class="rsub">${((r.goalArr&&r.goalArr.length)?r.goalArr.join(' · '):(r.goal||r.direction))||"Junior специалист"}</div>
      <div class="rsec">О себе</div>
      <p>Студент${r.university?" · "+r.university:""}${r.course?", "+r.course:""}. Ищу стажировку в формате «${r.format}».</p>
      <div class="rsec">Языки</div><p>${langSummary()||"—"}</p>
      <div class="rsec">Навыки</div><p>${skillSummary()||"—"}</p>
      <div class="rsec">Опыт</div><p>${r.exp||"Учебные проекты"}</p>
    </div>
    ${onbNav("Всё верно, продолжить →","onbGo(7)")}`;},

  /* STEP (student): desired work fields, multi-select */
  work:()=>{
    const q=(MOCK.reg._fieldQuery||'').toLowerCase().trim();
    const list=WORK_FIELDS.filter(([name])=>!q||name.toLowerCase().includes(q));
    const chosen=(MOCK.workFields||[]).length+(MOCK.workFieldsOther||[]).length;
    return `<div class="onb-banner"><h2>${IC.target} Кем хотите работать?</h2><p>Выберите направления — по ним подберём вакансии</p></div>
    <div class="field-search">${ico('search')}<input placeholder="Найти направление…" value="${MOCK.reg._fieldQuery||''}" oninput="setFieldQuery(this.value)"></div>
    <div class="chip-count">${chosen?`Выбрано: ${chosen}`:'Можно выбрать несколько'}</div>
    <div class="chip-scroll">
      <div class="chip-pick">
        ${list.map(([name,ic])=>`<button class="${MOCK.workFields.includes(name)?'on':''}" onclick="onbToggleField('${name}')">${IC[ic]}${name}</button>`).join('')}
        ${(MOCK.workFieldsOther||[]).map(name=>`<button class="on" onclick="onbRemoveWorkOther('${name}')">${name} ✕</button>`).join('')}
        <button onclick="onbAddWorkOther()">+ Другое</button>
      </div>
      ${list.length===0?`<div style="text-align:center;color:var(--muted);font-size:13px;padding:16px">Ничего не найдено — добавьте своё через «+ Другое»</div>`:''}
    </div>
    ${onbNav("Продолжить →","onbGo(8)",{skip:true})}`;
  },

  /* STEP: summary before finish (requirement 11) */
  summary:()=>{
    const r=MOCK.reg;
    const rows = onbFlow.role==='student'
      ? [["Роль","Студент"],["Имя",[r.first,r.last].filter(Boolean).join(' ')||'—'],["Город",r.city||'—'],
         ["Университет",r.university||'—'],["Направление",r.direction||'—'],["Курс",r.course||'—'],
         ["Телефон",(r.code||'+998')+' '+(r.phone||'—')],["Языки",langSummary()||'—'],
         ["Чем заниматься",((r.goalArr&&r.goalArr.length)?r.goalArr.join(', '):(r.goal||'—'))],
         ["Интересы",[...(MOCK.workFields||[]),...(MOCK.workFieldsOther||[])].join(', ')||'—']]
      : [["Роль",onbFlow.role==='university'?'ВУЗ':'Компания'],["Организация",r.org||'—'],["Тип",r.orgType||'—'],
         ["Регион",r.region||'—'],["Контакт",r.contact||'—'],["Телефон",(r.code||'+998')+' '+(r.phone||'—')]];
    return `<h2 class="title">Проверьте данные</h2>
    <p class="subtitle">Всё верно? Можно вернуться и поправить.</p>
    <div class="sum-card">${rows.map(x=>`<div class="sum-row"><span class="sk">${x[0]}</span><span class="sv">${x[1]}</span></div>`).join('')}</div>
    ${onbNav("Подтвердить и открыть кабинет →", onbFlow.role==='student'?"onbFinishStudent()":"onbFinishOther()")}`;
  },

  /* STEP: done (univ/company) */
  done:()=>`<div style="text-align:center;padding:14px 0"><div class="bc-ic" style="width:56px;height:56px;margin:0 auto 14px">${IC.check}</div><h2 class="title">Готово</h2><p class="subtitle" style="max-width:300px;margin:6px auto 0">Открываем ваш кабинет.</p></div>`,
};

/* consent (requirement 1) */
function consentRow(){
  const on=!!MOCK.reg.consent;
  return `<div class="consent ${on?'on':''}" id="consent-row" onclick="MOCK.reg.consent=!MOCK.reg.consent;renderOnb2()">
    <div class="cbox">${ico('check')}</div>
    <div>Я согласен на обработку персональных данных и принимаю <a onclick="event.stopPropagation();toast('Демо: политика конфиденциальности')">условия и политику конфиденциальности</a>.</div>
  </div>`;
}

/* languages with proficiency level (requirement 2) */
const LANG_LIST=["Узбекский","Русский","Английский","Каракалпакский","Казахский","Турецкий","Немецкий","Корейский","Арабский","Китайский","Французский","Испанский"];
/* CEFR codes stay in the data (so old profiles keep working),
   but the UI always shows plain language first — most people don't know what "B1" is. */
const LANG_LEVELS=["A1","A2","B1","B2","C1","C2","Родной"];
const LANG_META={
  'A1':{n:'Начальный',   d:'Знаю отдельные слова и простые фразы'},
  'A2':{n:'Базовый',     d:'Понимаю простую речь, могу представиться и попросить о помощи'},
  'B1':{n:'Средний',     d:'Общаюсь на бытовые темы, понимаю основную мысль текста'},
  'B2':{n:'Уверенный',   d:'Свободно говорю на большинство тем, понимаю фильмы и статьи'},
  'C1':{n:'Продвинутый', d:'Работаю и учусь на этом языке, говорю почти без усилий'},
  'C2':{n:'В совершенстве',d:'Понимаю всё, выражаюсь точно и тонко'},
  'Родной':{n:'Родной',  d:'Язык, на котором вы выросли'},
};
function langLabel(code){ return (LANG_META[code]||{}).n || code; }
function langDesc(code){ return (LANG_META[code]||{}).d || ''; }

/* the level rail shows 5 rungs; C2 and «Родной» sit at the top end */
const LANG_RAIL=["A1","A2","B1","B2","C1","C2","Родной"];

function langLevels(){
  MOCK.reg.langLevels = MOCK.reg.langLevels || {};
  const chosen=MOCK.reg.langLevels;
  const custom=MOCK.reg.langCustom||[];
  const all=[...LANG_LIST,...custom.filter(c=>!LANG_LIST.includes(c))];
  const picked=all.filter(l=>chosen[l]!=null);
  const rest=all.filter(l=>chosen[l]==null);

  const card=l=>{
    const cur=chosen[l]||'B1';
    const idx=LANG_RAIL.indexOf(cur);
    return `<div class="lang-card">
      <div class="lc-head">
        <span class="lc-check">${ico('check')}</span>
        <span class="lc-name">${l}</span>
        <button class="lc-x" onclick="onbToggleLang(${JSON.stringify(l).replace(/"/g,'&quot;')})" title="Убрать">✕</button>
      </div>
      <div class="lang-rail">
        ${LANG_RAIL.map((code,i)=>`<div class="lang-lvl ${i<=idx?'filled':''} ${i===idx?'active':''}"
             onclick="onbSetLang(${JSON.stringify(l).replace(/"/g,'&quot;')},'${code}')" title="${langDesc(code)}">
          <div class="ll-bar"></div>
          <div class="ll-t">${langLabel(code)}</div>
          <div class="ll-code">${code==='Родной'?'':code}</div>
        </div>`).join('')}
      </div>
      <div class="lang-explain">${ico('spark')}<span><b>${langLabel(cur)}</b> — ${langDesc(cur)}</span></div>
    </div>`;
  };

  return `<div class="lang-grid">
      ${picked.map(card).join('')}
      ${rest.map(l=>`<button class="lang-chip" onclick="onbToggleLang(${JSON.stringify(l).replace(/"/g,'&quot;')})">
        <span class="lc-plus">${ico('plus')}</span>${l}</button>`).join('')}
      <button class="lang-chip" onclick="onbAddLang()"><span class="lc-plus">${ico('plus')}</span>Другой язык</button>
    </div>
    ${picked.length?`<div class="sk-summary">${ico('check')}<span>Выбрано <b>${picked.length}</b> ${plural(picked.length,'язык','языка','языков')} · уровень указан у каждого</span></div>`:''}
    <details class="lvl-help">
      <summary>${ico('compass')}Что означают уровни?</summary>
      <div class="lh-body">
        ${LANG_RAIL.map(code=>`<div class="lh-row">
          <span class="lh-code">${code==='Родной'?'—':code}</span>
          <div><div class="lh-n">${langLabel(code)}</div><div class="lh-d">${langDesc(code)}</div></div>
        </div>`).join('')}
        <div class="lh-row" style="border:none;padding-top:10px">
          <div class="lh-d">A1–C2 — это шкала CEFR, общеевропейский стандарт. Её понимают работодатели и вузы.</div>
        </div>
      </div>
    </details>`;
}
function onbToggleLang(l){
  MOCK.reg.langLevels=MOCK.reg.langLevels||{};
  if(MOCK.reg.langLevels[l]!=null) delete MOCK.reg.langLevels[l];
  else MOCK.reg.langLevels[l]='B1';
  syncLangArr();
  if(typeof persistState==='function') persistState();
  renderOnb2();
}
function onbSetLang(l,code){
  MOCK.reg.langLevels=MOCK.reg.langLevels||{};
  MOCK.reg.langLevels[l]=code;
  if(typeof persistState==='function') persistState();
  renderOnb2();
}
function onbAddLang(){
  const v=(prompt('Какой язык добавить?')||'').trim();
  if(!v) return;
  MOCK.reg.langCustom=MOCK.reg.langCustom||[];
  if(!MOCK.reg.langCustom.includes(v)&&!LANG_LIST.includes(v)) MOCK.reg.langCustom.push(v);
  MOCK.reg.langLevels=MOCK.reg.langLevels||{};
  MOCK.reg.langLevels[v]='B1';
  syncLangArr();
  if(typeof persistState==='function') persistState();
  renderOnb2();
}
/* keep the plain array in step with the level map (other screens read it) */
function syncLangArr(){ MOCK.reg.langsArr=Object.keys(MOCK.reg.langLevels||{}); }
/* "Английский · Уверенный (B2)" — readable, but keeps the code for recruiters */
function langSummary(){
  const m=MOCK.reg.langLevels||{};
  return Object.keys(m).map(l=>{
    const c=m[l];
    return c==='Родной' ? `${l} · родной` : `${l} · ${langLabel(c)} (${c})`;
  }).join(', ');
}
function onbAddOther(field,promptText){ const v=prompt(promptText); if(!v)return; MOCK.reg[field]=MOCK.reg[field]||[]; if(!MOCK.reg[field].includes(v))MOCK.reg[field].push(v); renderOnb2(); }
function onbAddWorkOther(){ const v=prompt('Добавьте направление:'); if(!v)return; MOCK.workFieldsOther=MOCK.workFieldsOther||[]; if(!MOCK.workFieldsOther.includes(v))MOCK.workFieldsOther.push(v); renderOnb2(); }
/* filter the 30 work fields; re-render only the chip area so the input keeps focus */
function setFieldQuery(q){
  MOCK.reg._fieldQuery=q;
  const body=document.getElementById('onb2-body'); if(!body){ renderOnb2(); return; }
  const wrap=document.createElement('div'); wrap.innerHTML=ONB.work();
  const fresh=wrap.querySelector('.chip-scroll'); const cur=body.querySelector('.chip-scroll');
  const freshCount=wrap.querySelector('.chip-count'); const curCount=body.querySelector('.chip-count');
  if(fresh&&cur){ cur.replaceWith(fresh); if(freshCount&&curCount) curCount.replaceWith(freshCount); }
  else renderOnb2();
}
function onbRemoveWorkOther(v){ MOCK.workFieldsOther=(MOCK.workFieldsOther||[]).filter(x=>x!==v); renderOnb2(); }

/* ---- onboarding actions ---- */
function onbPickRole(r){ onbFlow.role=r; saveRole(r); renderOnb2(); }
function onbChooseRole(r){ onbFlow.role=r; saveRole(r); onbGo(2); } /* select + advance */
/* explicit "change role" from the auth screen — this is the one place the role
   picker still earns its own screen, because there is no landing behind it */
function startOnbPickRole(){ onbReset(null); onbFlow._viaPicker=true; show('scr-onb2'); renderOnb2(); }
function onbAfterRole(){ if(!onbFlow.role){toast("Выберите роль");return;} onbGo(2); }
function markInvalid(id,bad){ const el=document.getElementById(id); if(el) el.classList.toggle('invalid',bad); return bad; }
function isEmail(v){ return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(v||''); }
function onbRegisterNext(){
  const r=MOCK.reg, code=r.code||'+998', need=PHONE_LEN[code]||10;
  const d=r.phoneDigits||phoneDigits(r.phone);
  let bad=false;
  if(onbFlow.role==='student'){
    bad = markInvalid('f-first',!r.first) | bad;
    bad = markInvalid('f-last',!r.last) | bad;
    bad = markInvalid('f-city',!r.city) | bad;
  }else{
    bad = markInvalid('f-org',!r.org) | bad;
    bad = markInvalid('f-orgType',!r.orgType) | bad;
    bad = markInvalid('f-contact',!r.contact) | bad;
  }
  bad = markInvalid('f-phone', d.length!==need) | bad;
  const consentBad = !r.consent;
  const crow=document.getElementById('consent-row'); if(crow) crow.classList.toggle('err',consentBad);
  if(bad){ toast('Заполните обязательные поля'); return; }
  if(consentBad){ toast('Подтвердите согласие на обработку данных'); return; }
  MOCK.users.phone=code+' '+r.phone;
  state.email=MOCK.users.phone;
  persistState();
  onbGo(3); /* → SMS */
}
/* SMS already is the activation — everything after it is profile, not access.
   The draft survives, so the same onboarding can be resumed from the banner. */
function onbSkipToApp(){
  MOCK.users.code=(document.getElementById('onb-code')||{}).value||"1234";
  MOCK.users.role='student';
  MOCK.users.fromMockFlow=true;
  MOCK.users.resumeCompleted=false;
  MOCK.users.onbDeferred=true;      /* → the nudge banner appears on home */
  persistState();                    /* z2h_onb_draft is deliberately NOT cleared */
  toast("Аккаунт создан. Профиль можно заполнить позже.");
  enterApp('student',true);
}
/* resume the interrupted onboarding exactly where the draft left off */
function onbResume(){
  onbFlow={role:'student',step:4};   /* step 4 = resume-choice, right after sms */
  MOCK.users.onbDeferred=false;
  show('scr-onb2'); renderOnb2();
}

function onbConfirmSms(){
  MOCK.users.code=(document.getElementById('onb-code')||{}).value||"1234"; /* any code ok */
  if(onbFlow.role==='student'){ onbGo(4); }   /* → resume choice */
  else{ onbGo(4); }                            /* → summary (org) */
}
function onbUploadResume(){ toast("Резюме загружено (демо)"); MOCK.reg.skills=MOCK.reg.skills||"Импортировано из файла"; onbGo(6); }
function onbGenResume(){ toast("AI сформировал резюме (демо)"); onbGo(6); }
function onbToggleField(name){ const i=MOCK.workFields.indexOf(name); if(i>-1)MOCK.workFields.splice(i,1); else MOCK.workFields.push(name); renderOnb2(); }
/* multi-select toggle for array fields in MOCK.reg (languages, skills) */
function onbMulti(field,val){ if(!Array.isArray(MOCK.reg[field]))MOCK.reg[field]=[]; const a=MOCK.reg[field]; const i=a.indexOf(val); if(i>-1)a.splice(i,1); else a.push(val); MOCK.reg[field.replace('Arr','')]=a.join(', '); renderOnb2(); }
function onbFinishStudent(){
  MOCK.users.role='student'; MOCK.users.fromMockFlow=true; MOCK.users.resumeCompleted=true; /* resume built → AI assistant unlocked */
  clearOnbDraft(); persistState();
  toast("Добро пожаловать в Zero-to-Hero");
  enterApp('student',true);
}
function onbFinishOther(){
  const role=onbFlow.role||'student';
  MOCK.users.role=role; MOCK.users.fromMockFlow=true; MOCK.users.resumeCompleted=false;
  clearOnbDraft(); persistState();
  enterApp(role,true);
}
/* legacy finish kept as no-op alias to avoid breaking old refs */
function onb2Finish(){ onbFinishStudent(); }

/* fresh student home — zero-state consistent with what registration actually produced */
function studentHeroBanner(){
  const name=[(MOCK.reg&&MOCK.reg.first)||'',(MOCK.reg&&MOCK.reg.last)||''].join(' ').trim()||'Студент';
  const uni=(MOCK.reg&&MOCK.reg.university)||'';
  const course=(MOCK.reg&&MOCK.reg.course)||'';
  const fmt=(MOCK.reg&&MOCK.reg.format)||'';
  const photo=MOCK.users.photo;
  const pct=(typeof resumeCompleteness==='function')?resumeCompleteness():0;
  const r=44,c=2*Math.PI*r,off=c-(pct/100)*c;
  const hour=new Date().getHours();
  const greet = hour<6?'Доброй ночи':hour<12?'Доброе утро':hour<18?'Добрый день':'Добрый вечер';
  const first=(MOCK.reg&&MOCK.reg.first)||'';
  return `<div class="hero-banner">
    <div class="hb-avatar">
      ${photo?`<img src="${photo}" alt="">`:`<div class="ph-illu">${ico('user')}</div>`}
      <div class="hb-upload" onclick="uploadPhoto()">Загрузить</div>
    </div>
    <div class="hb-info">
      <div class="hb-sub" style="opacity:.75;margin:0 0 2px;display:flex;align-items:center;gap:6px">${ico('wave')}${greet}${first?', '+first:''}</div>
      <div class="hb-hi">${name}</div>
      <div class="hb-sub">${(MOCK.reg&&MOCK.reg.direction)||'Будущий специалист'}</div>
      <div class="hb-meta">
        ${uni?`<span class="hb-chip">${ico('university')}${uni.length>28?uni.slice(0,26)+'…':uni}</span>`:''}
        ${course?`<span class="hb-chip">${ico('student')}${course}</span>`:''}
        ${fmt?`<span class="hb-chip">${ico('briefcase')}${fmt}</span>`:''}
      </div>
    </div>
    <div class="hb-ring">
      <svg width="104" height="104" viewBox="0 0 104 104">
        <circle cx="52" cy="52" r="${r}" fill="none" stroke="rgba(255,255,255,.22)" stroke-width="8"/>
        <circle cx="52" cy="52" r="${r}" fill="none" stroke="#fff" stroke-width="8" stroke-linecap="round"
                stroke-dasharray="${c.toFixed(1)}" stroke-dashoffset="${off.toFixed(1)}"/>
      </svg>
      <div class="hbr-v"><div class="hbr-num">${pct}%</div><div class="hbr-lbl">профиль</div></div>
    </div>
    <div class="hb-cta">
      <button class="hb-btn" onclick="go('resume')">${ico('resume')} Дозаполнить</button>
      <button class="hb-btn ghost" onclick="uploadPhoto()">${ico('upload')} Фото</button>
    </div>
  </div>`;
}
/* real photo upload (requirement 5): file input → dataURL → MOCK.users.photo */
function uploadPhoto(){
  let inp=document.getElementById('z2h-photo-input');
  if(!inp){
    inp=document.createElement('input'); inp.type='file'; inp.accept='image/*'; inp.id='z2h-photo-input'; inp.style.display='none';
    inp.addEventListener('change',()=>{
      const f=inp.files&&inp.files[0]; if(!f) return;
      if(f.size>4*1024*1024){ toast('Файл больше 4 МБ — выберите поменьше'); return; }
      const r=new FileReader();
      r.onload=()=>{ MOCK.users.photo=r.result; if(typeof persistState==='function')persistState(); toast('Фото загружено'); go(state.page||'home'); };
      r.readAsDataURL(f);
    });
    document.body.appendChild(inp);
  }
  inp.value=''; inp.click();
}
function removePhoto(){ MOCK.users.photo=null; if(typeof persistState==='function')persistState(); toast('Фото удалено'); go(state.page||'home'); }

/* ---- resume constructor (detailed, requirement 4) ---- */
/* section registry — order & visibility are user-controlled */
const RESUME_SECTIONS=[
  ['about','О себе','spark'],
  ['education','Образование','university'],
  ['skills','Навыки','code'],
  ['langs','Языки','globe'],
  ['experience','Опыт','briefcase'],
  ['projects','Проекты','folder'],
  ['portfolio','Портфолио · симуляции','puzzle'],
  ['achievements','Достижения','trophy'],
  ['certificates','Сертификаты','check'],
  ['links','Ссылки','globe'],
  ['extra','Дополнительно','list'],
];
const SKILL_LEVELS=['Базовый','Средний','Продвинутый','Эксперт'];
MOCK.resumeData = MOCK.resumeData || {
  template:'classic', about:'',
  order: RESUME_SECTIONS.map(s=>s[0]),
  hidden: {},
  education:[
    {org:'', spec:'', period:'', note:''},
  ],
  experience:[
    {company:'Учебный проект · университет', role:'Аналитик данных', period:'2025', desc:'Анализ продаж за 12 месяцев, выявление сезонности, подготовка дашборда.'},
  ],
  skillLevels:{},
  links:[
    {label:'Telegram', url:'t.me/username'},
  ],
  achievements:[
    'Победитель внутреннего хакатона по аналитике данных',
    'Стипендиат за академические успехи (2 года подряд)',
  ],
  projects:[
    {name:'Дашборд продаж для учебного проекта', desc:'Power BI, анализ 12 мес. данных, выявил сезонность спроса'},
    {name:'Телеграм-бот для расписания', desc:'Python, aiogram — 200+ активных пользователей на курсе'},
  ],
  certificates:[
    {name:'Google Data Analytics', org:'Coursera', year:'2025'},
    {name:'Основы SQL', org:'Stepik', year:'2024'},
  ],
  extra:'Готов к переезду и командировкам. Водительские права категории B. Волонтёр IT-сообщества.',
};
/* backfill for older persisted state */
/* Normalise resumeData so every field the renderer touches exists.
   Must run AFTER restoreState(), because a resumeData saved by an older
   build can be missing fields added later. */
function migrateResumeData(){
  if(!MOCK.resumeData || typeof MOCK.resumeData!=='object') MOCK.resumeData={};
  const d=MOCK.resumeData;
  if(typeof d.template!=='string') d.template='classic';
  if(typeof d.about!=='string') d.about='';
  if(typeof d.extra!=='string') d.extra='';
  if(!Array.isArray(d.order)||!d.order.length) d.order=RESUME_SECTIONS.map(s=>s[0]);
  else { /* add any sections introduced after this resume was saved */
    RESUME_SECTIONS.forEach(s=>{ if(!d.order.includes(s[0])) d.order.push(s[0]); });
    const valid=RESUME_SECTIONS.map(s=>s[0]);
    d.order=d.order.filter(k=>valid.includes(k));
  }
  if(!d.hidden||typeof d.hidden!=='object') d.hidden={};
  if(!Array.isArray(d.education)) d.education=[];
  if(!Array.isArray(d.experience)) d.experience=[];
  if(!Array.isArray(d.projects)) d.projects=[];
  if(!Array.isArray(d.achievements)) d.achievements=[];
  if(!Array.isArray(d.certificates)) d.certificates=[];
  if(!Array.isArray(d.links)) d.links=[];
  if(!d.skillLevels||typeof d.skillLevels!=='object') d.skillLevels={};
  return d;
}
migrateResumeData();
function resumeField(){
  const r=MOCK.reg||{};
  const name=[r.first,r.last].filter(Boolean).join(' ')||'Ваше имя';
  const role=r.goal||r.direction||'Junior специалист';
  const skills=(r.skillsArr&&r.skillsArr.length)?r.skillsArr:(r.skills?r.skills.split(',').map(s=>s.trim()).filter(Boolean):[]);
  const langs=(r.langsArr&&r.langsArr.length)?r.langsArr:(r.langs?r.langs.split(',').map(s=>s.trim()).filter(Boolean):[]);
  return {name,role,skills,langs,r};
}
function resumeCompleteness(){
  const {role,skills,langs,r}=resumeField();
  const d=MOCK.resumeData;
  const has=a=>Array.isArray(a)&&a.length>0&&a.some(x=>x&&(typeof x==='string'?x.trim():Object.values(x).some(v=>v&&String(v).trim())));
  const checks=[
    !!(r.first&&r.last),
    !!(r.goal||r.direction),
    !!MOCK.users.photo,
    !!(d.about&&d.about.trim()),
    has(d.education),
    skills.length>0,
    Object.keys((MOCK.reg&&MOCK.reg.langLevels)||{}).length>0,
    has(d.experience),
    has(d.projects),
    has(d.achievements),
    has(d.certificates),
    has(d.links),
    !!(d.extra&&d.extra.trim()),
  ];
  return Math.round(checks.filter(Boolean).length/checks.length*100);
}
function setTemplate(t){ MOCK.resumeData.template=t; rSave(); }
function rSave(){ if(typeof persistState==='function')persistState(); go('resume'); }
function rSaveQuiet(){ if(typeof persistState==='function')persistState(); }

/* ============================================================
   INLINE EDITING — contenteditable fields write straight back
   into the model on blur. No prompt() dialogs anywhere.
   ============================================================ */
function ce(path,placeholder,cls){
  /* path: dot/bracket path into a root object, e.g. "reg.first" or "res.projects[0].name" */
  const val=readPath(path);
  return `<span class="ce ${cls||''}" contenteditable="true" spellcheck="false"
    data-path="${path}" data-ph="${placeholder||''}"
    oninput="writePath(this.dataset.path,this.textContent)"
    onblur="rSaveQuiet()"
    onkeydown="if(event.key==='Enter'){event.preventDefault();this.blur();}"
    >${val||''}</span>`;
}
function readPath(p){
  const root = p.startsWith('reg.') ? MOCK.reg : MOCK.resumeData;
  const rest = p.replace(/^(reg|res)\./,'');
  try{ return rest.split(/[.\[\]]+/).filter(Boolean).reduce((o,k)=>o[k],root) ?? ''; }catch(e){ return ''; }
}
function writePath(p,v){
  const root = p.startsWith('reg.') ? MOCK.reg : MOCK.resumeData;
  const rest = p.replace(/^(reg|res)\./,'');
  const keys = rest.split(/[.\[\]]+/).filter(Boolean);
  const last = keys.pop();
  let o=root; for(const k of keys){ if(o[k]==null) o[k]={}; o=o[k]; }
  o[last]=v;
}

/* ---- structural operations (these DO re-render) ---- */
/* education */
function addEducation(){ MOCK.resumeData.education.push({org:'Новое учебное заведение',spec:'Направление',period:'Годы',note:''}); rSave(); }
function removeEducation(i){ MOCK.resumeData.education.splice(i,1); rSave(); }
/* experience */
function addExperience(){ MOCK.resumeData.experience.push({company:'Компания',role:'Должность',period:'Период',desc:'Что делали и с каким результатом'}); rSave(); }
function removeExperience(i){ MOCK.resumeData.experience.splice(i,1); rSave(); }
/* skills with levels */
function addSkill(){ MOCK.reg.skillsArr=MOCK.reg.skillsArr||[]; MOCK.reg.skillsArr.push('Новый навык'); MOCK.resumeData.skillLevels['Новый навык']='Средний'; rSave(); }
function removeSkill(i){ const s=(MOCK.reg.skillsArr||[])[i]; (MOCK.reg.skillsArr||[]).splice(i,1); if(s)delete MOCK.resumeData.skillLevels[s]; rSave(); }
function setSkillLevel(skill,lvl){ MOCK.resumeData.skillLevels[skill]=lvl; rSaveQuiet(); }
/* languages */
function addLangResume(){ MOCK.reg.langLevels=MOCK.reg.langLevels||{}; MOCK.reg.langLevels['Новый язык']='B1'; rSave(); }
function removeLang(l){ if(MOCK.reg.langLevels)delete MOCK.reg.langLevels[l]; MOCK.reg.langsArr=(MOCK.reg.langsArr||[]).filter(x=>x!==l); rSave(); }
function setLangLevel(l,lvl){ MOCK.reg.langLevels[l]=lvl; rSaveQuiet(); }
/* links */
function addLink(){ MOCK.resumeData.links.push({label:'Ссылка',url:'https://'}); rSave(); }
function removeLink(i){ MOCK.resumeData.links.splice(i,1); rSave(); }
/* projects */
function addProject(){ MOCK.resumeData.projects.push({name:'Название проекта',desc:'Что делали, инструменты, результат'}); rSave(); }
function removeProject(i){ MOCK.resumeData.projects.splice(i,1); rSave(); }
/* achievements */
function addAchievement(){ MOCK.resumeData.achievements.push('Новое достижение'); rSave(); }
function removeAchievement(i){ MOCK.resumeData.achievements.splice(i,1); rSave(); }
/* certificates */
function addCertificate(){ MOCK.resumeData.certificates.push({name:'Название сертификата',org:'Кем выдан',year:'Год'}); rSave(); }
function removeCertificate(i){ MOCK.resumeData.certificates.splice(i,1); rSave(); }
/* section order & visibility */
function moveSection(key,dir){
  const o=MOCK.resumeData.order, i=o.indexOf(key), j=i+dir;
  if(i<0||j<0||j>=o.length) return;
  o.splice(j,0,o.splice(i,1)[0]); rSave();
}
function toggleSection(key){ MOCK.resumeData.hidden[key]=!MOCK.resumeData.hidden[key]; rSave(); }
/* employer preview */
function toggleEmployerView(){ state._resumePreview=!state._resumePreview; go('resume'); }

/* ---- real PDF export (html2canvas → jsPDF), multi-page A4 ---- */
async function exportResumePDF(){
  const node=document.getElementById('resume-doc');
  if(!node){ toast('Резюме не найдено'); return; }
  if(typeof html2canvas==='undefined' || !(window.jspdf&&window.jspdf.jsPDF)){
    toast('Библиотека PDF не загрузилась — проверьте интернет'); return;
  }
  toast('Готовим PDF…');
  /* hide edit affordances while capturing */
  node.classList.add('pdf-clean');
  try{
    const canvas=await html2canvas(node,{scale:2,useCORS:true,backgroundColor:'#ffffff',logging:false});
    const img=canvas.toDataURL('image/jpeg',0.95);
    const {jsPDF}=window.jspdf;
    const pdf=new jsPDF({unit:'mm',format:'a4',orientation:'portrait'});
    const pw=pdf.internal.pageSize.getWidth();
    const ph_=pdf.internal.pageSize.getHeight();
    const imgH=(canvas.height*pw)/canvas.width;   // scaled height in mm
    let remaining=imgH, position=0;
    pdf.addImage(img,'JPEG',0,position,pw,imgH);
    remaining-=ph_;
    while(remaining>0){
      position-=ph_;
      pdf.addPage();
      pdf.addImage(img,'JPEG',0,position,pw,imgH);
      remaining-=ph_;
    }
    const nm=[(MOCK.reg&&MOCK.reg.first)||'resume',(MOCK.reg&&MOCK.reg.last)||''].filter(Boolean).join('-').toLowerCase();
    pdf.save(`${nm||'resume'}-z2h.pdf`);
    toast('PDF скачан');
  }catch(e){
    toast('Не удалось создать PDF');
  }finally{
    node.classList.remove('pdf-clean');
  }
}
function resumeBuilder(){
  migrateResumeData();   // stale resumeData from an older build must not crash the page
  const {name,role,skills,langs,r}=resumeField();
  const d=MOCK.resumeData;
  /* seed education from registration once, if still empty */
  if((!d.education||!d.education.length||!d.education[0].org) && r.university){
    d.education=[{org:r.university,spec:r.direction||'',period:r.course||'',note:''}];
  }
  const pct=resumeCompleteness();
  const photo=MOCK.users.photo;
  const preview=!!state._resumePreview;      // employer view: hides all edit affordances
  const tpl=d.template||'classic';
  const lv=(MOCK.reg&&MOCK.reg.langLevels)||{};
  const langsFull=Object.keys(lv).map(n=>({name:n,level:lv[n]}));
  const about=d.about||'';
  const email=(r.first?`${(r.first||'').toLowerCase()}.${(r.last||'').toLowerCase()}@mail.uz`:'student@mail.uz');
  const E=preview?'':'edit';                 // marker class

  /* ---- section renderers (each returns inner HTML of a section) ---- */
  const SEC={
    about:()=>`<p class="rd-para">${preview?(about||'—'):ce('res.about','Расскажите о себе — цели, сильные стороны, чего ищете')}</p>`,

    education:()=>`${(d.education||[]).map((e,i)=>`
      <div class="rd-item">
        <div class="ri-t">${preview?(e.org||'—'):ce(`res.education[${i}].org`,'Учебное заведение')}</div>
        <div class="ri-d">${preview?[e.spec,e.period].filter(Boolean).join(' · '):`${ce(`res.education[${i}].spec`,'Направление')} · ${ce(`res.education[${i}].period`,'Годы')}`}</div>
        ${preview?'':`<div class="rd-item-actions"><button onclick="removeEducation(${i})" title="Удалить">✕</button></div>`}
      </div>`).join('')||`<div class="ri-d rd-empty">Нажмите + чтобы добавить</div>`}`,

    skills:()=>`<div class="rd-skills">${skills.map((s,i)=>`
        <div class="rd-skill">
          <span class="rs-name">${preview?s:ce(`reg.skillsArr[${i}]`,'Навык')}</span>
          ${preview
            ? `<span class="rs-lvl-static">${d.skillLevels[s]||'Средний'}</span>`
            : `<select class="rs-lvl" onchange="setSkillLevel('${s}',this.value)">${SKILL_LEVELS.map(l=>`<option ${((d.skillLevels[s]||'Средний')===l)?'selected':''}>${l}</option>`).join('')}</select>
               <button class="rs-x" onclick="removeSkill(${i})">✕</button>`}
        </div>`).join('')||`<div class="ri-d rd-empty">Добавьте навыки</div>`}</div>`,

    langs:()=>`<div class="rd-skills">${langsFull.map(l=>`
        <div class="rd-skill">
          <span class="rs-name">${l.name}</span>
          ${preview
            ? `<span class="rs-lvl-static" title="${langDesc(l.level)}">${l.level==='Родной'?'Родной':`${langLabel(l.level)} · ${l.level}`}</span>`
            : `<select class="rs-lvl" onchange="setLangLevel('${l.name}',this.value)">${LANG_LEVELS.map(v=>`<option value="${v}" ${l.level===v?'selected':''}>${v==='Родной'?'Родной':`${langLabel(v)} (${v})`}</option>`).join('')}</select>
               <button class="rs-x" onclick="removeLang('${l.name}')">✕</button>`}
        </div>`).join('')||`<div class="ri-d rd-empty">Добавьте языки</div>`}</div>`,

    experience:()=>`${(d.experience||[]).map((e,i)=>`
      <div class="rd-item">
        <div class="ri-head">
          <div class="ri-t">${preview?(e.role||'—'):ce(`res.experience[${i}].role`,'Должность')}</div>
          <div class="ri-period">${preview?(e.period||''):ce(`res.experience[${i}].period`,'Период')}</div>
        </div>
        <div class="ri-d">${preview?(e.company||''):ce(`res.experience[${i}].company`,'Компания / организация')}</div>
        <div class="ri-body">${preview?(e.desc||''):ce(`res.experience[${i}].desc`,'Что делали и с каким результатом')}</div>
        ${preview?'':`<div class="rd-item-actions"><button onclick="removeExperience(${i})">✕</button></div>`}
      </div>`).join('')||`<div class="ri-d rd-empty">Нажмите + чтобы добавить опыт</div>`}`,

    projects:()=>`${(d.projects||[]).map((p,i)=>`
      <div class="rd-item">
        <div class="ri-t">${preview?p.name:ce(`res.projects[${i}].name`,'Название проекта')}</div>
        <div class="ri-body">${preview?p.desc:ce(`res.projects[${i}].desc`,'Инструменты, что сделали, результат')}</div>
        ${preview?'':`<div class="rd-item-actions"><button onclick="removeProject(${i})">✕</button></div>`}
      </div>`).join('')||`<div class="ri-d rd-empty">Нажмите + чтобы добавить проект</div>`}`,

    portfolio:()=>{
      const done=(typeof SIMS!=='undefined')?SIMS.slice(0,2):[];
      return done.length?done.map(s=>`
        <div class="rd-item"><div class="ri-t">${s.t}</div><div class="ri-d">${s.role} · оценка ${s.match}%</div></div>`).join('')
        : `<div class="ri-d rd-empty">Пройдите симуляции — они появятся здесь</div>`;
    },

    achievements:()=>`${(d.achievements||[]).map((a,i)=>`
      <div class="rd-item rd-bullet">
        <div class="ri-body">${preview?a:ce(`res.achievements[${i}]`,'Достижение')}</div>
        ${preview?'':`<div class="rd-item-actions"><button onclick="removeAchievement(${i})">✕</button></div>`}
      </div>`).join('')||`<div class="ri-d rd-empty">Нажмите + чтобы добавить</div>`}`,

    certificates:()=>`${(d.certificates||[]).map((c,i)=>`
      <div class="rd-item">
        <div class="ri-head">
          <div class="ri-t">${preview?c.name:ce(`res.certificates[${i}].name`,'Название')}</div>
          <div class="ri-period">${preview?(c.year||''):ce(`res.certificates[${i}].year`,'Год')}</div>
        </div>
        <div class="ri-d">${preview?(c.org||''):ce(`res.certificates[${i}].org`,'Кем выдан')}</div>
        ${preview?'':`<div class="rd-item-actions"><button onclick="removeCertificate(${i})">✕</button></div>`}
      </div>`).join('')||`<div class="ri-d rd-empty">Нажмите + чтобы добавить</div>`}`,

    links:()=>`<div class="rd-links">${(d.links||[]).map((l,i)=>`
        <div class="rd-link">
          ${ico('globe')}
          <span class="rl-label">${preview?l.label:ce(`res.links[${i}].label`,'Название')}</span>
          <span class="rl-url">${preview?l.url:ce(`res.links[${i}].url`,'https://...')}</span>
          ${preview?'':`<button class="rs-x" onclick="removeLink(${i})">✕</button>`}
        </div>`).join('')||`<div class="ri-d rd-empty">GitHub, LinkedIn, Telegram, портфолио…</div>`}</div>`,

    extra:()=>`<p class="rd-para">${preview?(d.extra||'—'):ce('res.extra','Переезд, права, хобби, волонтёрство')}</p>`,
  };
  const ADDERS={education:'addEducation()',experience:'addExperience()',projects:'addProject()',
    achievements:'addAchievement()',certificates:'addCertificate()',skills:'addSkill()',
    langs:'addLangResume()',links:'addLink()'};

  /* ---- render sections in user order, skipping hidden ---- */
  const order=(d.order||RESUME_SECTIONS.map(s=>s[0]));
  const meta=k=>RESUME_SECTIONS.find(s=>s[0]===k)||[k,k,'list'];
  const renderSection=k=>{
    if(d.hidden[k]) return '';
    const [,label,icon]=meta(k);
    return `<div class="rd-sec" data-sec="${k}">
      <h4>${ico(icon)} ${label}
        ${(!preview&&ADDERS[k])?`<span class="rd-edit" onclick="${ADDERS[k]}" title="Добавить">${ico('plus')}</span>`:''}
      </h4>
      ${SEC[k]?SEC[k]():''}
    </div>`;
  };

  /* ---- template layouts differ structurally, not just in colour ---- */
  const SIDEBAR_KEYS=['skills','langs','links','certificates'];
  const isTwoCol = tpl==='sidebar';
  const isMinimal = tpl==='minimal';
  const headClass = isMinimal?'minimal':(tpl==='bold'?'bold':'accent');

  const head=`
    <div class="rd-head ${headClass}">
      <div class="rd-photo ${isMinimal?'plain':''}" ${preview?'':'onclick="uploadPhoto()"'}>
        ${photo?`<img src="${photo}" alt="">`:ico('user')}
      </div>
      <div class="rd-idbox">
        <div class="rd-name">${preview?name:`${ce('reg.first','Имя')} ${ce('reg.last','Фамилия')}`}</div>
        <div class="rd-role">${preview?role:ce('reg.goal','Желаемая должность')}</div>
        <div class="rd-contacts">
          ${r.phone?`<span>${ico('phone')}${(r.code||'+998')} ${r.phone}</span>`:''}
          <span>${ico('mail')}${email}</span>
          ${r.city?`<span>${ico('pin')}${r.city}</span>`:''}
        </div>
      </div>
    </div>`;

  const body = isTwoCol
    ? `<div class="rd-body two-col">
         <div class="rd-col-main">${order.filter(k=>!SIDEBAR_KEYS.includes(k)).map(renderSection).join('')}</div>
         <div class="rd-col-side">${order.filter(k=>SIDEBAR_KEYS.includes(k)).map(renderSection).join('')}</div>
       </div>`
    : `<div class="rd-body">${order.map(renderSection).join('')}</div>`;

  const doc=`<div class="resume-doc tpl-${tpl}" id="resume-doc">${head}${body}</div>`;

  /* ---- employer preview mode: document only, no sidebar ---- */
  if(preview){
    return ph("Резюме глазами работодателя","Так вашу карточку увидит компания",
      `<button class="btn btn-ghost btn-sm" onclick="toggleEmployerView()">${ico('gear')} Вернуться к редактированию</button>
       <button class="btn btn-primary btn-sm" onclick="exportResumePDF()">${ico('doc')} Скачать PDF</button>`)
      +`<div style="max-width:820px;margin:0 auto">${doc}</div>`;
  }

  /* ---- editor sidebar ---- */
  const orderList=order.map((k,i)=>{
    const [,label,icon]=meta(k);
    const hidden=!!d.hidden[k];
    return `<div class="ord-row ${hidden?'off':''}">
      <span class="ord-ic">${ico(icon)}</span>
      <span class="ord-l">${label}</span>
      <button onclick="moveSection('${k}',-1)" ${i===0?'disabled':''} title="Выше">↑</button>
      <button onclick="moveSection('${k}',1)" ${i===order.length-1?'disabled':''} title="Ниже">↓</button>
      <button onclick="toggleSection('${k}')" title="${hidden?'Показать':'Скрыть'}">${hidden?'○':'●'}</button>
    </div>`;
  }).join('');

  return ph("Резюме студента","Кликните на любой текст, чтобы отредактировать",
    `<button class="btn btn-ghost btn-sm" onclick="toggleEmployerView()">${ico('user')} Глазами компании</button>
     <button class="btn btn-primary btn-sm" onclick="exportResumePDF()">${ico('doc')} Скачать PDF</button>`)+`
  <div class="rc-wrap">
    <div class="rc-side">
      <div class="rc-meter">
        <div class="rm-top"><span class="rm-v">${pct}%</span><span class="rm-l">заполнено</span></div>
        <div class="progress"><i style="width:${pct}%"></i></div>
        <div class="rm-l" style="margin-top:8px">${pct<60?'Добавьте недостающие блоки':pct<100?'Почти готово!':'Резюме готово к отправке'}</div>
      </div>

      <div>
        <div class="section-label" style="margin:0 0 8px">Фото</div>
        <div class="rc-photo-ctl">
          <div class="rcp-thumb">${photo?`<img src="${photo}" alt="">`:ico('user')}</div>
          <div style="flex:1">
            <button class="btn btn-primary btn-sm" style="width:100%;margin-bottom:6px" onclick="uploadPhoto()">${ico('upload')} ${photo?'Заменить':'Загрузить'}</button>
            ${photo?`<button class="btn btn-ghost btn-sm" style="width:100%" onclick="removePhoto()">Удалить</button>`:''}
          </div>
        </div>
      </div>

      <div>
        <div class="section-label" style="margin:0 0 8px">Шаблон</div>
        <div class="rc-templates">
          ${[['classic','Классика'],['minimal','Минимал'],['sidebar','Две колонки'],['bold','Акцент']].map(t=>
            `<div class="rc-tpl ${tpl===t[0]?'on':''}" onclick="setTemplate('${t[0]}')">
              <div class="tpl-preview tpl-p-${t[0]}"><span></span><span></span><span></span></div>${t[1]}
            </div>`).join('')}
        </div>
      </div>

      <div>
        <div class="section-label" style="margin:0 0 8px">Секции · порядок и видимость</div>
        <div class="rc-order">${orderList}</div>
      </div>
    </div>
    ${doc}
  </div>`;
}

function freshStudentHome(){
  const fields=(MOCK.workFields&&MOCK.workFields.length)?MOCK.workFields.join(', '):null;
  const diagDone=state._diag&&state._diag.done;
  const resumeDone=!!(MOCK.resumeData&&MOCK.resumeData.about);
  const pct=(typeof resumeCompleteness==='function')?resumeCompleteness():0;

  const steps=[
    {t:'Диагностика',d:'12 вопросов · ~7 минут. Самооценка и проверка знаний',go:'diagnostics',done:diagDone},
    {t:'Резюме',d:resumeDone?'Готово — можно улучшать':'Соберите профиль: о себе, навыки, опыт',go:'resume',done:resumeDone},
    {t:'Первая симуляция',d:'Реальный бизнес-кейс от компании',go:'simulations',done:false},
    {t:'Первый отклик',d:'Отправьте резюме на подходящую вакансию',go:'jobs',done:false},
  ];
  const curIdx=steps.findIndex(s=>!s.done);
  const next=steps[curIdx]||steps[steps.length-1];

  const topJobs=JOBS.slice().sort((a,b)=>matchFor(b)-matchFor(a)).slice(0,3);

  const nudge = MOCK.users.onbDeferred ? `
    <div class="nudge-profile">
      <div class="np-ic">${ico('user')}</div>
      <div style="flex:1">
        <div class="np-t">Заполните профиль</div>
        <div class="np-d">Без интересов и навыков подбор вакансий приблизительный — ${pct}% профиля готово</div>
      </div>
      <button class="btn btn-primary btn-sm" style="width:auto;flex:none" onclick="onbResume()">Продолжить →</button>
    </div>` : '';

  return (FEATURES.studentHero?studentHeroBanner():'')+nudge+`
    <div class="next-hero">
      <span class="nh-badge">Следующий шаг</span>
      <div class="nh-ic">${ico('target')}</div>
      <div class="nh-b">
        <h3>${next.t}</h3>
        <p>${next.d}</p>
        <div class="nh-meta">
          <span>${ico('clock')}Шаг ${Math.max(1,curIdx+1)} из ${steps.length}</span>
          <span>${ico('flame')}Начните сегодня — путь занимает ~6 недель</span>
        </div>
      </div>
      <button class="btn btn-primary" style="width:auto;flex:none" onclick="go('${next.go}')">Начать →</button>
    </div>

    <div class="g g4" style="margin-bottom:16px">
      ${statCard('target',pct+'%','Заполненность профиля','var(--blue)','var(--blue-soft)',null,{hint:pct<50?'Дозаполните — так вас заметят':'Хороший старт'})}
      ${statCard('compass',(curIdx<0?steps.length:curIdx)+'/'+steps.length,'Шагов пройдено','var(--purple)','var(--purple-soft)',null,{hint:'До первого оффера ~6 недель'})}
      ${statCard('puzzle','0','Симуляций сдано','var(--teal)','var(--teal-soft)',null,{hint:'Портфолио сильнее резюме'})}
      ${statCard('briefcase','0','Откликов','var(--amber)','var(--amber-soft)',null,{hint:`${JOBS.length} вакансий ждут`})}
    </div>

    <div class="g g2">
      <div class="panel"><h3>${ico('compass')} Ваш путь</h3><div class="ps">Четыре шага до первого оффера</div>
        <div class="trail">
          ${steps.map((st,i)=>`<div class="trail-step ${st.done?'done':(i===curIdx?'cur':'')}" onclick="go('${st.go}')">
            <div class="trail-num">${st.done?ico('check'):(i+1)}</div>
            <div class="trail-b"><div class="trail-t">${st.t}</div><div class="trail-d">${st.d}</div></div>
            <span class="trail-go">→</span>
          </div>`).join('')}
        </div>
      </div>
      <div class="panel"><h3>${ico('briefcase')} Подходящие вакансии</h3><div class="ps">${fields?'По вашим интересам: '+fields:'Выберите интересы, чтобы уточнить подбор'}</div>
        <div style="margin-top:8px">
          ${topJobs.map(j=>`<div class="mini-job" onclick="openJob(${j.id})">
            <div class="mj-logo" style="background:${j.color}">${j.logo}</div>
            <div class="mj-b"><div class="mj-t">${j.t}</div><div class="mj-d">${j.co} · ${j.loc}</div></div>
            <span class="mj-m">${matchFor(j)}%</span>
          </div>`).join('')}
        </div>
        <button class="btn btn-ghost btn-sm" style="width:100%;margin-top:14px" onclick="go('jobs')">Все ${JOBS.length} вакансий →</button>
      </div>
    </div>`;
}

/* ---- features/ai: assistant with mock voice ---- */
function aiSend(){
  const inp=document.getElementById('ai-input'); const t=(inp.value||'').trim(); if(!t)return;
  aiAppend('me',t); inp.value='';
  const key=Object.keys(MOCK.ai.canned).find(k=>k&&t.toLowerCase().includes(k));
  setTimeout(()=>aiAppend('them',MOCK.ai.canned[key||'']),500);
}
function aiAppend(who,text){
  const box=document.getElementById('ai-msgs'); if(!box)return;
  const div=document.createElement('div'); div.className='msg '+(who==='me'?'me':'them');
  div.style.whiteSpace='pre-line'; div.textContent=text; box.appendChild(div); box.scrollTop=box.scrollHeight;
}
function aiVoice(btn){
  btn.classList.add('rec'); btn.innerHTML=ico('dot');
  const box=document.getElementById('ai-msgs');
  const typing=document.createElement('div'); typing.className='msg them'; typing.textContent='Запись…'; box.appendChild(typing); box.scrollTop=box.scrollHeight;
  setTimeout(()=>{
    typing.remove(); btn.classList.remove('rec'); btn.innerHTML=ico('mic');
    aiAppend('me',MOCK.ai.voicePhrase);
    setTimeout(()=>aiAppend('them',MOCK.ai.voiceReply),600);
  },2200);
}

/* ---- features/resume: wizard ---- */
let wizStep=0;
function wizNext(){
  if(wizStep<MOCK.resume.steps.length-1){ wizStep++; go('resume-wizard'); }
  else{ MOCK.users.resumeCompleted=true; MOCK.resume.done=true; persistState(); toast("Резюме создано"); go('resume-done'); }
}
function wizBack(){ if(wizStep>0){ wizStep--; go('resume-wizard'); } }

/* ---- features/payment ---- */
function payNow(plan){
  const ov=document.createElement('div'); ov.className='overlay'; ov.onclick=(e)=>{if(e.target===ov)ov.remove();};
  ov.innerHTML=`<div class="success-modal"><div class="si">✓</div><h2 class="title" style="text-align:center">Оплата прошла успешно</h2><p class="subtitle" style="text-align:center">Тариф «${plan}» активирован (демо).</p><button class="btn btn-primary" onclick="this.closest('.overlay').remove()">Готово</button></div>`;
  document.body.appendChild(ov);
}

/* ---- register new pages into existing PAGES map (no existing key changed) ---- */
Object.assign(PAGES,{
  "resume-wizard":()=>{const steps=MOCK.resume.steps;const fields=[
      [["Имя","Студент Зерохиров"],["Телефон",MOCK.users.phone||"+998 90 000 00 00"],["Город","Ташкент"]],
      [["Желаемая роль","Junior Marketing"],["Навыки","SMM, копирайтинг, аналитика"],["Опыт","Учебные проекты, стажировка"]],
      [["Карьерная цель","Стать маркетологом"],["Готовность","Стажировка / part-time"]],
    ][wizStep];
    return ph("Создать резюме",`Шаг ${wizStep+1} из ${steps.length} · ${steps[wizStep]}`)+`
    <div style="max-width:560px">
      <div class="wiz-steps">${steps.map((_,i)=>`<i class="${i<=wizStep?'on':''}"></i>`).join('')}</div>
      <div class="panel">
        ${fields.map(f=>`<div class="field"><label>${f[0]}</label><input value="${f[1]}"></div>`).join('')}
      </div>
      <div style="display:flex;gap:10px;margin-top:16px">
        ${wizStep>0?`<button class="btn btn-ghost" style="width:auto" onclick="wizBack()">← Назад</button>`:''}
        <button class="btn btn-primary" style="width:auto;margin-left:auto" onclick="wizNext()">${wizStep<steps.length-1?'Далее →':'Завершить'}</button>
      </div>
    </div>`;
  },
  "resume-done":()=>`<div class="stub-screen">
      <div class="stub-ic">${ico('check')}</div>
      <h1>Резюме успешно создано</h1>
      <p>Теперь доступны рекомендации и дополнительные разделы кабинета.</p>
      <div style="display:flex;gap:10px;justify-content:center;margin-top:20px">
        <button class="btn btn-primary" style="width:auto" onclick="go('home')">На главную →</button>
        <button class="btn btn-ghost" style="width:auto" onclick="heroOpen()">${ico('bot')} Спросить Hero</button>
      </div>
    </div>`,
  /* Superseded by the floating Hero. Kept reachable, but it just points there —
     two assistants with separate histories was the bug, not a feature. */
  "ai-assistant":()=>`<div class="stub-screen">
      <div class="stub-ic">${ico('bot')}</div>
      <h1>Hero теперь всегда рядом</h1>
      <p>Помощник живёт в правом нижнем углу и доступен на любом экране.</p>
      <button class="btn btn-primary" style="width:auto;margin:18px auto 0" onclick="heroOpen()">${ico('bot')} Открыть Hero</button>
    </div>`,

  "ai-assistant-legacy":()=>ph("AI Помощник","Задайте вопрос или воспользуйтесь голосом")+`
    <div class="chat" style="grid-template-columns:1fr">
      <div class="chat-main">
        <div class="chat-msgs" id="ai-msgs">
          <div class="msg them">Здравствуйте! Я помогу построить ваш карьерный путь. С чего начнём?</div>
        </div>
        <div class="chat-input">
          <button class="mic-btn" onclick="aiVoice(this)" title="Голосовой помощник">${ico('mic')}</button>
          <input id="ai-input" placeholder="Сообщение…" onkeydown="if(event.key==='Enter')aiSend()">
          <button class="btn btn-primary btn-sm" onclick="aiSend()">Отпр.</button>
        </div>
      </div>
    </div>`,
  "payment":()=>ph("Тарифы","Выберите план — оплата в демо-режиме")+`
    <div class="plan-grid">
      ${[["Free","Бесплатно","Старт и базовые функции",["Диагностика","Создание резюме","AI Помощник (базовый)"],false],
         ["Pro","49 000 сум/мес","Для активного поиска работы",["Всё из Free","Безлимит симуляций","AI-рекомендации","Приоритет откликов"],true],
         ["Business","149 000 сум/мес","Для команд и наставников",["Всё из Pro","До 5 профилей","Аналитика прогресса","Поддержка 24/7"],false]].map(p=>`
        <div class="plan ${p[4]?'hot':''}"><div class="pn">${p[0]}</div><div class="pp">${p[1]}</div><div class="ptag">${p[2]}</div>
          <ul>${p[3].map(f=>`<li>${f}</li>`).join('')}</ul>
          <button class="btn ${p[4]?'btn-primary':'btn-ghost'}" onclick="payNow('${p[0]}')">Оплатить</button>
        </div>`).join('')}
    </div>`,
  "univ-stub":()=>`<div class="stub-screen"><div class="stub-ic">${ico('university')}</div><h1>Добро пожаловать, ВУЗ</h1><p>Кабинет куратора готов к работе — откройте демонстрационные данные когорт и аналитики.</p><button class="btn btn-primary" style="width:auto;margin:18px auto 0" onclick="openFullCabinet()">Открыть кабинет →</button></div>`,
  "company-stub":()=>`<div class="stub-screen"><div class="stub-ic">${ico('company')}</div><h1>Добро пожаловать, компания</h1><p>Кабинет работодателя готов — откройте демонстрационные вакансии и воронку найма.</p><button class="btn btn-primary" style="width:auto;margin:18px auto 0" onclick="openFullCabinet()">Открыть кабинет →</button></div>`,
});
Object.assign(LABELS,{"resume-wizard":"Создать резюме","resume-done":"Резюме создано","ai-assistant":"Hero · AI-помощник","payment":"Тарифы","univ-stub":"Кабинет ВУЗа","company-stub":"Кабинет компании"});

/* AI-recommendations block, shown on student home after resume is completed */
function recommendBlock(){
  if(!MOCK.users.resumeCompleted) return '';
  return `<div class="rec-band">
    <h3>${ico('bot')} AI рекомендует · компании сейчас ищут</h3>
    <div class="rec-chips">${MOCK.companies.map(c=>`<span class="rec-chip">${c.role}<span class="rc-badge">${c.tag}</span></span>`).join('')}</div>
  </div>`;
}
/* ---- features/recommendations: improvement backlog per section ---- */
const RECS={
  student:[
    ["Обзор",ico('home'),[
      ["p1","S","Кликабельные задачи дня","Чекбокс закрывает задачу, прогресс дня растёт — дашборд должен двигать пользователя каждый день."],
      ["p1","S","Кнопка «Продолжить» в hero","Один клик из обзора в текущий шаг траектории, а не только надпись «шаг 4»."],
      ["p2","M","Расчёт «до оффера»","Привязать срок к формуле (осталось шагов × средний темп), а не выдуманное число."],
      ["p3","S","Прогресс к следующему бейджу","«Ещё 2 симуляции до Аналитик PRO» мотивирует сильнее бинарного открыто/закрыто."],
    ]],
    ["Траектория",ico('compass'),[
      ["p2","M","Артефакт и время у шага","Показать, что останется в портфолио и сколько займёт — сейчас шаг это просто заголовок."],
      ["p2","S","Причина блокировки шага","Вместо alert показывать «откроется после первой симуляции»."],
      ["p3","L","Ветвление по специализации","Со шага 6 трек должен расходиться под маркетинг/аналитику/продукт."],
    ]],
    ["Диагностика",ico('chart'),[
      ["p1","M","Диагностика с проверкой знаний","Сделано: 12 вопросов, самооценка + тест, разбор ошибок."],
      ["p1","M","Результат → перестройка трека","Явно показать связь «на основе диагностики добавлены шаги X, Y»."],
      ["p3","S","Прогресс-бар и возврат назад","Навигация между вопросами."],
    ]],
    ["Симуляции",ico('puzzle'),[
      ["p2","M","Рабочие фильтры","Сейчас декоративные — минимум по направлению и уровню."],
      ["p1","S","Статус прохождения в карточке","Не начато / в работе / сдано с оценкой."],
      ["p2","M","Автосохранение черновика","Поле решения теряется при уходе; добавить счётчик попыток."],
      ["p3","M","Пример хорошего решения","Показывать после сдачи — обучающая ценность, не только оценка."],
    ]],
    ["Вакансии",ico('briefcase'),[
      ["p1","M","Разбор match%","«85%: есть SQL, Python; не хватает A/B» — цифра превращается в план."],
      ["p1","M","Статус отклика","Отправлено / просмотрено / приглашение вместо alert; переход в воронку."],
      ["p2","M","Связь вакансия ↔ симуляция","«Пройди симуляцию X, чтобы поднять шанс»."],
      ["p3","S","Фильтры и сортировка","По match / дедлайну / зарплате."],
    ]],
    ["AI-резюме",ico('doc'),[
      ["p1","S","Реальная генерация превью","Кнопка должна менять превью на моковом наборе, а не alert."],
      ["p2","M","Шаблоны и экспорт PDF","Выбор шаблона + кнопка экспорта (мок)."],
      ["p2","M","Автоподтягивание из симуляций","Портфолио в резюме связать с пройденными кейсами."],
      ["p3","S","Индикатор силы резюме","Подсказки, чего не хватает."],
    ]],
    ["Сообщения",ico('chat'),[
      ["p2","S","Счётчик непрочитанных","Жирный шрифт и бейдж на диалогах."],
      ["p3","S","Тип собеседника","Визуально разделить HR / куратор / система."],
      ["p3","S","Быстрые ответы-шаблоны","Для типовых ситуаций вроде приглашения на интервью."],
    ]],
  ],
  university:[
    ["Обзор ВУЗа",ico('university'),[
      ["p1","M","Клик по «требуют внимания»","Блоки-алерты должны вести к списку конкретных студентов."],
      ["p2","M","Тренд метрик во времени","Мини-графики динамики готовности, а не только текущее число."],
      ["p2","S","Сравнение с планом/бенчмарком","Показывать отклонение когорт от цели."],
    ]],
    ["Когорты",ico('folder'),[
      ["p1","M","Рабочее создание когорты","Кнопка «Новая когорта» открывает форму, а не пустая."],
      ["p2","M","Массовые действия","Выбрать студентов и назначить симуляцию / напоминание."],
      ["p3","S","Фильтр и поиск когорт","При росте числа групп."],
    ]],
    ["Студенты",ico('users'),[
      ["p2","M","Фильтры реестра","По когорте, статусу, готовности."],
      ["p2","S","Экспорт списка","CSV выбранных студентов."],
      ["p1","M","Быстрое действие из строки","Написать студенту / связать с HR прямо из таблицы."],
    ]],
    ["Gap-матрица",ico('chart'),[
      ["p1","M","Клик по ячейке → студенты","Показать, у кого именно этот пробел."],
      ["p2","M","Рекомендация по пробелу","«Назначьте курс/симуляцию X для закрытия»."],
      ["p3","S","Переключение когорта/направление","Сейчас матрица общая."],
    ]],
    ["Отчёты",ico('list'),[
      ["p2","M","Предпросмотр отчёта","Перед экспортом показать, что внутри."],
      ["p2","S","Реальный экспорт (мок PDF/CSV)","Сейчас только alert."],
      ["p3","M","Расписание и подписка","Автоотправка отчёта раз в период."],
    ]],
    ["Команда",ico('plus'),[
      ["p2","S","Рабочая форма приглашения","Ввод email и роли вместо alert."],
      ["p3","S","Управление правами","Что видит куратор vs владелец."],
    ]],
    ["Настройки",ico('gear'),[
      ["p3","M","Рабочий загрузчик логотипа","Сейчас тумблер-заглушка."],
      ["p3","S","Проверка SSO-подключения","Статус и тестовая кнопка."],
    ]],
  ],
  company:[
    ["Обзор компании",ico('company'),[
      ["p1","M","Клик по этапу воронки","Переход к кандидатам этого этапа."],
      ["p2","M","Скорость найма (time-to-hire)","Метрика, которой сейчас нет, но она ключевая для HR."],
      ["p2","S","Топ-кандидаты → карточка","Клик ведёт в профиль, а не статичная строка."],
    ]],
    ["Стажировки",ico('briefcase'),[
      ["p1","M","Статус и метрики по позиции","Сколько откликов, на каком этапе, конверсия."],
      ["p2","S","Дубликат/архив вакансии","Быстро создать похожую или закрыть."],
      ["p2","M","Обязательная симуляция-фильтр","Привязать кейс как барьер отбора."],
    ]],
    ["Кандидаты",ico('list'),[
      ["p1","M","Сохранение позиции в Kanban","Перетаскивание есть, но сбрасывается при уходе."],
      ["p1","M","Карточка кандидата с портфолио","Решения симуляций, оценка, заметки — сейчас alert."],
      ["p2","S","Фильтр по match и позиции","Разделить воронки по вакансиям."],
      ["p3","S","Массовые действия","Отклонить/пригласить пачкой."],
    ]],
    ["Сообщения",ico('chat'),[
      ["p2","S","Шаблоны для HR","Приглашение на интервью, тестовое, отказ."],
      ["p3","S","Привязка чата к кандидату","Переход из карточки в диалог."],
    ]],
    ["Профиль компании",ico('company'),[
      ["p2","S","Предпросмотр глазами кандидата","Как страница выглядит публично."],
      ["p3","M","Медиа и преимущества","Фото, культура, отзывы стажёров."],
    ]],
    ["Команда",ico('plus'),[
      ["p2","S","Рабочая форма приглашения","Email + роль вместо alert."],
      ["p3","S","Матрица прав Owner/Recruiter/Viewer","Явно показать, кто что может."],
    ]],
    ["Настройки",ico('gear'),[
      ["p2","M","Рабочий экран биллинга","Смена тарифа связать с экраном оплаты."],
      ["p3","M","Настройка вебхуков/интеграций","Сейчас тумблеры-заглушки."],
    ]],
  ],
  common:[
    ["Общее по платформе",ico('globe'),[
      ["p1","M","Сохранение состояния","Флаги и формы сбрасываются при перезагрузке — вынести в localStorage."],
      ["p1","M","Иконки вместо эмодзи","Перейти на единый SVG-набор под дизайн-стандарт (Tabler)."],
      ["p2","S","Живой поиск во всех разделах","Расширить существующий /app/search."],
      ["p2","M","Тёмная тема — контраст","Проверить бейджи и слабоконтрастные места."],
      ["p2","M","Мобильная вёрстка","Проверить Kanban, таблицы, чат, лендинг на узком экране."],
      ["p3","M","Узбекская локализация (Uz Latin)","Второй язык интерфейса."],
      ["p3","L","Публичные превью симуляций","Для незалогиненных — сейчас только в кабинете."],
    ]],
  ],
};
const RECS_DONE=new Set();
let recTab='student';
function recCount(role){let t=0,d=0;RECS[role].forEach(s=>s[2].forEach((r,i)=>{t++;if(RECS_DONE.has(role+'|'+s[0]+'|'+i))d++;}));return[d,t];}
function recToggle(id){if(RECS_DONE.has(id))RECS_DONE.delete(id);else RECS_DONE.add(id);persistState();go('recommend-panel');}
function recSetTab(t){recTab=t;go('recommend-panel');}
Object.assign(PAGES,{
  "recommend-panel":()=>{
    const roles=[["student","Студент"],["university","ВУЗ"],["company","Компания"],["common","Общее"]];
    let allD=0,allT=0;roles.forEach(([r])=>{const[d,t]=recCount(r);allD+=d;allT+=t;});
    const[cd,ct]=recCount(recTab);
    const sections=RECS[recTab].map(sec=>{
      const cards=sec[2].map((r,i)=>{
        const id=recTab+'|'+sec[0]+'|'+i;const done=RECS_DONE.has(id);
        const eff={S:'S · быстро',M:'M · средне',L:'L · крупно'}[r[1]];
        return `<div class="rec-card ${done?'done':''}">
          <div class="rec-check" onclick="recToggle('${id}')">✓</div>
          <div class="rec-body">
            <div class="rec-title">${r[2]}</div>
            <div class="rec-desc">${r[3]}</div>
            <div class="rec-tags"><span class="rec-p ${r[0]}">${r[0].toUpperCase()}</span><span class="rec-eff">${eff}</span></div>
          </div>
        </div>`;
      }).join('');
      const[sd,st]=[sec[2].filter((_,i)=>RECS_DONE.has(recTab+'|'+sec[0]+'|'+i)).length,sec[2].length];
      return `<div class="rec-sec"><div class="rec-sec-h"><div class="ico">${sec[1]}</div><h3>${sec[0]}</h3><span class="rc">${sd}/${st}</span></div>${cards}</div>`;
    }).join('');
    return ph("Рекомендации по улучшению","Применяйте по очереди — отмечайте выполненные. P1 важнее, S/M/L — объём работы.")+`
      <div class="rec-summary">
        <div class="rec-kpi"><div class="v">${allT}</div><div class="l">всего идей</div></div>
        <div class="rec-kpi"><div class="v">${allD}</div><div class="l">применено</div></div>
        <div class="rec-kpi"><div class="v">${allT-allD}</div><div class="l">в очереди</div></div>
      </div>
      <div class="rec-tabs">
        ${roles.map(([r,l])=>{const[d,t]=recCount(r);return `<button class="rec-tab ${recTab===r?'on':''}" onclick="recSetTab('${r}')">${l} · ${d}/${t}</button>`;}).join('')}
      </div>
      ${sections}`;
  },
});
LABELS["recommend-panel"]="Рекомендации";
/* reachable from every role's footer nav (additive) */
NAV.student.foot.push(["recommend-panel","spark","Рекомендации"]);
NAV.university.foot.push(["recommend-panel","spark","Рекомендации"]);
NAV.company.foot.push(["recommend-panel","spark","Рекомендации"]);
/* ---- features/diagnostics: 6 questions → competency profile ---- */
/* ============================================================
   DIAGNOSTICS
   Two kinds of questions:
     • self  — self-assessment (fast, but people over/under-rate themselves)
     • test  — a knowledge check with one correct answer (objective)
   The final score per skill blends both, and we show the gap between
   "how you rate yourself" and "what the check showed".
   ============================================================ */
const DIAG_SECTIONS=[
  {k:'data',  t:'Работа с данными', ic:'chart'},
  {k:'product',t:'Продукт',         ic:'target'},
  {k:'soft',  t:'Софт-скиллы',      ic:'users'},
  {k:'tech',  t:'Технические навыки',ic:'code'},
];
const DIAG_Q=[
  /* ---------- data ---------- */
  {sec:'data',type:'self',dim:'Аналитика данных',
   q:"Насколько уверенно вы работаете с таблицами и SQL?",
   a:[["Никогда не пробовал",15],["Базовые SELECT и WHERE",42],["Уверенно: JOIN, GROUP BY",70],["Оконные функции, оптимизация",92]]},
  {sec:'data',type:'test',dim:'Аналитика данных',
   q:"В таблице заказов нужно посчитать средний чек по каждому городу. Какой запрос верный?",
   a:[["SELECT AVG(sum) FROM orders",0],
      ["SELECT city, AVG(sum) FROM orders GROUP BY city",1],
      ["SELECT city, SUM(sum)/COUNT(*) FROM orders",0],
      ["SELECT AVG(sum) FROM orders WHERE city IS NOT NULL",0]],
   why:"Средний чек по каждому городу требует группировки: GROUP BY city. Третий вариант тоже даёт среднее, но без группировки — по всей таблице."},
  {sec:'data',type:'test',dim:'Аналитика данных',
   q:"Конверсия упала с 5% до 4%. На сколько процентов она снизилась?",
   a:[["На 1%",0],["На 20%",1],["На 25%",0],["На 80%",0]],
   why:"Падение с 5 до 4 — это −1 процентный пункт, но −20% относительно исходного значения. Путаница между «процентом» и «процентным пунктом» — классическая ошибка на собеседовании."},

  /* ---------- product ---------- */
  {sec:'product',type:'self',dim:'Продукт',
   q:"Опыт с продуктовыми метриками — retention, воронки, когорты?",
   a:[["Не знаком с терминами",20],["Слышал, но не считал",45],["Считал вручную",68],["Строил дашборды и следил",88]]},
  {sec:'product',type:'test',dim:'Продукт',
   q:"Из 1000 новых пользователей через 30 дней активны 180. Что это за метрика?",
   a:[["Конверсия",0],["Retention 30 дней = 18%",1],["Отток = 18%",0],["ARPU",0]],
   why:"Это retention (удержание) за 30 дней. Отток был бы обратной величиной — 82%."},
  {sec:'product',type:'test',dim:'Продукт',
   q:"A/B-тест показал прирост конверсии на 0,3% при 200 пользователях в каждой группе. Что делать?",
   a:[["Раскатывать — есть прирост",0],
      ["Выборка мала, результат может быть случайным",1],
      ["Остановить тест, гипотеза не сработала",0],
      ["Увеличить прирост, изменив дизайн",0]],
   why:"При такой выборке разница в 0,3% статистически незначима. Нужно больше данных, иначе можно принять шум за эффект."},

  /* ---------- soft ---------- */
  {sec:'soft',type:'self',dim:'Коммуникация',
   q:"Как вы оцениваете навыки коммуникации и презентации?",
   a:[["Стесняюсь выступать",30],["Нормально в малой группе",55],["Уверенно презентую",78],["Веду встречи и дискуссии",92]]},
  {sec:'soft',type:'self',dim:'Готовность',
   q:"Готовность работать в команде над реальными задачами?",
   a:[["Только учусь",35],["Пробовал в учебных проектах",60],["Активно участвую",80],["Веду инициативы сам",95]]},
  {sec:'soft',type:'test',dim:'Коммуникация',
   q:"Вы нашли ошибку в расчётах коллеги за час до презентации клиенту. Что делаете?",
   a:[["Молчу — не моя зона ответственности",0],
      ["Сразу говорю коллеге наедине и предлагаю помощь",1],
      ["Пишу руководителю",0],
      ["Поднимаю вопрос на самой презентации",0]],
   why:"Прямой разговор с коллегой сохраняет отношения и решает проблему быстрее всего. Эскалация — следующий шаг, если он откажется исправлять."},

  /* ---------- tech ---------- */
  {sec:'tech',type:'self',dim:'Python',
   q:"Знание Python и автоматизации?",
   a:[["Не программирую",15],["Базовый синтаксис",42],["pandas, простые скрипты",70],["Автоматизирую рабочие задачи",90]]},
  {sec:'tech',type:'test',dim:'Python',
   q:"Что вернёт этот код? len([x for x in range(10) if x % 2 == 0])",
   a:[["10",0],["5",1],["4",0],["Ошибку",0]],
   why:"range(10) даёт числа 0–9; чётных среди них пять: 0, 2, 4, 6, 8."},
  {sec:'tech',type:'self',dim:'Маркетинг',
   q:"Опыт в маркетинге и продвижении?",
   a:[["Нулевой",18],["Вёл личные соцсети",48],["Запускал кампании",70],["Работал с бюджетами и отчётностью",88]]},
];

const DIAG_DIMS=[...new Set(DIAG_Q.map(q=>q.dim))];

function diagInit(){
  if(!state._diag || typeof state._diag!=='object') state._diag={step:-1,ans:[],done:false};
  if(typeof state._diag.step!=='number') state._diag.step=-1;   // -1 = intro screen
  if(!Array.isArray(state._diag.ans)) state._diag.ans=[];
  if(typeof state._diag.done!=='boolean') state._diag.done=false;
  return state._diag;
}
function diagStart(){ diagInit(); state._diag.step=0; persistDiag(); go('diagnostics'); }
function persistDiag(){ if(typeof persistState==='function') persistState(); }

/* pick an answer without redrawing the whole page — no flicker, no scroll jump */
function diagPick(i){
  diagInit();
  state._diag.ans[state._diag.step]=i;
  persistDiag();
  document.querySelectorAll('#diag-opts .opt').forEach((el,idx)=>el.classList.toggle('on',idx===i));
  const btn=document.getElementById('diag-next'); if(btn) btn.disabled=false;
}
function diagNext(){
  diagInit();
  if(state._diag.ans[state._diag.step]==null){ toast("Выберите вариант ответа"); return; }
  if(state._diag.step<DIAG_Q.length-1) state._diag.step++;
  else { state._diag.done=true; applyDiagScores(); toast("Диагностика завершена"); }
  persistDiag(); go('diagnostics');
}
function diagBack(){
  diagInit();
  if(state._diag.step>0){ state._diag.step--; persistDiag(); go('diagnostics'); }
}
function diagRestart(){
  if(state._diag && state._diag.done && !confirm('Пройти заново? Текущий результат будет перезаписан.')) return;
  state._diag={step:0,ans:[],done:false}; persistDiag(); go('diagnostics');
}
function diagExit(){ persistDiag(); go('home'); toast('Прогресс сохранён — вернётесь и продолжите'); }

/* ---- scoring: self-rating and knowledge check are combined per skill ---- */
function diagScores(){
  const byDim={};
  DIAG_DIMS.forEach(d=>byDim[d]={self:[],test:[]});
  DIAG_Q.forEach((q,i)=>{
    const a=state._diag.ans[i];
    if(a==null) return;
    if(q.type==='self') byDim[q.dim].self.push(q.a[a][1]);
    else                byDim[q.dim].test.push(q.a[a][1]===1?100:0);
  });
  const out={};
  DIAG_DIMS.forEach(d=>{
    const s=byDim[d].self, t=byDim[d].test;
    const selfAvg = s.length?Math.round(s.reduce((a,b)=>a+b,0)/s.length):null;
    const testAvg = t.length?Math.round(t.reduce((a,b)=>a+b,0)/t.length):null;
    let final;
    if(selfAvg!=null && testAvg!=null) final=Math.round(selfAvg*0.4 + testAvg*0.6);  // the check weighs more
    else final = selfAvg!=null?selfAvg:(testAvg!=null?testAvg:50);
    out[d]={self:selfAvg,test:testAvg,final,
            gap: (selfAvg!=null&&testAvg!=null)?selfAvg-testAvg:null};
  });
  return out;
}
function applyDiagScores(){
  const sc=diagScores();
  Object.keys(sc).forEach(d=>{ COMP_SCORES[d]=sc[d].final; });
}
function diagCorrectCount(){
  let ok=0,total=0;
  DIAG_Q.forEach((q,i)=>{
    if(q.type!=='test') return;
    total++;
    const a=state._diag.ans[i];
    if(a!=null && q.a[a][1]===1) ok++;
  });
  return {ok,total};
}
function diagLevel(avg){
  if(avg>=80) return {t:'Продвинутый',d:'Вы готовы к сложным кейсам и стажировкам уровня Middle',c:'var(--green)'};
  if(avg>=60) return {t:'Уверенный',  d:'Хорошая база — беритесь за Junior-стажировки',c:'var(--accent)'};
  if(avg>=40) return {t:'Начинающий', d:'Основы есть, нужна практика на реальных кейсах',c:'var(--amber)'};
  return {t:'Старт',d:'Всё впереди — начните с базовых симуляций',c:'var(--faint)'};
}
/* what to do about each weak skill — links into the rest of the platform */
const DIAG_ADVICE={
  'Аналитика данных':{go:'simulations',b:'Кейс по аналитике',t:'Возьмите симуляцию с SQL — теория закрепляется только практикой'},
  'Продукт':{go:'simulations',b:'Продуктовый кейс',t:'Разберите A/B-тест на реальных данных'},
  'Коммуникация':{go:'simulations',b:'Командный кейс',t:'Симуляции с защитой решения тренируют презентацию'},
  'Python':{go:'simulations',b:'Кейс с автоматизацией',t:'Начните с задач на pandas'},
  'Маркетинг':{go:'jobs',b:'Маркетинговые стажировки',t:'Стажировка даст опыт быстрее курсов'},
  'Готовность':{go:'path',b:'Открыть траекторию',t:'Пройдите первые шаги — уверенность приходит с результатом'},
};
function diagSectionProgress(){
  return DIAG_SECTIONS.map(sec=>{
    const idx=DIAG_Q.map((q,i)=>q.sec===sec.k?i:-1).filter(i=>i>=0);
    const answered=idx.filter(i=>state._diag.ans[i]!=null).length;
    return {...sec, total:idx.length, answered, first:idx[0], done:answered===idx.length};
  });
}
function diagRender(){
  diagInit();
  const d=state._diag;

  /* ---------- intro ---------- */
  if(d.step===-1 && !d.done){
    const secs=diagSectionProgress();
    const tests=DIAG_Q.filter(q=>q.type==='test').length;
    return `<div class="dg-intro">
      <div class="dg-hero">
        <div class="dh-ic">${ico('brain')}</div>
        <h2>Входная диагностика</h2>
        <p>Не только спросим, как вы себя оцениваете, но и проверим знания. Так результат честнее — и траектория точнее.</p>
        <div class="dg-meta">
          <span>${ico('list')}${DIAG_Q.length} вопросов</span>
          <span>${ico('clock')}около 7 минут</span>
          <span>${ico('check')}${tests} проверочных задач</span>
        </div>
      </div>

      <div class="dg-sections">
        ${secs.map(sec=>`<div class="dg-sec">
          <div class="ds-ic">${ico(sec.ic)}</div>
          <div class="ds-b"><div class="ds-t">${sec.t}</div>
            <div class="ds-d">${sec.total} ${plural(sec.total,'вопрос','вопроса','вопросов')}</div></div>
          <span class="ds-c">${sec.total}</span>
        </div>`).join('')}
      </div>

      <div class="dg-hint" style="margin-bottom:18px">${ico('spark')}<span>
        Отвечайте честно — заниженная самооценка так же вредна, как завышенная.
        Прогресс сохраняется, можно прерваться и вернуться.</span></div>

      <button class="btn btn-primary" style="width:100%;height:48px" onclick="diagStart()">
        ${ico('spark')} Начать диагностику</button>
    </div>`;
  }

  /* ---------- result ---------- */
  if(d.done){
    const sc=diagScores();
    const dims=DIAG_DIMS.map(x=>({dim:x,...sc[x]}));
    const avg=Math.round(dims.reduce((a,x)=>a+x.final,0)/dims.length);
    const lvl=diagLevel(avg);
    const quiz=diagCorrectCount();
    const rr=52,cc=2*Math.PI*rr,off=cc-(avg/100)*cc;
    const weak=dims.slice().sort((a,b)=>a.final-b.final).slice(0,2);
    const color=v=>v>=75?'var(--green)':v>=55?'var(--accent)':v>=40?'var(--amber)':'var(--red)';
    const gapLabel=g=>{
      if(g==null) return '<span style="color:var(--faint)">—</span>';
      if(g>=25)  return `<span class="gap-over">переоценка +${g}</span>`;
      if(g<=-25) return `<span class="gap-under">недооценка ${g}</span>`;
      return `<span class="gap-match">оценка точна</span>`;
    };
    const tests=DIAG_Q.map((q,i)=>({q,i})).filter(x=>x.q.type==='test');

    return ph("Результат диагностики","Профиль компетенций построен — траектория адаптирована",
      `<button class="btn btn-ghost btn-sm" style="width:auto" onclick="diagRestart()">Пройти заново</button>`)+`
    <div class="dg-result">
      <div class="dg-score">
        <div class="dg-ring">
          <svg width="118" height="118" viewBox="0 0 118 118">
            <circle cx="59" cy="59" r="${rr}" fill="none" stroke="var(--hair2)" stroke-width="10"/>
            <circle cx="59" cy="59" r="${rr}" fill="none" stroke="${lvl.c}" stroke-width="10" stroke-linecap="round"
                    stroke-dasharray="${cc.toFixed(1)}" stroke-dashoffset="${off.toFixed(1)}"/>
          </svg>
          <div class="dr-v"><div class="dr-n" style="color:${lvl.c}">${avg}</div><div class="dr-l">из 100</div></div>
        </div>
        <div class="dg-lvl">
          <span class="dl-badge" style="background:${lvl.c}">${lvl.t}</span>
          <h3>Ваш уровень</h3>
          <p>${lvl.d}</p>
        </div>
        <div class="dg-quiz">
          <div class="dq-v" style="color:${quiz.ok/quiz.total>=0.6?'var(--green)':'var(--amber)'}">${quiz.ok}/${quiz.total}</div>
          <div class="dq-l">верных ответов<br>в проверке</div>
        </div>
      </div>

      <div class="panel" style="margin-bottom:18px">
        <h3>${ico('chart')} Профиль компетенций</h3>
        <div class="ps">Полоса — итоговый балл, засечка — ваша самооценка</div>
        <div style="margin-top:14px">
          ${dims.map(x=>`<div class="skill-row">
            <span class="sr-n">${x.dim}</span>
            <div class="sr-track">
              <i style="width:${x.final}%;background:${color(x.final)}"></i>
              ${x.self!=null?`<span class="sr-self" style="left:calc(${x.self}% - 1px)" title="Самооценка: ${x.self}"></span>`:''}
            </div>
            <span class="sr-v" style="color:${color(x.final)}">${x.final}</span>
            <span class="sr-gap">${gapLabel(x.gap)}</span>
          </div>`).join('')}
        </div>
        <div class="dg-legend">
          <span><span class="lg-d" style="background:var(--accent)"></span>Итоговый балл (проверка весит 60%)</span>
          <span><span class="lg-d" style="background:var(--faint);width:3px;height:11px"></span>Ваша самооценка</span>
        </div>
      </div>

      <div class="section-label" style="margin:0 0 10px">Что делать дальше</div>
      ${weak.map(w=>{const ad=DIAG_ADVICE[w.dim]||{go:'simulations',b:'Открыть симуляции',t:'Практика закрывает пробелы быстрее теории'};
        return `<div class="advice">
          <div class="ad-ic">${ico('target')}</div>
          <div class="ad-b"><div class="ad-t">${w.dim} · ${w.final} из 100</div><div class="ad-d">${ad.t}</div></div>
          <button class="btn btn-primary" onclick="go('${ad.go}')">${ad.b}</button>
        </div>`;}).join('')}

      <div class="panel" style="margin-top:18px">
        <h3>${ico('check')} Разбор проверочных вопросов</h3>
        <div class="ps">Где ошиблись и почему</div>
        <div class="dg-review">
          ${tests.map(({q,i})=>{
            const a=state._diag.ans[i];
            const ok=a!=null && q.a[a][1]===1;
            const correct=q.a.find(o=>o[1]===1);
            return `<div class="rev-row ${ok?'ok':'bad'}">
              <div class="rev-h"><span class="rh-ic">${ico(ok?'check':'ban')}</span><span>${q.q}</span></div>
              <div class="rev-a">
                <div class="ra-y">Ваш ответ: ${a!=null?q.a[a][0]:'—'}</div>
                ${ok?'':`<div class="ra-c">Верно: ${correct[0]}</div>`}
              </div>
              ${q.why?`<div class="rev-why">${ico('spark')} ${q.why}</div>`:''}
            </div>`;}).join('')}
        </div>
      </div>

      <div style="display:flex;gap:10px;margin-top:18px;flex-wrap:wrap">
        <button class="btn btn-primary" style="width:auto" onclick="go('path')">${ico('compass')} Перейти к траектории</button>
        <button class="btn btn-ghost" style="width:auto" onclick="go('simulations')">${ico('puzzle')} Взять первый кейс</button>
      </div>

      <div class="ai-note" style="margin-top:16px">${ico('alert')}<span>Проверочные задачи охватывают лишь часть навыка. Балл — ориентир, а не приговор: его повышают решённые кейсы.</span></div>
    </div>`;
  }

  /* ---------- a question ---------- */
  const st=d.step, q=DIAG_Q[st], picked=d.ans[st];
  const pct=Math.round(st/DIAG_Q.length*100);
  const sec=DIAG_SECTIONS.find(x=>x.k===q.sec);
  const KEYS=['A','B','C','D'];

  return `<div class="dg-wrap">
    <div class="dg-bar"><i style="width:${Math.max(3,pct)}%"></i></div>
    <div class="dg-bar-l">
      <span>${sec?sec.t:''} · вопрос ${st+1} из ${DIAG_Q.length}</span>
      <span>${pct}%</span>
    </div>

    <div class="dg-card">
      <span class="dg-tag ${q.type}">
        ${ico(q.type==='test'?'check':'user')}${q.type==='test'?'Проверка знаний':'Самооценка'}
      </span>
      <div class="dg-q">${q.q}</div>
      <div class="dg-opts" id="diag-opts">
        ${q.a.map((o,i)=>`<button class="dg-opt opt${picked===i?' on':''}" onclick="diagPick(${i})">
          <span class="do-k">${KEYS[i]||i+1}</span>${o[0]}</button>`).join('')}
      </div>

      ${q.type==='test'?`<div class="dg-hint">${ico('spark')}<span>Здесь есть один верный ответ. Разбор всех задач покажем в конце.</span></div>`
                       :`<div class="dg-hint">${ico('spark')}<span>Оцените себя честно — это не экзамен, а точка отсчёта.</span></div>`}

      <div class="dg-nav">
        <button class="btn btn-ghost" ${st===0?'disabled':''} onclick="diagBack()">← Назад</button>
        <button class="btn btn-primary" id="diag-next" ${picked==null?'disabled':''} onclick="diagNext()">
          ${st<DIAG_Q.length-1?'Далее →':'Завершить'}</button>
        <span class="dg-exit" onclick="diagExit()">Продолжить позже</span>
      </div>
    </div>
  </div>`;
}

/* ▲▲▲ END NEW FEATURES ▲▲▲ */

/* ============================================================
   HERO — AI navigator. Always reachable, knows where things are.
   Mock intelligence: keyword intents + page context. No real AI call.
   ============================================================ */
const HERO_PLACES={
  home:{label:'Обзор',what:'Ваш главный экран: прогресс траектории, задачи на сегодня, активные симуляции и ближайшие события.'},
  path:{label:'Траектория',what:'Ваш путь из 10 шагов от диагностики до оффера. Показывает, что пройдено и что дальше.'},
  diagnostics:{label:'Диагностика',what:'12 вопросов, ~7 минут: самооценка плюс проверка знаний. По результатам строится траектория и уточняется подбор вакансий.'},
  simulations:{label:'Симуляции',what:'Реальные бизнес-кейсы от компаний. Решаете их и собираете портфолио, которое видят работодатели.'},
  jobs:{label:'Вакансии',what:'Стажировки и работа с процентом совпадения по вашему профилю. Есть поиск, фильтры, вид списком и карточками.'},
  resume:{label:'AI-резюме',what:'Конструктор резюме: слева блоки и шаблоны, справа живой документ. Всё редактируется прямо в тексте. Есть экспорт в PDF.'},
  applications:{label:'Мои отклики',what:'Все вакансии, на которые вы откликнулись, с этапом по каждой: отправлен, скрининг, интервью, оффер.'},
  portfolio:{label:'Портфолио',what:'Решённые симуляции с оценками. Это доказательство навыков, которое видит работодатель.'},
  'candidate-search':{label:'Поиск кандидатов',what:'Найдите студентов по навыкам и решённым кейсам, а не по словам в резюме.'},
  placement:{label:'Трудоустройство',what:'Воронка от диагностики до оффера и список компаний, куда взяли ваших студентов.'},
  messages:{label:'Сообщения',what:'Переписка с работодателями и куратором ВУЗа.'},
  profile:{label:'Профиль',what:'Ваши данные, фото и настройки аккаунта.'},
  notifications:{label:'Уведомления',what:'Приглашения на интервью, дедлайны симуляций, ответы на отклики.'},
  settings:{label:'Настройки',what:'Тема оформления, приватность, уведомления.'},
  cohorts:{label:'Когорты',what:'Группы студентов, которые ведёт ВУЗ.'},
  students:{label:'Студенты',what:'Список студентов с прогрессом и готовностью к рынку.'},
  gaps:{label:'Gap-матрица',what:'Где у когорты проседают компетенции.'},
  reports:{label:'Отчёты',what:'Выгрузки по готовности студентов и офферам.'},
  internships:{label:'Стажировки',what:'Ваши опубликованные вакансии-стажировки.'},
  candidates:{label:'Кандидаты',what:'Kanban-воронка найма: перетаскивайте кандидатов между этапами.'},
  company:{label:'Компания',what:'Публичный профиль вашей компании для студентов.'},
};
/* what to do next, in order — drives the "с чего начать" answer */
function heroNextStep(){
  if(state.role!=='student') return null;
  const diagDone=state._diag&&state._diag.done;
  if(!diagDone) return {page:'diagnostics',t:'Пройти диагностику',why:'Это 5 минут. Без неё траектория и проценты совпадения будут приблизительными.'};
  if(!(MOCK.resumeData&&MOCK.resumeData.about)) return {page:'resume',t:'Дозаполнить резюме',why:'Работодатели видят именно его. Добавьте «О себе» и навыки.'};
  return {page:'simulations',t:'Взять первую симуляцию',why:'Решённый кейс попадёт в портфолио — это сильнее строчки в резюме.'};
}
/* aliases so "где резюме" finds the page labelled "AI-резюме" */
const HERO_ALIASES={resume:['резюме','cv'],applications:['отклик','подал','заявк'],portfolio:['портфолио','кейсы мои'],
  'candidate-search':['поиск кандидат','найти студент'],placement:['трудоустрой','офферы'],
  jobs:['ваканс','работ','стажировк'],diagnostics:['диагностик','тест'],
  simulations:['симуляц','кейс'],messages:['сообщен','чат','переписк'],profile:['профил','аккаунт'],
  notifications:['уведомлен'],settings:['настройк'],path:['траектор'],home:['обзор','главн'],
  cohorts:['когорт'],students:['студент'],gaps:['gap','матриц'],reports:['отчёт','отчет'],
  internships:['стажировк'],candidates:['кандидат','воронк'],company:['компани']};
function heroFindPlace(q){
  /* only offer pages the current role actually has in its nav */
  const nav=(NAV[state.role]||{});
  const allowed=[...(nav.main||[]),...(nav.foot||[])].filter(x=>x[0]!=='__group').map(x=>x[0]);
  const ok=p=>allowed.includes(p)&&HERO_PLACES[p];
  for(const p of Object.keys(HERO_ALIASES)){
    if(!ok(p)) continue;
    if(HERO_ALIASES[p].some(a=>q.includes(a))) return p;
  }
  return Object.keys(HERO_PLACES).find(p=>ok(p)&&q.includes(HERO_PLACES[p].label.toLowerCase()));
}
const HERO_INTENTS=[
  /* specific topics first — a generic "где" must not swallow them */
  {k:['начать','с чего','что делать','дальше','следующий шаг'],fn:()=>{
    const n=heroNextStep();
    if(!n) return {text:'Начните с обзора — там видно все ключевые метрики вашей организации.',go:'home'};
    return {text:`Следующий шаг: <b>${n.t}</b>.<br>${n.why}`,go:n.page};
  }},
  {k:['тур','покажи','экскурс','обучение'],fn:()=>({text:'Запускаю короткий тур по разделам.',tour:true})},
  {k:['совпадение','процент','match'],fn:()=>({text:'Процент считается из трёх вещей: выбранные направления, ваши навыки против требований вакансии и пройденная диагностика. Откройте вакансию — там есть блок «Почему такой процент».'})},
  {k:['фото','аватар','загруз'],fn:()=>({text:'Фото загружается в <b>AI-резюме</b> — слева блок «Фото», кнопка «Загрузить». Оно появится и в резюме, и в обзоре.',go:'resume'})},
  {k:['тема','тёмн','темн','светл'],fn:()=>({text:'Переключатель темы — иконка луны в верхней панели, справа. Настройка сохраняется.'})},
  {k:['pdf','скачать','экспорт'],fn:()=>({text:'Кнопка <b>«Скачать PDF»</b> — вверху справа в разделе AI-резюме. Рядом «Глазами компании»: покажет, как вас увидит работодатель.',go:'resume'})},
  {k:['спасибо','понял','ок'],fn:()=>({text:'Обращайтесь. Я всегда в правом нижнем углу.'})},
  {k:['файл','прикрепить','вложение','загрузить резюме','pdf разбери'],fn:()=>({text:'Прикрепите файл скрепкой слева от поля ввода — или просто перетащите его в это окно.<br>Честно: в демо я <b>не читаю содержимое</b> файлов, это требует разбора на сервере.'})},
  /* place lookup — works both with and without "где" */
  {k:['где','найти','куда','как попасть','раздел','находится','резюме','ваканс','симуляц','диагностик','траектор','кандидат','когорт','сообщен','настройк','профил'],fn:q=>{
    const hit=heroFindPlace(q);
    if(hit) return {text:`<b>${HERO_PLACES[hit].label}</b> — в левом меню.<br>${HERO_PLACES[hit].what}`,go:hit};
    return {text:'Скажите, что ищете — резюме, вакансии, симуляции, диагностику? Или нажмите ⌘K: там поиск по всем разделам.'};
  }},
  {k:['поиск'],fn:()=>({text:'Строка поиска всегда наверху. Или нажмите <b>⌘K</b> — откроется быстрый переход по разделам.'})},
];
function heroReply(q){
  const t=(q||'').toLowerCase();
  for(const it of HERO_INTENTS){ if(it.k.some(k=>t.includes(k))) return it.fn(t); }
  const cur=HERO_PLACES[state.page];
  if(cur) return {text:`Не уверен, что понял. Сейчас вы в разделе <b>${cur.label}</b> — ${cur.what}<br>Спросите «где резюме», «с чего начать» или «покажи тур».`};
  return {text:'Спросите «где резюме», «с чего начать», «как считается совпадение» или «покажи тур».'};
}
let HERO_LOG=[];
function heroChips(){
  const c=[];
  const n=heroNextStep();
  if(n) c.push('С чего начать?');
  c.push('Где резюме?','Где вакансии?','Как считается совпадение?','Покажи тур');
  return c;
}
function heroRenderChips(){
  const el=document.getElementById('hero-chips'); if(!el) return;
  el.innerHTML=heroChips().map(c=>`<button class="hp-chip" onclick="heroAsk(${JSON.stringify(c).replace(/"/g,'&quot;')})">${c}</button>`).join('');
}
function heroPush(who,html,go,atts){
  HERO_LOG.push({who,html,go,atts});
  const box=document.getElementById('hero-msgs'); if(!box) return;
  const d=document.createElement('div'); d.className='hmsg '+who;
  d.innerHTML=html
    + heroFilesHtml(atts)
    + (go?`<div class="hm-link" onclick="heroGo('${go}')">${ico('compass')}Открыть «${(HERO_PLACES[go]||{}).label||go}»</div>`:'');
  box.appendChild(d); box.scrollTop=box.scrollHeight;
}
function heroTyping(on){
  const box=document.getElementById('hero-msgs'); if(!box) return;
  let t=document.getElementById('hero-typing');
  if(on){ if(!t){ t=document.createElement('div'); t.id='hero-typing'; t.className='htyping'; t.innerHTML='<i></i><i></i><i></i>'; box.appendChild(t); box.scrollTop=box.scrollHeight; } }
  else if(t) t.remove();
}
function heroGo(page){ heroClose(); go(page); }
function heroAsk(q){ const i=document.getElementById('hero-input'); if(i)i.value=q; heroSend(); }
function heroSend(){
  const i=document.getElementById('hero-input'); const q=(i&&i.value||'').trim();
  const atts=HERO_ATTS.slice();
  if(!q && !atts.length) return;
  heroPush('me', q||'<i style="opacity:.85">Файл</i>', null, atts);
  if(i)i.value='';
  HERO_ATTS=[]; heroRenderAtts();
  heroTyping(true);
  setTimeout(()=>{
    heroTyping(false);
    const r = atts.length ? heroFileReply(atts) : heroReply(q);
    heroPush('them',r.text,r.go);
    if(r.tour){ heroClose(); setTimeout(startTour,250); }
  },550);
}
function heroGreeting(){
  const name=(MOCK.reg&&MOCK.reg.first)||'';
  const n=heroNextStep();
  heroPush('them',`Привет${name?', '+name:''}! Я <b>Hero</b> — помогу разобраться, где что находится.`);
  if(n) heroPush('them',`Сейчас логичнее всего: <b>${n.t}</b>. ${n.why}`,n.page);
  else heroPush('them','Спросите, где найти нужный раздел — подскажу и открою его.');
}
function heroOpen(){
  document.getElementById('hero-panel').classList.remove('hidden');
  document.getElementById('hero-fab').classList.add('hidden');
  document.getElementById('hero-dot').classList.add('hidden');
  heroApplySize(); heroInitResize(); heroInitDrop();
  if(!HERO_LOG.length) heroGreeting();
  heroRenderChips(); heroRenderAtts();
  setTimeout(()=>{const i=document.getElementById('hero-input'); if(i)i.focus();},60);
}
function heroClose(){
  document.getElementById('hero-panel').classList.add('hidden');
  document.getElementById('hero-fab').classList.remove('hidden');
}
function heroShowFab(){ const f=document.getElementById('hero-fab'); if(f)f.classList.remove('hidden'); }
function heroReset(){
  HERO_LOG=[]; HERO_ATTS=[];
  const box=document.getElementById('hero-msgs'); if(box) box.innerHTML='';
  heroRenderAtts();
  heroHideFab();
}

/* ---------------- panel sizing: resize grip, minimise, maximise ---------------- */
function heroApplySize(){
  const p=document.getElementById('hero-panel'); if(!p) return;
  let s={};
  try{ s=JSON.parse(localStorage.getItem('z2h_hero_size')||'{}'); }catch(e){}
  if(s.w) p.style.setProperty('--hp-w', s.w+'px');
  if(s.h) p.style.setProperty('--hp-h', s.h+'px');
  p.classList.toggle('max', !!s.max);
  p.classList.toggle('min', !!s.min);
  heroSyncMaxIcon();
}
function heroSaveSize(patch){
  let s={};
  try{ s=JSON.parse(localStorage.getItem('z2h_hero_size')||'{}'); }catch(e){}
  Object.assign(s,patch);
  try{ localStorage.setItem('z2h_hero_size', JSON.stringify(s)); }catch(e){}
}
function heroSyncMaxIcon(){
  const p=document.getElementById('hero-panel'), b=document.getElementById('hp-max');
  if(!p||!b) return;
  const isMax=p.classList.contains('max');
  b.title = isMax?'Свернуть к окну':'Развернуть';
  b.innerHTML = isMax
    ? '<svg class="onb-icon" viewBox="0 0 24 24"><path d="M4 9h3a2 2 0 002-2V4M20 9h-3a2 2 0 01-2-2V4M4 15h3a2 2 0 012 2v3M20 15h-3a2 2 0 00-2 2v3"/></svg>'
    : '<svg class="onb-icon" viewBox="0 0 24 24"><path d="M8 3H5a2 2 0 00-2 2v3M16 3h3a2 2 0 012 2v3M8 21H5a2 2 0 01-2-2v-3M16 21h3a2 2 0 002-2v-3"/></svg>';
}
function heroToggleMax(){
  const p=document.getElementById('hero-panel'); if(!p) return;
  p.classList.remove('min');
  const on=p.classList.toggle('max');
  heroSaveSize({max:on,min:false});
  heroSyncMaxIcon();
  const box=document.getElementById('hero-msgs'); if(box) box.scrollTop=box.scrollHeight;
}
function heroToggleMin(){
  const p=document.getElementById('hero-panel'); if(!p) return;
  p.classList.remove('max');
  const on=p.classList.toggle('min');
  heroSaveSize({min:on,max:false});
  heroSyncMaxIcon();
}
/* drag the top-left grip; panel is pinned bottom-right so size = delta */
function heroInitResize(){
  const grip=document.getElementById('hp-grip'), p=document.getElementById('hero-panel');
  if(!grip||!p||grip._wired) return; grip._wired=true;
  let sx=0,sy=0,sw=0,sh=0;
  const onMove=e=>{
    const dx=sx-e.clientX, dy=sy-e.clientY;
    const w=Math.min(Math.max(320,sw+dx), window.innerWidth-48);
    const h=Math.min(Math.max(380,sh+dy), window.innerHeight-48);
    p.style.setProperty('--hp-w', w+'px');
    p.style.setProperty('--hp-h', h+'px');
  };
  const onUp=()=>{
    p.classList.remove('resizing');
    document.removeEventListener('mousemove',onMove);
    document.removeEventListener('mouseup',onUp);
    heroSaveSize({w:parseInt(p.style.getPropertyValue('--hp-w'))||400,
                  h:parseInt(p.style.getPropertyValue('--hp-h'))||580});
  };
  grip.addEventListener('mousedown',e=>{
    if(p.classList.contains('max')||p.classList.contains('min')) return;
    e.preventDefault();
    const r=p.getBoundingClientRect();
    sx=e.clientX; sy=e.clientY; sw=r.width; sh=r.height;
    p.classList.add('resizing');
    document.addEventListener('mousemove',onMove);
    document.addEventListener('mouseup',onUp);
  });
}

/* ---------------- attachments ---------------- */
let HERO_ATTS=[];
const HERO_MAX_FILE=8*1024*1024;
function fmtSize(b){ return b<1024?b+' Б':b<1048576?(b/1024).toFixed(0)+' КБ':(b/1048576).toFixed(1)+' МБ'; }
function heroPickFile(){
  let inp=document.getElementById('hero-file');
  if(!inp){
    inp=document.createElement('input'); inp.type='file'; inp.id='hero-file'; inp.multiple=true; inp.style.display='none';
    inp.accept='image/*,.pdf,.doc,.docx,.txt,.csv,.xlsx';
    inp.addEventListener('change',()=>{ heroAddFiles(inp.files); inp.value=''; });
    document.body.appendChild(inp);
  }
  inp.click();
}
function heroAddFiles(files){
  [...files].forEach(f=>{
    if(f.size>HERO_MAX_FILE){ toast(`«${f.name}» больше 8 МБ`); return; }
    if(HERO_ATTS.length>=5){ toast('Не больше 5 файлов за раз'); return; }
    const att={name:f.name,size:f.size,type:f.type,preview:null};
    HERO_ATTS.push(att);
    if(f.type.startsWith('image/')){
      const r=new FileReader();
      r.onload=()=>{ att.preview=r.result; heroRenderAtts(); };
      r.readAsDataURL(f);
    }
    heroRenderAtts();
  });
}
function heroRemoveAtt(i){ HERO_ATTS.splice(i,1); heroRenderAtts(); }
function heroRenderAtts(){
  const el=document.getElementById('hero-atts'); if(!el) return;
  el.innerHTML=HERO_ATTS.map((a,i)=>`<div class="hp-att">
    ${a.preview?`<img src="${a.preview}" alt="">`:`<span class="ha-ic">${ico('doc')}</span>`}
    <span class="ha-n">${a.name}</span><span class="ha-s">${fmtSize(a.size)}</span>
    <button class="ha-x" onclick="heroRemoveAtt(${i})" title="Убрать">✕</button>
  </div>`).join('');
}
function heroFilesHtml(atts){
  if(!atts||!atts.length) return '';
  return `<div class="hm-files">${atts.map(a=>a.preview
    ? `<img src="${a.preview}" alt="${a.name}">`
    : `<div class="hm-file">${ico('doc')}<span>${a.name}</span><span style="opacity:.7">${fmtSize(a.size)}</span></div>`).join('')}</div>`;
}
/* mock analysis — real parsing needs a backend or a model call */
function heroFileReply(atts){
  const img=atts.filter(a=>a.preview).length;
  const docs=atts.length-img;
  const names=atts.map(a=>a.name).join(', ');
  let t=`Получил: <b>${names}</b>.<br>`;
  if(docs&&/\.(pdf|docx?|txt)$/i.test(names)) t+='Похоже на резюме или документ. В демо я не читаю содержимое файлов — это требует разбора на сервере. Могу подсказать, что стоит добавить в резюме.';
  else if(img) t+='Вижу изображение. В демо я его не анализирую, но если это фото для профиля — загрузите его в разделе AI-резюме.';
  else t+='В демо содержимое файлов не разбирается.';
  return {text:t,go:'resume'};
}
function heroInitDrop(){
  const p=document.getElementById('hero-panel'); if(!p||p._drop) return; p._drop=true;
  ['dragenter','dragover'].forEach(ev=>p.addEventListener(ev,e=>{ e.preventDefault(); p.classList.add('drag'); }));
  ['dragleave','drop'].forEach(ev=>p.addEventListener(ev,e=>{
    e.preventDefault();
    if(ev==='dragleave' && p.contains(e.relatedTarget)) return;
    p.classList.remove('drag');
  }));
  p.addEventListener('drop',e=>{ if(e.dataTransfer&&e.dataTransfer.files) heroAddFiles(e.dataTransfer.files); });
}
function heroHideFab(){
  const f=document.getElementById('hero-fab'), p=document.getElementById('hero-panel');
  if(f)f.classList.add('hidden'); if(p)p.classList.add('hidden');
}

/* ---------------- guided tour: spotlight over real nav items ---------------- */
function tourSteps(){
  const r=state.role;
  /* `page` makes the tour actually navigate — you see the real screen behind the spotlight */
  const common=[
    {sel:'.search-mini',ic:'search',t:'Поиск везде',x:'Ищите разделы, вакансии и симуляции с любого экрана.',tip:'Горячая клавиша: <b>⌘K</b> (или Ctrl+K)'},
    {sel:'[data-page="settings"]',ic:'gear',t:'Настройки под себя',x:'Тема, размер шрифта, плотность интерфейса, приватность — всё меняется здесь.',page:'settings'},
    {sel:'#hero-fab',ic:'bot',t:'Это Hero — я',x:'Не знаете, где что находится, или застряли? Нажмите на меня в любой момент.',forceFab:true,tip:'Я подскажу и сразу открою нужный раздел'},
  ];
  if(r==='student') return [
    {sel:'[data-page="home"]',ic:'home',t:'Обзор',x:'Прогресс, следующий шаг и подходящие вакансии — всё на одном экране.',page:'home'},
    {sel:'[data-page="diagnostics"]',ic:'brain',t:'Начните с диагностики',x:'12 вопросов, около 7 минут: самооценка и проверка знаний. Именно она строит вашу траекторию.',page:'diagnostics',tip:'Без неё проценты совпадения будут приблизительными'},
    {sel:'[data-page="path"]',ic:'compass',t:'Ваша траектория',x:'Пошаговый план от текущего уровня до цели. Обновляется по мере прохождения кейсов и диагностики.',page:'path',tip:'Курс не важен — важно соответствие тому, что ищет работодатель'},
    {sel:'[data-page="simulations"]',ic:'puzzle',t:'Симуляции',x:'Реальные бизнес-кейсы от компаний. Решённые попадают в портфолио, которое видят работодатели.',page:'simulations',tip:'Один решённый кейс весит больше, чем строчка в резюме'},
    {sel:'[data-page="diary"]',ic:'list',t:'Дневник практики',x:'Ведите записи по неделям, отмечайте часы и задачи. Ментор подтверждает часы, вуз видит статус практики.',page:'diary',tip:'Подтверждённые навыки отсюда попадают в витрину для работодателей'},
    {sel:'[data-page="jobs"]',ic:'briefcase',t:'Вакансии',x:'Отсортированы по совпадению с вашим профилем. Есть поиск, фильтры и два вида отображения.',page:'jobs'},
    {sel:'[data-page="applications"]',ic:'list',t:'Мои отклики',x:'Все ваши заявки и их статусы в одном месте: отправлен, просмотрен, приглашение, отказ.',page:'applications'},
    {sel:'[data-page="resume"]',ic:'resume',t:'AI-резюме',x:'Кликните на любой текст — и правьте прямо в документе. Есть шаблоны и экспорт в PDF.',page:'resume',tip:'Кнопка «Глазами компании» покажет, как вас увидит работодатель'},
    ...common];
  if(r==='university') return [
    {sel:'[data-page="home"]',ic:'home',t:'Обзор',x:'Ключевые метрики: студенты, когорты, средняя готовность, офферы.',page:'home'},
    {sel:'[data-page="cohorts"]',ic:'folder',t:'Когорты',x:'Группы студентов, которые вы ведёте, с прогрессом каждой.',page:'cohorts'},
    {sel:'[data-page="gaps"]',ic:'chart',t:'Gap-матрица',x:'Показывает, где у когорты проседают компетенции — куда направить усилия.',page:'gaps'},
    {sel:'[data-page="kpi"]',ic:'chart',t:'KPI деканата',x:'Аналитика трудоустройства по факультетам и «Индекс качества выпускника» — под гос-KPI по занятости.',page:'kpi',tip:'Кнопка «Экспорт» готовит отчёт для отчётности'},
    {sel:'[data-page="contracts"]',ic:'list',t:'Договоры практики',x:'Реестр трёхсторонних договоров (вуз + студент + компания) со статусами подписания через E-imzo.',page:'contracts'},
    {sel:'[data-page="placement"]',ic:'trophy',t:'Трудоустройство',x:'Воронка занятости выпускников: от практики до оффера.',page:'placement'},
    ...common];
  if(r==='admin') return [
    {sel:'[data-page="home"]',ic:'gear',t:'Панель админа',x:'Сводка по всей платформе: договоры, студенты на практике, трудоустройство, заказы на кадры.',page:'home'},
    {sel:'[data-page="contracts"]',ic:'list',t:'Реестр договоров',x:'Все договоры практики по вузам и компаниям со статусами подписания.',page:'contracts'},
    {sel:'[data-page="kpi"]',ic:'chart',t:'Сводный KPI',x:'Аналитика трудоустройства в разрезе факультетов и вузов.',page:'kpi'},
    ...common];
  return [
    {sel:'[data-page="home"]',ic:'home',t:'Обзор',x:'Воронка найма и качество кандидатов в одном месте.',page:'home'},
    {sel:'[data-page="internships"]',ic:'briefcase',t:'Стажировки',x:'Публикуйте вакансии и следите за откликами.',page:'internships'},
    {sel:'[data-page="htd"]',ic:'puzzle',t:'Заказ на кадры',x:'Hire-Train-Deploy: закажите специалистов под свой спрос — под заказ соберётся учебный трек, студенты обучатся и попадут в витрину.',page:'htd',tip:'Воронка показывает конверсию от отклика до трудоустройства'},
    {sel:'[data-page="talent-showcase"]',ic:'trophy',t:'Витрина талантов',x:'Студенты с навыками, подтверждёнными практикой и HTD-треками. Premium открывает контакты.',page:'talent-showcase'},
    {sel:'[data-page="candidates"]',ic:'list',t:'Кандидаты',x:'Kanban-воронка найма — перетаскивайте кандидатов между этапами.',page:'candidates',tip:'Счётчики и метрики пересчитываются сразу'},
    ...common];
}

let TOUR={i:0,steps:[],active:false};

/* ============================================================
   ОБУЧАЮЩИЙ ЦЕНТР — «Как пользоваться платформой».
   Гайды по разделам берутся из tourSteps() (единый источник, без дублей).
   FAQ — короткие ответы на частые вопросы, свои для каждой роли.
   ============================================================ */
function helpGuides(){
  // переиспользуем описания разделов из тура: заголовок, иконка, текст, подсказка, страница
  return tourSteps().filter(s=>s.page).map(s=>({ic:s.ic,title:s.t,text:s.x,tip:s.tip,page:s.page}));
}
const HELP_FAQ={
  student:[
    {q:'С чего начать?',a:'Пройдите диагностику (12 вопросов, ~7 минут) — она строит вашу траекторию и делает проценты совпадения с вакансиями точными.'},
    {q:'Что важнее — курсы или практика?',a:'Соответствие тому, что ищет работодатель. Решённые симуляции и подтверждённая практика весят больше строчек в резюме.'},
    {q:'Как навыки попадают в витрину для компаний?',a:'Через подтверждение: ментор подтверждает часы и оценки в дневнике практики, принятые задания во фрилансе — и навык становится верифицированным.'},
    {q:'Оплата во фрилансе — это реальные деньги?',a:'Нет. Контур оплаты показан как демонстрация. Фактическая оплата идёт по договору практики, вне платформы.'},
    {q:'Кто видит мои данные?',a:'Работодатели видят только верифицированные навыки и портфолио. Настройки приватности — в разделе «Настройки».'},
  ],
  university:[
    {q:'Что даёт KPI-дашборд деканата?',a:'Аналитику трудоустройства по факультетам и «Индекс качества выпускника» — под государственные KPI по занятости. Есть экспорт для отчётности.'},
    {q:'Как устроен договор практики?',a:'Трёхсторонний: вуз + студент + компания. Статусы подписания имитируют E-imzo (в прототипе — демо).'},
    {q:'Откуда берутся компании-партнёры?',a:'Из реестра партнёров. Оттуда вуз выбирает базу практики при создании договора.'},
    {q:'Что показывает Gap-матрица?',a:'Где у когорты проседают компетенции — чтобы направить обучение точечно.'},
  ],
  company:[
    {q:'Чем «Заказ на кадры» отличается от вакансии?',a:'Это Hire-Train-Deploy: под ваш спрос собирается учебный трек, студенты обучаются и попадают в витрину уже подготовленными.'},
    {q:'Как работает фриланс с оплатой?',a:'Вы публикуете гиг, назначаете исполнителя, принимаете работу. Контур эскроу показан как демо — реальные деньги идут по договору практики, вне платформы.'},
    {q:'Что открывает Premium в витрине талантов?',a:'Контакты студентов с верифицированными навыками. В прототипе пейволл имитирован.'},
    {q:'Как оценивать задания?',a:'На экране проверки — оценки hard/soft и решение. Принятое задание пишет навыки в паспорт студента и обновляет витрину.'},
  ],
  mentor:[
    {q:'Что я подтверждаю?',a:'Часы и оценки в дневнике практики закреплённых за вами студентов. Ваша оценка усиливает их паспорт навыков.'},
    {q:'Где мои практиканты?',a:'В разделе «Мои практиканты». Записи, ожидающие подтверждения, — в «На проверку».'},
  ],
  admin:[
    {q:'Что доступно администратору?',a:'Реестр договоров, сводный KPI по вузам и факультетам, модерация фриланс-заданий.'},
    {q:'Как скрыть задание?',a:'В «Модерации фриланса» — кнопка «Скрыть». Оно перестанет показываться студентам, но останется в системе.'},
  ],
};

/* ---------------- welcome & finish screens ---------------- */
function tourWelcome(){
  const r=state.role;
  const name=(MOCK.reg&&MOCK.reg.first)||'';
  const n=tourSteps().length;
  const perks = r==='student'
    ? [['brain','Диагностика','Поймём ваши сильные стороны за 5 минут'],
       ['puzzle','Симуляции','Решайте реальные кейсы вместо теории'],
       ['briefcase','Вакансии','Подбор по совпадению с вашим профилем']]
    : r==='university'
    ? [['users','Когорты','Ведите группы студентов и следите за прогрессом'],
       ['chart','Аналитика','Видите, где проседают компетенции'],
       ['list','Отчёты','Выгрузки по готовности к рынку']]
    : [['users','Готовые кандидаты','С портфолио из решённых кейсов'],
       ['briefcase','Стажировки','Публикуйте и собирайте отклики'],
       ['target','Воронка','Kanban от отклика до оффера']];

  showTourModal(`
    <div class="tm-top">
      <div class="tm-ava">${ico('bot')}</div>
      <div class="tm-h">Привет${name?', '+name:''}! Я Hero</div>
      <div class="tm-s">Покажу платформу за минуту — чтобы вы сразу знали, где что находится.</div>
    </div>
    <div class="tm-body">
      <div class="tm-list">
        ${perks.map(p=>`<div class="tm-item">
          <div class="ti-ic">${ico(p[0])}</div>
          <div><div class="ti-t">${p[1]}</div><div class="ti-d">${p[2]}</div></div>
        </div>`).join('')}
      </div>
      <div class="tm-meta">${ico('clock')}${n} шагов · около минуты</div>
      <div class="tm-actions">
        <button class="btn btn-primary" onclick="tourBegin()">${ico('spark')} Показать платформу</button>
        <div class="tm-later" onclick="tourSkip()">Осмотрюсь сам</div>
      </div>
    </div>`);
}
function tourFinish(){
  const r=state.role;
  const next = r==='student'
    ? {t:'Пройти диагностику',d:'5 минут — и траектория построена',go:'diagnostics'}
    : r==='university' ? {t:'Открыть когорты',d:'Посмотрите на свои группы',go:'cohorts'}
    : {t:'Открыть кандидатов',d:'Воронка уже наполнена',go:'candidates'};
  showTourModal(`
    <div class="tm-top tm-done">
      <div class="tm-ava">${ico('check')}</div>
      <div class="tm-h">Готово — вы разобрались</div>
      <div class="tm-s">Теперь вы знаете, где что лежит. Я остаюсь в правом нижнем углу.</div>
    </div>
    <div class="tm-body">
      <div class="tm-stat">
        <div><div class="s-v">${TOUR.steps.length}</div><div class="s-l">Разделов показано</div></div>
        <div><div class="s-v">∞</div><div class="s-l">Вопросов к Hero</div></div>
        <div><div class="s-v">~6 нед</div><div class="s-l">До первого оффера</div></div>
      </div>
      <div class="tm-actions">
        <button class="btn btn-primary" onclick="tourGoNext('${next.go}')">${next.t} →</button>
        <div class="tm-later" onclick="closeTourModal()">Позже, спасибо</div>
      </div>
    </div>`);
}
function showTourModal(html){
  const m=document.getElementById('tour-modal'), c=document.getElementById('tm-card');
  if(!m||!c) return;
  c.innerHTML=html; m.classList.remove('hidden');
  TOUR.active=true;
}
function closeTourModal(){
  const m=document.getElementById('tour-modal'); if(m) m.classList.add('hidden');
  markTourSeen(); TOUR.active=false; heroShowFab();
  if(state.page!=='home') go('home');   // the tour wandered through sections; bring them back
}
function tourGoNext(page){
  const m=document.getElementById('tour-modal'); if(m) m.classList.add('hidden');
  markTourSeen(); TOUR.active=false; heroShowFab();
  go(page);
}

/* ---------------- the spotlight walkthrough ---------------- */
function startTour(){
  if(tourSeen()){ tourBegin(); return; }   // replay from settings skips the intro
  tourWelcome();
}
function tourBegin(){
  const m=document.getElementById('tour-modal'); if(m) m.classList.add('hidden');
  TOUR={i:0,steps:tourSteps(),active:true};
  document.getElementById('tour-mask').classList.remove('hidden');
  document.getElementById('tour-card').classList.remove('hidden');
  tourRender();
}
/* on narrow screens the sidebar is hidden — open it so the spotlight has a target */
function tourEnsureVisible(sel){
  if(!sel.startsWith('[data-page')) return;
  try{
    if(window.innerWidth<=900){
      const sb=document.getElementById('sidebar'); if(sb) sb.classList.add('open');
    }
  }catch(e){}
}
function tourRender(){
  const s=TOUR.steps[TOUR.i];
  if(!s){ tourSkip(true); return; }
  if(s.forceFab) heroShowFab();
  if(s.page && state.page!==s.page) go(s.page);   // show the real screen behind the mask
  tourEnsureVisible(s.sel);

  const hole=document.getElementById('tour-hole');
  const card=document.getElementById('tour-card');
  const el=document.querySelector(s.sel);

  /* наполняем контент СНАЧАЛА — тогда card.offsetHeight отражает реальную высоту,
     и позиционирование ниже корректно удержит карточку в пределах экрана */
  document.getElementById('tc-ic').innerHTML=ico(s.ic||'compass');
  document.getElementById('tc-step').textContent=`Шаг ${TOUR.i+1} из ${TOUR.steps.length}`;
  document.getElementById('tc-title').textContent=s.t;
  document.getElementById('tc-text').innerHTML=s.x;
  const tip=document.getElementById('tc-tip');
  if(s.tip){ tip.innerHTML=ico('spark')+`<span>${s.tip}</span>`; tip.classList.remove('hidden'); }
  else tip.classList.add('hidden');
  document.getElementById('tc-back').disabled = TOUR.i===0;
  document.getElementById('tc-next').textContent = (TOUR.i===TOUR.steps.length-1)?'Завершить':'Далее →';
  document.getElementById('tc-dots').innerHTML=TOUR.steps.map((_,i)=>
    `<i class="${i===TOUR.i?'on':(i<TOUR.i?'past':'')}" onclick="tourGo(${i})"></i>`).join('');

  if(el && hole){
    const r=el.getBoundingClientRect(), pad=6;
    hole.style.left=(r.left-pad)+'px'; hole.style.top=(r.top-pad)+'px';
    hole.style.width=(r.width+pad*2)+'px'; hole.style.height=(r.height+pad*2)+'px';
    hole.style.opacity='1';

    /* place the card on whichever side has room, and point the arrow there */
    const CW=356, GAP=18;
    const CH=Math.max(card.offsetHeight||0, 260);   // реальная высота карточки (уже с контентом)
    const maxTop=Math.max(16, window.innerHeight-CH-16);   // ниже этого — низ карточки уйдёт за экран
    let cx, cy, side;
    if(r.right+GAP+CW < window.innerWidth){ cx=r.right+GAP; cy=r.top-10; side='right'; }
    else if(r.left-GAP-CW > 0){ cx=r.left-GAP-CW; cy=r.top-10; side='left'; }
    else if(r.bottom+GAP+CH < window.innerHeight){ cx=Math.max(16,r.left); cy=r.bottom+GAP; side='bottom'; }
    else { cx=Math.max(16,r.left); cy=Math.max(16,r.top-GAP-CH); side='top'; }
    cx=Math.min(Math.max(16,cx), window.innerWidth-CW-16);
    cy=Math.min(Math.max(16,cy), maxTop);   // гарантируем, что низ карточки (кнопки) в экране
    card.style.left=cx+'px'; card.style.top=cy+'px';
    card.setAttribute('data-side',side);
  }else if(hole){
    /* target missing (e.g. hidden on mobile) — centre the card, no arrow */
    hole.style.opacity='0';
    card.style.left=Math.max(16,(window.innerWidth-356)/2)+'px';
    const CH=Math.max(card.offsetHeight||0, 260);
    card.style.top=Math.max(16, Math.min(90, window.innerHeight-CH-16))+'px';
    card.setAttribute('data-side','none');
  }
}
function tourGo(i){ if(i>=0&&i<TOUR.steps.length){ TOUR.i=i; tourRender(); } }
function tourNext(){
  if(TOUR.i<TOUR.steps.length-1){ TOUR.i++; tourRender(); }
  else { hideSpotlight(); tourFinish(); }
}
function tourBack(){ if(TOUR.i>0){ TOUR.i--; tourRender(); } }
function hideSpotlight(){
  document.getElementById('tour-mask').classList.add('hidden');
  document.getElementById('tour-card').classList.add('hidden');
}
function markTourSeen(){ try{ localStorage.setItem('z2h_tour_done','1'); }catch(e){} }
function tourSkip(done){
  hideSpotlight();
  const m=document.getElementById('tour-modal'); if(m) m.classList.add('hidden');
  markTourSeen(); TOUR.active=false;
  heroShowFab();
  if(state.page && state.page!=='home') go('home');
  if(done) toast('Тур пройден — Hero всегда в правом нижнем углу');
  else {
    const dot=document.getElementById('hero-dot'); if(dot) dot.classList.remove('hidden');
  }
}
/* keyboard: ← → to move, Esc to leave */
if(typeof document!=='undefined' && document.addEventListener){
  document.addEventListener('keydown',e=>{
    if(!TOUR.active) return;
    const spotlight=!document.getElementById('tour-card').classList.contains('hidden');
    if(e.key==='Escape'){ e.preventDefault(); tourSkip(); }
    else if(spotlight && (e.key==='ArrowRight'||e.key==='Enter')){ e.preventDefault(); tourNext(); }
    else if(spotlight && e.key==='ArrowLeft'){ e.preventDefault(); tourBack(); }
  });
}
function tourSeen(){ try{ return localStorage.getItem('z2h_tour_done')==='1'; }catch(e){ return false; } }
if(typeof window!=='undefined' && window.addEventListener){
  window.addEventListener('resize',()=>{
    const c=document.getElementById('tour-card');
    if(c && !c.classList.contains('hidden')) tourRender();
  });
}

/* ▲▲▲ END HERO ▲▲▲ */

/* ============================================================
   INIT
   ============================================================ */
authTab('signin');
pubGo('home');
/* restore session: only a fully active app auto-logs in. An unfinished
   registration draft must NOT hijack the landing page — a returning visitor
   always sees the public site first. The draft is still kept in localStorage,
   so "Начать" will offer to resume from where they left off. */
(function(){
  const s=restoreState();
  if(s && s.role && s.active){
    enterApp(s.role, true);   // genuine logged-in session → app
    return;
  }
  show('scr-public');
})();
</script>
</body>
</html>
