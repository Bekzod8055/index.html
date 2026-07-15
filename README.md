<!DOCTYPE html>
<html lang="uz">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Techna — AI-chatbot mijozlaringiz uchun</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Instrument+Sans:wght@400;500;600&family=Instrument+Serif:ital@0;1&family=Geist+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root{
  --paper:#FBFAF7;
  --paper-2:#F3F1EB;
  --ink:#14140F;
  --ink-60:rgba(20,20,15,.60);
  --ink-40:rgba(20,20,15,.38);
  --ink-12:rgba(20,20,15,.12);
  --ink-06:rgba(20,20,15,.06);
  --lime:#22D3EE;
  --lime-deep:#0891B2;
  --violet:#4B2EE0;
  --r:14px;
  --sans:'Instrument Sans',system-ui,sans-serif;
  --serif:'Instrument Serif',Georgia,serif;
  --mono:'Geist Mono',ui-monospace,monospace;
}
/* ── тёмная тема: переопределяем те же переменные ── */
html[data-theme="dark"]{
  --paper:#0a0b10;
  --paper-2:#14161f;
  --ink:#EDEEF2;
  --ink-60:rgba(237,238,242,.62);
  --ink-40:rgba(237,238,242,.40);
  --ink-12:rgba(237,238,242,.14);
  --ink-06:rgba(237,238,242,.07);
}
html[data-theme="dark"]{background:#0a0b10}
html[data-theme="dark"] body{background:transparent}
html[data-theme="dark"] .card,
html[data-theme="dark"] .pk,
html[data-theme="dark"] .calc,
html[data-theme="dark"] .night-box,
html[data-theme="dark"] .modal,
html[data-theme="dark"] .prod-menu{background:#14161f}
html[data-theme="dark"] nav{background:rgba(10,11,16,.72)}
html[data-theme="dark"] .mobile-nav{background:#0a0b10;border-bottom-color:rgba(237,238,242,.14)}
html[data-theme="dark"] .bot-txt{background:#1c1f2a}
html[data-theme="dark"] .c-ans .bot-av,
html[data-theme="dark"] .core{background:#0f1015}
html[data-theme="dark"] .pk.hot,
html[data-theme="dark"] .op{background:#EDEEF2;color:#0a0b10}
html[data-theme="dark"] .op .s{color:rgba(20,20,15,.5)}
html[data-theme="dark"] .calc-out{background:#0a0b10}
html[data-theme="dark"] .btn-dark{background:#EDEEF2;color:#0a0b10}
html[data-theme="dark"] input,html[data-theme="dark"] select{background:#0f1015;color:#EDEEF2}
html[data-theme="dark"] .tl-st.wait{background:rgba(237,238,242,.08)}
html[data-theme="dark"] .fcell,html[data-theme="dark"] .m,html[data-theme="dark"] .type,html[data-theme="dark"] .step,html[data-theme="dark"] .tbl,html[data-theme="dark"] .case{background:#14161f}
html[data-theme="dark"] .cell{background:#14161f;border-color:rgba(237,238,242,.14)}
html[data-theme="dark"] .cell .ic{border-color:rgba(237,238,242,.18)}
/* accent blocks that are dark-by-design: keep them dark in BOTH themes so their light text reads */
html[data-theme="dark"] .night-box,
html[data-theme="dark"] .m.night,
html[data-theme="dark"] .m.night:hover,
html[data-theme="dark"] .cta-band,
html[data-theme="dark"] .cell.big{background:#14161f;border-color:#14161f}
html[data-theme="dark"] .cell.big{color:#EDEEF2}
html[data-theme="dark"] .cta-band,
html[data-theme="dark"] .night-box{color:#EDEEF2}
/* .pk.hot becomes a LIGHT card in dark theme — its secondary text must go dark to stay readable */
html[data-theme="dark"] .pk.hot .msgs{color:rgba(20,20,15,.6)}
html[data-theme="dark"] .pk.hot .price small{color:rgba(20,20,15,.5)}
html[data-theme="dark"] .pk.hot .per{background:rgba(20,20,15,.07)}
html[data-theme="dark"] .pk.hot .per span{color:rgba(20,20,15,.55)}
html[data-theme="dark"] .pk.hot .price{color:var(--lime-deep)}
html[data-theme="dark"] .pk.hot .per b{color:var(--lime-deep)}
html[data-theme="dark"] .pk.hot .save{color:var(--lime-deep)}
html[data-theme="dark"] .pk .pop{color:#14140F}
html[data-theme="dark"] .cell.big p{color:rgba(237,238,242,.62)}
html[data-theme="dark"] .cell.big .num{color:rgba(237,238,242,.4)}
/* lime-карточка в тёмной теме становится тёмной (#14161f от .cell override) —
   значит её содержимое должно быть светлым, а не тёмным */
html[data-theme="dark"] .cell.lime p{color:rgba(237,238,242,.62)}
html[data-theme="dark"] .cell.lime .ic{border-color:rgba(237,238,242,.18);color:var(--lime)}
html[data-theme="dark"] .cell.lime .ic svg path{stroke:var(--lime)}
html[data-theme="dark"] .cell.lime .num{color:rgba(237,238,242,.4)}
html[data-theme="dark"] .lang button.on{background:#0a0b10;color:#EDEEF2}
html[data-theme="dark"] .prod-item:hover,html[data-theme="dark"] .prod-item.active{background:#0a0b10}

*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
html{background:var(--paper)}
body{
  background:transparent;color:var(--ink);
  font-family:var(--sans);font-size:16px;line-height:1.55;
  -webkit-font-smoothing:antialiased;overflow-x:hidden;
  position:relative;
}

/* ── анимированный световой фон ── */
.bg-lights{position:fixed;inset:0;z-index:0;overflow:hidden;pointer-events:none}
/* весь контент над световым слоем (nav/footer имеют свои z-index) */
section,main{position:relative;z-index:1}
.bg-lights span{position:absolute;border-radius:50%;filter:blur(65px);will-change:transform,opacity}
/* два света по краям, не заходят в центр */
.bg-lights .l1{width:30vw;height:30vw;left:-8vw;top:8vh;
  background:radial-gradient(circle,rgba(34,211,238,.5),transparent 63%);animation:orb1 18s ease-in-out infinite}
.bg-lights .l2{width:28vw;height:28vw;right:-8vw;bottom:10vh;
  background:radial-gradient(circle,rgba(75,46,224,.3),transparent 63%);animation:orb2 22s ease-in-out infinite}
@keyframes orb1{0%{transform:translate(0,0) scale(1)}33%{transform:translate(8vw,14vh) scale(1.15)}66%{transform:translate(-2vw,26vh) scale(.95)}100%{transform:translate(0,0) scale(1)}}
@keyframes orb2{0%{transform:translate(0,0) scale(1)}33%{transform:translate(-8vw,-14vh) scale(1.18)}66%{transform:translate(-2vw,-28vh) scale(.95)}100%{transform:translate(0,0) scale(1)}}
html[data-theme="dark"] .bg-lights span{mix-blend-mode:screen}
@media(max-width:640px){.bg-lights span{filter:blur(45px)}}
.wrap{max-width:1320px;margin:0 auto;padding:0 28px}
header .wrap{max-width:1320px}
a{color:inherit;text-decoration:none}
:focus-visible{outline:2px solid var(--violet);outline-offset:3px;border-radius:4px}

/* ── type ── */
.eyebrow{
  font-family:var(--mono);font-size:11px;letter-spacing:.16em;
  text-transform:uppercase;color:var(--ink-40);
  display:flex;align-items:center;gap:9px;
}
.eyebrow::before{content:"";width:6px;height:6px;background:var(--lime-deep);border-radius:50%}
h1,h2{font-weight:500;letter-spacing:-.03em;line-height:1.02}
h1{font-size:clamp(36px,4.4vw,60px);min-height:366px}
h2{font-size:clamp(32px,4.2vw,58px)}
.it{font-family:var(--serif);font-style:italic;font-weight:400;letter-spacing:-.01em}
.lead{font-size:17px;color:var(--ink-60);max-width:46ch}

/* ── nav ── */
nav{
  position:fixed;top:0;left:0;right:0;z-index:60;
  backdrop-filter:blur(14px);background:rgba(251,250,247,.72);
  border-bottom:1px solid transparent;transition:border-color .3s;
}
nav.stuck{border-bottom-color:var(--ink-12)}
.nav-in{display:flex;align-items:center;justify-content:space-between;height:68px}
.wrap.nav-in{max-width:1320px}
.logo{display:flex;align-items:center;gap:9px;font-weight:600;font-size:17px;letter-spacing:-.02em}
.dot{width:9px;height:9px;border-radius:50%;background:var(--lime-deep);
  box-shadow:0 0 0 0 rgba(8,145,178,.5);animation:pulse 2.6s infinite}
@keyframes pulse{70%{box-shadow:0 0 0 9px rgba(8,145,178,0)}100%{box-shadow:0 0 0 0 rgba(8,145,178,0)}}
.nav-links{display:flex;gap:30px;font-size:14.5px;color:var(--ink-60)}
.nav-links a{position:relative;transition:color .2s}
.nav-links a:hover{color:var(--ink)}
.nav-links a::after{content:"";position:absolute;left:0;bottom:-4px;height:1.5px;width:0;background:var(--ink);transition:width .25s}
.nav-links a:hover::after{width:100%}

/* ── burger (mobile nav) ── */
.burger{display:none;width:40px;height:40px;border-radius:11px;border:1px solid var(--ink-12);
  background:transparent;cursor:pointer;align-items:center;justify-content:center;
  flex-direction:column;gap:4px;padding:0;transition:background .2s,border-color .2s}
.burger:hover{background:var(--ink-06)}
.burger span{display:block;width:17px;height:1.6px;background:var(--ink);border-radius:2px;
  transition:transform .28s cubic-bezier(.2,.8,.2,1),opacity .2s}
.burger.open span:nth-child(1){transform:translateY(5.6px) rotate(45deg)}
.burger.open span:nth-child(2){opacity:0}
.burger.open span:nth-child(3){transform:translateY(-5.6px) rotate(-45deg)}
.mobile-nav{display:none;position:fixed;top:68px;left:0;right:0;z-index:59;
  background:var(--paper);border-bottom:1px solid var(--ink-12);
  padding:8px 0 14px;transform:translateY(-8px);opacity:0;pointer-events:none;
  transition:opacity .26s,transform .26s}
.mobile-nav.open{opacity:1;transform:none;pointer-events:auto}
.mobile-nav a{display:block;padding:13px 24px;font-size:16px;color:var(--ink);
  border-bottom:1px solid var(--ink-06)}
.mobile-nav a:last-child{border-bottom:0}
.mobile-nav a:active{background:var(--ink-06)}

/* ── product switcher ── */
.prod{position:relative}
.prod-btn{display:flex;align-items:center;gap:8px;padding:7px 12px;border-radius:100px;
  border:1px solid var(--ink-12);background:transparent;cursor:pointer;font-family:var(--sans);
  font-size:14px;font-weight:500;color:var(--ink);transition:background .2s,border-color .2s}
.prod-btn:hover{background:var(--ink-06);border-color:var(--ink-40)}
.prod-btn .cur-p{display:flex;align-items:center;gap:7px}
.prod-btn .chev{transition:transform .25s}
.prod.open .prod-btn .chev{transform:rotate(180deg)}
.prod-menu{position:absolute;top:calc(100% + 8px);left:0;width:288px;
  background:#fff;border:1px solid var(--ink-12);border-radius:14px;padding:6px;z-index:70;
  box-shadow:0 24px 60px -24px rgba(20,20,15,.4);
  opacity:0;transform:translateY(-6px);pointer-events:none;transition:opacity .22s,transform .22s}
.prod.open .prod-menu{opacity:1;transform:none;pointer-events:auto}
.prod-item{display:flex;gap:11px;align-items:flex-start;padding:11px;border-radius:10px;
  transition:background .18s;cursor:pointer}
.prod-item:hover{background:var(--paper-2)}
.prod-item.active{background:var(--paper-2)}
.prod-item .pic{width:34px;height:34px;border-radius:9px;flex-shrink:0;display:grid;place-items:center;
  background:var(--ink)}
.prod-item.active .pic{background:var(--lime)}
.prod-item .pt{font-size:13.5px;font-weight:600;letter-spacing:-.01em;display:flex;align-items:center;gap:7px}
.prod-item .pt .badge-now{font-family:var(--mono);font-size:8px;letter-spacing:.08em;text-transform:uppercase;
  background:var(--lime);color:#14140F;padding:2px 6px;border-radius:100px;font-weight:600}
.prod-item .pd{font-size:11.5px;color:var(--ink-60);margin-top:2px;line-height:1.35}

/* ── language switcher ── */
.theme-btn{width:36px;height:36px;border-radius:50%;border:1px solid var(--ink-12);background:transparent;cursor:pointer;display:grid;place-items:center;color:var(--ink);transition:background .2s,border-color .2s}
.theme-btn:hover{background:var(--ink-06);border-color:var(--ink-40)}
.theme-btn .sun{display:none}
.theme-btn .moon{display:block}
html[data-theme="dark"] .theme-btn .sun{display:block}
html[data-theme="dark"] .theme-btn .moon{display:none}
.lang{display:flex;gap:2px;background:var(--paper-2);border-radius:100px;padding:3px;border:1px solid var(--ink-12)}
.lang button{border:0;background:transparent;font-family:var(--mono);font-size:11px;font-weight:600;
  letter-spacing:.04em;color:var(--ink-40);padding:5px 9px;border-radius:100px;cursor:pointer;
  transition:background .2s,color .2s}
.lang button.on{background:#fff;color:var(--ink);box-shadow:0 1px 3px rgba(20,20,15,.1)}
.lang button:hover:not(.on){color:var(--ink-60)}
.nav-right{display:flex;align-items:center;gap:12px}

/* ── buttons ── */
.btn{
  display:inline-flex;align-items:center;gap:8px;
  padding:13px 22px;border-radius:100px;font-size:14.5px;font-weight:500;
  border:1px solid transparent;cursor:pointer;position:relative;overflow:hidden;
  transition:transform .18s cubic-bezier(.2,.8,.2,1),box-shadow .18s;
}
.btn:active{transform:scale(.97)}
.btn-dark{background:var(--ink);color:var(--paper)}
.btn-dark:hover{box-shadow:0 8px 26px -8px rgba(20,20,15,.55);transform:translateY(-1.5px)}
.btn-dark .arw{transition:transform .22s cubic-bezier(.16,1,.3,1)}
.btn-dark:hover .arw{transform:translateX(4px)}
/* блик, пробегающий по кнопке при наведении */
.btn-dark::before,.btn-lime::before{content:"";position:absolute;top:0;left:-120%;width:80%;height:100%;
  background:linear-gradient(100deg,transparent,rgba(255,255,255,.35),transparent);
  transform:skewX(-18deg);transition:none;pointer-events:none;z-index:0}
.btn>*{position:relative;z-index:1}
.btn-dark:hover::before,.btn-lime:hover::before{animation:btnShine .7s cubic-bezier(.2,.7,.3,1)}
@keyframes btnShine{from{left:-120%}to{left:130%}}
.btn-ghost{border-color:var(--ink-12);color:var(--ink)}
.btn-ghost:hover{background:var(--ink-06);border-color:var(--ink-40)}
.btn-lime{background:var(--lime);color:#14140F;font-weight:600}
.btn-lime:hover{box-shadow:0 10px 30px -10px rgba(8,145,178,.8);transform:translateY(-1.5px)}
.btn-lime .arw{transition:transform .22s cubic-bezier(.16,1,.3,1)}
.btn-lime:hover .arw{transform:translateX(4px)}
/* главная CTA в hero — лаймовое свечение, бегущее по обводке */
.hero-cta .btn-dark{position:relative;overflow:hidden;background:var(--ink);isolation:isolate;
  box-shadow:0 0 24px -2px rgba(34,211,238,.35), 0 8px 30px -12px rgba(34,211,238,.4)}
html[data-theme="dark"] .hero-cta .btn-dark{background:#EDEEF2;color:#0a0b10}
/* вращающийся конический градиент — заполняет всю площадь и крутится (виден кантом) */
.hero-cta .btn-dark::before{content:"";position:absolute;z-index:0;
  top:50%;left:50%;width:180%;aspect-ratio:1;
  background:conic-gradient(from 0deg,
    transparent 0deg, transparent 210deg,
    var(--lime) 285deg, #f0ffb0 300deg, var(--lime) 315deg,
    transparent 360deg);
  transform:translate(-50%,-50%) rotate(0deg);
  animation:btnRotate 2.6s linear infinite}
@keyframes btnRotate{to{transform:translate(-50%,-50%) rotate(360deg)}}
/* заливка поверх градиента — оставляет тонкий светящийся кант ~2px по краю */
.hero-cta .btn-dark::after{content:"";position:absolute;inset:2px;z-index:1;border-radius:100px;
  background:var(--ink)}
html[data-theme="dark"] .hero-cta .btn-dark::after{background:#EDEEF2}
.hero-cta .btn-dark > span,.hero-cta .btn-dark > svg{position:relative;z-index:2}
.hero-cta .btn-dark .shine{display:none}
.hero-cta .btn-dark:hover{transform:translateY(-2px)}
@media(prefers-reduced-motion:reduce){
  .hero-cta .btn-dark::before{animation:none}
}

/* ── hero ── */
header{padding:150px 0 96px;position:relative;overflow-x:clip}
.glow{
  position:absolute;top:-160px;right:-120px;width:620px;height:620px;pointer-events:none;
  background:radial-gradient(circle,rgba(34,211,238,.34),transparent 62%);
  filter:blur(30px);z-index:0;
}
.hero{display:grid;grid-template-columns:.70fr 1.30fr;gap:26px;align-items:center;position:relative;z-index:1}
.wrap.hero{max-width:1320px}
h1 .ln{display:block;overflow:hidden}
h1 .ln span{display:block;transform:translateY(102%);animation:rise .95s cubic-bezier(.16,1,.3,1) forwards}
h1 .ln:nth-child(2) span{animation-delay:.09s}
h1 .ln:nth-child(3) span{animation-delay:.18s}
@keyframes rise{to{transform:translateY(0)}}
/* повторный проигрыш при смене заголовка */
h1.swap .ln span{animation:rise .8s cubic-bezier(.16,1,.3,1) forwards}
h1.swap .ln:nth-child(1) span{animation-delay:0s}
h1.swap .ln:nth-child(2) span{animation-delay:.08s}
h1.swap .ln:nth-child(3) span{animation-delay:.16s}
.h1-dots{display:flex;gap:8px;margin-top:22px}
.h1-dots i{width:22px;height:3px;border-radius:100px;background:var(--ink-12);
  cursor:pointer;transition:background .3s}
.h1-dots i.on{background:var(--ink)}
.h1-dots i .fill{display:block;height:100%;width:0;border-radius:100px;background:var(--lime-deep)}
.h1-dots i.on .fill{animation:h1fill 5s linear forwards}
@keyframes h1fill{to{width:100%}}
.fade{opacity:0;animation:fade .8s ease forwards}
@keyframes fade{to{opacity:1}}
.d1{animation-delay:.38s}.d2{animation-delay:.5s}.d3{animation-delay:.62s}
.hero-copy .eyebrow{margin-bottom:26px}
.hero-copy h1{margin-bottom:26px}
.hero-cta{display:flex;gap:12px;margin-top:34px;flex-wrap:wrap}
.trust{margin-top:30px;display:flex;align-items:center;gap:10px;font-size:12px;color:var(--ink-40);font-family:var(--mono);flex-wrap:wrap}
.trust b{color:var(--ink);font-weight:500}

/* ── hub ── */
.stage{position:relative;height:786px}
.hub{position:relative;width:100%;height:100%}

.core{
  position:absolute;left:50%;top:50%;transform:translate(-50%,-50%);
  width:112px;height:112px;border-radius:50%;
  background:var(--ink);display:grid;place-items:center;z-index:5;
}
.core::before{
  content:"";position:absolute;inset:-30px;border-radius:50%;
  box-shadow:0 0 44px 14px rgba(34,211,238,.55);
  animation:breathe 3.6s ease-in-out infinite;z-index:-1;
}
.core::after{
  content:"";position:absolute;inset:-9px;border-radius:50%;
  border:1px solid rgba(34,211,238,.4);animation:ring 3.6s ease-out infinite;
}
.core.fire{animation:fire .5s cubic-bezier(.2,.8,.2,1)}
@keyframes fire{0%{transform:translate(-50%,-50%) scale(1)}
  40%{transform:translate(-50%,-50%) scale(1.12)}
  100%{transform:translate(-50%,-50%) scale(1)}}
/* волна из ядра */
.shock{
  position:absolute;left:50%;top:50%;width:112px;height:112px;
  border-radius:50%;border:2px solid rgba(34,211,238,.7);
  transform:translate(-50%,-50%) scale(1);pointer-events:none;z-index:2;opacity:0;
}
.shock.go{animation:shock 1.05s cubic-bezier(.16,1,.3,1) forwards}
@keyframes shock{0%{opacity:.9;transform:translate(-50%,-50%) scale(1)}
  100%{opacity:0;transform:translate(-50%,-50%) scale(4.6)}}
@keyframes breathe{0%,100%{transform:scale(.96);opacity:.6}50%{transform:scale(1.06);opacity:1}}
@keyframes ring{0%{transform:scale(.94);opacity:.85}100%{transform:scale(1.44);opacity:0}}
.face{display:flex;gap:10px;transform:translateX(-0.5px)}
.face i{width:11px;height:16px;border-radius:5px;background:var(--lime);display:block;animation:blink 4.2s infinite}
@keyframes blink{0%,92%,100%{transform:scaleY(1)}95%{transform:scaleY(.12)}}
.core-lbl{
  position:absolute;left:50%;top:calc(50% + 74px);transform:translateX(-50%);
  font-family:var(--mono);font-size:9.5px;letter-spacing:.14em;text-transform:uppercase;
  color:var(--ink-40);white-space:nowrap;z-index:5;text-align:center;
}

.wires{position:absolute;inset:0;z-index:1;overflow:visible;pointer-events:none}
.wire{fill:none;stroke:rgba(20,20,15,.18);stroke-width:1.2;stroke-dasharray:3 4;
  transition:stroke .35s,stroke-width .35s}
.wire.live{stroke:rgba(34,211,238,.85);stroke-width:2;stroke-dasharray:none;
  filter:drop-shadow(0 0 4px rgba(34,211,238,.8))}
.wire.dim{opacity:0}
.spark{fill:none;stroke:#8FBF12;stroke-width:3;stroke-linecap:round;opacity:0;
  filter:drop-shadow(0 0 5px rgba(34,211,238,.9))}

.card{
  position:absolute;width:216px;height:176px;overflow:hidden;box-sizing:border-box;
  background:#fff;border:1px solid var(--ink-12);
  border-radius:13px;padding:11px 12px 40px;z-index:3;
  box-shadow:0 16px 40px -22px rgba(20,20,15,.3);
  opacity:0;transform:translateY(10px) scale(.96);
  animation:cardIn .6s cubic-bezier(.16,1,.3,1) forwards;
  transition:transform .3s cubic-bezier(.2,.8,.2,1),box-shadow .3s,border-color .3s;
}
.card:hover{transform:translateY(-4px);border-color:var(--ink-40);box-shadow:0 22px 50px -22px rgba(20,20,15,.4);z-index:7}
@keyframes cardIn{to{opacity:1;transform:none}}

/* новый клиент въезжает */
.card.enter{animation:enter .62s cubic-bezier(.16,1,.3,1) forwards}
@keyframes enter{
  0%{opacity:0;transform:translateY(16px) scale(.9)}
  55%{opacity:1}
  100%{opacity:1;transform:translateY(0) scale(1)}
}
/* отработавший клиент уходит */
.card.leave{animation:leave .5s cubic-bezier(.5,0,.75,0) forwards;pointer-events:none}
@keyframes leave{
  0%{opacity:1;transform:translateY(0) scale(1);filter:blur(0)}
  100%{opacity:0;transform:translateY(-14px) scale(.92);filter:blur(2px)}
}
/* вспышка «новое окно» */
.card.enter::after{
  content:"";position:absolute;inset:0;border-radius:13px;pointer-events:none;
  box-shadow:0 0 0 3px rgba(34,211,238,.55);
  animation:flash .8s cubic-bezier(.16,1,.3,1) forwards;
}
@keyframes flash{0%{opacity:1}100%{opacity:0}}

/* призрачный слот пока карточки нет */
.s0{top:72px;left:0}.s1{top:72px;right:0}
.s2{top:302px;left:0}.s3{top:302px;right:0}
.s4{bottom:78px;left:0}.s5{bottom:78px;right:0}
.slot{
  position:absolute;width:216px;height:176px;border-radius:13px;
  border:1.5px dashed var(--ink-12);z-index:2;pointer-events:none;
  opacity:0;transition:opacity .3s;
}
.slot.on{opacity:.75;animation:slotPulse 1.2s ease-in-out infinite}
@keyframes slotPulse{0%,100%{border-color:var(--ink-12);transform:scale(.99)}50%{border-color:rgba(34,211,238,.75);transform:scale(1)}}
.c1{top:72px;left:0}
.c2{top:72px;right:0}
.c3{top:302px;left:0}
.c4{top:302px;right:0}
.c5{bottom:78px;left:0}
.c6{bottom:78px;right:0}
.c1{animation-delay:.46s}.c2{animation-delay:.56s}.c3{animation-delay:.66s}
.c4{animation-delay:.76s}.c5{animation-delay:.86s}.c6{animation-delay:.96s}

/* мигающая рамка «бот печатает именно тут» */
.card.act{border-color:var(--lime-deep);
  box-shadow:0 0 0 4px rgba(34,211,238,.42),0 18px 44px -20px rgba(20,20,15,.34);
  transform:translateY(-3px)}
.card.hit{animation:hit .42s cubic-bezier(.34,1.56,.64,1) forwards}
@keyframes hit{0%{opacity:1;transform:translateY(-3px) scale(1)}
  45%{opacity:1;transform:translateY(-5px) scale(1.035)}
  100%{opacity:1;transform:translateY(-3px) scale(1)}}

.c-top{display:flex;align-items:center;gap:7px;margin-bottom:9px}
.pf{width:19px;height:19px;border-radius:5px;display:grid;place-items:center;flex-shrink:0}
.pf svg{width:11px;height:11px}
.c-top .ch{font-size:11.5px;font-weight:600;letter-spacing:-.01em}
.c-top .tm{margin-left:auto;font-family:var(--mono);font-size:9px;color:var(--ink-40)}

.c-body{display:flex;gap:8px;align-items:flex-start;padding-bottom:9px}
.c-body .av{width:24px;height:24px;border-radius:50%;flex-shrink:0;display:grid;place-items:center;font-size:10px;font-weight:600;color:#fff}
.c-body .u{font-size:11px;font-weight:600;line-height:1.3}
.c-body .q{font-size:11px;color:var(--ink-60);line-height:1.35}

/* строка статуса — теперь без секунд */
/* ответ бота */
.c-ans{
  display:flex;gap:7px;align-items:flex-start;
  border-top:1px solid var(--ink-06);padding-top:9px;
}
.bot-av{
  width:20px;height:20px;border-radius:6px;background:var(--ink);flex-shrink:0;
  display:grid;place-items:center;margin-top:1px;
}
.bot-av i{width:3.5px;height:5px;border-radius:2px;background:var(--lime);display:block}
.bot-av span{display:flex;gap:2.5px}
.bot-txt{
  align-self:stretch;background:var(--paper-2);border-radius:9px;border-top-left-radius:3px;
  padding:7px 9px;font-size:10.5px;line-height:1.45;color:var(--ink);
  min-height:40px;flex:1;position:relative;
  display:flex;align-items:center;
}
.bot-txt:not(.wait){display:block;padding-top:11px}
.bot-txt .bt{display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical;overflow:hidden}
.bot-txt .typecur{
  display:inline-block;width:1.5px;height:10px;background:var(--lime-deep);
  vertical-align:-1px;margin-left:1.5px;animation:blinkcur .7s steps(1) infinite;
}
.bot-txt.wait{gap:4px}
@keyframes blinkcur{50%{opacity:0}}
.dot3{display:flex;gap:3.5px}
.dot3 i{width:4px;height:4px;border-radius:50%;background:var(--ink-40);display:block;animation:bob 1.05s infinite}
.dot3 i:nth-child(2){animation-delay:.13s}.dot3 i:nth-child(3){animation-delay:.26s}
@keyframes bob{0%,60%,100%{transform:translateY(0);opacity:.35}30%{transform:translateY(-3px);opacity:1}}

.c-foot{position:absolute;left:12px;right:12px;bottom:10px;
  display:flex;align-items:center;gap:6px;height:22px;line-height:1}
.c-foot .ok{color:var(--lime-deep);display:flex;align-items:center;gap:4px;letter-spacing:.03em}
.c-foot .typ{display:flex;align-items:center;gap:5px;color:var(--ink-40);letter-spacing:.03em}
.c-foot .typ b{display:flex;gap:3px}
.c-foot .typ i{width:3.5px;height:3.5px;border-radius:50%;background:var(--lime-deep);display:block;animation:bob 1.05s infinite}
.c-foot .typ i:nth-child(2){animation-delay:.13s}.c-foot .typ i:nth-child(3){animation-delay:.26s}
@keyframes bob{0%,60%,100%{transform:translateY(0);opacity:.35}30%{transform:translateY(-3px);opacity:1}}
.c-lead.off{display:none}

/* стадии: цветные чипы состояния */
.stg{
  max-width:100%;min-width:0;height:20px;box-sizing:border-box;
  display:inline-flex;align-items:center;gap:5px;padding:0 8px;border-radius:100px;
  font-family:var(--mono);font-size:8.5px;letter-spacing:.06em;text-transform:uppercase;
  white-space:nowrap;transition:background .3s,color .3s;
}
.stg svg{flex-shrink:0}
.stg.new{background:var(--paper-2);color:var(--ink-60)}
.stg.typing{background:rgba(34,211,238,.22);color:#5F8409}
.stg.sent{background:transparent;color:var(--lime-deep);padding-left:0}
.stg.lead{background:var(--lime);color:#14140F;font-weight:600}
.stg.tooper{background:var(--ink);color:var(--lime)}
.stg.deal{background:transparent;color:var(--ink-40);border:1px solid var(--ink-12)}
.stg .d3{display:flex;gap:3px}
.stg .d3 i{width:3.5px;height:3.5px;border-radius:50%;background:#7BA80C;display:block;animation:bob 1.05s infinite}
.stg .d3 i:nth-child(2){animation-delay:.13s}.stg .d3 i:nth-child(3){animation-delay:.26s}

/* орбитальные счётчики «+N» */
.orb{
  position:absolute;z-index:1;pointer-events:none;
  background:#fff;border:1px solid var(--ink-12);border-radius:100px;
  padding:4px 9px;font-family:var(--mono);font-size:9.5px;color:rgba(20,20,15,.55);
  box-shadow:0 8px 20px -10px rgba(20,20,15,.28);
  opacity:0;transform:scale(.6);
}
.orb b{color:var(--lime-deep);font-weight:600}
.orb.on{animation:orbIn 3.4s cubic-bezier(.16,1,.3,1) forwards}
@keyframes orbIn{
  0%{opacity:0;transform:scale(.6) translateY(6px)}
  14%{opacity:1;transform:scale(1) translateY(0)}
  76%{opacity:1;transform:scale(1) translateY(-6px)}
  100%{opacity:0;transform:scale(.94) translateY(-14px)}
}

/* лента событий */
.feed{
  position:absolute;z-index:7;left:50%;transform:translateX(-50%);
  top:calc(50% + 116px);height:70px;
  display:flex;flex-direction:column;align-items:center;justify-content:flex-start;gap:4px;
  pointer-events:none;width:196px;overflow:hidden;
}
.ev{
  background:#fff;color:#14140F;border:1px solid var(--ink-12);border-radius:100px;
  padding:5px 11px;font-family:var(--mono);font-size:9px;letter-spacing:.05em;
  display:flex;align-items:center;gap:6px;white-space:nowrap;
  box-shadow:0 10px 24px -14px rgba(20,20,15,.3);
  opacity:0;transform:translateY(10px);animation:evIn 2.6s cubic-bezier(.16,1,.3,1) forwards;
}
.ev i{width:5px;height:5px;border-radius:50%;background:var(--lime-deep);flex-shrink:0}
.ev.dark{background:var(--ink);color:var(--paper);border-color:var(--ink)}
.ev.dark i{background:var(--lime)}
@keyframes evIn{
  0%{opacity:0;transform:translateY(12px) scale(.92)}
  12%{opacity:1;transform:translateY(0) scale(1)}
  72%{opacity:1;transform:translateY(-4px) scale(1)}
  100%{opacity:0;transform:translateY(-16px) scale(.96)}
}

/* сон операторов vs бот */
.who{
  position:absolute;left:0;top:-8px;z-index:8;
  display:flex;gap:0;background:#fff;border:1px solid var(--ink-12);border-radius:100px;
  padding:4px;box-shadow:0 12px 30px -16px rgba(20,20,15,.3);
  opacity:0;animation:cardIn .6s .3s cubic-bezier(.16,1,.3,1) forwards;
}
.who .w{display:flex;align-items:center;gap:7px;padding:6px 13px;border-radius:100px;
  font-size:11px;font-weight:500;letter-spacing:-.01em;white-space:nowrap;color:#14140F}
.who .w .s{font-family:var(--mono);font-size:9px;letter-spacing:.05em}
.who .off{color:rgba(20,20,15,.62)}
.who .off .dt{width:6px;height:6px;border-radius:50%;background:#B9B9AF;display:block}
.who .on{background:#14140F;color:#EDEEF2}
.who .on .dt{width:6px;height:6px;border-radius:50%;background:var(--lime);display:block;
  animation:pulse 1.9s infinite}
.who .on .s{color:var(--lime)}
.who .off .s{color:rgba(20,20,15,.62)}

.c-lead{
  margin-top:7px;background:var(--lime);border-radius:100px;padding:4px 9px;
  transition:opacity .3s,transform .3s;
  font-family:var(--mono);font-size:8.5px;letter-spacing:.07em;text-transform:uppercase;
  display:inline-flex;align-items:center;gap:5px;
}
@keyframes popIn{to{opacity:1;transform:none}}

  .pill-x{}
.pill{
  position:absolute;left:50%;top:calc(50% - 172px);transform:translateX(-50%);z-index:6;
  background:#fff;border:1px solid var(--ink-12);border-radius:12px;padding:9px 15px;
  box-shadow:0 14px 34px -18px rgba(20,20,15,.3);
  opacity:0;animation:cardIn .6s .3s cubic-bezier(.16,1,.3,1) forwards;
}
.pill .t{font-size:11.5px;font-weight:600;display:flex;align-items:center;gap:6px;letter-spacing:-.01em;color:#14140F}
.pill .t i{width:6px;height:6px;border-radius:50%;background:var(--lime-deep);animation:pulse 1.9s infinite}
.pill .s{font-family:var(--mono);font-size:9px;color:rgba(20,20,15,.5);margin-top:2px;letter-spacing:.05em;white-space:nowrap}
.pill.blast{border-color:var(--lime-deep);box-shadow:0 0 0 4px rgba(34,211,238,.35)}
.pill .n{color:var(--lime-deep);font-weight:600}

.op{
  position:absolute;left:50%;top:calc(50% + 174px);transform:translateX(-50%);z-index:6;
  width:200px;background:var(--ink);color:var(--paper);border-radius:13px;padding:14px;text-align:center;
  opacity:0;animation:cardIn .6s 1.1s cubic-bezier(.16,1,.3,1) forwards;
  box-shadow:0 20px 46px -22px rgba(20,20,15,.55);
}
.op .t{font-size:12px;font-weight:600;letter-spacing:-.01em}
.op .s{font-family:var(--mono);font-size:9px;color:rgba(251,250,247,.42);margin-top:3px;letter-spacing:.05em}
.op .faces{display:flex;justify-content:center;margin-top:11px}
.op .faces span{width:26px;height:26px;border-radius:50%;border:2px solid var(--ink);margin-left:-7px;
  display:grid;place-items:center;font-size:10px;font-weight:600;color:#fff}
.op .faces span:first-child{margin-left:0}
.op .faces .plus{background:var(--lime);color:#14140F;font-family:var(--mono);font-size:8.5px}

/* ── полоса метрик под hero ── */
.metrics{border-top:1px solid var(--ink-12);background:var(--paper-2)}
.m-grid{display:grid;grid-template-columns:repeat(4,1fr);border-left:1px solid var(--ink-12)}
.m{padding:34px 28px;border-right:1px solid var(--ink-12);position:relative;overflow:hidden;
  transition:background .3s}
.m:hover{background:#fff}
.metrics .m .ic{width:28px;height:28px;border-radius:8px;background:var(--paper-2);border:1px solid var(--ink-12);
  display:grid;place-items:center;margin-bottom:20px;color:var(--lime-deep)}
html[data-theme="dark"] .metrics .m .ic{background:rgba(34,211,238,.08);border-color:rgba(34,211,238,.2);color:var(--lime)}
.m .v{font-size:clamp(34px,3.6vw,48px);font-weight:500;letter-spacing:-.045em;line-height:1;
  font-variant-numeric:tabular-nums}
.m .v small{font-size:.42em;color:var(--ink-40);font-weight:400;letter-spacing:0;margin-left:4px}
.m .l{font-size:13.5px;color:var(--ink-60);margin-top:10px;line-height:1.4;max-width:20ch}
.m.hi .v{color:var(--lime-deep)}
.m.night{background:var(--ink);border-right-color:var(--ink)}
.m.night:hover{background:var(--ink)}
.m.night .v{color:var(--lime);font-family:var(--mono);font-size:clamp(26px,2.6vw,34px);letter-spacing:.01em}
.m.night .l{color:rgba(251,250,247,.5)}
.m.night .ic{background:transparent;border-color:rgba(251,250,247,.2)}

/* ── marquee ── */
.marq{border-top:1px solid var(--ink-12);border-bottom:1px solid var(--ink-12);padding:19px 0;overflow:hidden;background:var(--paper-2)}
.marq-in{display:flex;gap:56px;width:max-content;animation:slide 34s linear infinite}
.marq-in span{font-family:var(--mono);font-size:12.5px;letter-spacing:.09em;text-transform:uppercase;color:var(--ink-40);white-space:nowrap;display:flex;align-items:center;gap:56px}
.marq-in span::after{content:"◆";color:var(--lime-deep);font-size:8px}
@keyframes slide{to{transform:translateX(-50%)}}

/* ── sections ── */
section{padding:112px 0}
.sec-head{margin-bottom:56px;max-width:660px}
.sec-head .eyebrow{margin-bottom:20px}
.sec-head h2{margin-bottom:18px}

/* ── проблема ── */
.prob{display:grid;grid-template-columns:1fr 1fr;gap:56px;align-items:start}
.night-box{
  background:var(--ink);color:var(--paper);border-radius:18px;padding:28px 26px;
  position:relative;overflow:hidden;
}
.night-box::after{content:"";position:absolute;right:-70px;top:-90px;width:260px;height:260px;
  background:radial-gradient(circle,rgba(34,211,238,.16),transparent 66%);filter:blur(18px)}
.nb-head{display:flex;align-items:center;gap:9px;margin-bottom:22px;
  font-family:var(--mono);font-size:10px;letter-spacing:.13em;text-transform:uppercase;color:rgba(251,250,247,.42)}
.nb-head svg{opacity:.6}
.tl{position:relative;z-index:1}
.tl-row{display:grid;grid-template-columns:52px 1fr auto;gap:14px;align-items:center;
  padding:9px 0;border-bottom:1px solid rgba(251,250,247,.09)}
.tl-row:last-child{border-bottom:0}
.tl-t{font-family:var(--mono);font-size:12px;color:rgba(251,250,247,.5)}
.tl-m{font-size:13.5px;color:rgba(251,250,247,.85);line-height:1.35}
.tl-st{font-family:var(--mono);font-size:9px;letter-spacing:.07em;text-transform:uppercase;
  padding:4px 8px;border-radius:100px;white-space:nowrap;line-height:1}
.tl-st.gone{background:rgba(196,54,43,.16);color:#F08379}
.tl-st.wait{background:rgba(251,250,247,.08);color:rgba(251,250,247,.42)}
.nb-foot{margin-top:22px;padding-top:20px;border-top:1px solid rgba(251,250,247,.12);
  display:flex;align-items:baseline;gap:11px;position:relative;z-index:1}
.nb-foot b{font-size:42px;font-weight:500;letter-spacing:-.045em;color:#F08379;line-height:1}
.nb-foot span{font-size:13.5px;color:rgba(251,250,247,.55);max-width:20ch;line-height:1.4}

/* ── кейс ── */
.case{
  border:1px solid var(--ink-12);border-radius:18px;padding:34px;background:#fff;
  display:grid;grid-template-columns:1.15fr .85fr;gap:44px;align-items:center;
}
.case .quote{font-size:19px;line-height:1.5;letter-spacing:-.015em;margin-bottom:24px}
.author{display:flex;align-items:center;gap:12px}
.author .ph{width:44px;height:44px;border-radius:50%;background:#14140F;color:var(--lime);
  display:grid;place-items:center;font-weight:600;font-size:15px;flex-shrink:0}
.author .nm{font-size:14.5px;font-weight:600;letter-spacing:-.01em}
.author .ro{font-size:12.5px;color:var(--ink-60)}
.case-nums{display:grid;grid-template-columns:1fr;gap:0;border-left:1px solid var(--ink-12);padding-left:36px}
.cn{padding:16px 0;border-bottom:1px solid var(--ink-06)}
.cn:last-child{border-bottom:0}
.cn b{font-size:32px;font-weight:500;letter-spacing:-.04em;line-height:1;display:block}
.cn.up b{color:var(--lime-deep)}
.cn span{font-size:12.5px;color:var(--ink-60);margin-top:5px;display:block;line-height:1.35}
.case-note{font-family:var(--mono);font-size:10px;color:var(--ink-40);letter-spacing:.05em;
  text-align:center;margin-top:20px}

/* ── CASE: вау-анимации ── */
.case{position:relative;overflow:hidden;transform-style:preserve-3d;perspective:1200px}
/* весь блок въезжает с 3D-наклоном */
.case{opacity:0;transform:perspective(1200px) rotateX(8deg) translateY(40px) scale(.97)}
.case.in{animation:caseEnter 1s cubic-bezier(.16,1,.3,1) forwards}
@keyframes caseEnter{to{opacity:1;transform:perspective(1200px) rotateX(0) translateY(0) scale(1)}}
.case-left{position:relative}
/* большая кавычка-декор — вылетает и покачивается */
.case-qmark{position:absolute;top:-64px;left:-6px;font-family:var(--serif,Georgia);font-size:120px;
  line-height:1;color:var(--lime);opacity:0;pointer-events:none;
  font-style:italic;transform:translateY(24px) scale(.5) rotate(-12deg)}
.case.in .case-qmark{animation:caseQ .9s .3s cubic-bezier(.2,1.5,.3,1) forwards}
@keyframes caseQ{60%{opacity:.22;transform:translateY(0) scale(1.08) rotate(3deg)}100%{opacity:.16;transform:none}}
/* СКАНИРУЮЩАЯ лаймовая линия проходит по блоку */
.case::before{content:"";position:absolute;top:0;bottom:0;left:-30%;width:22%;z-index:3;pointer-events:none;
  background:linear-gradient(100deg,transparent,rgba(34,211,238,.16),rgba(34,211,238,.32),rgba(34,211,238,.16),transparent);
  transform:skewX(-14deg);opacity:0}
.case.in::before{animation:caseScan 1.3s .35s cubic-bezier(.5,0,.2,1) forwards}
@keyframes caseScan{0%{left:-30%;opacity:0}12%{opacity:1}88%{opacity:1}100%{left:130%;opacity:0}}
/* лаймовое свечение-ореол в углу */
.case::after{content:"";position:absolute;inset:0;border-radius:18px;pointer-events:none;z-index:0;
  background:radial-gradient(700px 240px at 15% -10%,rgba(34,211,238,.16),transparent 55%);
  opacity:0}
.case.in::after{animation:caseGlow 1.8s .3s ease-out forwards}
@keyframes caseGlow{0%{opacity:0}45%{opacity:1}100%{opacity:.4}}
/* цитата — построчный подъём с blur */
.case .quote{opacity:0;transform:translateY(22px);filter:blur(6px);position:relative;z-index:1}
.case.in .quote{animation:caseRise .8s .45s cubic-bezier(.16,1,.3,1) forwards}
.case .author{opacity:0;transform:translateY(16px);position:relative;z-index:1}
.case.in .author{animation:caseRise .7s .8s cubic-bezier(.16,1,.3,1) forwards}
@keyframes caseRise{to{opacity:1;transform:none;filter:blur(0)}}
/* аватар впрыгивает с оборотом + свечение */
.case .author .ph{transform:scale(0) rotate(-90deg)}
.case.in .author .ph{animation:casePop .8s .85s cubic-bezier(.2,1.6,.35,1) forwards}
@keyframes casePop{to{transform:scale(1) rotate(0);box-shadow:0 0 0 4px rgba(34,211,238,.12)}}
/* метрики — влетают со вспышкой */
.case-nums{position:relative;z-index:1}
.cn{opacity:0;transform:translateX(28px) scale(.9);position:relative;transition:background .25s}
.case.in .cn:nth-child(1){animation:caseMetric .7s .7s cubic-bezier(.2,1.3,.3,1) forwards}
.case.in .cn:nth-child(2){animation:caseMetric .7s .9s cubic-bezier(.2,1.3,.3,1) forwards}
.case.in .cn:nth-child(3){animation:caseMetric .7s 1.1s cubic-bezier(.2,1.3,.3,1) forwards}
@keyframes caseMetric{0%{opacity:0;transform:translateX(28px) scale(.9)}
  60%{opacity:1;transform:translateX(-3px) scale(1.03)}100%{opacity:1;transform:none}}
/* вспышка числа при появлении */
.cn.up b{position:relative}
.case.in .cn:nth-child(1) b{animation:numFlash .6s .95s ease-out}
.case.in .cn:nth-child(3) b{animation:numFlash .6s 1.35s ease-out}
@keyframes numFlash{0%{text-shadow:0 0 0 rgba(34,211,238,0)}40%{text-shadow:0 0 22px rgba(34,211,238,.9)}100%{text-shadow:0 0 0 rgba(34,211,238,0)}}
/* лаймовые числа — постоянное мягкое мерцание после появления */
.cn.up b{color:var(--lime-deep)}
html[data-theme="dark"] .cn.up b{color:var(--lime)}
.cn b{position:relative;display:inline-block}
/* hover-интерактив */
@media(hover:hover){
  .cn{border-radius:10px;margin:0 -12px;padding-left:12px;padding-right:12px}
  .cn:hover{background:rgba(34,211,238,.08)}
  .cn:hover b{filter:brightness(1.15)}
}
@media(prefers-reduced-motion:reduce){
  .case,.case-qmark,.case .quote,.case .author,.case .author .ph,.cn{animation:none!important;opacity:1;transform:none;filter:none}
  .case-qmark{opacity:.16}
  .case::before,.case::after{display:none}
}

@media(max-width:940px){
  .prob{grid-template-columns:1fr;gap:36px}
  .case{grid-template-columns:1fr;gap:28px;padding:26px}
  .case-nums{border-left:0;border-top:1px solid var(--ink-12);padding-left:0;padding-top:8px;
    grid-template-columns:1fr 1fr;gap:0 28px}
  .tl-row{grid-template-columns:48px 1fr;gap:10px}
  .tl-st{grid-column:2;justify-self:start;margin-top:3px}
}

/* bento */
.bento{display:grid;grid-template-columns:repeat(3,1fr);gap:14px}
.cell{
  border:1px solid var(--ink-12);border-radius:var(--r);padding:26px;background:#fff;
  position:relative;overflow:hidden;transition:transform .3s cubic-bezier(.2,.8,.2,1),border-color .3s,box-shadow .3s;
}
.cell:hover{transform:translateY(-4px);border-color:var(--ink-40);box-shadow:0 18px 40px -22px rgba(20,20,15,.3)}
.cell h3{font-size:19px;font-weight:600;letter-spacing:-.02em;margin:16px 0 9px}
.cell p{font-size:14.5px;color:var(--ink-60);line-height:1.6}
.cell .num{font-family:var(--mono);font-size:11px;color:var(--ink-40)}
.cell.big{grid-column:span 2;background:var(--ink);color:var(--paper);border-color:var(--ink)}
.cell.big p{color:rgba(251,250,247,.62)}
.cell.big .num{color:rgba(251,250,247,.4)}
.cell.big:hover{border-color:var(--ink)}
.stat{font-size:clamp(46px,6vw,80px);font-weight:500;letter-spacing:-.045em;line-height:1;color:var(--lime)}
.stat small{font-size:.36em;color:rgba(251,250,247,.5);font-weight:400;margin-left:6px;letter-spacing:0}
.cell.lime{background:var(--lime);border-color:var(--lime)}
.cell.lime:hover{border-color:var(--lime-deep)}
.cell.lime p{color:rgba(20,20,15,.65)}
.ic{width:34px;height:34px;border-radius:9px;display:grid;place-items:center;border:1px solid var(--ink-12);color:var(--ink)}
.cell.big .ic{border-color:rgba(251,250,247,.2)}
.cell.lime .ic{border-color:rgba(20,20,15,.2)}

/* steps — вертикальный timeline с кривой SVG-линией */
.steps{position:relative;padding-top:8px}
.steps-svg{position:absolute;left:0;top:0;width:100%;height:100%;pointer-events:none;z-index:0;overflow:visible}
.steps-track{fill:none;stroke:var(--ink-12);stroke-width:2}
html[data-theme="dark"] .steps-track{stroke:rgba(237,238,242,.18)}
.steps-fill{fill:none;stroke:var(--lime);stroke-width:2.5;stroke-linecap:round;
  transition:stroke-dashoffset .7s cubic-bezier(.16,1,.3,1)}
.step{
  display:grid;grid-template-columns:44px 1fr;gap:28px;
  padding:0 0 44px;position:relative;
}
.step:last-child{padding-bottom:0}
.step-rail{position:relative;width:44px;display:flex;justify-content:center}
/* кружок-номер */
.step-dot{
  width:44px;height:44px;border-radius:50%;display:grid;place-items:center;
  font-family:var(--mono);font-size:15px;font-weight:500;
  background:var(--paper-2);border:2px solid var(--ink-12);color:var(--ink-40);
  position:relative;z-index:2;transition:all .45s cubic-bezier(.2,1.2,.35,1)}
.step.active .step-dot,.step.done .step-dot{
  background:var(--lime);border-color:var(--lime);color:#14140F;
  box-shadow:0 0 0 5px rgba(34,211,238,.14)}
.step.active .step-dot{box-shadow:0 0 0 6px rgba(34,211,238,.2),0 6px 20px -6px rgba(34,211,238,.45)}
/* контент */
.step-body{padding-top:5px;transition:transform .4s cubic-bezier(.16,1,.3,1),opacity .4s}
.step-viz{display:none}   /* показывается только на мобильном */
.step-body .k{font-family:var(--mono);font-size:11.5px;color:var(--ink-40);letter-spacing:.08em;transition:color .4s;margin-bottom:8px}
.step.active .step-body .k,.step.done .step-body .k{color:var(--lime-deep)}
html[data-theme="dark"] .step.active .step-body .k,html[data-theme="dark"] .step.done .step-body .k{color:var(--lime)}
.step-body h3{font-size:clamp(21px,2.3vw,29px);font-weight:500;letter-spacing:-.025em}
.step-body p{font-size:14.5px;color:var(--ink-60);line-height:1.6;max-width:46ch;margin-top:10px}
.step:hover .step-dot{border-color:var(--lime)}
.step.active .step-dot,.step.done .step-dot,
.step.active:hover .step-dot,.step.done:hover .step-dot{color:#14140F}
@media(max-width:640px){
  .step{grid-template-columns:44px 1fr;gap:18px;padding-bottom:34px}
  .step-dot{width:36px;height:36px;font-size:13px}
  .step-rail::before,.step-rail::after{top:36px;bottom:-34px}
}
@media(prefers-reduced-motion:reduce){
  .step-rail::after{transition:none}
  .step-dot,.step-body h3{transition:none}
}

/* how: 2 колонки — timeline + живая иллюстрация */
.how-grid{display:grid;grid-template-columns:1fr 420px;gap:60px;align-items:start}
.how-viz{position:sticky;top:120px;height:420px}
.hv-stage{position:relative;width:100%;height:100%;
  background:var(--paper);border:1px solid var(--ink-12);border-radius:20px;overflow:hidden}
html[data-theme="dark"] .hv-stage{background:#14161f;border-color:rgba(237,238,242,.08)}
.hv-card{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:26px;
  opacity:0;transform:scale(.94);pointer-events:none;transition:opacity .5s cubic-bezier(.16,1,.3,1),transform .5s cubic-bezier(.16,1,.3,1)}
.hv-card.on{opacity:1;transform:none}
.hv-cap{font-family:var(--mono);font-size:11.5px;letter-spacing:.06em;color:var(--ink-40);text-transform:uppercase}
/* 1 — ядро + документы */
.hv-core{width:80px;height:80px;border-radius:50%;background:#0f1015;display:grid;place-items:center;gap:5px;grid-auto-flow:column;
  box-shadow:0 0 0 8px rgba(34,211,238,.1);position:relative}
.hv-core span{width:9px;height:14px;border-radius:5px;background:var(--lime);display:block;animation:hvBlink 2.4s infinite}
.hv-core span:last-child{animation-delay:.3s}
@keyframes hvBlink{0%,100%{opacity:1}50%{opacity:.3}}
.hv-docs{display:flex;gap:12px}
.hv-doc{width:34px;height:44px;border-radius:6px;background:#eef0f4;border:1px solid rgba(20,20,15,.1);position:relative;opacity:0}
html[data-theme="dark"] .hv-doc{background:#eef0f4;border-color:transparent}
.hv-doc::before,.hv-doc::after{content:"";position:absolute;left:6px;right:6px;height:2px;background:rgba(20,20,15,.22);border-radius:2px;top:12px}
.hv-doc::after{top:20px;right:14px}
.hv-card.on .hv-doc{animation:hvDocIn .5s cubic-bezier(.2,1.2,.35,1) forwards}
.hv-card.on .hv-doc.d2{animation-delay:.12s}
.hv-card.on .hv-doc.d3{animation-delay:.24s}
@keyframes hvDocIn{0%{opacity:0;transform:translateY(14px)}100%{opacity:1;transform:none}}
/* 2 — чат */
.hv-chat{display:flex;flex-direction:column;gap:12px;width:260px}
.hv-b{padding:11px 15px;border-radius:14px;font-size:14px;max-width:88%;opacity:0;line-height:1.35}
.hv-b.in{align-self:flex-start;background:#eef0f4;color:#14140F;border-bottom-left-radius:4px}
.hv-b.ai{align-self:flex-end;background:var(--lime);color:#14140F;border-bottom-right-radius:4px;font-weight:500}
.hv-b.out{align-self:flex-end;background:#2a2e3a;border-bottom-right-radius:4px;display:inline-flex;gap:4px;padding:13px 16px}
.hv-b.out i{width:6px;height:6px;border-radius:50%;background:rgba(237,238,242,.8);animation:hvBounce 1.1s infinite}
.hv-b.out i:nth-child(2){animation-delay:.15s}.hv-b.out i:nth-child(3){animation-delay:.3s}
@keyframes hvBounce{0%,60%,100%{transform:translateY(0);opacity:.5}30%{transform:translateY(-4px);opacity:1}}
.hv-card.on .hv-b.in{animation:hvMsg .4s .1s forwards}
.hv-card.on .hv-b.out{animation:hvMsg .4s .7s forwards}
.hv-card.on .hv-b.ai{animation:hvMsg .4s 1.6s forwards}
@keyframes hvMsg{0%{opacity:0;transform:translateY(8px)}100%{opacity:1;transform:none}}
/* 3 — лид */
.hv-lead{width:250px;background:#fff;border:1px solid rgba(20,20,15,.1);border-radius:14px;padding:22px;display:flex;flex-direction:column;gap:16px;position:relative;box-shadow:0 20px 50px -30px rgba(0,0,0,.5)}
html[data-theme="dark"] .hv-lead{background:#fff;border-color:transparent}
.hv-lrow{display:flex;align-items:center;gap:12px}
.hv-lk{font-family:var(--mono);font-size:11px;color:rgba(20,20,15,.5);width:34px}
.hv-lv{height:11px;border-radius:5px;background:rgba(20,20,15,.1);flex:1;transform-origin:left;transform:scaleX(0)}
.hv-card.on .hv-l1{animation:hvFill .5s .3s cubic-bezier(.16,1,.3,1) forwards}
.hv-card.on .hv-l2{animation:hvFill .5s .6s cubic-bezier(.16,1,.3,1) forwards}
@keyframes hvFill{to{transform:scaleX(1);background:var(--lime)}}
.hv-lbadge{align-self:flex-start;font-family:var(--mono);font-size:11px;font-weight:600;color:#14140F;background:var(--lime);padding:5px 11px;border-radius:100px;opacity:0}
.hv-card.on .hv-lbadge{animation:hvMsg .4s 1s forwards}
/* 4 — звонок */
.hv-call{position:relative;width:120px;height:120px;display:grid;place-items:center}
.hv-phone{width:64px;height:64px;border-radius:50%;background:var(--lime);display:grid;place-items:center;z-index:2;animation:hvShake 1.4s ease-in-out infinite}
@keyframes hvShake{0%,100%{transform:rotate(0)}20%{transform:rotate(-12deg)}40%{transform:rotate(12deg)}60%{transform:rotate(-8deg)}80%{transform:rotate(8deg)}}
.hv-ring{position:absolute;inset:0;border-radius:50%;border:2px solid var(--lime);opacity:0;animation:hvPulse 2s ease-out infinite}
.hv-ring.r2{animation-delay:1s}
@keyframes hvPulse{0%{transform:scale(.6);opacity:.7}100%{transform:scale(1.4);opacity:0}}
@media(max-width:940px){
  .how-grid{grid-template-columns:1fr;gap:36px}
  .how-viz{position:static;height:220px;max-width:380px;margin:0 auto}
}
@media(prefers-reduced-motion:reduce){
  .hv-doc,.hv-b,.hv-lbadge{opacity:1!important;animation:none!important}
  .hv-lv{transform:scaleX(1)!important}
  .hv-phone,.hv-ring,.hv-core span{animation:none!important}
}

/* ── explain-animations ── */
/* how: авто-подсветка активного шага (как hover) */
.step.active{padding-left:22px}
.step.active::before{width:100%}
.step.active .k{color:#14140F}
.step .k{transition:color .35s}
/* problem: построчное появление таймлайна */
#probTimeline .tl-row{opacity:0;transform:translateX(-10px);transition:opacity .5s cubic-bezier(.16,1,.3,1),transform .5s cubic-bezier(.16,1,.3,1)}
#probTimeline.play .tl-row{opacity:1;transform:none}
#probTimeline .tl-st{transition:transform .3s,background .3s,color .3s}
#probTimeline .tl-row.flash .tl-st{animation:stFlash .6s ease-out}
@keyframes stFlash{0%{transform:scale(1)}30%{transform:scale(1.18)}100%{transform:scale(1)}}
/* why: пульс иконок при появлении */
.cell.rv .ic{transition:transform .4s cubic-bezier(.2,1.4,.4,1)}
.cell.rv.in .ic{animation:icPop .55s cubic-bezier(.2,1.4,.4,1)}
@keyframes icPop{0%{transform:scale(.4);opacity:0}60%{transform:scale(1.12)}100%{transform:scale(1);opacity:1}}
@media(prefers-reduced-motion:reduce){
  #probTimeline .tl-row{opacity:1;transform:none}
  .cell.rv.in .ic{animation:none}
}

/* ── live demo ── */
.demo-wrap{display:grid;grid-template-columns:1fr 1fr;gap:40px;align-items:center}
.demo-copy .eyebrow{margin-bottom:18px}
.demo-copy h2{font-size:clamp(28px,3.4vw,44px);font-weight:500;letter-spacing:-.03em;line-height:1.08;margin-bottom:18px}
.demo-copy .lead{margin-bottom:26px}
.demo-qs{display:flex;flex-wrap:wrap;gap:10px}
.demo-q{font-size:14px;padding:10px 16px;border-radius:100px;border:1px solid var(--ink-12);
  background:var(--paper-2);cursor:pointer;transition:transform .2s,border-color .2s,background .2s;color:var(--ink)}
.demo-q:hover{transform:translateY(-2px);border-color:var(--lime-deep);background:var(--lime);color:#14140F}
.demo-q.used{opacity:.4;pointer-events:none}
.demo-phone{background:#14161f;border-radius:24px;padding:20px;min-height:440px;
  box-shadow:0 40px 90px -50px rgba(0,0,0,.6);border:1px solid rgba(237,238,242,.1);display:flex;flex-direction:column}
html[data-theme="light"] .demo-phone{background:#14161f}
.demo-top{display:flex;align-items:center;gap:10px;padding-bottom:14px;border-bottom:1px solid rgba(237,238,242,.1);margin-bottom:14px}
.demo-top .av{width:34px;height:34px;border-radius:50%;background:#0f1015;display:grid;place-items:center}
.demo-top .av i{width:5px;height:8px;border-radius:3px;background:var(--lime);display:inline-block;margin:0 1px}
.demo-top .nm{font-size:14px;font-weight:600;color:#EDEEF2}
.demo-top .st{font-family:var(--mono);font-size:9.5px;color:var(--lime);letter-spacing:.06em}
.demo-feed{flex:1;display:flex;flex-direction:column;gap:10px;overflow:hidden}
.dmsg{max-width:82%;padding:10px 14px;border-radius:14px;font-size:14px;line-height:1.4;opacity:0;transform:translateY(8px);animation:dIn .4s cubic-bezier(.16,1,.3,1) forwards}
.dmsg.me{align-self:flex-end;background:var(--lime);color:#14140F;border-bottom-right-radius:5px}
.dmsg.ai{align-self:flex-start;background:#1c1f2a;color:#EDEEF2;border-bottom-left-radius:5px}
.dmsg.lead{align-self:stretch;max-width:100%;background:rgba(34,211,238,.12);border:1px solid rgba(34,211,238,.3);color:#EDEEF2;text-align:center;font-size:13px}
@keyframes dIn{to{opacity:1;transform:none}}
.dtyping{align-self:flex-start;background:#1c1f2a;padding:12px 16px;border-radius:14px;border-bottom-left-radius:5px;display:inline-flex;gap:4px}
.dtyping i{width:6px;height:6px;border-radius:50%;background:rgba(237,238,242,.5);animation:dBounce 1.2s infinite}
.dtyping i:nth-child(2){animation-delay:.2s}.dtyping i:nth-child(3){animation-delay:.4s}
@keyframes dBounce{0%,60%,100%{transform:translateY(0);opacity:.4}30%{transform:translateY(-5px);opacity:1}}
@media(max-width:940px){.demo-wrap{grid-template-columns:1fr;gap:28px}}
@media(prefers-reduced-motion:reduce){.dmsg{animation:none;opacity:1;transform:none}}

/* pricing */
.plans{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;align-items:start}
.plan{border:1px solid var(--ink-12);border-radius:var(--r);padding:30px;background:#fff;transition:transform .3s,box-shadow .3s}
.plan:hover{transform:translateY(-3px);box-shadow:0 20px 44px -26px rgba(20,20,15,.32)}
.plan.hot{background:var(--ink);color:var(--paper);border-color:var(--ink);padding:38px 30px;position:relative}
.plan .tag{font-family:var(--mono);font-size:10.5px;letter-spacing:.14em;text-transform:uppercase;
  color:#14140F;background:var(--lime);padding:5px 11px;border-radius:100px;position:absolute;top:-11px;left:30px}
.plan h3{font-size:20px;font-weight:600;letter-spacing:-.02em}
.plan .sub{font-size:13.5px;color:var(--ink-60);margin-top:5px;min-height:38px}
.plan.hot .sub{color:rgba(251,250,247,.55)}
.price{font-size:36px;font-weight:500;letter-spacing:-.04em;margin:22px 0 3px;line-height:1}
.plan.hot .price{color:var(--lime)}
.price .cur{font-size:15px;color:var(--ink-40);font-weight:400;letter-spacing:0;margin-left:5px}
.plan.hot .price .cur{color:rgba(251,250,247,.45)}
.approx{font-family:var(--mono);font-size:10.5px;color:var(--ink-40);letter-spacing:.05em}
.plan.hot .approx{color:rgba(251,250,247,.4)}
ul{list-style:none;margin:24px 0}
li{display:flex;gap:11px;padding:9px 0;font-size:14px;border-top:1px solid var(--ink-06);align-items:flex-start}
.plan.hot li{border-color:rgba(251,250,247,.12);color:rgba(251,250,247,.85)}
li svg{flex-shrink:0;margin-top:4px}
.plan .btn{width:100%;justify-content:center}

/* cta */
.cta-band{background:var(--ink);color:var(--paper);border-radius:28px;padding:60px 56px;position:relative;overflow:hidden;
  display:grid;grid-template-columns:1fr .95fr;align-items:center;gap:56px}
.cta-band::after{content:"";position:absolute;right:-120px;bottom:-160px;width:460px;height:460px;
  background:radial-gradient(circle,rgba(34,211,238,.24),transparent 65%);filter:blur(24px)}
.cta-copy{position:relative;z-index:1}
.cta-band h2{max-width:16ch;position:relative;z-index:1;font-size:clamp(30px,3.4vw,46px)}
.cta-band .btn{position:relative;z-index:1}
.cta-btn{margin-top:26px}
.cta-note{font-family:var(--mono);font-size:11.5px;color:rgba(251,250,247,.4);margin-top:14px}
/* индикатор день/ночь */
.cta-daynight{display:inline-flex;align-items:center;gap:8px;margin-bottom:22px;
  padding:7px 12px;border-radius:100px;background:rgba(251,250,247,.06);border:1px solid rgba(251,250,247,.1)}
.dn-ico{display:grid;place-items:center;transition:color .6s,opacity .6s}
.dn-sun{color:#ffd166}.dn-moon{color:#9db4ff}
.cta-band.night-on .dn-sun{opacity:.3}.cta-band:not(.night-on) .dn-moon{opacity:.3}
.dn-track{position:relative;width:34px;height:5px;border-radius:5px;background:rgba(251,250,247,.15)}
.dn-dot{position:absolute;top:50%;left:2px;width:9px;height:9px;border-radius:50%;background:var(--lime);
  transform:translateY(-50%);transition:left .8s cubic-bezier(.5,0,.2,1)}
.cta-band.night-on .dn-dot{left:23px}
.dn-label{font-family:var(--mono);font-size:10px;letter-spacing:.1em;text-transform:uppercase;color:rgba(251,250,247,.6)}

/* сравнение оператор vs Techna */
.cta-compare{position:relative;z-index:1;display:grid;grid-template-columns:1fr 1fr;gap:14px}
.cmp-col{background:rgba(251,250,247,.04);border:1px solid rgba(251,250,247,.1);border-radius:18px;
  padding:16px;min-height:200px;position:relative;overflow:hidden;transition:opacity .6s,filter .6s}
.cmp-tk{border-color:rgba(34,211,238,.3);background:rgba(34,211,238,.05)}
/* оператор ночью — гаснет */
.cta-band.night-on .cmp-op{opacity:.55;filter:saturate(.5)}
.cmp-head{display:flex;align-items:center;gap:9px;margin-bottom:14px;position:relative}
.cmp-ava{width:30px;height:30px;border-radius:50%;display:grid;place-items:center;flex-shrink:0}
.cmp-ava.op{background:rgba(251,250,247,.06);color:rgba(251,250,247,.45)}
.cmp-ava.tk{background:#0f1015;display:flex;align-items:center;justify-content:center;gap:3px}
.cmp-ava.tk i{width:4px;height:7px;border-radius:3px;background:var(--lime);display:block}
.cta-band.night-on .cmp-ava.tk i{animation:cmpBlink 2.6s infinite}
@keyframes cmpBlink{0%,44%,50%,100%{transform:scaleY(1)}47%{transform:scaleY(.2)}}
.cmp-name{font-size:13px;font-weight:600}
.cmp-st{font-size:10.5px;font-family:var(--mono);color:rgba(251,250,247,.45)}
.cmp-st.on{color:var(--lime)}
.cmp-zzz{position:absolute;right:2px;top:-2px;font-size:13px;font-weight:700;color:#9db4ff;opacity:0}
.cta-band.night-on .cmp-op .cmp-zzz{animation:cmpZzz 2.4s ease-out infinite}
@keyframes cmpZzz{0%{opacity:0;transform:translateY(4px) scale(.8)}30%{opacity:.9}100%{opacity:0;transform:translateY(-14px) scale(1.2)}}
.cmp-feed{display:flex;flex-direction:column;gap:7px}
.cmp-msg{font-size:11.5px;line-height:1.3;padding:7px 10px;border-radius:9px;max-width:92%;
  opacity:0;transform:translateY(6px);animation:cmpMsgIn .35s forwards}
@keyframes cmpMsgIn{to{opacity:1;transform:none}}
.cmp-msg.in{align-self:flex-start;background:rgba(251,250,247,.1)}
.cmp-msg.reply{align-self:flex-end;background:var(--lime);color:#14140F;font-weight:500}
.cmp-msg.reply.op-reply{background:rgba(251,250,247,.85);color:#14140F}
.cmp-msg.pending{align-self:flex-start;background:rgba(251,250,247,.06);color:rgba(251,250,247,.4);
  border:1px dashed rgba(251,250,247,.2)}
.cmp-badge{position:absolute;bottom:12px;left:16px;right:16px;text-align:center;
  font-family:var(--mono);font-size:10px;letter-spacing:.06em;padding:6px;border-radius:8px;
  opacity:1;transition:opacity .4s,background .4s,color .4s}
.cmp-badge.op{background:rgba(251,250,247,.08);color:rgba(251,250,247,.5)}
.cmp-badge.op.alert{background:rgba(229,72,77,.18);color:#ff9ea1}
.cmp-badge.tk{background:rgba(34,211,238,.16);color:var(--lime)}
.cmp-badge.tk{opacity:1}
@media(max-width:940px){
  .cta-band{grid-template-columns:1fr;padding:40px 26px;gap:36px}
  .cta-band h2{max-width:none}
}
@media(prefers-reduced-motion:reduce){
  .cmp-ava.tk i,.cmp-zzz,.cmp-msg{animation:none!important;opacity:1;transform:none}
}

/* footer */
footer{border-top:1px solid var(--ink-12);padding:56px 0 34px;margin-top:112px}
.f-grid{display:grid;grid-template-columns:2fr 1fr 1fr;gap:40px}
.f-grid p{font-size:14px;color:var(--ink-60);max-width:32ch;margin-top:14px}
.f-col h4{font-family:var(--mono);font-size:10.5px;letter-spacing:.14em;text-transform:uppercase;color:var(--ink-40);margin-bottom:16px;font-weight:400}
.f-col a{display:block;font-size:14.5px;padding:5px 0;color:var(--ink-60);transition:color .2s,padding-left .2s}
.f-col a:hover{color:var(--ink);padding-left:5px}
.f-bot{display:flex;justify-content:space-between;margin-top:56px;padding-top:26px;border-top:1px solid var(--ink-06);
  font-family:var(--mono);font-size:11px;color:var(--ink-40);flex-wrap:wrap;gap:10px}

/* ── модал формы ── */
.mask{
  position:fixed;inset:0;z-index:200;background:rgba(20,20,15,.55);
  backdrop-filter:blur(6px);display:grid;place-items:center;padding:20px;overflow-y:auto;
  opacity:0;pointer-events:none;transition:opacity .28s;
}
.mask.on{opacity:1;pointer-events:auto}
.modal{
  width:100%;max-width:432px;background:var(--paper);border-radius:20px;
  padding:32px;position:relative;
  box-shadow:0 40px 90px -30px rgba(20,20,15,.6);
  transform:translateY(18px) scale(.97);transition:transform .34s cubic-bezier(.16,1,.3,1);
}
.mask.on .modal{transform:none}
.modal h3{font-size:26px;font-weight:500;letter-spacing:-.03em;line-height:1.1;margin-bottom:8px}
.modal .sub{font-size:14px;color:var(--ink-60);margin-bottom:24px}
.x{
  position:absolute;top:18px;right:18px;width:30px;height:30px;border-radius:50%;
  border:1px solid var(--ink-12);background:transparent;cursor:pointer;
  display:grid;place-items:center;color:var(--ink-40);transition:background .2s,color .2s;
}
.x:hover{background:var(--ink-06);color:var(--ink)}
.f-row{margin-bottom:14px}
.f-row label{display:block;font-family:var(--mono);font-size:10px;letter-spacing:.11em;
  text-transform:uppercase;color:var(--ink-40);margin-bottom:7px}
.f-row input,.f-row select{
  width:100%;padding:13px 14px;border:1px solid var(--ink-12);border-radius:11px;
  background:#fff;font-family:var(--sans);font-size:15px;color:var(--ink);
  transition:border-color .2s,box-shadow .2s;box-sizing:border-box;
}
.f-row input:focus,.f-row select:focus{
  outline:none;border-color:var(--ink);box-shadow:0 0 0 3px rgba(34,211,238,.35);
}
.f-row input.bad{border-color:#C4362B;box-shadow:0 0 0 3px rgba(196,54,43,.14)}
.f-err{font-size:12px;color:#C4362B;margin-top:6px;display:none}
.f-err.on{display:block}
.modal .btn{width:100%;justify-content:center;margin-top:6px}
.or{display:flex;align-items:center;gap:12px;margin:20px 0 16px;
  font-family:var(--mono);font-size:10px;letter-spacing:.11em;text-transform:uppercase;color:var(--ink-40)}
.or::before,.or::after{content:"";flex:1;height:1px;background:var(--ink-12)}
.tg-btn{
  display:flex;align-items:center;justify-content:center;gap:9px;width:100%;
  padding:13px;border:1px solid var(--ink-12);border-radius:100px;
  font-size:14.5px;font-weight:500;transition:background .2s,border-color .2s;
}
.tg-btn:hover{background:var(--ink-06);border-color:var(--ink-40)}
.note{font-family:var(--mono);font-size:10px;color:var(--ink-40);text-align:center;margin-top:16px;letter-spacing:.04em}

/* ── форма: усиленные анимации ── */
/* поля появляются по очереди при открытии */
.mask.on #mForm .f-row,.mask.on #mForm .or,.mask.on #mForm .tg-btn,.mask.on #mForm .note,.mask.on #mForm .btn{
  animation:fRise .5s cubic-bezier(.16,1,.3,1) backwards}
.mask.on #mForm .sub{animation:fRise .5s .04s cubic-bezier(.16,1,.3,1) backwards}
.mask.on #mForm .f-row:nth-of-type(1){animation-delay:.08s}
.mask.on #mForm .f-row:nth-of-type(2){animation-delay:.14s}
.mask.on #mForm .f-row:nth-of-type(3){animation-delay:.20s}
.mask.on #mForm .btn{animation-delay:.26s}
.mask.on #mForm .or{animation-delay:.30s}
.mask.on #mForm .tg-btn{animation-delay:.34s}
.mask.on #mForm .note{animation-delay:.38s}
@keyframes fRise{from{opacity:0;transform:translateY(12px)}to{opacity:1;transform:none}}
/* label подсвечивается при фокусе поля */
.f-row{position:relative}
.f-row:focus-within label{color:var(--lime-deep)}
html[data-theme="dark"] .f-row:focus-within label{color:var(--lime)}
.f-row input,.f-row select{transition:border-color .2s,box-shadow .2s,transform .2s}
.f-row input:focus{transform:translateY(-1px)}
/* трясётся при ошибке */
.f-row input.bad{animation:fShake .4s cubic-bezier(.36,.07,.19,.97)}
@keyframes fShake{10%,90%{transform:translateX(-2px)}20%,80%{transform:translateX(3px)}30%,50%,70%{transform:translateX(-5px)}40%,60%{transform:translateX(5px)}}
/* кнопка: стрелка едет вправо, лёгкий подъём */
.modal .btn-dark .arw{transition:transform .25s cubic-bezier(.16,1,.3,1)}
.modal .btn-dark:hover{transform:translateY(-2px)}
.modal .btn-dark:hover .arw{transform:translateX(4px)}
.modal .btn-dark:active{transform:translateY(0)}
/* success: галочка рисуется */
.ok-state .ico svg path{stroke-dasharray:24;stroke-dashoffset:24;animation:okDraw .5s .15s cubic-bezier(.16,1,.3,1) forwards}
@keyframes okDraw{to{stroke-dashoffset:0}}
.ok-state .ico{animation:okPop .5s cubic-bezier(.2,1.3,.4,1)}
@keyframes okPop{0%{transform:scale(0)}70%{transform:scale(1.1)}100%{transform:scale(1)}}
@media(prefers-reduced-motion:reduce){
  .mask.on #mForm *{animation:none!important}
  .f-row input.bad{animation:none}
  .ok-state .ico,.ok-state .ico svg path{animation:none;stroke-dashoffset:0}
}
.ok-state{text-align:center;padding:16px 0}
.ok-state .ico{width:56px;height:56px;border-radius:50%;background:var(--lime);
  display:grid;place-items:center;margin:0 auto 20px;
  animation:popIn .5s cubic-bezier(.34,1.56,.64,1)}
.ok-state h3{margin-bottom:10px}


/* ── пакетные тарифы ── */
.pk-head{display:flex;flex-wrap:wrap;gap:10px;margin-bottom:8px}
.pk-tag{font-family:var(--mono);font-size:10px;letter-spacing:.06em;text-transform:uppercase;
  color:var(--ink-60);background:var(--paper-2);border:1px solid var(--ink-12);
  border-radius:100px;padding:6px 12px;display:inline-flex;align-items:center;gap:7px}
.pk-tag b{color:var(--ink);font-weight:600}
.pks{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-top:32px;align-items:stretch}
.pk{border:1px solid var(--ink-12);border-radius:16px;padding:26px;background:#fff;
  display:flex;flex-direction:column;position:relative;
  transition:transform .3s cubic-bezier(.2,.8,.2,1),box-shadow .3s,border-color .3s}
.pk:hover{transform:translateY(-4px);box-shadow:0 22px 48px -26px rgba(20,20,15,.32);border-color:var(--ink-40)}
.pk.hot{background:var(--ink);color:var(--paper);border-color:var(--ink)}
.pk.hot:hover{border-color:var(--ink)}
.pk .lbl{font-size:19px;font-weight:600;letter-spacing:-.02em;display:flex;align-items:center;gap:10px}
.pk .pop{font-family:var(--mono);font-size:9.5px;letter-spacing:.11em;text-transform:uppercase;
  background:var(--lime);color:#14140F;border-radius:100px;padding:4px 10px;font-weight:600}
.pk .msgs{font-family:var(--mono);font-size:12.5px;color:var(--ink-60);margin-top:6px}
.pk.hot .msgs{color:rgba(251,250,247,.55)}
.pk .price{font-size:30px;font-weight:500;letter-spacing:-.04em;margin:22px 0 2px;line-height:1}
.pk.hot .price{color:var(--lime)}
.pk .price small{font-size:.44em;color:var(--ink-40);font-weight:400;letter-spacing:0}
.pk.hot .price small{color:rgba(251,250,247,.45)}
.pk .per{display:inline-flex;align-items:baseline;gap:6px;margin-top:12px;padding:7px 12px;
  border-radius:100px;background:var(--paper-2);width:fit-content}
.pk.hot .per{background:rgba(251,250,247,.09)}
.pk .per b{font-size:16px;font-weight:600;letter-spacing:-.02em}
.pk.hot .per b{color:var(--lime)}
.pk .per span{font-size:11px;color:var(--ink-40);font-family:var(--mono)}
.pk.hot .per span{color:rgba(251,250,247,.42)}
.pk .save{font-family:var(--mono);font-size:10px;color:var(--lime-deep);margin-top:10px;letter-spacing:.03em}
.pk.hot .save{color:var(--lime)}
.pk .btn{width:100%;justify-content:center;margin-top:auto;margin-top:24px}

/* ── тарифы: визуал + анимация ── */
.pks{perspective:1200px}
/* popular-карточка слегка приподнята и выделена */
.pk.hot{transform:translateY(-10px);box-shadow:0 30px 70px -30px rgba(34,211,238,.35);z-index:1}
.pk.hot:hover{transform:translateY(-14px)}
/* каскадное появление */
.pk{opacity:0;transform:translateY(28px) scale(.96)}
.pk.seen{animation:pkIn .7s cubic-bezier(.16,1,.3,1) forwards}
.pk:nth-child(1).seen{animation-delay:.05s}
.pk:nth-child(2).seen{animation-delay:.18s}
.pk:nth-child(3).seen{animation-delay:.31s}
@keyframes pkIn{to{opacity:1;transform:translateY(0) scale(1)}}
.pk.hot.seen{animation:pkInHot .7s .18s cubic-bezier(.16,1,.3,1) forwards}
@keyframes pkInHot{to{opacity:1;transform:translateY(-10px) scale(1)}}
/* бейдж популярного мягко пульсирует */
.pk .pop{animation:pkPop 2.4s ease-in-out infinite}
@keyframes pkPop{0%,100%{box-shadow:0 0 0 0 rgba(8,145,178,0)}50%{box-shadow:0 0 0 4px rgba(8,145,178,.18)}}
/* усиленный hover */
.pk:hover{border-color:var(--lime-deep)}
.pk.hot:hover{box-shadow:0 34px 76px -28px rgba(34,211,238,.5)}
/* save как читаемый бейдж со скидкой */
.pk .save{display:inline-block;margin-top:14px;padding:5px 10px;border-radius:100px;
  background:rgba(34,211,238,.12);color:var(--lime-deep);font-weight:500;letter-spacing:.02em;width:fit-content}
.pk.hot .save{background:rgba(20,20,15,.08)}
html[data-theme="dark"] .pk.hot .save{background:rgba(20,20,15,.1)}
/* цена крупнее и контрастнее */
.pk .price{font-size:clamp(28px,2.6vw,34px)}
.pk .per{transition:transform .25s}
.pk:hover .per{transform:scale(1.04)}
.pk .btn{transition:transform .2s}
.pk .btn .arw,.pk .btn svg{transition:transform .22s}
.pk:hover .btn svg{transform:translateX(3px)}
@media(prefers-reduced-motion:reduce){
  .pk{animation:none!important;opacity:1;transform:none}
  .pk.hot{transform:translateY(-10px)}
  .pk .pop{animation:none}
}

/* динамика цены за сообщение */
.dyn{margin-top:44px;border:1px solid var(--ink-12);border-radius:16px;padding:28px 30px;background:var(--paper-2)}
.dyn-h{font-size:15px;font-weight:600;letter-spacing:-.01em;margin-bottom:4px}
.dyn-s{font-size:13px;color:var(--ink-60);margin-bottom:24px}
.bars{display:flex;align-items:flex-end;gap:26px;height:150px}
.bar-col{flex:1;display:flex;flex-direction:column;align-items:center;gap:10px;height:100%;justify-content:flex-end}
.bar{width:100%;max-width:82px;border-radius:9px 9px 0 0;background:var(--ink);position:relative;
  display:flex;align-items:flex-start;justify-content:center;transition:height .6s cubic-bezier(.2,.8,.2,1)}
.bar.mid{background:#3a3d34}
.bar.low{background:var(--lime);}
.bar .val{position:absolute;top:-24px;font-family:var(--mono);font-size:13px;font-weight:600;white-space:nowrap}
.bar .val.val-best{color:var(--lime-deep)}
html[data-theme="dark"] .bar .val.val-best{color:var(--lime)}
.bar-lbl{font-size:12.5px;font-weight:500}
.bar-sub{font-family:var(--mono);font-size:10px;color:var(--ink-40);margin-top:-4px}

/* калькулятор */
.calc{margin-top:14px;border:1px solid var(--ink-12);border-radius:16px;padding:30px;background:#fff}
.calc-top{display:flex;align-items:baseline;justify-content:space-between;flex-wrap:wrap;gap:8px;margin-bottom:6px}
.calc-h{font-size:17px;font-weight:600;letter-spacing:-.02em}
.calc-hint{font-family:var(--mono);font-size:11px;color:var(--ink-40)}
.calc-grid{display:grid;grid-template-columns:1.4fr 1fr;gap:36px;align-items:center;margin-top:22px}
.slider-wrap label{display:flex;justify-content:space-between;align-items:baseline;margin-bottom:14px}
.slider-wrap .k{font-size:13.5px;color:var(--ink-60)}
.slider-wrap .n{font-family:var(--mono);font-size:22px;font-weight:600;letter-spacing:-.02em}
input[type=range]{-webkit-appearance:none;appearance:none;width:100%;height:6px;border-radius:100px;
  background:var(--paper-2);outline:none;cursor:pointer}
input[type=range]::-webkit-slider-thumb{-webkit-appearance:none;width:24px;height:24px;border-radius:50%;
  background:var(--ink);border:3px solid #fff;box-shadow:0 2px 8px rgba(20,20,15,.3);cursor:pointer;transition:transform .15s}
input[type=range]::-webkit-slider-thumb:hover{transform:scale(1.12)}
input[type=range]::-moz-range-thumb{width:24px;height:24px;border-radius:50%;background:var(--ink);
  border:3px solid #fff;box-shadow:0 2px 8px rgba(20,20,15,.3);cursor:pointer}
.ticks{display:flex;justify-content:space-between;margin-top:10px;font-family:var(--mono);font-size:10px;color:var(--ink-40)}
.calc-out{background:var(--ink);color:var(--paper);border-radius:14px;padding:24px}
.calc-out .plan-row{display:flex;align-items:center;gap:8px;font-family:var(--mono);font-size:10px;
  letter-spacing:.1em;text-transform:uppercase;color:rgba(251,250,247,.5);margin-bottom:14px}
.calc-out .plan-row .dt{width:6px;height:6px;border-radius:50%;background:var(--lime)}
.calc-out .big{font-size:34px;font-weight:500;letter-spacing:-.04em;line-height:1;color:var(--lime)}
.calc-out .big small{font-size:.4em;color:rgba(251,250,247,.5);font-weight:400;letter-spacing:0}
.calc-out .sub2{font-size:12.5px;color:rgba(251,250,247,.55);margin-top:10px;line-height:1.5}
.calc-out .rec{margin-top:16px;padding-top:16px;border-top:1px solid rgba(251,250,247,.14);
  font-size:12px;color:rgba(251,250,247,.7)}
.calc-out .rec b{color:var(--lime)}
/* шкала пакетов под слайдером */
.pkscale{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-top:26px}
.pks-item{padding:12px 14px;border-radius:12px;border:1px solid var(--ink-12);background:var(--paper-2);
  display:flex;flex-direction:column;gap:3px;transition:all .3s cubic-bezier(.2,.8,.2,1);position:relative;overflow:hidden}
.pks-item .pks-nm{font-size:13px;font-weight:600;letter-spacing:-.01em}
.pks-item .pks-rg{font-family:var(--mono);font-size:10.5px;color:var(--ink-40)}
.pks-item.active{border-color:var(--lime-deep);background:rgba(34,211,238,.1);transform:translateY(-2px);
  box-shadow:0 10px 24px -14px rgba(8,145,178,.5)}
.pks-item.active .pks-nm{color:var(--lime-deep)}
html[data-theme="dark"] .pks-item.active{background:rgba(34,211,238,.12)}
html[data-theme="dark"] .pks-item.active .pks-nm{color:var(--lime)}
.pks-item.active::after{content:"";position:absolute;top:8px;right:8px;width:6px;height:6px;border-radius:50%;
  background:var(--lime);box-shadow:0 0 0 3px rgba(34,211,238,.2)}
/* кнопка Telegram в результате */
.calc-tg{width:100%;justify-content:center;margin-top:18px;gap:9px;font-size:14px}
.calc-tg svg{flex-shrink:0}
/* появление калькулятора */
.calc.seen .pks-item{opacity:0;transform:translateY(12px);animation:pkScaleIn .5s forwards}
.calc.seen .pks-item:nth-child(1){animation-delay:.1s}
.calc.seen .pks-item:nth-child(2){animation-delay:.2s}
.calc.seen .pks-item:nth-child(3){animation-delay:.3s}
@keyframes pkScaleIn{to{opacity:1;transform:none}}
/* число обновляется с лёгким акцентом */
.slider-wrap .n{transition:color .2s}
.slider-wrap .n.bump{animation:nBump .3s ease}
@keyframes nBump{0%{transform:scale(1)}40%{transform:scale(1.12);color:var(--lime-deep)}100%{transform:scale(1)}}
@media(prefers-reduced-motion:reduce){
  .calc.seen .pks-item{animation:none;opacity:1;transform:none}
  .slider-wrap .n.bump{animation:none}
}
.calc-note{font-family:var(--mono);font-size:10px;color:var(--ink-40);text-align:center;margin-top:18px;letter-spacing:.04em}

@media(max-width:940px){
  .pks{grid-template-columns:1fr}
  .bars{gap:14px;height:130px}
  .calc-grid{grid-template-columns:1fr;gap:26px}
  .dyn,.calc{padding:22px}
}

/* reveal */
.rv{opacity:0;transform:translateY(22px);transition:opacity .7s cubic-bezier(.16,1,.3,1),transform .7s cubic-bezier(.16,1,.3,1)}
.rv.in{opacity:1;transform:none}

/* ── scroll-reveal варианты ── */
.rv-left{opacity:0;transform:translateX(-46px);transition:opacity .8s cubic-bezier(.16,1,.3,1),transform .8s cubic-bezier(.16,1,.3,1)}
.rv-right{opacity:0;transform:translateX(46px);transition:opacity .8s cubic-bezier(.16,1,.3,1),transform .8s cubic-bezier(.16,1,.3,1)}
.rv-left.in,.rv-right.in{opacity:1;transform:none}
.rv-scale{opacity:0;transform:scale(.9);transition:opacity .7s cubic-bezier(.16,1,.3,1),transform .7s cubic-bezier(.2,1.2,.35,1)}
.rv-scale.in{opacity:1;transform:none}
.rv-blur{opacity:0;filter:blur(14px);transform:translateY(16px);transition:opacity .8s ease,filter .8s ease,transform .8s cubic-bezier(.16,1,.3,1)}
.rv-blur.in{opacity:1;filter:blur(0);transform:none}
.rv-rise{opacity:0;transform:translateY(60px) scale(.97);transition:opacity .85s cubic-bezier(.16,1,.3,1),transform .85s cubic-bezier(.16,1,.3,1)}
.rv-rise.in{opacity:1;transform:none}
/* каскад дочерних: элементы появляются по очереди */
.rv-stagger>*{opacity:0;transform:translateY(28px);transition:opacity .6s cubic-bezier(.16,1,.3,1),transform .6s cubic-bezier(.16,1,.3,1)}
.rv-stagger.in>*{opacity:1;transform:none}
.rv-stagger.in>*:nth-child(1){transition-delay:.05s}
.rv-stagger.in>*:nth-child(2){transition-delay:.13s}
.rv-stagger.in>*:nth-child(3){transition-delay:.21s}
.rv-stagger.in>*:nth-child(4){transition-delay:.29s}
.rv-stagger.in>*:nth-child(5){transition-delay:.37s}
.rv-stagger.in>*:nth-child(6){transition-delay:.45s}
/* заголовок секции: слова/строки чуть выезжают */
.sec-head.rv-head .eyebrow{opacity:0;transform:translateY(14px);transition:opacity .6s ease,transform .6s cubic-bezier(.16,1,.3,1)}
.sec-head.rv-head h2{opacity:0;transform:translateY(22px);transition:opacity .7s ease .08s,transform .7s cubic-bezier(.16,1,.3,1) .08s}
.sec-head.rv-head .lead{opacity:0;transform:translateY(20px);transition:opacity .7s ease .18s,transform .7s cubic-bezier(.16,1,.3,1) .18s}
.sec-head.rv-head.in .eyebrow,.sec-head.rv-head.in h2,.sec-head.rv-head.in .lead{opacity:1;transform:none}
@media(prefers-reduced-motion:reduce){
  .rv-left,.rv-right,.rv-scale,.rv-blur,.rv-rise,.rv-stagger>*,
  .sec-head.rv-head .eyebrow,.sec-head.rv-head h2,.sec-head.rv-head .lead{opacity:1;transform:none;filter:none}
}

@media(max-width:940px){
  .hero{grid-template-columns:1fr;gap:56px}
  .bento,.plans{grid-template-columns:1fr}
  .cell.big{grid-column:span 1}
  .step{grid-template-columns:1fr;gap:10px;padding:26px 0}
  .f-grid{grid-template-columns:1fr;gap:32px}
  .nav-links{display:none}
  .burger{display:flex}
  .nav-right .btn-dark{display:none}
  .nav-right{gap:8px}
  .prod-btn{padding:7px 10px}
  header{padding:118px 0 72px}
  section{padding:80px 0}
  .cta-band{padding:48px 30px}
  /* ── мобильный hero: 3 карточки, без прыжков ── */
  .stage{height:auto}
  .hub{display:flex;flex-direction:column;gap:10px;height:auto!important}
  .core,.core-lbl,.wires,.orb,.feed,.slot,.shock{display:none!important}
  /* карточки чатов — в аккуратный поток, без абсолютного разброса */
  .hub .card{position:static!important;left:auto!important;top:auto!important;right:auto!important;
    width:100%!important;transform:none!important;margin:0!important;opacity:1!important}
  .hub .card .c-foot{position:static!important;margin-top:10px}
  .who{position:static;transform:none;width:100%;justify-content:center;margin-bottom:6px;
    animation:none;opacity:1}
  .pill{position:static;transform:none;width:100%;
    animation:none;opacity:1;margin-bottom:2px;padding:10px 15px}
  .pill .t{justify-content:center}
  .pill .s{text-align:center}
  /* только 3 карточки — экран не растягивается */
  .c4,.c5,.c6{display:none!important}
  #hero-h1{min-height:232px}
  .card{
    position:relative!important;width:100%;height:156px;
    transform:none!important;animation:none!important;
    padding:11px 12px 40px;box-sizing:border-box;
  }
  .card .bot-txt{min-height:36px}
  .card.leave,.card.enter{animation:none!important;opacity:1!important}
  .card:hover{transform:none}
  .op{position:static;transform:none;width:100%;order:9;animation:none;opacity:1}
  .m-grid{grid-template-columns:1fr 1fr;border-left:0}
  .m{padding:26px 20px}
  .m:nth-child(-n+2){border-bottom:1px solid var(--ink-12)}

  .wall-bot .sep{display:none}
}
@media(prefers-reduced-motion:reduce){
  *{animation:none!important;transition:none!important}
  .rv{opacity:1;transform:none}
  h1 .ln span{transform:none}
  .fade{opacity:1}
}
/* ═══ INTRO / WELCOME PRELOADER ═══ */
.intro{position:fixed;inset:0;z-index:9999;display:flex;flex-direction:column;align-items:center;justify-content:center;
  background:#07080c;overflow:hidden;
  animation:introOut .9s 2.4s cubic-bezier(.7,0,.3,1) forwards}
.intro-bg{position:absolute;inset:0;
  background:radial-gradient(circle at 50% 50%,rgba(34,211,238,.16),transparent 55%);
  opacity:0;animation:introGlow 1.2s .1s ease-out forwards}
.intro-core{position:relative;width:120px;height:120px;display:grid;place-items:center;margin-bottom:34px;flex:none}
.intro-orb{width:96px;height:96px;border-radius:50%;background:#0f1015;display:flex;gap:7px;
  align-items:center;justify-content:center;z-index:2;
  box-shadow:0 0 0 1px rgba(34,211,238,.25),0 0 60px -6px rgba(34,211,238,.6);
  transform:scale(0);animation:introPop .8s .2s cubic-bezier(.2,1.4,.4,1) forwards}
.intro-orb i{width:11px;height:17px;border-radius:6px;background:var(--lime);display:block;
  opacity:0;animation:introBlink 2.4s .9s infinite,introEye .4s .7s ease forwards}
.intro-orb i:nth-child(2){animation-delay:2.5s,.8s}
.intro-ring{position:absolute;width:96px;height:96px;border-radius:50%;border:2px solid rgba(34,211,238,.5);
  opacity:0;animation:introRing 2.2s .5s ease-out infinite}
.intro-ring.r2{animation-delay:1.2s}
.intro-ring.r3{animation-delay:1.8s}
.intro-txt{text-align:center;position:relative;z-index:2}
.intro-hi{font-family:var(--mono);font-size:12px;letter-spacing:.28em;text-transform:uppercase;
  color:var(--lime);opacity:0;transform:translateY(8px);
  animation:introUp .6s .7s cubic-bezier(.16,1,.3,1) forwards;margin-bottom:14px}
.intro-brand{font-size:clamp(38px,6vw,64px);font-weight:500;letter-spacing:-.03em;color:#fff;line-height:1;display:flex;justify-content:center}
.intro-brand span{display:inline-block;opacity:0;transform:translateY(24px) rotate(6deg);
  animation:introLetter .55s cubic-bezier(.16,1,.3,1) forwards}
.intro-brand span.sp{width:.28em}
.intro-brand span:nth-child(1){animation-delay:.85s}
.intro-brand span:nth-child(2){animation-delay:.90s}
.intro-brand span:nth-child(3){animation-delay:.95s}
.intro-brand span:nth-child(4){animation-delay:1.00s}
.intro-brand span:nth-child(5){animation-delay:1.05s}
.intro-brand span:nth-child(6){animation-delay:1.10s}
.intro-brand span:nth-child(8){animation-delay:1.18s;color:var(--lime)}
.intro-brand span:nth-child(9){animation-delay:1.23s;color:var(--lime)}
.intro-sub{font-size:14px;color:rgba(255,255,255,.5);margin-top:18px;opacity:0;
  animation:introUp .6s 1.35s cubic-bezier(.16,1,.3,1) forwards}
@keyframes introGlow{to{opacity:1}}
@keyframes introPop{to{transform:scale(1)}}
@keyframes introEye{to{opacity:1}}
@keyframes introBlink{0%,44%,52%,100%{opacity:1}48%{opacity:.25}}
@keyframes introRing{0%{opacity:.7;transform:scale(.7)}100%{opacity:0;transform:scale(2.4)}}
@keyframes introUp{to{opacity:1;transform:none}}
@keyframes introLetter{to{opacity:1;transform:none}}
@keyframes introOut{to{opacity:0;transform:translateY(-40px);visibility:hidden;pointer-events:none}}
.intro.done{display:none}
@media(prefers-reduced-motion:reduce){
  .intro{animation:introOut .5s 1.6s forwards}
  .intro-orb,.intro-hi,.intro-brand span,.intro-sub{animation:introUp .01s forwards!important;opacity:1;transform:none}
  .intro-orb i{opacity:1;animation:none}
  .intro-ring{display:none}
}
/* ═══ PROMO POP-UP ═══ */
.promo-mask{position:fixed;inset:0;z-index:9998;display:grid;place-items:center;padding:20px;overflow-y:auto;
  background:rgba(6,7,11,.72);backdrop-filter:blur(6px);opacity:0;pointer-events:none;
  transition:opacity .4s ease}
.promo-mask.on{opacity:1;pointer-events:auto}
.promo{position:relative;width:min(500px,100%);background:var(--paper);border-radius:26px;
  padding:44px 40px 36px;text-align:center;border:1px solid var(--ink-12);
  box-shadow:0 40px 100px -30px rgba(0,0,0,.6);
  transform:translateY(30px) scale(.94);opacity:0;transition:transform .5s cubic-bezier(.16,1,.3,1),opacity .5s}
html[data-theme="dark"] .promo{background:#14161f;border-color:rgba(237,238,242,.14)}
.promo-mask.on .promo{transform:none;opacity:1}
.promo-x{position:absolute;top:16px;right:16px;width:34px;height:34px;border-radius:50%;
  border:1px solid var(--ink-12);background:transparent;color:var(--ink-60);cursor:pointer;
  display:grid;place-items:center;transition:all .2s;z-index:2}
.promo-x:hover{background:var(--ink-06);color:var(--ink);transform:rotate(90deg)}
/* анимированное ядро Текны с глазами */
.promo-orb{width:78px;height:78px;border-radius:50%;background:#0f1015;margin:0 auto 22px;
  display:flex;align-items:center;justify-content:center;gap:7px;position:relative;
  box-shadow:0 0 0 1px rgba(34,211,238,.25),0 0 46px -6px rgba(34,211,238,.6);
  animation:promoOrbFloat 3s ease-in-out infinite}
.promo-orb::after{content:"";position:absolute;inset:-8px;border-radius:50%;
  border:2px solid rgba(34,211,238,.4);opacity:0;animation:promoRing 2.4s ease-out infinite}
.promo-orb i{width:9px;height:15px;border-radius:5px;background:var(--lime);display:block;
  animation:promoBlink 3.2s infinite}
@keyframes promoOrbFloat{0%,100%{transform:translateY(0)}50%{transform:translateY(-6px)}}
@keyframes promoRing{0%{opacity:.6;transform:scale(.85)}100%{opacity:0;transform:scale(1.5)}}
@keyframes promoBlink{0%,42%,48%,100%{transform:scaleY(1)}45%{transform:scaleY(.15)}}
.promo-badge{display:inline-block;font-family:var(--mono);font-size:10px;letter-spacing:.14em;
  text-transform:uppercase;color:var(--lime-deep);background:rgba(34,211,238,.14);
  padding:6px 12px;border-radius:100px;margin-bottom:14px}
html[data-theme="dark"] .promo-badge{color:var(--lime)}
.promo-title{font-size:26px;font-weight:600;letter-spacing:-.025em;line-height:1.15;margin-bottom:10px}
.promo-sub{font-size:14.5px;color:var(--ink-60);line-height:1.5;margin-bottom:24px;max-width:380px;margin-left:auto;margin-right:auto}
#promoForm .f-row{margin-bottom:12px;text-align:left}
#promoForm input{width:100%;padding:14px 16px;border-radius:12px;border:1px solid var(--ink-12);
  background:var(--paper-2);font-size:15px;color:var(--ink);transition:border-color .2s,box-shadow .2s}
html[data-theme="dark"] #promoForm input{background:#0f1015;border-color:rgba(237,238,242,.14)}
#promoForm input:focus{outline:none;border-color:var(--lime-deep);box-shadow:0 0 0 3px rgba(34,211,238,.14)}
#promoForm input.bad{border-color:#e5484d;animation:fShake .4s}
.promo-send{width:100%;justify-content:center;margin-top:6px;font-size:15px;padding:15px}
.promo-tg{display:block;margin-top:16px;font-size:13.5px;color:var(--ink-60);text-decoration:none;
  transition:color .2s}
.promo-tg:hover{color:var(--lime-deep)}
html[data-theme="dark"] .promo-tg:hover{color:var(--lime)}
/* success */
.promo-ok{padding:20px 0 8px;text-align:center}
.promo-ok-ic{width:56px;height:56px;border-radius:50%;background:var(--lime);margin:0 auto 16px;
  display:grid;place-items:center;animation:okPop .5s cubic-bezier(.2,1.3,.4,1)}
.promo-ok-ic svg path{stroke-dasharray:24;stroke-dashoffset:24;animation:okDraw .5s .2s forwards}
.promo-ok-t{font-size:16px;font-weight:500}
@media(prefers-reduced-motion:reduce){
  .promo-orb,.promo-orb::after,.promo-orb i{animation:none}
  .promo,.promo-mask{transition:opacity .2s}
}
/* ═══ ПЛАВАЮЩИЙ БОТ ═══ */
.fab{position:fixed;right:24px;bottom:24px;z-index:9997;display:flex;flex-direction:column;align-items:flex-end;gap:14px}
.fab-btn{width:62px;height:62px;border-radius:50%;border:none;cursor:pointer;padding:0;position:relative;
  background:transparent;display:grid;place-items:center}
.fab-orb{width:62px;height:62px;border-radius:50%;background:#0f1015;display:flex;align-items:center;
  justify-content:center;gap:6px;position:relative;z-index:2;
  box-shadow:0 8px 30px -6px rgba(0,0,0,.5),0 0 0 1px rgba(34,211,238,.25),0 0 34px -8px rgba(34,211,238,.55);
  transition:transform .25s cubic-bezier(.2,1.4,.4,1)}
.fab-btn:hover .fab-orb{transform:scale(1.08)}
.fab-orb i{width:8px;height:14px;border-radius:5px;background:var(--lime);display:block;
  animation:fabBlink 3.4s infinite}
@keyframes fabBlink{0%,45%,51%,100%{transform:scaleY(1)}48%{transform:scaleY(.15)}}
/* пульс-кольцо вокруг */
.fab-ping{position:absolute;inset:0;border-radius:50%;border:2px solid var(--lime);opacity:0;z-index:1;
  animation:fabPing 2.6s ease-out infinite}
@keyframes fabPing{0%{opacity:.6;transform:scale(.85)}100%{opacity:0;transform:scale(1.5)}}
/* всплывающее окно */
.fab-pop{width:290px;background:var(--paper);border-radius:20px;border:1px solid var(--ink-12);
  box-shadow:0 30px 70px -24px rgba(0,0,0,.5);padding:18px;
  opacity:0;transform:translateY(14px) scale(.94);transform-origin:bottom right;pointer-events:none;
  transition:opacity .3s,transform .35s cubic-bezier(.16,1,.3,1)}
html[data-theme="dark"] .fab-pop{background:#14161f;border-color:rgba(237,238,242,.14)}
.fab.open .fab-pop{opacity:1;transform:none;pointer-events:auto}
.fab-pop-head{display:flex;align-items:center;gap:10px;margin-bottom:14px}
.fab-mini{width:38px;height:38px;border-radius:50%;background:#0f1015;display:flex;align-items:center;
  justify-content:center;gap:4px;flex-shrink:0}
.fab-mini i{width:5px;height:9px;border-radius:3px;background:var(--lime);display:block}
.fab-nm{font-size:14px;font-weight:600;letter-spacing:-.01em}
.fab-st{font-size:11px;font-family:var(--mono);color:var(--lime-deep)}
html[data-theme="dark"] .fab-st{color:var(--lime)}
.fab-x{margin-left:auto;width:26px;height:26px;border-radius:50%;border:none;background:var(--ink-06);
  color:var(--ink-60);cursor:pointer;display:grid;place-items:center;transition:all .2s;flex-shrink:0}
.fab-x:hover{background:var(--ink-12);color:var(--ink);transform:rotate(90deg)}
.fab-msg{font-size:13.5px;line-height:1.5;color:var(--ink-60);margin-bottom:16px;
  background:var(--paper-2);padding:12px 14px;border-radius:12px;border-top-left-radius:3px}
html[data-theme="dark"] .fab-msg{background:#0f1015}
.fab-tg{display:flex;align-items:center;justify-content:center;gap:9px;width:100%;
  background:#229ED9;color:#fff;padding:13px;border-radius:12px;font-size:14.5px;font-weight:600;
  text-decoration:none;transition:transform .2s,box-shadow .2s}
.fab-tg:hover{transform:translateY(-2px);box-shadow:0 10px 24px -10px rgba(34,158,217,.7)}
@media(max-width:600px){
  .fab{right:16px;bottom:16px}
  .fab-pop{width:min(290px,calc(100vw - 32px))}
}
@media(prefers-reduced-motion:reduce){
  .fab-orb i,.fab-ping{animation:none}
}
/* тизер-облачко (через 10 сек) */
.fab-teaser{position:absolute;right:74px;bottom:6px;max-width:238px;
  background:#0f1015;color:#EDEEF2;border-radius:16px;border-bottom-right-radius:4px;
  padding:13px 34px 13px 15px;font-size:13.5px;line-height:1.4;
  box-shadow:0 16px 40px -14px rgba(0,0,0,.55),0 0 0 1px rgba(34,211,238,.18);
  opacity:0;transform:translateX(12px) scale(.9);transform-origin:bottom right;pointer-events:none;
  white-space:normal;cursor:pointer;transition:opacity .35s,transform .45s cubic-bezier(.16,1,.3,1)}
.fab-teaser::after{content:"";position:absolute;right:-6px;bottom:12px;width:12px;height:12px;
  background:#0f1015;transform:rotate(45deg);border-radius:2px}
.fab.teaser-on .fab-teaser{opacity:1;transform:none;pointer-events:auto;
  animation:teaserBob 2.6s ease-in-out 1s infinite}
@keyframes teaserBob{0%,100%{transform:translateY(0)}50%{transform:translateY(-4px)}}
.fab.open .fab-teaser{opacity:0;pointer-events:none;transform:translateX(12px) scale(.9)}
.fab-teaser-txt{position:relative;z-index:1}
.fab-teaser-x{position:absolute;top:6px;right:6px;width:20px;height:20px;border-radius:50%;border:none;
  background:rgba(237,238,242,.12);color:rgba(237,238,242,.7);cursor:pointer;display:grid;place-items:center;
  transition:background .2s;z-index:2}
.fab-teaser-x:hover{background:rgba(237,238,242,.22)}
/* иконка привлекает внимание когда тизер активен */
.fab.teaser-on .fab-orb{animation:fabWiggle 2.6s ease-in-out infinite}
@keyframes fabWiggle{0%,88%,100%{transform:rotate(0)}91%{transform:rotate(-9deg)}95%{transform:rotate(9deg)}}
@media(max-width:600px){
  .fab-teaser{max-width:min(238px,calc(100vw - 100px))}
}
@media(prefers-reduced-motion:reduce){
  .fab.teaser-on .fab-teaser,.fab.teaser-on .fab-orb{animation:none}
}
/* ═══ АДАПТИВ: телефоны и малые экраны ═══ */
@media(max-width:600px){
  /* общие отступы и типографика */
  section{padding:64px 0}
  .wrap{padding:0 18px}
  h1{font-size:clamp(34px,10vw,52px)}
  .sec-head h2,h2{font-size:clamp(26px,7vw,36px)}

  /* CTA сравнение день/ночь — колонки в столбик, компактнее */
  .cta-band{padding:32px 20px;border-radius:22px;gap:28px}
  .cta-compare{grid-template-columns:1fr;gap:12px}
  .cmp-col{min-height:auto;padding:14px;padding-bottom:14px}
  .cmp-feed{min-height:auto;margin-bottom:10px}
  /* аватар не должен растягиваться в полосу */
  .cmp-ava{width:30px!important;height:30px!important;min-width:30px;aspect-ratio:1;overflow:hidden;
    display:flex!important;align-items:center!important;justify-content:center!important}
  .cmp-ava svg{width:15px;height:15px;display:block;flex:none}
  /* бейдж в потоке, а не absolute внахлёст */
  .cmp-badge{position:static!important;margin-top:10px;left:auto;right:auto;bottom:auto}
  .cta-band h2{font-size:clamp(26px,7.5vw,34px)}

  /* тарифы — одна колонка, popular не приподнят (чтобы не съезжал) */
  .pks{grid-template-columns:1fr;gap:14px}
  .pk.hot,.pk.hot.seen{transform:none}
  .pk.hot:hover{transform:translateY(-4px)}

  /* калькулятор — шкала пакетов в столбик на очень узких */
  .pkscale{grid-template-columns:1fr;gap:8px}
  .pks-item{flex-direction:row;justify-content:space-between;align-items:center}
  .calc-out{padding:20px}
  .calc-out .big{font-size:28px}

  /* how timeline — большая панель скрыта, у каждого шага своя мини-иллюстрация */
  .how-viz{display:none}
  .step-viz{display:flex;align-items:center;gap:8px;margin-top:14px;height:56px;
    background:#14140F;border-radius:12px;padding:0 16px;overflow:hidden}
  /* шаг 1 — документы */
  .sv1 .sv-doc{width:20px;height:26px;border-radius:3px;background:rgba(34,211,238,.25);
    border:1px solid var(--lime);animation:svFloat 1.6s ease-in-out infinite}
  .sv1 .sv-doc:nth-child(2){animation-delay:.2s}
  .sv1 .sv-doc:nth-child(3){animation-delay:.4s}
  @keyframes svFloat{0%,100%{transform:translateY(0)}50%{transform:translateY(-4px)}}
  /* шаг 2 — чат-пузыри */
  .sv2 .sv-b{font-size:11px;padding:6px 11px;border-radius:10px;font-family:var(--mono)}
  .sv2 .sv-b.in{background:rgba(255,255,255,.14);color:#FBFAF7;border-bottom-left-radius:3px}
  .sv2 .sv-b.ai{background:var(--lime);color:#14140F;border-bottom-right-radius:3px;font-weight:600;
    animation:svPulse 1.8s ease-in-out infinite}
  @keyframes svPulse{0%,100%{transform:scale(1)}50%{transform:scale(1.06)}}
  /* шаг 3 — карточка лида */
  .sv3 .sv-lead{display:flex;align-items:center;gap:8px}
  .sv3 .sv-lead b{width:26px;height:26px;border-radius:50%;background:var(--lime);color:#14140F;
    display:grid;place-items:center;font-size:12px}
  .sv3 .sv-lead i{width:60px;height:7px;border-radius:4px;background:rgba(251,250,247,.3);display:block}
  .sv3 .sv-lead i.s{width:38px;background:rgba(251,250,247,.16)}
  /* шаг 4 — звонок */
  .sv4 .sv-call{width:34px;height:34px;border-radius:50%;background:var(--lime);color:#14140F;
    display:grid;place-items:center;animation:svRing 1.2s ease-in-out infinite}
  @keyframes svRing{0%,100%{transform:rotate(0)}25%{transform:rotate(-12deg)}75%{transform:rotate(12deg)}}
  @media(prefers-reduced-motion:reduce){
    .sv-doc,.sv2 .sv-b.ai,.sv-call{animation:none!important}
  }

  /* промо-popup */
  .promo{padding:36px 22px 28px;border-radius:22px}
  .promo-title{font-size:22px}
  .promo-orb{width:66px;height:66px}

  /* метрики блока кейса — стек */
  .case{padding:28px 22px!important}
  .case-qmark{font-size:90px;top:-48px}

  /* плавающий бот — чуть меньше, ближе к краю */
  .fab{right:16px;bottom:16px;gap:12px}
  .fab-btn,.fab-orb{width:56px;height:56px}
  .fab-pop{width:min(300px,calc(100vw - 32px))}
  .fab-teaser{right:66px;max-width:min(210px,calc(100vw - 90px));font-size:13px}

  /* заставка intro — компактнее */
  .intro-brand{font-size:clamp(34px,11vw,52px)}
  .intro-core{width:100px;height:100px;margin-bottom:26px}

  /* footer — колонки в столбик */
  .f-grid{grid-template-columns:1fr 1fr;gap:28px 24px}
  .f-grid>div:first-child{grid-column:1/-1}
  .f-bot{flex-direction:column;align-items:flex-start;gap:8px}

  /* формы/модалки на всю ширину удобнее */
  .modal{width:min(440px,calc(100vw - 24px));padding:26px 22px}
}

/* очень узкие телефоны */
@media(max-width:380px){
  h1{font-size:30px}
  .pk{padding:22px}
  .cta-band{padding:26px 16px}
  .promo{padding:30px 18px 24px}
  .fab-teaser{display:none}   /* на совсем узких прячем облачко, оставляем иконку */
}

/* планшеты (портрет) — промежуточная сетка */
@media(min-width:601px) and (max-width:940px){
  .f-grid{grid-template-columns:1fr 1fr;gap:32px}
  .f-grid>div:first-child{grid-column:1/-1}
  .cta-compare{gap:12px}
}
/* ═══ ФИНАЛЬНАЯ МОБИЛЬНАЯ ПОЛИРОВКА ═══ */
/* защита от горизонтального скролла: декоративные свечения не тянут ширину */
html,body{overflow-x:clip;max-width:100%}
section,header,footer,.cta-band,.case{overflow-x:clip}
/* фоновые свечения не должны выходить за края (создают гор.скролл) */
.bg-lights{max-width:100vw;overflow:hidden}
.bg-lights .l1{left:0}
.bg-lights .l2{right:0}

/* ── на мобильном: упрощаем тяжёлые анимации до спокойного fade+подъём ── */
@media(max-width:768px){
  /* case: убираем 3D-поворот, сканлинию, вспышки — оставляем мягкий подъём */
  .case{transform:translateY(24px)!important;perspective:none}
  .case.in{animation:mobRise .6s cubic-bezier(.16,1,.3,1) forwards!important}
  .case::before{display:none!important}                 /* сканирующая линия */
  .case .quote{filter:none!important;transform:translateY(14px)}
  .case.in .quote{animation:mobRise .5s .15s cubic-bezier(.16,1,.3,1) forwards}
  .case .author .ph{transform:scale(.6)!important}
  .case.in .author .ph{animation:mobPop .5s .3s cubic-bezier(.2,1.3,.4,1) forwards}
  .case.in .cn:nth-child(1),.case.in .cn:nth-child(2),.case.in .cn:nth-child(3){
    animation:mobRise .5s cubic-bezier(.16,1,.3,1) forwards!important}
  .case.in .cn:nth-child(1){animation-delay:.25s}
  .case.in .cn:nth-child(2){animation-delay:.35s}
  .case.in .cn:nth-child(3){animation-delay:.45s}
  .cn{transform:translateY(12px)!important}             /* без бокового въезда */
  .case.in .cn b{animation:none!important}              /* без вспышки числа */
  /* тарифы: без scale/бокового, просто подъём */
  .pk{transform:translateY(18px)!important}
  .pk.seen,.pk.hot.seen{animation:mobRise .55s cubic-bezier(.16,1,.3,1) forwards!important}
  .pk .pop{animation:none!important}                    /* без пульса бейджа */
  /* калькулятор-шкала: мягкий подъём вместо прыжков */
  .calc.seen .pks-item{transform:translateY(8px)!important;animation:mobRise .4s forwards!important}
  .slider-wrap .n.bump{animation:none!important}         /* без пульса числа */
  /* кнопки: убираем постоянные пульсации/бегущую обводку (отвлекает, ест батарею) */
  .hero-cta .btn-dark::before,.hero-cta .btn-dark::after{display:none!important}
  .hero-cta .btn-dark{box-shadow:0 8px 24px -12px rgba(34,211,238,.4)}
  .btn-dark::before,.btn-lime::before{display:none!important}   /* блик-sweep */
  /* бот: без постоянного пинг-кольца и виляния (спокойнее на телефоне) */
  .fab-ping{display:none!important}
  .fab.teaser-on .fab-orb{animation:none!important}
  /* фоновые светящиеся орбы приглушаем (мельтешат на мелком экране) */
  .bg-lights span{opacity:.5}
}
@keyframes mobRise{to{opacity:1;transform:none}}
@keyframes mobPop{to{transform:scale(1)}}
@media(max-width:768px){
  section{padding-top:64px;padding-bottom:64px}
  .wrap{padding:0 20px}
  .sec-head{margin-bottom:36px}
  h1{font-size:clamp(34px,10vw,52px)}
  h2{font-size:clamp(26px,7vw,38px)}
  .cta-band{padding:34px 22px;border-radius:22px}
  .cta-band h2{font-size:clamp(26px,7vw,36px)}
  .calc-grid{gap:22px}
  .pkscale{margin-top:20px}
  /* тарифы: popular не приподнят на мобильном (чтобы не наезжал) */
  .pk.hot{transform:none}
  .pk.hot.seen{animation:pkIn .7s .18s cubic-bezier(.16,1,.3,1) forwards}
  .pk.hot:hover{transform:translateY(-3px)}
}
@media(max-width:600px){
  /* плавающий бот компактнее */
  .fab{right:14px;bottom:14px;gap:12px}
  .fab-btn,.fab-orb{width:56px;height:56px}
  .fab-pop{width:min(280px,calc(100vw - 28px))}
  .fab-teaser{right:66px;max-width:min(210px,calc(100vw - 90px));font-size:12.5px;padding:11px 30px 11px 13px}
  /* промо pop-up */
  .promo{padding:36px 22px 28px;border-radius:22px}
  .promo-title{font-size:22px}
  .promo-orb{width:66px;height:66px;margin-bottom:18px}
  /* сравнение оператор/Techna — стек */
  .cta-compare{grid-template-columns:1fr}
  /* метрики кейса — в столбик */
  .case{padding:28px 22px}
  .case-qmark{font-size:88px;top:-44px}
}
@media(max-width:400px){
  h1{font-size:30px}
  .cta-band h2{font-size:24px}
  .promo-sub{font-size:13px}
  .fab-teaser{display:none}   /* на самых узких — только иконка, без облачка */
  .nav-in{height:60px}
}

/* ═══════════════════════════════════════════════
   TECHNA VOICE — компоненты речевой аналитики
   ═══════════════════════════════════════════════ */

/* hero live-panel вместо hub */
.stage{height:auto}
.vpanel{
  background:#fff;border:1px solid var(--ink-12);border-radius:20px;
  padding:18px;position:relative;overflow:hidden;
  box-shadow:0 30px 70px -40px rgba(20,20,15,.4);
}
html[data-theme="dark"] .vpanel{background:#14161f;border-color:rgba(237,238,242,.14)}
.vp-tabs{display:flex;gap:6px;margin-bottom:14px;overflow-x:auto;scrollbar-width:none;padding-bottom:2px}
.vp-tabs::-webkit-scrollbar{display:none}
.vt{flex:none;font-family:var(--sans);font-size:12px;font-weight:500;letter-spacing:-.01em;
  padding:7px 12px;border-radius:9px;border:1px solid var(--ink-12);background:transparent;color:var(--ink-60);
  cursor:pointer;transition:background .2s,color .2s,border-color .2s;white-space:nowrap}
.vt:hover{border-color:var(--ink-40);color:var(--ink)}
.vt.on{background:var(--lime);border-color:var(--lime);color:#06323a;font-weight:600}
html[data-theme="dark"] .vt.on{color:#06323a}

.vp-hero{display:grid;grid-template-columns:1fr auto;gap:18px;align-items:center;
  background:var(--paper-2);border-radius:16px;padding:18px;margin-bottom:11px}
html[data-theme="dark"] .vp-hero{background:#0f1015}
.vp-badge{display:inline-block;font-family:var(--mono);font-size:10px;letter-spacing:.04em;
  color:var(--lime-deep);background:rgba(34,211,238,.14);padding:5px 10px;border-radius:100px;margin-bottom:10px}
html[data-theme="dark"] .vp-badge{color:var(--lime)}
.vp-h3{font-size:22px;font-weight:600;letter-spacing:-.03em;line-height:1.1;margin-bottom:7px}
.vp-p{font-size:12.5px;color:var(--ink-60);line-height:1.45;max-width:34ch}
.vp-hero-r{display:flex;align-items:center;gap:16px}
.vp-ring-wrap{display:flex;flex-direction:column;align-items:center;gap:6px}
.vp-ring{position:relative;display:grid;place-items:center;width:94px;height:94px;flex:none}
.vp-ring svg{position:absolute}
.vp-ring svg .ring-bg{fill:none;stroke:var(--ink-12);stroke-width:7}
.vp-ring svg .ring-fg{fill:none;stroke:#2fbf71;stroke-width:7;stroke-linecap:round;
  transition:stroke .6s linear;
  stroke-dasharray:326.7;stroke-dashoffset:326.7;transition:stroke-dashoffset 1.3s cubic-bezier(.16,1,.3,1)}
.vp-ring-c{text-align:center;position:relative;z-index:1;display:flex;align-items:baseline;justify-content:center}
.vp-ring-c b{font-size:26px;font-weight:600;letter-spacing:-.03em;line-height:1;color:#2fbf71}
.vp-ring-c span{font-size:15px;font-weight:600;color:#2fbf71}
.vp-ring-lbl{font-size:9px;color:var(--ink-40);font-family:var(--mono);letter-spacing:.02em}
.vp-succ{border-left:1px solid var(--ink-12);padding-left:16px;display:flex;flex-direction:column;justify-content:center}
.vp-succ-l{font-family:var(--mono);font-size:9px;letter-spacing:.1em;color:var(--ink-40);margin-bottom:5px}
.vp-succ-v{font-size:28px;font-weight:600;letter-spacing:-.04em;line-height:1}
.vp-succ-s{font-family:var(--mono);font-size:10.5px;color:var(--ink-40);margin-top:4px}

.vp-kpis{display:grid;grid-template-columns:repeat(2,1fr);gap:9px;margin-bottom:11px}
.vk{background:var(--paper-2);border-radius:13px;padding:12px 14px}
html[data-theme="dark"] .vk{background:#0f1015}
.vk-row{display:flex;align-items:center;justify-content:space-between;margin-bottom:7px}
.vk-t{font-size:11.5px;color:var(--ink-60);font-weight:500}
.vk-ic{width:26px;height:26px;border-radius:8px;display:grid;place-items:center;flex:none}
.vk-ic.ic-a{background:rgba(34,211,238,.16);color:var(--lime-deep)}
.vk-ic.ic-b{background:rgba(47,191,113,.16);color:#2fbf71}
.vk-ic.ic-c{background:rgba(34,211,238,.16);color:var(--lime-deep)}
.vk-ic.ic-d{background:rgba(255,138,138,.18);color:#e46a6a}
html[data-theme="dark"] .vk-ic.ic-a,html[data-theme="dark"] .vk-ic.ic-c{color:var(--lime)}
.vk>b{display:block;font-size:26px;font-weight:600;letter-spacing:-.04em;line-height:1;margin-bottom:6px}
.vk>b span{font-size:.55em;font-weight:600}
.vk-d{font-family:var(--mono);font-size:10px;color:var(--ink-40);display:flex;align-items:center;gap:5px}
.vk-d i{font-style:normal;color:var(--ink-40)}
.vk-d .vk-arw{font-weight:700}
.vk-d.up .vk-arw{color:#2fbf71}
.vk-d.down .vk-arw{color:#e46a6a}
.vk-d.flat .vk-arw{color:var(--ink-40)}

.vp-donut{background:var(--paper-2);border-radius:14px;padding:15px}
html[data-theme="dark"] .vp-donut{background:#0f1015}
.vp-donut-h{display:flex;align-items:center;gap:8px;font-size:13px;font-weight:600;letter-spacing:-.01em;margin-bottom:11px}
.vp-donut-ic{width:8px;height:8px;border-radius:50%;background:var(--lime)}
.vp-donut-row{display:flex;align-items:center;gap:22px}
.donut{transform:rotate(-90deg);flex:none}
.donut .d-bg{fill:none;stroke:var(--ink-12);stroke-width:4}
.donut .d-seg{fill:none;stroke-width:4;stroke-dasharray:0 100;transition:stroke-dasharray 1.1s cubic-bezier(.16,1,.3,1)}
.donut .s1{stroke:#a855c8}
.donut .s2{stroke:#22D3EE}
.donut .s3{stroke:#e14b7a}
.donut .s4{stroke:#e0a83a}
.vp-legend{list-style:none;display:flex;flex-direction:column;gap:7px;flex:1;margin:0;padding:0}
.vp-legend li{display:flex;align-items:center;gap:9px;font-size:12.5px;color:var(--ink-60)}
.vp-legend li b{margin-left:auto;color:var(--ink);font-weight:600;font-family:var(--mono);font-size:12px}
.vp-legend .lg{width:9px;height:9px;border-radius:50%;flex:none}
.vp-legend .lg1{background:#a855c8}.vp-legend .lg2{background:#22D3EE}
.vp-legend .lg3{background:#e14b7a}.vp-legend .lg4{background:#e0a83a}

.vp-foot{margin-top:11px;text-align:center;font-family:var(--mono);font-size:10px;letter-spacing:.02em;color:var(--ink-40)}
@media(max-width:940px){
  .vp-hero{grid-template-columns:1fr;gap:16px}
  .vp-hero-r{justify-content:flex-start}
}
/* ── фикс горизонтального overflow на мобильном ── */
@media(max-width:640px){
  /* дети hero-грида могут сжиматься ниже своего min-content */
  .hero{min-width:0}
  .hero-copy,.stage{min-width:0;max-width:100%}
  .hero-copy h1{overflow-wrap:anywhere}
  /* панель не шире экрана */
  .vpanel{max-width:100%;padding:16px;overflow:hidden}
  .vp-hero{padding:16px;min-width:0}
  .vp-hero-l{min-width:0}
  .vp-h3{font-size:20px}
  .vp-p{max-width:none}
  /* метрики в один столбец, чтобы длинные подписи не распирали */
  .vp-kpis{grid-template-columns:1fr}
  .vk{min-width:0}
  .vk-t{white-space:normal}
  /* строка "vs. пред. период" может переноситься */
  .vk-d{flex-wrap:wrap}
  /* пончик и легенда переносятся вертикально */
  .vp-donut-row{flex-wrap:wrap;gap:14px}
  .vp-legend{min-width:0}
  /* карточка разбора звонка */
  .live-card{padding:18px 16px;overflow:hidden}
  .lc-top{flex-direction:column}
  .lc-top-r{align-self:flex-start;flex-wrap:wrap;gap:12px}
  .lc-meta{gap:6px}
  .lc-tabs{overflow-x:auto;scrollbar-width:none}
  .lc-tabs::-webkit-scrollbar{display:none}
  .lct{flex:none}
  .lc-crit-t{min-width:0}
  /* марки-строка не должна давать горизонтальный скролл (она и так transform) */
  .marq{overflow:hidden}
}
@media(prefers-reduced-motion:reduce){
  .vp-ring svg .ring-fg,.donut .d-seg{transition:none}
}

/* ── разбор звонка (секция #live) — как экран продукта ── */
.live-card{max-width:820px;margin:0 auto;background:#fff;border:1px solid var(--ink-12);border-radius:18px;
  padding:26px 28px;box-shadow:0 26px 60px -40px rgba(20,20,15,.4)}
html[data-theme="dark"] .live-card{background:#14161f;border-color:rgba(237,238,242,.14)}

.lc-top{display:flex;justify-content:space-between;align-items:flex-start;gap:20px;
  padding-bottom:22px;margin-bottom:18px;border-bottom:1px solid var(--ink-12)}
.lc-type-row{display:flex;align-items:center;gap:10px;flex-wrap:wrap;margin-bottom:12px}
.lc-type{display:flex;align-items:center;gap:7px;font-size:15px;font-weight:600;letter-spacing:-.01em;color:var(--lime-deep)}
html[data-theme="dark"] .lc-type{color:var(--lime)}
.lc-chip{font-size:12px;padding:4px 11px;border-radius:8px;border:1px solid var(--ink-12);color:var(--ink-60)}
.lc-chip-v{background:rgba(123,92,246,.14);border-color:transparent;color:#8B6CF6;font-family:var(--mono);font-size:11px}
.lc-meta{display:flex;align-items:center;gap:9px;flex-wrap:wrap;font-family:var(--mono);font-size:12px;color:var(--ink-40)}
.lc-m{display:flex;align-items:center;gap:6px}
.lc-sep{color:var(--ink-12)}
.lc-top-r{display:flex;align-items:center;gap:16px;flex:none}
.lc-ring{position:relative;display:grid;place-items:center;width:88px;height:100px}
.lc-ring svg{position:absolute;top:0}
.lc-ring-bg{fill:none;stroke:var(--ink-12);stroke-width:7}
.lc-ring-fg{fill:none;stroke:#2fbf71;stroke-width:7;stroke-linecap:round;
  stroke-dasharray:326.7;stroke-dashoffset:326.7;transition:stroke-dashoffset 1.2s cubic-bezier(.16,1,.3,1)}
.lc-ring-c{position:absolute;top:30px;display:flex;align-items:baseline}
.lc-ring-c b{font-size:22px;font-weight:600;letter-spacing:-.03em;color:#2fbf71}
.lc-ring-c span{font-size:13px;font-weight:600;color:#2fbf71}
.lc-ring-lbl{position:absolute;bottom:0;font-size:11px;color:#2fbf71;font-family:var(--mono)}
.lc-pass{display:flex;align-items:center;gap:7px;font-size:14px;font-weight:600;color:#2fbf71;
  background:rgba(47,191,113,.12);padding:9px 15px;border-radius:11px;white-space:nowrap;height:fit-content;align-self:center}

.lc-flags{display:flex;align-items:center;justify-content:space-between;margin-bottom:20px}
.lc-flags-l{display:flex;align-items:center;gap:12px}
.lc-warn{color:#e0a83a;display:flex}
.lc-hot{display:flex;align-items:center;gap:6px;font-size:12.5px;font-weight:500;color:#2fbf71;
  background:rgba(47,191,113,.12);padding:6px 12px;border-radius:100px}
.lc-editflags{font-size:13px;color:var(--ink-40);cursor:default}

.lc-tabs{display:flex;gap:8px;margin-bottom:22px}
.lct{display:flex;align-items:center;gap:7px;font-family:var(--sans);font-size:13px;font-weight:500;
  padding:9px 16px;border-radius:10px;border:1px solid var(--ink-12);background:transparent;color:var(--ink-60);cursor:pointer;
  transition:background .2s,color .2s,border-color .2s}
.lct:hover{border-color:var(--ink-40);color:var(--ink)}
.lct.on{background:var(--lime);border-color:var(--lime);color:#06323a;font-weight:600}

.lc-summary{border:0;border-left:3px solid var(--lime);background:var(--paper-2);
  padding:16px 18px;border-radius:0 12px 12px 0;margin:0 0 18px;font-size:14px;line-height:1.6;color:var(--ink-60)}
html[data-theme="dark"] .lc-summary{background:#0f1015}

.lc-why{display:flex;align-items:center;gap:9px;background:rgba(224,168,58,.1);
  padding:14px 18px;border-radius:12px;margin-bottom:22px;font-size:14px;font-weight:600;color:#c68a1f;cursor:default}
html[data-theme="dark"] .lc-why{color:#e0a83a}
.lc-why-n{background:#e0a83a;color:#1a1400;font-size:11px;font-weight:700;
  width:20px;height:20px;border-radius:50%;display:grid;place-items:center}
.lc-chev{margin-left:auto;color:var(--ink-40)}

.lc-crit-h{display:flex;align-items:center;gap:8px;font-size:15px;font-weight:600;letter-spacing:-.01em;margin-bottom:14px}
.lc-crit-ic{width:9px;height:9px;border-radius:50%;background:var(--lime)}
.lc-crit-n{color:var(--ink-40);font-weight:500}
.lc-crit-list{display:flex;flex-direction:column;gap:8px}
.lc-crit{display:flex;align-items:center;gap:12px;padding:14px 16px;border-radius:12px;
  background:var(--paper-2);font-size:14px}
html[data-theme="dark"] .lc-crit{background:#0f1015}
.lc-crit.bad{background:rgba(255,90,90,.08)}
html[data-theme="dark"] .lc-crit.bad{background:rgba(255,90,90,.1)}
.lc-crit-i{width:22px;height:22px;border-radius:50%;display:grid;place-items:center;flex:none;color:#fff}
.lc-crit-i.ok{background:#2fbf71}
.lc-crit-i.x{background:#e14b4b}
.lc-crit-t{flex:1;color:var(--ink);font-weight:500}
.lc-pct{font-family:var(--mono);font-size:14px;font-weight:600;flex:none}
.lc-pct.p-hi{color:#2fbf71}
.lc-pct.p-mid{color:var(--lime-deep)}
html[data-theme="dark"] .lc-pct.p-mid{color:var(--lime)}
.lc-pct.p-lo{color:#e0a83a}
.live-card .vp-foot{margin-top:18px}
@media(max-width:640px){
  .lc-top{flex-direction:column}
  .lc-top-r{align-self:flex-start}
}

/* ── секция #criteria: аналитика по критериям (как экран продукта) ── */
.cr-card{background:#fff;border:1px solid var(--ink-12);border-radius:20px;padding:24px;
  box-shadow:0 26px 60px -40px rgba(20,20,15,.4)}
html[data-theme="dark"] .cr-card{background:#14161f;border-color:rgba(237,238,242,.14)}
.cr-head{display:flex;align-items:flex-start;justify-content:space-between;gap:16px;
  padding-bottom:20px;margin-bottom:18px;border-bottom:1px solid var(--ink-12)}
.cr-head-l{display:flex;align-items:flex-start;gap:12px}
.cr-head-ic{width:36px;height:36px;border-radius:11px;flex:none;display:grid;place-items:center;
  background:rgba(34,211,238,.14);color:var(--lime-deep)}
html[data-theme="dark"] .cr-head-ic{color:var(--lime)}
.cr-h3{font-size:19px;font-weight:600;letter-spacing:-.02em}
.cr-h-tag{color:var(--ink-40);font-weight:500}
.cr-sub{font-size:12.5px;color:var(--ink-40);margin-top:3px}
.cr-xls{display:flex;align-items:center;gap:7px;font-size:12.5px;font-weight:500;color:var(--ink-60);
  border:1px solid var(--ink-12);padding:8px 13px;border-radius:10px;white-space:nowrap;flex:none;cursor:default}

.cr-kpis{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin-bottom:18px}
.crk{background:var(--paper-2);border-radius:14px;padding:16px 18px}
html[data-theme="dark"] .crk{background:#0f1015}
.crk-t{display:flex;align-items:center;gap:8px;font-size:12px;color:var(--ink-60);font-weight:500;margin-bottom:12px}
.crk-ic{width:24px;height:24px;border-radius:7px;display:grid;place-items:center;flex:none}
.crk-ic.ic-a{background:rgba(224,168,58,.16);color:#c68a1f}
.crk-ic.ic-b{background:rgba(34,211,238,.16);color:var(--lime-deep)}
.crk-ic.ic-c{background:rgba(123,92,246,.14);color:#8B6CF6}
.crk-ic.ic-d{background:rgba(47,191,113,.16);color:#2fbf71}
html[data-theme="dark"] .crk-ic.ic-a{color:#e0a83a}
html[data-theme="dark"] .crk-ic.ic-b{color:var(--lime)}
.crk-v{font-size:30px;font-weight:600;letter-spacing:-.04em;line-height:1;display:block}
.crk-v.p-mid{color:#e0a83a}
.crk-v.p-cyan{color:var(--lime-deep)}
html[data-theme="dark"] .crk-v.p-cyan{color:var(--lime)}

.cr-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:14px}
.cr-box{background:var(--paper-2);border-radius:14px;padding:18px}
html[data-theme="dark"] .cr-box{background:#0f1015}
.cr-box-h{margin-bottom:14px}
.cr-box-h b{display:block;font-size:15px;font-weight:600;letter-spacing:-.01em}
.cr-box-h>span{display:block;font-size:12px;color:var(--ink-40);margin-top:2px}
.cr-box-h.cr-box-h-red,.cr-box-h.cr-box-h-green{display:flex;align-items:center;gap:9px;margin-bottom:14px}
.cr-box-h.cr-box-h-red b,.cr-box-h.cr-box-h-green b{margin:0}
.cr-box-ic{width:26px;height:26px;border-radius:8px;display:grid;place-items:center;flex:none}
.cr-ic-down{background:rgba(225,75,75,.14);color:#e14b4b}
.cr-ic-up{background:rgba(47,191,113,.16);color:#2fbf71}

/* рейтинг критериев (таблица) */
.cr-tbl{display:flex;flex-direction:column}
.cr-tr{display:grid;grid-template-columns:1fr auto auto auto;gap:14px;align-items:center;
  padding:11px 0;border-bottom:1px solid var(--ink-12);font-size:13.5px}
.cr-tr:last-child{border-bottom:0}
.cr-th{font-size:11.5px;color:var(--ink-40);font-weight:500;padding-top:0;text-transform:none}
.cr-th span:not(:first-child),.cr-tr>span:not(.cr-nm),.cr-tr>b{text-align:right;min-width:64px}
.cr-nm{display:flex;align-items:center;gap:11px;color:var(--ink);font-weight:500}
.cr-nm i{width:22px;height:22px;border-radius:50%;background:var(--ink-12);color:var(--ink-60);
  display:grid;place-items:center;font-size:11px;font-style:normal;font-weight:600;flex:none}
.cr-sc{font-family:var(--mono);font-weight:600;font-size:13px}
.cr-sc.q-hi{color:#2fbf71}.cr-sc.q-good{color:var(--lime-deep)}.cr-sc.q-mid{color:#e0a83a}.cr-sc.q-bad{color:#e14b4b}
html[data-theme="dark"] .cr-sc.q-good{color:var(--lime)}
.cr-pass{font-family:var(--mono);color:var(--ink-60);font-size:12.5px}
.cr-cl{font-family:var(--mono);color:var(--ink-40);font-size:12.5px}

/* распределение оценок (стек-бары) */
.cr-dist{display:flex;flex-direction:column;gap:14px}
.cr-d-top{display:flex;align-items:center;justify-content:space-between;margin-bottom:7px;font-size:13px}
.cr-d-top i{font-style:normal;font-family:var(--mono);font-size:11px;color:var(--ink-40)}
.cr-bar{display:flex;height:9px;border-radius:100px;overflow:hidden;background:var(--ink-12);gap:2px}
.cr-bar span{height:100%;width:0;transition:width 1s cubic-bezier(.16,1,.3,1)}
.cr-bar .s-ok{background:#2fbf71}.cr-bar .s-good{background:#3B82F6}
.cr-bar .s-mid{background:#e0a83a}.cr-bar .s-bad{background:#e14b4b}
.cr-legend{display:flex;flex-wrap:wrap;gap:14px;margin-top:16px;padding-top:14px;border-top:1px solid var(--ink-12)}
.cr-legend>span{display:flex;align-items:center;gap:7px;font-size:11.5px;color:var(--ink-60)}
.cr-legend i{width:9px;height:9px;border-radius:3px;flex:none}
.cr-legend .lg-ok{background:#2fbf71}.cr-legend .lg-good{background:#3B82F6}
.cr-legend .lg-mid{background:#e0a83a}.cr-legend .lg-bad{background:#e14b4b}

/* коучинг / лучшие (списки) */
.cr-list{display:flex;flex-direction:column;gap:9px}
.cr-li{display:flex;align-items:center;justify-content:space-between;padding:14px 16px;border-radius:11px;font-size:13.5px;font-weight:500}
.cr-li b{font-family:var(--mono);font-size:14px}
.cr-li-red{background:rgba(225,75,75,.08)}.cr-li-red b{color:#e14b4b}
.cr-li-green{background:rgba(47,191,113,.09)}.cr-li-green b{color:#2fbf71}
html[data-theme="dark"] .cr-li-red{background:rgba(225,75,75,.1)}
html[data-theme="dark"] .cr-li-green{background:rgba(47,191,113,.12)}

/* таблица операторов */
.cr-ops{margin-bottom:0}
.cr-ops-scroll{overflow-x:auto;scrollbar-width:thin;margin:0 -4px}
.cr-optbl{width:100%;border-collapse:collapse;font-size:12.5px;min-width:760px}
.cr-optbl th{text-align:right;padding:10px 12px;font-size:11px;font-weight:500;color:var(--ink-40);
  border-bottom:1px solid var(--ink-12);white-space:nowrap;vertical-align:bottom}
.cr-optbl th:first-child{text-align:left}
.cr-optbl td{text-align:right;padding:11px 12px;border-bottom:1px solid var(--ink-12);font-family:var(--mono)}
.cr-optbl tr:last-child td{border-bottom:0}
.cr-op-id{text-align:left!important;color:var(--ink);font-weight:600;font-family:var(--sans)!important}
.cr-optbl td[data-v]{color:#fff}
.cr-optbl td .cell{display:inline-block;min-width:44px;text-align:center;padding:3px 8px;border-radius:6px;font-weight:600}
.cell.q-hi{background:rgba(47,191,113,.16);color:#2fbf71}
.cell.q-good{background:rgba(59,130,246,.16);color:#5a9bf6}
.cell.q-mid{background:rgba(224,168,58,.16);color:#e0a83a}
.cell.q-bad{background:rgba(225,75,75,.14);color:#e46a6a}
.cr-na{color:var(--ink-40)!important}
.cr-card .vp-foot{margin-top:16px}

@media(max-width:900px){
  .cr-kpis{grid-template-columns:repeat(2,1fr)}
  .cr-grid{grid-template-columns:1fr}
}
@media(max-width:640px){
  .cr-card{padding:16px}
  .cr-head{flex-direction:column;gap:12px}
  .cr-xls{align-self:flex-start}
  .cr-tr{gap:8px}
  .cr-th span:not(:first-child),.cr-tr>span:not(.cr-nm),.cr-tr>b{min-width:44px}
}

/* ── viz внутри проблемных карточек ── */
.viz-unheard{display:flex;flex-direction:column;gap:7px;margin-bottom:20px}
.viz-unheard .row{display:flex;align-items:center;gap:10px}
.viz-unheard .row span:first-child{font-family:var(--mono);font-size:11px;color:var(--ink-40);width:30px;flex:none}
.viz-unheard .bar{flex:1;height:8px;border-radius:100px;background:var(--ink-12)}
.viz-unheard .row:nth-child(1) .bar{width:100%}
.viz-unheard .row:nth-child(2) .bar{width:88%;opacity:.6}
.viz-unheard .row.hit .bar{background:var(--lime)}
.viz-unheard .row.hit span:first-child{color:var(--lime-deep);font-weight:600}

.viz-ops{display:flex;flex-direction:column;gap:8px;margin-bottom:20px}
.viz-ops .op{display:flex;align-items:center;gap:9px;font-size:12.5px;
  background:var(--paper-2);border-radius:9px;padding:7px 11px}
html[data-theme="dark"] .viz-ops .op{background:#0f1015}
.viz-ops .op .av{width:22px;height:22px;border-radius:6px;background:var(--ink);color:var(--paper);
  display:grid;place-items:center;font-size:9px;font-weight:600;flex:none}
.viz-ops .op .sc{margin-left:auto;font-family:var(--mono);font-size:12px;font-weight:600;color:var(--lime-deep)}
.viz-ops .op.q{opacity:.5}
.viz-ops .op.q .av{background:var(--ink-12);color:var(--ink-40)}
.viz-ops .op.q .sc{color:var(--ink-40)}

.viz-money{margin-bottom:20px}
.viz-money .mbig{font-size:23px;font-weight:600;letter-spacing:-.03em;color:var(--lime);margin-bottom:12px;line-height:1}
.viz-money .mbig span{font-size:13px;color:rgba(251,250,247,.5);font-weight:400}
.viz-money .lost{display:flex;align-items:center;justify-content:space-between;
  font-size:12.5px;padding:6px 0;border-top:1px solid rgba(251,250,247,.12)}
.viz-money .lost span{font-family:var(--mono);color:rgba(251,250,247,.5)}
.viz-money .lost b{color:#ff8a8a;font-weight:600}

/* ── features list + dash ── */
.f-grid{display:grid;grid-template-columns:1fr 1.05fr;gap:40px;align-items:start}
.f-list{display:flex;flex-direction:column;gap:8px}
.fcell{display:flex;gap:16px;padding:20px;border-radius:14px;background:#fff;border:1px solid var(--ink-12);
  transition:transform .3s cubic-bezier(.2,.8,.2,1),border-color .3s}
.fcell:hover{transform:translateX(4px);border-color:var(--ink-40)}
.fcell .ic{flex:none;color:var(--lime-deep)}
html[data-theme="dark"] .fcell .ic{color:var(--lime)}
.fcell h4{font-size:15.5px;font-weight:600;letter-spacing:-.01em;margin-bottom:4px}
.fcell p{font-size:13.5px;color:var(--ink-60);line-height:1.55}

.dash{background:#fff;border:1px solid var(--ink-12);border-radius:18px;padding:20px;position:sticky;top:96px;
  box-shadow:0 26px 60px -40px rgba(20,20,15,.4)}
.dash-top{display:flex;align-items:center;justify-content:space-between;margin-bottom:14px}
.dash-top .t{font-size:13px;font-weight:600;letter-spacing:-.01em}
.dash-live{font-family:var(--mono);font-size:10px;letter-spacing:.1em;color:#ff5a5a;display:flex;align-items:center;gap:6px}
.dash-live::before{content:"";width:6px;height:6px;border-radius:50%;background:#ff5a5a;animation:breathe 1.4s infinite}
.dash-stats{display:grid;grid-template-columns:repeat(3,1fr);gap:9px;margin-bottom:16px}
.dstat{background:var(--paper-2);border-radius:11px;padding:11px;text-align:center}
html[data-theme="dark"] .dstat{background:#0f1015}
.dstat b{display:block;font-size:22px;font-weight:600;letter-spacing:-.03em;line-height:1}
.dstat span{font-size:10px;color:var(--ink-40);font-family:var(--mono)}
.dash-call{background:var(--paper-2);border:1px solid var(--ink-12);border-radius:13px;padding:15px}
html[data-theme="dark"] .dash-call{background:#0f1015;border-color:rgba(237,238,242,.1)}
.dash-call .ch{display:flex;align-items:center;gap:10px;margin-bottom:13px}
.dash-call .ch .av{width:32px;height:32px;border-radius:9px;background:var(--ink);color:var(--paper);
  display:grid;place-items:center;font-size:11px;font-weight:600;flex:none}
.dash-call .nm{font-size:13px;font-weight:600;letter-spacing:-.01em}
.dash-call .meta{font-size:10.5px;color:var(--ink-40);font-family:var(--mono)}
.dash-call .tag{display:flex;align-items:center;gap:9px;font-size:12px;margin-bottom:8px}
.dash-call .tag .tm{font-family:var(--mono);font-size:10px;color:var(--ink-40);width:30px;flex:none}
.dash-call .tag .lbl{font-family:var(--mono);font-size:8.5px;letter-spacing:.05em;padding:3px 6px;border-radius:5px;font-weight:600;flex:none}
.dash-call .tag .lbl.risk{background:rgba(255,90,90,.14);color:#e14b4b}
.dash-call .tag .lbl.hot{background:rgba(34,211,238,.16);color:var(--lime-deep)}
.dash-call .tag .lbl.comp{background:rgba(120,120,140,.16);color:var(--ink-60)}
html[data-theme="dark"] .dash-call .tag .lbl.comp{background:rgba(237,238,242,.1)}
.dash-call .tag .desc{color:var(--ink-60)}
.dash-call .scores{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-top:13px;padding-top:13px;border-top:1px solid var(--ink-12)}
.dash-call .s{text-align:center}
.dash-call .s b{font-size:16px;font-weight:600;letter-spacing:-.02em;color:var(--lime-deep)}
html[data-theme="dark"] .dash-call .s b{color:var(--lime)}
.dash-call .s span{display:block;font-size:9.5px;color:var(--ink-40);font-family:var(--mono);margin-top:1px}

/* ── integrations ── */
.integr-box{max-width:720px}
.integr-chips{display:flex;flex-wrap:wrap;gap:10px;margin-bottom:16px}
.integr-chips .chip{font-family:var(--mono);font-size:12.5px;letter-spacing:.01em;
  padding:9px 16px;border-radius:100px;border:1px solid var(--ink-12);background:#fff;transition:border-color .25s,transform .25s}
html[data-theme="dark"] .integr-chips .chip{background:#14161f}
.integr-chips .chip:hover{border-color:var(--lime);transform:translateY(-2px)}
.integr-note{font-size:14px;color:var(--ink-60)}

/* ── steps (свой простой вертикальный вариант) ── */
#how .steps{display:flex;flex-direction:column;gap:0;padding-top:0;max-width:820px}
#how .step{display:grid;grid-template-columns:56px 1fr auto;align-items:center;gap:18px;
  padding:24px 0;border-bottom:1px solid var(--ink-12);position:static}
#how .step:last-child{border-bottom:0}
#how .step-n{width:44px;height:44px}
#how .step-n .dot{width:44px;height:44px;border-radius:13px;display:grid;place-items:center;
  background:var(--ink);color:var(--lime);font-family:var(--mono);font-weight:600;font-size:16px}
#how .step-c h4{font-size:18px;font-weight:600;letter-spacing:-.02em;margin-bottom:4px}
#how .step-c p{font-size:14px;color:var(--ink-60);line-height:1.55}
#how .step .when{font-family:var(--mono);font-size:11.5px;color:var(--ink-40);white-space:nowrap;
  border:1px solid var(--ink-12);border-radius:100px;padding:6px 12px}

/* ── price (свой вариант, не конфликтует с базовым .pk) ── */
#price .plans{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;align-items:stretch;margin-bottom:22px}
#price .pk{display:flex;flex-direction:column;border:1px solid var(--ink-12);border-radius:18px;padding:28px;background:#fff;
  position:relative;transition:transform .3s cubic-bezier(.2,.8,.2,1),border-color .3s,box-shadow .3s}
#price .pk:hover{transform:translateY(-4px);border-color:var(--ink-40);box-shadow:0 22px 48px -26px rgba(20,20,15,.32)}
#price .pk.hot{background:var(--ink);color:var(--paper);border-color:var(--ink)}
#price .pk-name{font-size:20px;font-weight:600;letter-spacing:-.02em;margin-bottom:6px}
#price .pk .price{font-size:30px;font-weight:600;letter-spacing:-.03em;margin:0 0 4px;line-height:1}
#price .pk.hot .price{color:var(--lime)}
#price .pk .price .ph{font-size:24px;font-weight:500;color:var(--ink);letter-spacing:-.02em}
#price .pk.hot .price .ph{color:var(--paper)}
#price .pk .per{font-family:var(--mono);font-size:11.5px;color:var(--ink-40);margin-bottom:18px}
#price .pk.hot .per{color:rgba(251,250,247,.5)}
#price .pk-feat{list-style:none;display:flex;flex-direction:column;gap:10px;margin:0 0 22px;flex:1}
#price .pk-feat li{position:relative;padding-left:24px;font-size:13.5px;color:var(--ink-60);line-height:1.45}
#price .pk.hot .pk-feat li{color:rgba(251,250,247,.7)}
#price .pk-feat li::before{content:"";position:absolute;left:0;top:5px;width:15px;height:15px;border-radius:50%;
  background:rgba(34,211,238,.16);
  background-image:url("data:image/svg+xml,%3Csvg width='9' height='9' viewBox='0 0 16 16' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M3 8l3 3 7-7' stroke='%230891B2' stroke-width='2.4' stroke-linecap='round' stroke-linejoin='round'/%3E%3C/svg%3E");
  background-repeat:no-repeat;background-position:center}
#price .pk .pop{position:absolute;top:-11px;left:28px;font-family:var(--mono);font-size:9.5px;letter-spacing:.11em;
  text-transform:uppercase;background:var(--lime);color:#0a2e34;padding:5px 11px;border-radius:100px;font-weight:600}
#price .pk-cta{width:100%;justify-content:center;margin-top:auto}
.price-note{text-align:center;font-size:13px;color:var(--ink-40);font-family:var(--mono);max-width:640px;margin:0 auto}

/* ── cta band inner (совместимо с базовым .cta-band) ── */
.cta-band{text-align:center}
.cta-band .cta-inner{position:relative;z-index:1;max-width:640px;margin:0 auto;display:flex;flex-direction:column;align-items:center}
.cta-band .cta-inner .eyebrow{color:var(--lime);margin-bottom:16px}
.cta-band .cta-inner h2{max-width:18ch;margin:0 auto 14px}
.cta-band .cta-inner p{color:rgba(251,250,247,.72);font-size:16px;margin-bottom:26px;max-width:44ch}
html[data-theme="dark"] .cta-band .cta-inner p{color:rgba(237,238,242,.7)}
.cta-band-btn{margin-bottom:26px}
.cta-benefits{display:flex;flex-wrap:wrap;justify-content:center;gap:10px 20px}
.cta-benefits span{position:relative;font-size:13px;color:rgba(251,250,247,.7);padding-left:20px}
html[data-theme="dark"] .cta-benefits span{color:rgba(237,238,242,.66)}
.cta-benefits span::before{content:"";position:absolute;left:0;top:4px;width:13px;height:13px;border-radius:50%;
  background:rgba(34,211,238,.2);
  background-image:url("data:image/svg+xml,%3Csvg width='8' height='8' viewBox='0 0 16 16' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M3 8l3 3 7-7' stroke='%2322D3EE' stroke-width='2.6' stroke-linecap='round' stroke-linejoin='round'/%3E%3C/svg%3E");
  background-repeat:no-repeat;background-position:center}

/* ── responsive ── */
@media(max-width:940px){
  .f-grid{grid-template-columns:1fr;gap:28px}
  .dash{position:static}
  #price .plans{grid-template-columns:1fr}
  #how .step{grid-template-columns:44px 1fr;gap:14px}
  #how .step .when{grid-column:2;justify-self:start;margin-top:4px}
}

</style>
<script>try{document.documentElement.setAttribute("data-theme",localStorage.getItem("techna_theme")||"light")}catch(e){}</script>
<script>
/* ═══ ЕДИНЫЙ TELEGRAM USERNAME ═══
   Чтобы сменить контакт во всём сайте — поменяйте ТОЛЬКО эту строку (без @). */
window.TECHNA_TG = "technauz";

/* ═══ ОТПРАВКА ЛИДОВ В TELEGRAM-ГРУППУ ═══
   Вставьте сюда URL вашего Cloudflare Worker (прослойка, которая пишет боту).
   Пока пусто ("") — лиды шлются только через открытие Telegram, как раньше. */
window.TECHNA_LEAD_WEBHOOK = "https://techna-leads.azimboyevbegzod.workers.dev";

/* Отправляет лид на webhook. Не мешает открытию Telegram (это запасной канал). */
window.sendLead = function(data){
  try{
    var url = window.TECHNA_LEAD_WEBHOOK;
    if(!url) return;                    // webhook не задан — тихо выходим
    data.page = location.href;
    data.ts = new Date().toISOString();
    /* text/plain — «простой» запрос без CORS-preflight (OPTIONS).
       Воркер всё равно читает тело через request.json(). */
    fetch(url, {
      method: "POST",
      headers: { "Content-Type": "text/plain;charset=UTF-8" },
      body: JSON.stringify(data),
      keepalive: true,
      mode: "cors"
    }).then(function(r){
      if(!r.ok){ console.warn("[Techna lead] воркер ответил:", r.status); }
      else { console.log("[Techna lead] отправлено в группу ✓"); }
    }).catch(function(err){
      console.warn("[Techna lead] ошибка отправки:", err);
    });
  }catch(e){ console.warn("[Techna lead] исключение:", e); }
};
</script>
<script>
/* Проставить единый username всем статичным t.me-ссылкам (кроме тех, что задаёт JS с текстом) */
document.addEventListener("DOMContentLoaded", function(){
  var u = window.TECHNA_TG || "technauz";
  document.querySelectorAll('a[href^="https://t.me/"]').forEach(function(a){
    // не трогаем ссылки, которым JS подставляет ?text=... (их обновляют свои обработчики)
    if(!a.href.includes("?text=")) a.href = "https://t.me/" + u;
  });
});
</script>
</head>
<body>

<div class="intro" id="intro" aria-hidden="true">
  <div class="intro-bg"></div>
  <div class="intro-core">
    <span class="intro-ring"></span>
    <span class="intro-ring r2"></span>
    <span class="intro-ring r3"></span>
    <div class="intro-orb"><i></i><i></i></div>
  </div>
  <div class="intro-txt">
    <div class="intro-hi" data-i18n="intro_hi">Xush kelibsiz</div>
    <div class="intro-brand"><span>T</span><span>e</span><span>c</span><span>h</span><span>n</span><span>a</span><span class="sp"> </span><span>V</span><span>o</span><span>i</span><span>c</span><span>e</span></div>
    <div class="intro-sub" data-i18n="intro_sub">Qo'ng'iroqlar AI-tahlili</div>
  </div>
</div>

<div class="bg-lights" aria-hidden="true"><span class="l1"></span><span class="l2"></span></div>

<nav id="nav">
  <div class="wrap nav-in">
    <div class="prod" id="prod">
      <button class="prod-btn" id="prodBtn" aria-haspopup="true" aria-expanded="false">
        <span class="cur-p"><span class="dot"></span><b>Techna Voice</b></span>
        <svg class="chev" width="12" height="12" viewBox="0 0 16 16" fill="none"><path d="M4 6l4 4 4-4" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/></svg>
      </button>
      <div class="prod-menu" id="prodMenu" role="menu">
        <a class="prod-item" href="index.html" role="menuitem">
          <span class="pic"><svg width="17" height="17" viewBox="0 0 24 24" fill="none"><path d="M4 5h16v11H8l-4 4V5z" stroke="#fff" stroke-width="2" stroke-linejoin="round"/></svg></span>
          <span>
            <span class="pt" data-i18n="prod_bot_t">Bot Messages AI</span>
            <span class="pd" data-i18n="prod_bot_d">Instagram va Telegramda AI-javob</span>
          </span>
        </a>
        <a class="prod-item active" href="speech.html" role="menuitem">
          <span class="pic"><svg width="17" height="17" viewBox="0 0 24 24" fill="none"><path d="M12 3v18M8 7v10M4 10v4M16 6v12M20 9v6" stroke="#22D3EE" stroke-width="2" stroke-linecap="round"/></svg></span>
          <span>
            <span class="pt" data-i18n="prod_voice_t">Voice Analytics <span class="badge-now" data-i18n="prod_now">Shu yerda</span></span>
            <span class="pd" data-i18n="prod_voice_d">100% qo'ng'iroqlar AI-tahlili</span>
          </span>
        </a>
        <a class="prod-item" href="calls.html" role="menuitem">
          <span class="pic"><svg width="17" height="17" viewBox="0 0 24 24" fill="none"><path d="M4 4h3l1.5 4-2 1.5a11 11 0 005 5l1.5-2 4 1.5V18a2 2 0 01-2 2A15 15 0 014 6a2 2 0 012-2z" stroke="#fff" stroke-width="2" stroke-linejoin="round"/><path d="M15 4l4 4M19 4l-4 4" stroke="#fff" stroke-width="1.6" stroke-linecap="round"/></svg></span>
          <span>
            <span class="pt" data-i18n="prod_calls_t">Outgoing Calls AI</span>
            <span class="pd" data-i18n="prod_calls_d">AI-ovoz bilan chiquvchi qo'ng'iroqlar</span>
          </span>
        </a>
      </div>
    </div>

    <div class="nav-links">
      <a href="#problem" data-i18n="nav_problem">Muammo</a>
      <a href="#why" data-i18n="nav_features">Imkoniyatlar</a>
      <a href="#how" data-i18n="nav_how">Qanday ishlaydi</a>
      <a href="#price" data-i18n="nav_price">Tariflar</a>
    </div>

    <div class="nav-right">
      <button class="theme-btn" id="themeBtn" aria-label="Tema">
        <svg class="moon" width="16" height="16" viewBox="0 0 16 16" fill="none"><path d="M13.5 9.6A5.8 5.8 0 016.4 2.5a5.8 5.8 0 107.1 7.1z" stroke="currentColor" stroke-width="1.4" stroke-linejoin="round"/></svg>
        <svg class="sun" width="16" height="16" viewBox="0 0 16 16" fill="none"><circle cx="8" cy="8" r="3.2" stroke="currentColor" stroke-width="1.4"/><path d="M8 1v1.5M8 13.5V15M1 8h1.5M13.5 8H15M3 3l1 1M12 12l1 1M13 3l-1 1M4 12l-1 1" stroke="currentColor" stroke-width="1.4" stroke-linecap="round"/></svg>
      </button>
      <div class="lang" id="lang">
        <button data-lang="uz" class="on">UZ</button>
        <button data-lang="ru">RU</button>
        <button data-lang="en">EN</button>
      </div>
      <a class="btn btn-dark" href="#cta" data-i18n-html="cta_try">Demo ko'rish <svg class="arw" width="13" height="13" viewBox="0 0 16 16" fill="none"><path d="M3 8h10M9 4l4 4-4 4" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/></svg></a>
      <button class="burger" id="burger" aria-label="Menyu" aria-expanded="false" aria-controls="mobileNav">
        <span></span><span></span><span></span>
      </button>
    </div>
  </div>
</nav>

<div class="mobile-nav" id="mobileNav">
  <a href="#problem" data-i18n="nav_problem">Muammo</a>
  <a href="#why" data-i18n="nav_features">Imkoniyatlar</a>
  <a href="#how" data-i18n="nav_how">Qanday ishlaydi</a>
  <a href="#price" data-i18n="nav_price">Tariflar</a>
</div>

<header>
  <div class="glow"></div>
  <div class="wrap hero">
    <div class="hero-copy">
      <div class="eyebrow fade d1" data-i18n="hero_eyebrow">Qo'ng'iroqlar analitikasi · AI</div>
      <h1 id="hero-h1">
        <span class="ln"><span>Har bir qo'ng'iroqni</span></span>
        <span class="ln"><span>tinglaydi. Har bir</span></span>
        <span class="ln"><span class="it">yo'qotishni topadi.</span></span>
      </h1>
      <p class="lead fade d2"><span data-i18n="hero_lead">Qo'lda 2% emas — sotuv bo'limining 100% qo'ng'irog'i. AI transkripsiya qiladi, baholaydi va aynan qayerda pul yo'qotayotganingizni ko'rsatadi.</span></p>
      <div class="hero-cta fade d3">
        <a class="btn btn-dark" href="#cta"><i class="shine" aria-hidden="true"></i><span data-i18n="cta_try_plain">Demo ko'rish</span> <svg class="arw" width="13" height="13" viewBox="0 0 16 16" fill="none"><path d="M3 8h10M9 4l4 4-4 4" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/></svg></a>
        <a class="btn btn-ghost" href="#problem" data-i18n="hero_how">Muammo nimada</a>
      </div>
      <div class="trust fade d3">
        <span data-i18n-html="hero_trust1"><b>30 daqiqa</b> ichida ulanish</span><span>·</span><span data-i18n="hero_trust2">Birinchi insight — bir soatda</span>
      </div>
    </div>

    <div class="stage fade d2">
      <div class="vpanel" id="vPanel">
        <div class="vp-tabs">
          <button class="vt on" data-i18n="vt_all">Все</button>
          <button class="vt" data-i18n="vt_sale">Продажа</button>
          <button class="vt" data-i18n="vt_call">Перезвон</button>
          <button class="vt" data-i18n="vt_push">Дожим</button>
          <button class="vt" data-i18n="vt_serv">Сервис</button>
          <button class="vt" data-i18n="vt_compl">Жалобы</button>
        </div>

        <div class="vp-hero">
          <div class="vp-hero-l">
            <span class="vp-badge" data-i18n="vp_badge">Все звонки</span>
            <h3 class="vp-h3" data-i18n="vp_title">Обзор качества звонков</h3>
            <p class="vp-p" data-i18n="vp_sub">Сводный анализ всех звонков: продажи и поддержка.</p>
          </div>
          <div class="vp-hero-r">
            <div class="vp-ring-wrap">
              <div class="vp-ring">
                <svg viewBox="0 0 120 120" width="104" height="104" aria-hidden="true">
                  <circle class="ring-bg" cx="60" cy="60" r="52"/>
                  <circle class="ring-fg" id="vRing" cx="60" cy="60" r="52" transform="rotate(-90 60 60)"/>
                </svg>
                <div class="vp-ring-c"><b id="vScore">0</b><span>%</span></div>
              </div>
              <div class="vp-ring-lbl" data-i18n="vp_ring">Средний балл</div>
            </div>
            <div class="vp-succ">
              <div class="vp-succ-l" data-i18n="vp_succ">УСПЕШНОСТЬ</div>
              <div class="vp-succ-v"><b id="vSucc">0</b>%</div>
              <div class="vp-succ-s"><span id="vSuccN">0</span> <span data-i18n="vp_of">из</span> 124</div>
            </div>
          </div>
        </div>

        <div class="vp-kpis">
          <div class="vk">
            <div class="vk-row"><span class="vk-t" data-i18n="vp_k1">Проанализировано</span><span class="vk-ic ic-a"><svg width="13" height="13" viewBox="0 0 24 24" fill="none"><path d="M4 4h3l1.5 4-2 1.5a11 11 0 005 5l1.5-2 4 1.5V18a2 2 0 01-2 2A15 15 0 014 6a2 2 0 012-2z" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/></svg></span></div>
            <b id="vk1">0</b>
            <div class="vk-d up"><span class="vk-arw">↗</span> 100.0% <i data-i18n="vp_vs">vs. пред. период</i></div>
          </div>
          <div class="vk">
            <div class="vk-row"><span class="vk-t" data-i18n="vp_k2">Решено успешно</span><span class="vk-ic ic-b"><svg width="13" height="13" viewBox="0 0 24 24" fill="none"><circle cx="12" cy="12" r="8" stroke="currentColor" stroke-width="2"/><circle cx="12" cy="12" r="3" stroke="currentColor" stroke-width="2"/></svg></span></div>
            <b id="vk2">0<span>%</span></b>
            <div class="vk-d flat"><span class="vk-arw">—</span> 0.0% <i data-i18n="vp_vs">vs. пред. период</i></div>
          </div>
          <div class="vk">
            <div class="vk-row"><span class="vk-t" data-i18n="vp_k3">Комплаенс</span><span class="vk-ic ic-c"><svg width="13" height="13" viewBox="0 0 24 24" fill="none"><path d="M4 20V9M10 20V4M16 20v-7M22 20H2" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg></span></div>
            <b id="vk3">0<span>%</span></b>
            <div class="vk-d up"><span class="vk-arw">↗</span> 100.0% <i data-i18n="vp_vs">vs. пред. период</i></div>
          </div>
          <div class="vk">
            <div class="vk-row"><span class="vk-t" data-i18n="vp_k4">Требуют проверки</span><span class="vk-ic ic-d"><svg width="13" height="13" viewBox="0 0 24 24" fill="none"><circle cx="9" cy="8" r="3" stroke="currentColor" stroke-width="2"/><path d="M3 20c0-3 2.7-5 6-5s6 2 6 5M17 11l2 2 4-4" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg></span></div>
            <b id="vk4">0</b>
            <div class="vk-d down"><span class="vk-arw">↘</span> 100.0% <i data-i18n="vp_vs">vs. пред. период</i></div>
          </div>
        </div>

        <div class="vp-donut">
          <div class="vp-donut-h"><span class="vp-donut-ic"></span> <span data-i18n="vp_out">Исходы обращений</span></div>
          <div class="vp-donut-row">
            <svg viewBox="0 0 42 42" width="104" height="104" class="donut" aria-hidden="true">
              <circle class="d-bg" cx="21" cy="21" r="15.9"/>
              <circle class="d-seg s1" cx="21" cy="21" r="15.9"/>
              <circle class="d-seg s2" cx="21" cy="21" r="15.9"/>
              <circle class="d-seg s3" cx="21" cy="21" r="15.9"/>
              <circle class="d-seg s4" cx="21" cy="21" r="15.9"/>
            </svg>
            <ul class="vp-legend">
              <li><span class="lg lg1"></span><span data-i18n="vp_l1">Перезвонить</span><b>88</b></li>
              <li><span class="lg lg2"></span><span data-i18n="vp_l2">Отказ</span><b>19</b></li>
              <li><span class="lg lg3"></span><span data-i18n="vp_l3">Решено</span><b>8</b></li>
              <li><span class="lg lg4"></span><span data-i18n="vp_l4">Назначен визит</span><b>7</b></li>
            </ul>
          </div>
        </div>

        <div class="vp-foot" data-i18n="vp_foot">Пример интерфейса · цифры условные</div>
      </div>
    </div>
  </div>
</header>

<section class="metrics" style="padding:0">
  <div class="wrap" style="padding:0">
    <div class="m-grid rv-stagger">
      <div class="m hi"><div class="ic"><svg width="14" height="14" viewBox="0 0 16 16" fill="none"><path d="M1 8h2l1.5-4 2.5 8 1.5-6 1.5 3H14" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/></svg></div><div class="v">100%</div><div class="l" data-i18n="m_all">Qo'ng'iroqlar nazoratda</div></div>
      <div class="m "><div class="ic"><svg width="14" height="14" viewBox="0 0 16 16" fill="none"><circle cx="7" cy="7" r="5" stroke="currentColor" stroke-width="1.6"/><path d="M14 14l-3-3" stroke="currentColor" stroke-width="1.6" stroke-linecap="round"/></svg></div><div class="v">2%</div><div class="l" data-i18n="m_manual">Ilgari qo'lda tinglanardi</div></div>
      <div class="m "><div class="ic"><svg width="14" height="14" viewBox="0 0 16 16" fill="none"><circle cx="8" cy="8" r="6.3" stroke="currentColor" stroke-width="1.5"/><path d="M8 4.5V8l2.3 2.3" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg></div><div class="v">1 <span data-i18n="m_hour_u">soat</span></div><div class="l" data-i18n="m_hour">Birinchi insightgacha</div></div>
      <div class="m night"><div class="ic"><svg width="14" height="14" viewBox="0 0 16 16" fill="none"><path d="M2 12l3-4 2.5 2.5L11 5l3 4" stroke="#22D3EE" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg></div><div class="v" data-i18n="m_night_v">30 daq</div><div class="l" data-i18n="m_night">Telefoniyaga ulanish</div></div>
    </div>
  </div>
</section>

<div class="marq">
  <div class="marq-in" id="marq"></div>
</div>

<section id="problem">
  <div class="wrap">
    <div class="sec-head rv-head">
      <div class="eyebrow" data-i18n="prob_eyebrow">Muammo</div>
      <h2 data-i18n-html="prob_title">Biznes raqamlarni ko'radi, ammo <em>sabablarini bilmaydi.</em></h2>
      <p class="lead" data-i18n="prob_lead">Jamoangiz kuniga yuzlab qo'ng'iroq qiladi — siz natijani ko'rasiz, jarayonni emas.</p>
    </div>
    <div class="bento rv-stagger">
      <div class="cell">
        <div class="viz-unheard" aria-hidden="true">
          <div class="row"><span>98%</span><span class="bar"></span></div>
          <div class="row"><span></span><span class="bar"></span></div>
          <div class="row hit"><span>2%</span><span class="bar"></span></div>
        </div>
        <div class="num">01</div>
        <h3 data-i18n="prob1_t">Qo'ng'iroqlar tinglanmay qoladi</h3>
        <p data-i18n="prob1_d">Qo'lda siz qo'ng'iroqlarning 2% ini tinglaysiz. Qolgan 98% — qora quti, jumladan mijoz ketgan qo'ng'iroqlar.</p>
      </div>
      <div class="cell">
        <div class="viz-ops" aria-hidden="true">
          <div class="op"><span class="av">AM</span>Anna M.<span class="sc">92</span></div>
          <div class="op q"><span class="av">?</span><span data-i18n="prob_noreview">baho yo'q</span><span class="sc">??</span></div>
          <div class="op"><span class="av">RS</span>Rahima S.<span class="sc">84</span></div>
          <div class="op q"><span class="av">?</span><span data-i18n="prob_noreview">baho yo'q</span><span class="sc">??</span></div>
        </div>
        <div class="num">02</div>
        <h3 data-i18n="prob2_t">Operatorlar ko'r-ko'rona ishlaydi</h3>
        <p data-i18n="prob2_d">Biri rejani bajaradi, boshqasi buzadi. Sabablari noma'lum — hech kim tinglamagan.</p>
      </div>
      <div class="cell big lime">
        <div class="viz-money" aria-hidden="true">
          <div class="mbig">2 450 000 000 <span data-i18n="cur_sum">so'm</span></div>
          <div class="lost"><span>#B-2284</span><b>420 mln</b></div>
          <div class="lost"><span>#B-2317</span><b>175 mln</b></div>
          <div class="lost"><span>#B-2402</span><b>85 mln</b></div>
        </div>
        <div class="num">03</div>
        <h3 data-i18n="prob3_t">Pul sezilmay oqib ketadi</h3>
        <p data-i18n="prob3_d">Bu yerda qo'ldan ketgan bitim. U yerda zaif skript. Umumiy hisobda — hech kim ko'rmaydigan daromad teshigi.</p>
      </div>
    </div>
  </div>
</section>

<section id="why">
  <div class="wrap">
    <div class="sec-head rv-head">
      <div class="eyebrow" data-i18n="why_eyebrow">Nima qiladi</div>
      <h2 data-i18n-html="why_title">Nazorat qiladi, tahlil qiladi, <em>o'rgatadi.</em></h2>
      <p class="lead" data-i18n="why_lead">Sotuv bo'limining 100% qo'ng'irog'ini tinglaydi va aynan qayerda pul yo'qotayotganingizni ko'rsatadi.</p>
    </div>
    <div class="f-grid">
      <div class="f-list rv-stagger">
        <div class="fcell">
          <div class="ic"><svg width="18" height="18" viewBox="0 0 24 24" fill="none"><path d="M12 3v18M8 7v10M4 10v4M16 6v12M20 9v6" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg></div>
          <div><h4 data-i18n="pf1_t">100% qo'ng'iroq nazoratda</h4><p data-i18n="pf1_d">2% tanlab olish emas. Har bir qo'ng'iroq transkripsiya qilinadi va baholanadi.</p></div>
        </div>
        <div class="fcell">
          <div class="ic"><svg width="18" height="18" viewBox="0 0 24 24" fill="none"><path d="M12 2l8 4v6c0 5-3.5 8-8 10-4.5-2-8-5-8-10V6z" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/></svg></div>
          <div><h4 data-i18n="pf2_t">Reglament nazorati</h4><p data-i18n="pf2_d">Buzilishlar va risklar — har bir qo'ng'iroqda, avtomatik.</p></div>
        </div>
        <div class="fcell">
          <div class="ic"><svg width="18" height="18" viewBox="0 0 24 24" fill="none"><path d="M4 20V10M10 20V4M16 20v-8M22 20H2" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg></div>
          <div><h4 data-i18n="pf3_t">Sotuv analitikasi</h4><p data-i18n="pf3_d">Qo'shimcha sotuv signallari — to'g'ridan-to'g'ri qo'ng'iroq transkriptlaridan.</p></div>
        </div>
        <div class="fcell">
          <div class="ic"><svg width="18" height="18" viewBox="0 0 24 24" fill="none"><circle cx="11" cy="11" r="7" stroke="currentColor" stroke-width="2"/><path d="M21 21l-4-4" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg></div>
          <div><h4 data-i18n="pf4_t">Transkript bo'yicha qidiruv</h4><p data-i18n="pf4_d">Istalgan so'z yoki raqam — soniyalar ichida barcha qo'ng'iroqlar bo'yicha.</p></div>
        </div>
      </div>

      <div class="dash rv-scale">
        <div class="dash-top">
          <span class="t" data-i18n="dash_t">Menejer · qo'ng'iroq tahlili</span>
          <span class="dash-live">LIVE</span>
        </div>
        <div class="dash-stats">
          <div class="dstat"><b>248</b><span data-i18n="dash_calls">bugungi qo'ng'iroq</span></div>
          <div class="dstat"><b style="color:#ff8a8a">12</b><span data-i18n="dash_flag">belgilangan</span></div>
          <div class="dstat"><b style="color:var(--lime-deep)">81</b><span data-i18n="dash_avg">o'rtacha ball</span></div>
        </div>
        <div class="dash-call">
          <div class="ch">
            <span class="av">AM</span>
            <div><div class="nm">Anna M. · #18472</div><div class="meta" data-i18n="dash_topic">Sotuv / Qaytarish · 5:12</div></div>
          </div>
          <div class="tag"><span class="tm">0:32</span><span class="lbl risk">RISK</span><span class="desc" data-i18n="dash_tag1">Qaytarish bo'yicha SLA buzildi</span></div>
          <div class="tag"><span class="tm">2:54</span><span class="lbl hot">HOT LEAD</span><span class="desc" data-i18n="dash_tag2">Pro-upgrade signali</span></div>
          <div class="tag"><span class="tm">4:18</span><span class="lbl comp">COMP</span><span class="desc" data-i18n="dash_tag3">Raqobatchini tilga oldi</span></div>
          <div class="scores">
            <div class="s"><b>92</b><span data-i18n="dash_s1">Reglament</span></div>
            <div class="s"><b>88</b><span data-i18n="dash_s2">Empatiya</span></div>
            <div class="s"><b>95</b><span data-i18n="dash_s3">Moslik</span></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="live">
  <div class="wrap">
    <div class="sec-head rv-head">
      <div class="eyebrow" data-i18n="live_eyebrow">Разбор звонка</div>
      <h2 data-i18n-html="live_title">Каждый звонок — <em>расшифрован и оценён.</em></h2>
      <p class="lead" data-i18n="live_lead">AI слушает запись, размечает ключевые моменты и выставляет баллы по вашим критериям.</p>
    </div>
    <div class="live-card rv-scale" id="livePanel">
      <div class="lc-top">
        <div class="lc-top-l">
          <div class="lc-type-row">
            <span class="lc-type"><svg width="15" height="15" viewBox="0 0 24 24" fill="none"><path d="M4 4h3l1.5 4-2 1.5a11 11 0 005 5l1.5-2 4 1.5V18a2 2 0 01-2 2A15 15 0 014 6a2 2 0 012-2z" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/><path d="M15 4l4 4M19 4l-4 4" stroke="currentColor" stroke-width="1.6" stroke-linecap="round"/></svg> <span data-i18n="lc_out">Исходящий</span></span>
            <span class="lc-chip lc-chip-v">support</span>
            <span class="lc-chip" data-i18n="lc_cat">Сервисная поддержка</span>
          </div>
          <div class="lc-meta">
            <span class="lc-m"><svg width="12" height="12" viewBox="0 0 24 24" fill="none"><path d="M4 4h3l1.5 4-2 1.5a11 11 0 005 5l1.5-2 4 1.5V18a2 2 0 01-2 2A15 15 0 014 6a2 2 0 012-2z" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/></svg> 113 → 903552540</span>
            <span class="lc-sep">·</span>
            <span class="lc-m">14.07.2026, 14:18</span>
            <span class="lc-sep">·</span>
            <span class="lc-m">2:03</span>
          </div>
        </div>
        <div class="lc-top-r">
          <div class="lc-ring">
            <svg viewBox="0 0 120 120" width="88" height="88" aria-hidden="true">
              <circle class="lc-ring-bg" cx="60" cy="60" r="52"/>
              <circle class="lc-ring-fg" id="lcRing" cx="60" cy="60" r="52" transform="rotate(-90 60 60)"/>
            </svg>
            <div class="lc-ring-c"><b id="lcScore">0</b><span>%</span></div>
            <div class="lc-ring-lbl">good</div>
          </div>
          <span class="lc-pass"><svg width="15" height="15" viewBox="0 0 24 24" fill="none"><circle cx="12" cy="12" r="9" stroke="currentColor" stroke-width="2"/><path d="M8 12l2.5 2.5L16 9" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg> <span data-i18n="lc_pass">Пройден</span></span>
        </div>
      </div>

      <div class="lc-flags">
        <div class="lc-flags-l">
          <span class="lc-warn"><svg width="15" height="15" viewBox="0 0 24 24" fill="none"><path d="M12 3l9 16H3z" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/><path d="M12 10v4M12 17v.5" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg></span>
          <span class="lc-hot"><svg width="13" height="13" viewBox="0 0 24 24" fill="none"><circle cx="12" cy="12" r="8" stroke="currentColor" stroke-width="2"/><circle cx="12" cy="12" r="3" stroke="currentColor" stroke-width="2"/></svg> <span data-i18n="lc_hotlead">Горячий лид</span></span>
        </div>
        <span class="lc-editflags" data-i18n="lc_editflags">Изменить флаги</span>
      </div>

      <div class="lc-tabs">
        <button class="lct on"><svg width="14" height="14" viewBox="0 0 24 24" fill="none"><path d="M4 20V10M10 20V4M16 20v-7M22 20H2" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg> <span data-i18n="lc_tab1">Анализ</span></button>
        <button class="lct"><svg width="14" height="14" viewBox="0 0 24 24" fill="none"><path d="M4 9v6M8 5v14M12 8v8M16 6v12M20 10v4" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg> <span data-i18n="lc_tab2">Транскрипт</span></button>
        <button class="lct"><svg width="14" height="14" viewBox="0 0 24 24" fill="none"><path d="M5 4h10l4 4v12H5z" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/><path d="M8 12h8M8 16h5" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg> <span data-i18n="lc_tab3">Детали</span></button>
      </div>

      <blockquote class="lc-summary" data-i18n="lc_summary">Клиент обратился с просьбой помочь в разборке и переносе беговой дорожки из одной комнаты в другую. Оператор уточнил локацию, зафиксировал имя клиента и пообещал передать контакт мастерам для обратной связи по стоимости и времени работ.</blockquote>

      <div class="lc-why">
        <svg width="15" height="15" viewBox="0 0 24 24" fill="none"><path d="M4 18l5-6 4 4 7-9" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg>
        <span data-i18n="lc_why">Почему не 100%?</span>
        <span class="lc-why-n">5</span>
        <svg class="lc-chev" width="13" height="13" viewBox="0 0 16 16" fill="none"><path d="M4 6l4 4 4-4" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/></svg>
      </div>

      <div class="lc-crit-h"><span class="lc-crit-ic"></span> <span data-i18n="lc_crit">Оценки по критериям</span> <span class="lc-crit-n">(6)</span></div>
      <div class="lc-crit-list" id="lcCrit">
        <div class="lc-crit bad"><span class="lc-crit-i x"><svg width="12" height="12" viewBox="0 0 16 16" fill="none"><path d="M4 4l8 8M12 4l-8 8" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg></span><span class="lc-crit-t" data-i18n="lc_c1">Приветствие и контекст повторного контакта</span><b class="lc-pct p-lo" data-v="40">0%</b></div>
        <div class="lc-crit"><span class="lc-crit-i ok"><svg width="12" height="12" viewBox="0 0 16 16" fill="none"><path d="M3 8l3 3 7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg></span><span class="lc-crit-t" data-i18n="lc_c2">Подтверждение параметров встречи</span><b class="lc-pct p-hi" data-v="80">0%</b></div>
        <div class="lc-crit"><span class="lc-crit-i ok"><svg width="12" height="12" viewBox="0 0 16 16" fill="none"><path d="M3 8l3 3 7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg></span><span class="lc-crit-t" data-i18n="lc_c3">Ответ и помощь (включая оплату)</span><b class="lc-pct p-mid" data-v="70">0%</b></div>
        <div class="lc-crit"><span class="lc-crit-i ok"><svg width="12" height="12" viewBox="0 0 16 16" fill="none"><path d="M3 8l3 3 7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg></span><span class="lc-crit-t" data-i18n="lc_c4">Эмпатия и сервис</span><b class="lc-pct p-hi" data-v="90">0%</b></div>
        <div class="lc-crit"><span class="lc-crit-i ok"><svg width="12" height="12" viewBox="0 0 16 16" fill="none"><path d="M3 8l3 3 7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg></span><span class="lc-crit-t" data-i18n="lc_c5">Закрытие</span><b class="lc-pct p-hi" data-v="90">0%</b></div>
        <div class="lc-crit"><span class="lc-crit-i ok"><svg width="12" height="12" viewBox="0 0 16 16" fill="none"><path d="M3 8l3 3 7-7" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg></span><span class="lc-crit-t" data-i18n="lc_c6">Управление диалогом</span><b class="lc-pct p-hi" data-v="100">0%</b></div>
      </div>

      <div class="vp-foot" data-i18n="vp_foot">Пример интерфейса · цифры условные</div>
    </div>
  </div>
</section>

<section id="criteria">
  <div class="wrap">
    <div class="sec-head rv-head">
      <div class="eyebrow" data-i18n="cr_eyebrow">Аналитика по критериям</div>
      <h2 data-i18n-html="cr_title">Видно, <em>что западает</em> — и у кого.</h2>
      <p class="lead" data-i18n="cr_lead">Каждый критерий скрипта — с баллом, долей прохождения и разбивкой по операторам. Сразу ясно, где учить команду.</p>
    </div>

    <div class="cr-card rv-scale" id="crPanel">
      <div class="cr-head">
        <div class="cr-head-l">
          <span class="cr-head-ic"><svg width="18" height="18" viewBox="0 0 24 24" fill="none"><circle cx="12" cy="12" r="9" stroke="currentColor" stroke-width="2"/><circle cx="12" cy="12" r="4" stroke="currentColor" stroke-width="2"/><circle cx="12" cy="12" r="1" fill="currentColor"/></svg></span>
          <div>
            <div class="cr-h3"><span data-i18n="cr_h">Аналитика по критериям</span> <span class="cr-h-tag">(<span data-i18n="cr_pack">Продажа</span>)</span></div>
            <div class="cr-sub" data-i18n="cr_sub">Показатели эффективности по критериям оценки звонков</div>
          </div>
        </div>
        <span class="cr-xls"><svg width="15" height="15" viewBox="0 0 24 24" fill="none"><path d="M12 3v11M12 14l-4-4M12 14l4-4M4 20h16" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg> <span data-i18n="cr_xls">Выгрузить XLS</span></span>
      </div>

      <div class="cr-kpis">
        <div class="crk"><div class="crk-t"><span class="crk-ic ic-a"><svg width="13" height="13" viewBox="0 0 24 24" fill="none"><path d="M4 20V8M10 20V4M16 20v-9M22 20H2" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg></span><span data-i18n="cr_k1">Средний балл</span></div><b class="crk-v p-mid" data-v="58">0%</b></div>
        <div class="crk"><div class="crk-t"><span class="crk-ic ic-b"><svg width="13" height="13" viewBox="0 0 24 24" fill="none"><path d="M4 18l6-7 4 4 6-8" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg></span><span data-i18n="cr_k2">Доля прохождения</span></div><b class="crk-v p-cyan" data-v="61">0%</b></div>
        <div class="crk"><div class="crk-t"><span class="crk-ic ic-c"><svg width="13" height="13" viewBox="0 0 24 24" fill="none"><circle cx="12" cy="12" r="8" stroke="currentColor" stroke-width="2"/><circle cx="12" cy="12" r="3" stroke="currentColor" stroke-width="2"/></svg></span><span data-i18n="cr_k3">Критериев</span></div><b class="crk-v" data-v="11" data-suf="">0</b></div>
        <div class="crk"><div class="crk-t"><span class="crk-ic ic-d"><svg width="13" height="13" viewBox="0 0 24 24" fill="none"><circle cx="9" cy="8" r="3" stroke="currentColor" stroke-width="2"/><path d="M3 20c0-3 2.7-5 6-5s6 2 6 5M16 8a3 3 0 010 6" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg></span><span data-i18n="cr_k4">Операторов</span></div><b class="crk-v" data-v="8" data-suf="">0</b></div>
      </div>

      <div class="cr-grid">
        <div class="cr-box">
          <div class="cr-box-h"><b data-i18n="cr_rank">Рейтинг критериев</b><span data-i18n="cr_rank_s">Отсортирован по среднему баллу</span></div>
          <div class="cr-tbl">
            <div class="cr-tr cr-th"><span data-i18n="cr_c_crit">Критерий</span><span data-i18n="cr_c_score">Балл</span><span data-i18n="cr_c_pass">Прохождение</span><span data-i18n="cr_c_calls">Звонков</span></div>
            <div class="cr-tr"><span class="cr-nm"><i>1</i><span data-i18n="crit_dialog">Управление диалогом</span></span><b class="cr-sc" data-v="87">0%</b><span class="cr-pass" data-v="97">0%</span><span class="cr-cl">73</span></div>
            <div class="cr-tr"><span class="cr-nm"><i>2</i><span data-i18n="crit_qual">Квалификация</span></span><b class="cr-sc" data-v="85">0%</b><span class="cr-pass" data-v="89">0%</span><span class="cr-cl">73</span></div>
            <div class="cr-tr"><span class="cr-nm"><i>3</i><span data-i18n="crit_price">Озвучивание стоимости</span></span><b class="cr-sc" data-v="80">0%</b><span class="cr-pass" data-v="100">0%</span><span class="cr-cl">3</span></div>
            <div class="cr-tr"><span class="cr-nm"><i>4</i><span data-i18n="crit_close">Закрытие</span></span><b class="cr-sc" data-v="72">0%</b><span class="cr-pass" data-v="74">0%</span><span class="cr-cl">76</span></div>
            <div class="cr-tr"><span class="cr-nm"><i>5</i><span data-i18n="crit_present">Презентация продукта</span></span><b class="cr-sc" data-v="63">0%</b><span class="cr-pass" data-v="63">0%</span><span class="cr-cl">76</span></div>
            <div class="cr-tr"><span class="cr-nm"><i>6</i><span data-i18n="crit_needs">Выявление потребностей</span></span><b class="cr-sc" data-v="59">0%</b><span class="cr-pass" data-v="58">0%</span><span class="cr-cl">76</span></div>
            <div class="cr-tr"><span class="cr-nm"><i>7</i><span data-i18n="crit_greet">Приветствие</span></span><b class="cr-sc" data-v="59">0%</b><span class="cr-pass" data-v="50">0%</span><span class="cr-cl">76</span></div>
            <div class="cr-tr"><span class="cr-nm"><i>8</i><span data-i18n="crit_next">Следующий шаг</span></span><b class="cr-sc" data-v="53">0%</b><span class="cr-pass" data-v="60">0%</span><span class="cr-cl">73</span></div>
          </div>
        </div>

        <div class="cr-box">
          <div class="cr-box-h"><b data-i18n="cr_dist">Распределение оценок</b><span data-i18n="cr_dist_s">Отлично / Хорошо / Удов. / Плохо</span></div>
          <div class="cr-dist">
            <div class="cr-d-row"><div class="cr-d-top"><span data-i18n="crit_greet">Приветствие</span><i>76 <span data-i18n="cr_calls">звонков</span></i></div><div class="cr-bar" data-seg="52,18,22,8"></div></div>
            <div class="cr-d-row"><div class="cr-d-top"><span data-i18n="crit_close">Закрытие</span><i>76 <span data-i18n="cr_calls">звонков</span></i></div><div class="cr-bar" data-seg="60,22,12,6"></div></div>
            <div class="cr-d-row"><div class="cr-d-top"><span data-i18n="crit_needs">Выявление потребностей</span><i>76 <span data-i18n="cr_calls">звонков</span></i></div><div class="cr-bar" data-seg="55,15,18,12"></div></div>
            <div class="cr-d-row"><div class="cr-d-top"><span data-i18n="crit_obj">Работа с возражениями</span><i>76 <span data-i18n="cr_calls">звонков</span></i></div><div class="cr-bar" data-seg="40,10,7,43"></div></div>
            <div class="cr-d-row"><div class="cr-d-top"><span data-i18n="crit_present">Презентация продукта</span><i>76 <span data-i18n="cr_calls">звонков</span></i></div><div class="cr-bar" data-seg="48,22,18,12"></div></div>
            <div class="cr-d-row"><div class="cr-d-top"><span data-i18n="crit_dialog">Управление диалогом</span><i>73 <span data-i18n="cr_calls">звонков</span></i></div><div class="cr-bar" data-seg="80,14,4,2"></div></div>
            <div class="cr-d-row"><div class="cr-d-top"><span data-i18n="crit_trial">Предложение пробного действия</span><i>73 <span data-i18n="cr_calls">звонков</span></i></div><div class="cr-bar" data-seg="30,6,4,60"></div></div>
          </div>
          <div class="cr-legend">
            <span><i class="lg-ok"></i><span data-i18n="cr_lg1">Отлично (≥80%)</span></span>
            <span><i class="lg-good"></i><span data-i18n="cr_lg2">Хорошо (60-79%)</span></span>
            <span><i class="lg-mid"></i><span data-i18n="cr_lg3">Удов. (40-59%)</span></span>
            <span><i class="lg-bad"></i><span data-i18n="cr_lg4">Плохо (&lt;40%)</span></span>
          </div>
        </div>
      </div>

      <div class="cr-grid">
        <div class="cr-box">
          <div class="cr-box-h cr-box-h-red"><span class="cr-box-ic cr-ic-down"><svg width="15" height="15" viewBox="0 0 24 24" fill="none"><path d="M4 6l6 7 4-4 6 8" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg></span><b data-i18n="cr_coach">Возможности для коучинга</b></div>
          <div class="cr-list">
            <div class="cr-li cr-li-red"><span data-i18n="crit_trial">Предложение пробного действия</span><b>19%</b></div>
            <div class="cr-li cr-li-red"><span data-i18n="crit_invite">Приглашение на встречу</span><b>20%</b></div>
            <div class="cr-li cr-li-red"><span data-i18n="crit_obj">Работа с возражениями</span><b>37%</b></div>
          </div>
        </div>
        <div class="cr-box">
          <div class="cr-box-h cr-box-h-green"><span class="cr-box-ic cr-ic-up"><svg width="15" height="15" viewBox="0 0 24 24" fill="none"><path d="M4 18l6-7 4 4 6-8" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg></span><b data-i18n="cr_best">Лучшие показатели</b></div>
          <div class="cr-list">
            <div class="cr-li cr-li-green"><span data-i18n="crit_dialog">Управление диалогом</span><b>87%</b></div>
            <div class="cr-li cr-li-green"><span data-i18n="crit_qual">Квалификация</span><b>85%</b></div>
            <div class="cr-li cr-li-green"><span data-i18n="crit_price">Озвучивание стоимости</span><b>80%</b></div>
          </div>
        </div>
      </div>

      <div class="cr-box cr-ops">
        <div class="cr-box-h"><b data-i18n="cr_ops">Сравнение операторов по критериям</b><span data-i18n="cr_ops_s">Средний балл по каждому критерию для каждого оператора</span></div>
        <div class="cr-ops-scroll">
          <table class="cr-optbl">
            <thead>
              <tr>
                <th data-i18n="cr_op">Оператор</th>
                <th data-i18n="crit_needs">Выявление потребностей</th>
                <th data-i18n="crit_close">Закрытие</th>
                <th data-i18n="crit_qual">Квалификация</th>
                <th data-i18n="crit_price">Озвучивание стоимости</th>
                <th data-i18n="crit_trial">Пробное действие</th>
                <th data-i18n="crit_present">Презентация</th>
                <th data-i18n="crit_greet">Приветствие</th>
                <th data-i18n="crit_invite">Приглашение</th>
              </tr>
            </thead>
            <tbody>
              <tr><td class="cr-op-id">101</td><td data-v="46">46%</td><td data-v="68">68%</td><td data-v="62">62%</td><td class="cr-na">—</td><td data-v="58">58%</td><td data-v="58">58%</td><td data-v="54">54%</td><td data-v="50">50%</td></tr>
              <tr><td class="cr-op-id">103</td><td data-v="59">59%</td><td data-v="69">69%</td><td data-v="83">83%</td><td data-v="90">90%</td><td data-v="11">11%</td><td data-v="63">63%</td><td data-v="44">44%</td><td data-v="23">23%</td></tr>
              <tr><td class="cr-op-id">104</td><td data-v="58">58%</td><td data-v="69">69%</td><td data-v="90">90%</td><td class="cr-na">—</td><td data-v="5">5%</td><td data-v="46">46%</td><td data-v="68">68%</td><td data-v="6">6%</td></tr>
              <tr><td class="cr-op-id">105</td><td data-v="68">68%</td><td data-v="75">75%</td><td data-v="89">89%</td><td data-v="80">80%</td><td data-v="37">37%</td><td data-v="77">77%</td><td data-v="59">59%</td><td data-v="16">16%</td></tr>
              <tr><td class="cr-op-id">107</td><td data-v="50">50%</td><td data-v="90">90%</td><td data-v="90">90%</td><td class="cr-na">—</td><td data-v="100">100%</td><td data-v="60">60%</td><td data-v="80">80%</td><td data-v="100">100%</td></tr>
              <tr><td class="cr-op-id">108</td><td data-v="73">73%</td><td data-v="90">90%</td><td data-v="95">95%</td><td class="cr-na">—</td><td data-v="35">35%</td><td data-v="70">70%</td><td data-v="65">65%</td><td data-v="50">50%</td></tr>
              <tr><td class="cr-op-id">109</td><td data-v="59">59%</td><td data-v="70">70%</td><td data-v="90">90%</td><td data-v="70">70%</td><td data-v="6">6%</td><td data-v="66">66%</td><td data-v="64">64%</td><td data-v="25">25%</td></tr>
              <tr><td class="cr-op-id">113</td><td data-v="53">53%</td><td data-v="71">71%</td><td data-v="71">71%</td><td class="cr-na">—</td><td data-v="11">11%</td><td data-v="63">63%</td><td data-v="54">54%</td><td data-v="42">42%</td></tr>
            </tbody>
          </table>
        </div>
      </div>

      <div class="vp-foot" data-i18n="vp_foot">Пример интерфейса · цифры условные</div>
    </div>
  </div>
</section>

<section id="integr" style="background:var(--paper-2);border-top:1px solid var(--ink-12);border-bottom:1px solid var(--ink-12)">
  <div class="wrap">
    <div class="sec-head rv-head">
      <div class="eyebrow" data-i18n="int_eyebrow">Integratsiyalar</div>
      <h2 data-i18n-html="int_title">Sizning <em>telefoniyangizga</em> ulanadi.</h2>
      <p class="lead" data-i18n="int_lead">O'zbekiston va MDH ning mashhur ATSlari bilan ishlaydi — yoki yozuvlarni to'g'ridan-to'g'ri yuklang.</p>
    </div>
    <div class="integr-box rv-scale">
      <div class="integr-chips">
        <span class="chip">OnlinePBX</span>
        <span class="chip">Bitrix24</span>
        <span class="chip">Moi Zvonki</span>
        <span class="chip">Sipuni</span>
        <span class="chip">VitalPBX</span>
        <span class="chip">Utel</span>
      </div>
      <div class="integr-note" data-i18n="int_note">— yoki integratsiyasiz, qo'ng'iroq yozuvlarini to'g'ridan-to'g'ri yuklang.</div>
    </div>
  </div>
</section>

<section id="how">
  <div class="wrap">
    <div class="sec-head rv-head">
      <div class="eyebrow" data-i18n="how_eyebrow">Qanday ishlaydi</div>
      <h2 data-i18n-html="how_title">30 daqiqada ulanish. <em>Birinchi insight — bir soatda.</em></h2>
      <p class="lead" data-i18n="how_lead">Noldan ishga tushishgacha — jamoangiz jarayonlariga o'zgarishsiz.</p>
    </div>
    <div class="steps">
      <div class="step rv-left">
        <div class="step-n"><span class="dot">1</span></div>
        <div class="step-c">
          <h4 data-i18n="hw1_t">Ulanish</h4>
          <p data-i18n="hw1_d">Telefoniyangizni ulaymiz. Jarayonlarga o'zgarishsiz.</p>
        </div>
        <div class="when" data-i18n="hw1_w">Start · 0 daq</div>
      </div>
      <div class="step rv-left">
        <div class="step-n"><span class="dot">2</span></div>
        <div class="step-c">
          <h4 data-i18n="hw2_t">AI tinglaydi</h4>
          <p data-i18n="hw2_d">Har bir qo'ng'iroq — sizning mezonlaringiz bo'yicha transkripsiya va baho.</p>
        </div>
        <div class="when" data-i18n="hw2_w">30 daq</div>
      </div>
      <div class="step rv-left">
        <div class="step-n"><span class="dot">3</span></div>
        <div class="step-c">
          <h4 data-i18n="hw3_t">Yo'qotishlarni topadi</h4>
          <p data-i18n="hw3_d">Risklar, issiq lidlar, rad etish sabablari — bitta ekranda.</p>
        </div>
        <div class="when" data-i18n="hw3_w">1 soat</div>
      </div>
      <div class="step rv-left">
        <div class="step-n"><span class="dot">4</span></div>
        <div class="step-c">
          <h4 data-i18n="hw4_t">Harakat qilasiz va o'sasiz</h4>
          <p data-i18n="hw4_d">Aniq tavsiyalar. Daromad o'sadi, yuklama kamayadi.</p>
        </div>
        <div class="when" data-i18n="hw4_w">keyin</div>
      </div>
    </div>
  </div>
</section>

<section id="price">
  <div class="wrap">
    <div class="sec-head rv-head">
      <div class="eyebrow" data-i18n="price_eyebrow">Tariflar</div>
      <h2 data-i18n-html="price_title">Qo'ng'iroqlar hajmiga qarab. <em>Yashirin to'lovlarsiz.</em></h2>
      <p class="lead" data-i18n="price_lead">Oylik qo'ng'iroqlar soniga qarab tarif tanlang. Demo — bepul.</p>
    </div>
    <div class="plans rv-stagger">
      <div class="pk">
        <div class="pk-name">Start</div>
        <div class="price"><span class="ph" data-i18n="price_ask">Kelishiladi</span></div>
        <div class="per"><span data-i18n="pk_start_l">1 000 qo'ng'iroqgacha / oy</span></div>
        <ul class="pk-feat">
          <li data-i18n="pk_f1">100% transkripsiya + baho</li>
          <li data-i18n="pk_f2">Risk va reglament nazorati</li>
          <li data-i18n="pk_f3">Transkript bo'yicha qidiruv</li>
        </ul>
        <a class="btn btn-ghost pk-cta" href="#cta" data-i18n="pk_cta">Demo olish</a>
      </div>
      <div class="pk hot">
        <div class="pop" data-i18n="pk_pop">Ommabop</div>
        <div class="pk-name">Biznes</div>
        <div class="price"><span class="ph" data-i18n="price_ask">Kelishiladi</span></div>
        <div class="per"><span data-i18n="pk_biz_l">5 000 qo'ng'iroqgacha / oy</span></div>
        <ul class="pk-feat">
          <li data-i18n="pk_f4">Start dagi hamma narsa</li>
          <li data-i18n="pk_f5">Sotuv analitikasi + signallar</li>
          <li data-i18n="pk_f6">Operatorlar bo'yicha dashboard</li>
          <li data-i18n="pk_f7">CRM integratsiya</li>
        </ul>
        <a class="btn btn-dark pk-cta" href="#cta" data-i18n="pk_cta">Demo olish</a>
      </div>
      <div class="pk">
        <div class="pk-name">Korporativ</div>
        <div class="price"><span class="ph" data-i18n="price_ask">Kelishiladi</span></div>
        <div class="per"><span data-i18n="pk_ent_l">Cheklanmagan hajm</span></div>
        <ul class="pk-feat">
          <li data-i18n="pk_f8">Biznes dagi hamma narsa</li>
          <li data-i18n="pk_f9">Individual mezonlar va integratsiya</li>
          <li data-i18n="pk_f10">Shaxsiy menejer</li>
        </ul>
        <a class="btn btn-ghost pk-cta" href="#cta" data-i18n="pk_cta">Demo olish</a>
      </div>
    </div>
    <div class="price-note" data-i18n="price_note">Aniq narx qo'ng'iroqlar hajmi va telefoniyangizga bog'liq — demoda hisoblab beramiz.</div>
  </div>
</section>

<section id="cta" style="padding-top:0">
  <div class="wrap">
    <div class="cta-band">
      <div class="cta-inner">
        <div class="eyebrow" data-i18n="cta_eyebrow">Demo</div>
        <h2 data-i18n-html="cta_title">Taxmin qilishni bas qiling. <em>Nazoratni qo'lga oling.</em></h2>
        <p data-i18n="cta_sub">Qo'ng'iroqlar analitikasini bir kundan kamroq vaqtda ishga tushiramiz. Birinchi demo — bepul.</p>
        <a class="btn btn-dark cta-band-btn" href="#cta"><i class="shine" aria-hidden="true"></i><span data-i18n="cta_btn">Demoga yozilish</span> <svg class="arw" width="13" height="13" viewBox="0 0 16 16" fill="none"><path d="M3 8h10M9 4l4 4-4 4" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/></svg></a>
        <div class="cta-benefits">
          <span data-i18n="cb1">Bir kundan kam ishga tushirish</span>
          <span data-i18n="cb2">100% qo'ng'iroq nazoratda</span>
          <span data-i18n="cb3">Jarayonlarga o'zgarishsiz</span>
          <span data-i18n="cb4">RU va UZ tilida qo'llab-quvvatlash</span>
        </div>
      </div>
    </div>
  </div>
</section>
<footer>
  <div class="wrap">
    <div class="f-grid">
      <div>
        <a class="logo" href="index.html"><span class="dot"></span>Techna Voice</a>
        <p data-i18n="f_tag">Sotuv bo'limining 100% qo'ng'irog'ini tinglaydigan va yo'qotishlarni topadigan AI-analitika.</p>
      </div>
      <div class="f-col">
        <h4 data-i18n="f_page">Sahifa</h4>
        <a href="#problem" data-i18n="nav_problem">Muammo</a>
        <a href="#why" data-i18n="nav_features">Imkoniyatlar</a>
        <a href="#how" data-i18n="nav_how">Qanday ishlaydi</a>
        <a href="#price" data-i18n="nav_price">Tariflar</a>
      </div>
      <div class="f-col">
        <h4 data-i18n="foot_contact">Bog'lanish</h4>
        <a href="https://t.me/technauz" target="_blank" rel="noopener">Telegram</a>
        <a href="https://www.instagram.com/techna.uz" target="_blank" rel="noopener">Instagram</a>
        <a href="https://www.linkedin.com/company/110869904" target="_blank" rel="noopener">LinkedIn</a>
      </div>
    </div>
    <div class="f-bot">
      <span data-i18n="foot_rights">© 2026 Techna. Barcha huquqlar himoyalangan.</span>
      <span data-i18n="foot_loc">Toshkent, O'zbekiston</span>
    </div>
  </div>
</footer>

<div class="mask" id="mask" role="dialog" aria-modal="true" aria-labelledby="mTitle">
  <div class="modal" id="modal">
    <button class="x" id="mClose" aria-label="Yopish">
      <svg width="12" height="12" viewBox="0 0 16 16" fill="none"><path d="M3 3l10 10M13 3L3 13" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/></svg>
    </button>

    <div id="mForm">
      <h3 id="mTitle" data-i18n="form_title">Demoga yozilish</h3>
      <div class="sub" data-i18n="form_sub">Qo'ng'iroqlar analitikasi demosi bepul. Raqamingizni qoldiring — 1 ish kuni ichida bog'lanamiz.</div>

      <div class="f-row">
        <label for="fName" data-i18n="form_name">Ismingiz</label>
        <input id="fName" type="text" placeholder="Aziz" autocomplete="name">
        <div class="f-err" id="eName" data-i18n="form_errname">Ismingizni kiriting</div>
      </div>

      <div class="f-row">
        <label for="fPhone" data-i18n="form_phone">Telefon raqam</label>
        <input id="fPhone" type="tel" placeholder="+998 90 123 45 67" autocomplete="tel" inputmode="tel">
        <div class="f-err" id="ePhone" data-i18n="form_errphone">To'g'ri raqam kiriting</div>
      </div>

      <div class="f-row">
        <label for="fCh" data-i18n="form_pbx">Qaysi telefoniyadan foydalanasiz?</label>
        <select id="fCh">
          <option>OnlinePBX</option>
          <option>Bitrix24</option>
          <option>Sipuni</option>
          <option data-i18n="form_pbx_other">Boshqa / bilmayman</option>
        </select>
      </div>

      <button class="btn btn-dark" id="fSend"><span data-i18n="form_send">Demoga yozilish</span>
        <svg class="arw" width="13" height="13" viewBox="0 0 16 16" fill="none"><path d="M3 8h10M9 4l4 4-4 4" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/></svg>
      </button>

      <div class="or" data-i18n="form_or">yoki</div>

      <a class="tg-btn" id="tgLink" href="https://t.me/technauz" target="_blank" rel="noopener">
        <svg width="17" height="17" viewBox="0 0 24 24" fill="#1E8FC6"><path d="M21.9 4.3L18.7 19c-.2 1-.9 1.3-1.7.8l-4.7-3.5-2.3 2.2c-.3.3-.5.5-1 .5l.4-4.9L18.3 6c.4-.3-.1-.5-.6-.2L7.6 12.2 3 10.8c-1-.3-1-1 .2-1.5l17.4-6.7c.8-.3 1.5.2 1.3 1.7z"/></svg>
        <span data-i18n="form_tg">Telegramda yozing</span>
      </a>

      <div class="note" data-i18n="form_note">Raqamingiz uchinchi shaxslarga berilmaydi</div>
    </div>

    <div id="mOk" style="display:none">
      <div class="ok-state">
        <div class="ico">
          <svg width="24" height="24" viewBox="0 0 16 16" fill="none"><path d="M3 8l3.5 3.5L13 4.5" stroke="#14140F" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/></svg>
        </div>
        <h3 data-i18n="ok_h">Qabul qilindi</h3>
        <div class="sub" style="margin-bottom:22px" data-i18n="ok_sub">1 ish kuni ichida bog'lanamiz.</div>
        <a class="tg-btn" href="https://t.me/technauz" target="_blank" rel="noopener">
          <svg width="17" height="17" viewBox="0 0 24 24" fill="#1E8FC6"><path d="M21.9 4.3L18.7 19c-.2 1-.9 1.3-1.7.8l-4.7-3.5-2.3 2.2c-.3.3-.5.5-1 .5l.4-4.9L18.3 6c.4-.3-.1-.5-.6-.2L7.6 12.2 3 10.8c-1-.3-1-1 .2-1.5l17.4-6.7c.8-.3 1.5.2 1.3 1.7z"/></svg>
          <span data-i18n="ok_tg">Hoziroq Telegramda yozing</span>
        </a>
      </div>
    </div>
  </div>
</div>

<div class="fab" id="fab">
  <div class="fab-pop" id="fabPop" role="dialog" aria-label="Techna Voice">
    <div class="fab-pop-head">
      <div class="fab-mini" aria-hidden="true"><i></i><i></i></div>
      <div>
        <div class="fab-nm">Techna Voice</div>
        <div class="fab-st" data-i18n="fab_online">onlayn · darrov javob beradi</div>
      </div>
      <button class="fab-x" id="fabX" aria-label="Yopish">
        <svg width="11" height="11" viewBox="0 0 16 16" fill="none"><path d="M3 3l10 10M13 3L3 13" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/></svg>
      </button>
    </div>
    <div class="fab-msg" data-i18n="fab_msg">Savolingiz bormi? Telegramda darrov javob beramiz 👋</div>
    <a class="fab-tg" id="fabTg" href="https://t.me/technauz" target="_blank" rel="noopener">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="#fff"><path d="M21.9 4.3L18.7 19c-.2 1-.9 1.3-1.7.8l-4.7-3.5-2.3 2.2c-.3.3-.5.5-1 .5l.4-4.9L18.3 6c.4-.3-.1-.5-.6-.2L7.6 12.2 3 10.8c-1-.3-1-1 .2-1.5l17.4-6.7c.8-.3 1.5.2 1.3 1.7z"/></svg>
      <span data-i18n="fab_write">Telegramda yozish</span>
    </a>
  </div>
  <button class="fab-btn" id="fabBtn" aria-label="Techna Voice — chat">
    <span class="fab-orb"><i></i><i></i></span>
    <span class="fab-ping"></span>
  </button>

  <div class="fab-teaser" id="fabTeaser" role="button" tabindex="0">
    <span class="fab-teaser-txt" data-i18n="fab_teaser">Salom! 👋 Qo'ng'iroqlar analitikasi haqida savolingiz bormi? Yozing!</span>
    <button class="fab-teaser-x" id="fabTeaserX" aria-label="Yopish">
      <svg width="9" height="9" viewBox="0 0 16 16" fill="none"><path d="M3 3l10 10M13 3L3 13" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg>
    </button>
  </div>
</div>
<script>
// nav border
const nav=document.getElementById('nav');
addEventListener('scroll',()=>nav.classList.toggle('stuck',scrollY>12));

// reveal
const io=new IntersectionObserver(es=>es.forEach(e=>{if(e.isIntersecting){e.target.classList.add('in');io.unobserve(e.target)}}),{threshold:0,rootMargin:'0px 0px -8% 0px'});
document.querySelectorAll('.rv,.rv-left,.rv-right,.rv-scale,.rv-blur,.rv-rise,.rv-stagger,.rv-head,.vpanel').forEach((el)=>{ io.observe(el); });

// marquee
const MARQ={
  uz:["100% qo'ng'iroq","Transkripsiya + baho","Risk nazorati","Sotuv signallari","Transkript qidiruv","O'zbek va rus tilida","30 daqiqada ulanish"],
  ru:["100% звонков","Транскрипт + оценка","Контроль рисков","Сигналы к продаже","Поиск по транскриптам","На узбекском и русском","Подключение за 30 минут"],
  en:["100% of calls","Transcript + scoring","Risk control","Upsell signals","Transcript search","Uzbek and Russian","Connect in 30 minutes"]
};
function buildMarq(){
  const items=MARQ[window.__lang||'uz']||MARQ.uz;
  document.getElementById('marq').innerHTML=[...items,...items].map(t=>`<span>${t}</span>`).join('');
}
buildMarq();
addEventListener('langchange',buildMarq);

// ── hero: обзор качества (живой дашборд: качество растёт 21%→100% за 2 мин, зациклено) ──
(function(){
  const reduce=matchMedia('(prefers-reduced-motion: reduce)').matches;
  const panel=document.getElementById('vPanel');
  if(!panel) return;

  // условные (placeholder) значения — НЕ реальные данные клиента
  // статичные (не «качество»): считаются один раз
  const STATIC_KPI=[['vk1',124,'']];      // Проанализировано
  const SEG=[71,15,6,6];                    // пончик: Перезвонить/Отказ/Решено/Визит

  // диапазоны «плохо → отлично» для анимируемых показателей качества
  // [начало, конец]
  const R = { ring:[21,100], succ:[24,100], succN:[26,124], vk2:[24,96], vk3:[35,100], vk4:[12,0] };
  const DUR = 120000;   // 2 минуты на полный проход

  const ring=document.getElementById('vRing');
  const C=2*Math.PI*52;                    // ≈ 326.7
  if(ring){ ring.style.strokeDasharray=C; ring.style.strokeDashoffset=C; ring.style.transition='none'; }

  const $=id=>document.getElementById(id);
  function setNum(id,v,suf){ const el=$(id); if(el) el.innerHTML=v+(suf?'<span>'+suf+'</span>':''); }

  // разовый count-up для статичных значений и пончика
  function countUp(id,to,suf){
    const el=$(id); if(!el) return;
    if(reduce){ setNum(id,to,suf); return; }
    const t0=performance.now(),dur=1000;
    (function s(now){ const p=Math.min(1,(now-t0)/dur),e=1-Math.pow(1-p,3);
      setNum(id,Math.round(to*e),suf); if(p<1) requestAnimationFrame(s); })(t0);
  }
  function paintStatic(){
    STATIC_KPI.forEach(([id,to,suf])=>countUp(id,to,suf));
    const segs=panel.querySelectorAll('.donut .d-seg'); let acc=0;
    segs.forEach((s,i)=>{ const val=SEG[i]||0; s.style.strokeDashoffset=-acc;
      requestAnimationFrame(()=>{ s.style.strokeDasharray=val+' '+(100-val); }); acc+=val; });
  }

  const lerp=(a,b,t)=>a+(b-a)*t;
  function qColor(v){                        // цвет по качеству: красный→янтарь→зелёный
    if(v<40) return '#e14b4b';
    if(v<70) return '#e0a83a';
    return '#2fbf71';
  }
  const ringC=$('vScore')?.closest('.vp-ring-c');
  function frame(p){                        // p: 0..1 прогресс качества
    // ease-out, чтобы рост был бодрым в начале и плавным к концу
    const e=1-Math.pow(1-p,2);
    const ringV=Math.round(lerp(R.ring[0],R.ring[1],e));
    setNum('vScore',ringV,'');
    if(ring){ ring.style.strokeDashoffset=C*(1-ringV/100); ring.style.stroke=qColor(ringV); }
    if(ringC){ const c=qColor(ringV); ringC.querySelectorAll('b,span').forEach(x=>x.style.color=c); }
    setNum('vSucc',Math.round(lerp(R.succ[0],R.succ[1],e)),'');
    setNum('vSuccN',Math.round(lerp(R.succN[0],R.succN[1],e)),'');
    setNum('vk2',Math.round(lerp(R.vk2[0],R.vk2[1],e)),'%');
    setNum('vk3',Math.round(lerp(R.vk3[0],R.vk3[1],e)),'%');
    setNum('vk4',Math.round(lerp(R.vk4[0],R.vk4[1],e)),'');
  }

  let raf=0, startT=0;
  function loop(now){
    if(!startT) startT=now;
    let p=(now-startT)/DUR;
    if(p>=1){ p=0; startT=now; }             // дошли до 100% → сброс на старт
    frame(p);
    raf=requestAnimationFrame(loop);
  }

  function play(){
    if(ring){ requestAnimationFrame(()=>{ ring.style.transition='stroke-dashoffset .25s linear'; }); }
    paintStatic();
    if(reduce){ frame(1); return; }          // без анимации — сразу отличное состояние
    frame(0);
    raf=requestAnimationFrame(loop);
  }

  if(reduce){ play(); return; }
  let done=false;
  const pio=new IntersectionObserver(es=>es.forEach(e=>{
    if(e.isIntersecting && !done){ done=true; play(); pio.disconnect(); }
  }),{threshold:.35});
  pio.observe(panel);
})();

// ── ротатор заголовка hero: 4 варианта под боли клиента, авто-смена ~5с ──
(function(){
  const h1=document.getElementById('hero-h1');
  if(!h1) return;
  const reduce=matchMedia('(prefers-reduced-motion: reduce)').matches;
  // каждый вариант — 3 строки; последняя строка курсивом (класс it)
  const VAR={
    uz:[
      ["Har bir qo'ng'iroqni","tinglaydi. Har bir","yo'qotishni topadi."],
      ["Endi hech bir","qo'ng'iroq","e'tibordan chetda qolmaydi."],
      ["Operatorlar endi","ko'r-ko'rona","emas — hammasi ko'rinadi."],
      ["Daromad qayerda","oqib ketayotganini","aniq ko'rsatadi."]
    ],
    ru:[
      ["Каждый звонок —","расшифрован","и оценён."],
      ["Ни один звонок","больше не","останется неуслышанным."],
      ["Операторы больше","не работают","вслепую — всё видно."],
      ["Показывает, где","именно утекает","ваша выручка."]
    ],
    en:[
      ["Every call —","transcribed","and scored."],
      ["Not a single call","goes","unheard anymore."],
      ["Your operators","no longer work","blind — it's all visible."],
      ["Shows exactly","where your revenue","is leaking away."]
    ]
  };
  let idx=0, timer=null;
  function lang(){ return window.__lang||'uz'; }
  function build(lines){
    return lines.map((t,i)=>`<span class="ln"><span${i===2?' class="it"':''}>${t}</span></span>`).join('');
  }
  function paint(animate){
    const list=VAR[lang()]||VAR.uz;
    const v=list[idx%list.length];
    h1.innerHTML=build(v);
    if(animate && !reduce){
      // перезапуск rise-анимации через класс swap
      h1.classList.remove('swap'); void h1.offsetWidth; h1.classList.add('swap');
    }
  }
  function next(){ idx=(idx+1)%4; paint(true); }
  paint(false);
  if(!reduce){ timer=setInterval(next,5000); }
  // при смене языка — перерисовать текущий вариант (без сдвига индекса)
  addEventListener('langchange',()=>paint(false));
})();

// ── секция #live: кольцо 78% + проценты по критериям ──
(function(){
  const reduce=matchMedia('(prefers-reduced-motion: reduce)').matches;
  const card=document.getElementById('livePanel');
  if(!card) return;
  const ring=document.getElementById('lcRing');
  const C=2*Math.PI*52;                 // ≈ 326.7
  const SCORE=78;
  if(ring){ ring.style.strokeDasharray=C; ring.style.strokeDashoffset=C; }

  function countTo(el,to,suf){
    if(reduce){ el.textContent=to+(suf||''); return; }
    const dur=1000,t0=performance.now();
    (function s(now){ const p=Math.min(1,(now-t0)/dur),e=1-Math.pow(1-p,3);
      el.textContent=Math.round(to*e)+(suf||''); if(p<1) requestAnimationFrame(s); })(t0);
  }
  function play(){
    if(ring){ requestAnimationFrame(()=>{ ring.style.strokeDashoffset=C*(1-SCORE/100); }); }
    const sc=document.getElementById('lcScore'); if(sc) countTo(sc,SCORE,'');
    card.querySelectorAll('.lc-pct').forEach(el=>{
      const v=+el.getAttribute('data-v')||0; countTo(el,v,'%');
    });
  }
  if(reduce){ play(); return; }
  let done=false;
  const io2=new IntersectionObserver(es=>es.forEach(e=>{
    if(e.isIntersecting && !done){ done=true; play(); io2.disconnect(); }
  }),{threshold:.3});
  io2.observe(card);
})();

// ── секция #criteria: счётчики, шкалы распределения, окраска ячеек ──
(function(){
  const reduce=matchMedia('(prefers-reduced-motion: reduce)').matches;
  const panel=document.getElementById('crPanel');
  if(!panel) return;

  function qClass(v){ if(v>=80) return 'q-hi'; if(v>=60) return 'q-good'; if(v>=40) return 'q-mid'; return 'q-bad'; }
  function countTo(el,to,suf){
    if(reduce){ el.textContent=to+suf; return; }
    const t0=performance.now(),dur=1100;
    (function s(now){ const p=Math.min(1,(now-t0)/dur),e=1-Math.pow(1-p,3);
      el.textContent=Math.round(to*e)+suf; if(p<1) requestAnimationFrame(s); })(t0);
  }
  function play(){
    // KPI-карточки
    panel.querySelectorAll('.crk-v').forEach(el=>{
      const v=+el.getAttribute('data-v')||0; const suf=el.hasAttribute('data-suf')?el.getAttribute('data-suf'):'%';
      countTo(el,v,suf);
    });
    // рейтинг: балл (с окраской) + прохождение
    panel.querySelectorAll('.cr-sc').forEach(el=>{
      const v=+el.getAttribute('data-v')||0; el.classList.add(qClass(v)); countTo(el,v,'%');
    });
    panel.querySelectorAll('.cr-pass').forEach(el=>{
      const v=+el.getAttribute('data-v')||0; countTo(el,v,'%');
    });
    // распределение: собрать сегменты и заполнить
    panel.querySelectorAll('.cr-bar').forEach(bar=>{
      const seg=(bar.getAttribute('data-seg')||'').split(',').map(Number);
      const cls=['s-ok','s-good','s-mid','s-bad'];
      bar.innerHTML=seg.map((_,i)=>`<span class="${cls[i]}"></span>`).join('');
      const spans=bar.querySelectorAll('span');
      requestAnimationFrame(()=>{ seg.forEach((val,i)=>{ if(spans[i]) spans[i].style.width=val+'%'; }); });
    });
    // таблица операторов: обернуть значения в .cell с окраской
    panel.querySelectorAll('.cr-optbl td[data-v]').forEach(td=>{
      const v=+td.getAttribute('data-v'); const txt=td.textContent;
      td.innerHTML=`<span class="cell ${qClass(v)}">${txt}</span>`;
    });
  }
  if(reduce){ play(); return; }
  let done=false;
  const io3=new IntersectionObserver(es=>es.forEach(e=>{
    if(e.isIntersecting && !done){ done=true; play(); io3.disconnect(); }
  }),{threshold:.15});
  io3.observe(panel);
})();
</script>
<script>
// ── i18n: UZ / RU / EN ──
(function(){
  const T={
    uz:{
      nav_problem:"Muammo", nav_features:"Imkoniyatlar", nav_how:"Qanday ishlaydi", nav_price:"Tariflar",
      intro_hi:"Xush kelibsiz", intro_sub:"Qo'ng'iroqlar AI-tahlili",
      prod_now:"Shu yerda", prod_bot_t:"Bot Messages AI", prod_bot_d:"Instagram va Telegramda AI-javob",
      prod_voice_t:"Voice Analytics", prod_voice_d:"100% qo'ng'iroqlar AI-tahlili",
      prod_calls_t:"Outgoing Calls AI", prod_calls_d:"AI-ovoz bilan chiquvchi qo'ng'iroqlar",
      cta_try:"Demo ko'rish", cta_try_plain:"Demo ko'rish",
      hero_eyebrow:"Qo'ng'iroqlar analitikasi · AI",
      hero_lead:"Qo'lda 2% emas — sotuv bo'limining 100% qo'ng'irog'i. AI transkripsiya qiladi, baholaydi va aynan qayerda pul yo'qotayotganingizni ko'rsatadi.",
      hero_how:"Muammo nimada",
      hero_trust1:"<b>30 daqiqa</b> ichida ulanish", hero_trust2:"Birinchi insight — bir soatda",
      vp_title:"Qo'ng'iroqlar sifati obzori", vp_sub:"Barcha qo'ng'iroqlar tahlili: sotuv va qo'llab-quvvatlash.",
      vp_badge:"Barcha qo'ng'iroqlar", vp_ring:"O'rtacha ball", vp_succ:"MUVAFFAQIYAT", vp_of:"dan",
      vt_all:"Barchasi", vt_sale:"Sotuv", vt_call:"Qayta qo'ng'iroq", vt_push:"Dojim", vt_serv:"Servis", vt_compl:"Shikoyatlar",
      vp_k1:"Tahlil qilingan", vp_k2:"Muvaffaqiyatli yechilgan", vp_k3:"Komplaens", vp_k4:"Tekshirish kerak", vp_vs:"o'tgan davrga nisbatan",
      vp_out:"Murojaatlar natijasi", vp_l1:"Qayta qo'ng'iroq", vp_l2:"Rad etish", vp_l3:"Yechilgan", vp_l4:"Vizit tayinlandi",
      vp_foot:"Namuna interfeys · raqamlar shartli",
      cr_eyebrow:"Mezonlar bo'yicha analitika", cr_title:"Nima <em>oqsayotgani</em> ko'rinadi — va kimda.",
      cr_lead:"Skriptning har bir mezoni — ball, o'tish ulushi va operatorlar bo'yicha taqsimot bilan. Jamoani qayerda o'qitish kerakligi darhol ayon.",
      cr_h:"Mezonlar bo'yicha analitika", cr_pack:"Sotuv", cr_sub:"Qo'ng'iroqlarni baholash mezonlari bo'yicha samaradorlik ko'rsatkichlari", cr_xls:"XLS yuklab olish",
      cr_k1:"O'rtacha ball", cr_k2:"O'tish ulushi", cr_k3:"Mezonlar", cr_k4:"Operatorlar",
      cr_rank:"Mezonlar reytingi", cr_rank_s:"O'rtacha ball bo'yicha saralangan",
      cr_c_crit:"Mezon", cr_c_score:"Ball", cr_c_pass:"O'tish", cr_c_calls:"Qo'ng'iroqlar",
      cr_dist:"Baholar taqsimoti", cr_dist_s:"A'lo / Yaxshi / Qoniqarli / Yomon", cr_calls:"qo'ng'iroq",
      cr_lg1:"A'lo (≥80%)", cr_lg2:"Yaxshi (60-79%)", cr_lg3:"Qoniqarli (40-59%)", cr_lg4:"Yomon (<40%)",
      cr_coach:"Kouching imkoniyatlari", cr_best:"Eng yaxshi ko'rsatkichlar",
      cr_ops:"Operatorlarni mezonlar bo'yicha taqqoslash", cr_ops_s:"Har bir operator uchun har bir mezon bo'yicha o'rtacha ball", cr_op:"Operator",
      crit_dialog:"Dialogni boshqarish", crit_qual:"Kvalifikatsiya", crit_price:"Narxni aytish", crit_close:"Yakunlash",
      crit_present:"Mahsulot taqdimoti", crit_needs:"Ehtiyojlarni aniqlash", crit_greet:"Salomlashish", crit_next:"Keyingi qadam",
      crit_obj:"E'tirozlar bilan ishlash", crit_trial:"Sinov harakatini taklif qilish", crit_invite:"Uchrashuvga taklif",
      live_eyebrow:"Qo'ng'iroq tahlili", live_title:"Har bir qo'ng'iroq — <em>transkripsiya va baho.</em>",
      live_lead:"AI yozuvni tinglaydi, muhim daqiqalarni belgilaydi va sizning mezonlaringiz bo'yicha ball qo'yadi.",
      lc_out:"Chiquvchi", lc_cat:"Servis qo'llab-quvvatlash", lc_pass:"O'tdi", lc_hotlead:"Issiq lid", lc_editflags:"Belgilarni o'zgartirish",
      lc_tab1:"Tahlil", lc_tab2:"Transkript", lc_tab3:"Tafsilotlar",
      lc_summary:"Mijoz yugurish yo'lakchasini bir xonadan ikkinchisiga ko'chirishda yordam so'radi. Operator joyni aniqladi, mijoz ismini qayd etdi va narx va ish vaqti bo'yicha aloqa uchun kontaktni ustalarga uzatishni va'da qildi.",
      lc_why:"Nega 100% emas?", lc_crit:"Mezonlar bo'yicha baholar",
      lc_c1:"Salomlashish va takroriy aloqa konteksti", lc_c2:"Uchrashuv parametrlarini tasdiqlash", lc_c3:"Javob va yordam (to'lov bilan)",
      lc_c4:"Empatiya va servis", lc_c5:"Yakunlash", lc_c6:"Dialogni boshqarish",
      m_all:"Qo'ng'iroqlar nazoratda", m_manual:"Ilgari qo'lda tinglanardi", m_hour:"Birinchi insightgacha", m_hour_u:"soat",
      m_night:"Telefoniyaga ulanish", m_night_v:"30 daq",
      prob_eyebrow:"Muammo", prob_title:"Biznes raqamlarni ko'radi, ammo <em>sabablarini bilmaydi.</em>",
      prob_lead:"Jamoangiz kuniga yuzlab qo'ng'iroq qiladi — siz natijani ko'rasiz, jarayonni emas.",
      prob_noreview:"baho yo'q",
      prob1_t:"Qo'ng'iroqlar tinglanmay qoladi", prob1_d:"Qo'lda siz qo'ng'iroqlarning 2% ini tinglaysiz. Qolgan 98% — qora quti, jumladan mijoz ketgan qo'ng'iroqlar.",
      prob2_t:"Operatorlar ko'r-ko'rona ishlaydi", prob2_d:"Biri rejani bajaradi, boshqasi buzadi. Sabablari noma'lum — hech kim tinglamagan.",
      prob3_t:"Pul sezilmay oqib ketadi", prob3_d:"Bu yerda qo'ldan ketgan bitim. U yerda zaif skript. Umumiy hisobda — hech kim ko'rmaydigan daromad teshigi.",
      cur_sum:"so'm",
      why_eyebrow:"Nima qiladi", why_title:"Nazorat qiladi, tahlil qiladi, <em>o'rgatadi.</em>",
      why_lead:"Sotuv bo'limining 100% qo'ng'irog'ini tinglaydi va aynan qayerda pul yo'qotayotganingizni ko'rsatadi.",
      pf1_t:"100% qo'ng'iroq nazoratda", pf1_d:"2% tanlab olish emas. Har bir qo'ng'iroq transkripsiya qilinadi va baholanadi.",
      pf2_t:"Reglament nazorati", pf2_d:"Buzilishlar va risklar — har bir qo'ng'iroqda, avtomatik.",
      pf3_t:"Sotuv analitikasi", pf3_d:"Qo'shimcha sotuv signallari — to'g'ridan-to'g'ri qo'ng'iroq transkriptlaridan.",
      pf4_t:"Transkript bo'yicha qidiruv", pf4_d:"Istalgan so'z yoki raqam — soniyalar ichida barcha qo'ng'iroqlar bo'yicha.",
      dash_t:"Menejer · qo'ng'iroq tahlili", dash_calls:"bugungi qo'ng'iroq", dash_flag:"belgilangan", dash_avg:"o'rtacha ball",
      dash_topic:"Sotuv / Qaytarish · 5:12",
      dash_tag1:"Qaytarish bo'yicha SLA buzildi", dash_tag2:"Pro-upgrade signali", dash_tag3:"Raqobatchini tilga oldi",
      dash_s1:"Reglament", dash_s2:"Empatiya", dash_s3:"Moslik",
      int_eyebrow:"Integratsiyalar", int_title:"Sizning <em>telefoniyangizga</em> ulanadi.",
      int_lead:"O'zbekiston va MDH ning mashhur ATSlari bilan ishlaydi — yoki yozuvlarni to'g'ridan-to'g'ri yuklang.",
      int_note:"— yoki integratsiyasiz, qo'ng'iroq yozuvlarini to'g'ridan-to'g'ri yuklang.",
      how_eyebrow:"Qanday ishlaydi", how_title:"30 daqiqada ulanish. <em>Birinchi insight — bir soatda.</em>",
      how_lead:"Noldan ishga tushishgacha — jamoangiz jarayonlariga o'zgarishsiz.",
      hw1_t:"Ulanish", hw1_d:"Telefoniyangizni ulaymiz. Jarayonlarga o'zgarishsiz.", hw1_w:"Start · 0 daq",
      hw2_t:"AI tinglaydi", hw2_d:"Har bir qo'ng'iroq — sizning mezonlaringiz bo'yicha transkripsiya va baho.", hw2_w:"30 daq",
      hw3_t:"Yo'qotishlarni topadi", hw3_d:"Risklar, issiq lidlar, rad etish sabablari — bitta ekranda.", hw3_w:"1 soat",
      hw4_t:"Harakat qilasiz va o'sasiz", hw4_d:"Aniq tavsiyalar. Daromad o'sadi, yuklama kamayadi.", hw4_w:"keyin",
      price_eyebrow:"Tariflar", price_title:"Qo'ng'iroqlar hajmiga qarab. <em>Yashirin to'lovlarsiz.</em>",
      price_lead:"Oylik qo'ng'iroqlar soniga qarab tarif tanlang. Demo — bepul.",
      price_ask:"Kelishiladi", pk_pop:"Ommabop", pk_cta:"Demo olish",
      pk_start_l:"1 000 qo'ng'iroqgacha / oy", pk_biz_l:"5 000 qo'ng'iroqgacha / oy", pk_ent_l:"Cheklanmagan hajm",
      pk_f1:"100% transkripsiya + baho", pk_f2:"Risk va reglament nazorati", pk_f3:"Transkript bo'yicha qidiruv",
      pk_f4:"Start dagi hamma narsa", pk_f5:"Sotuv analitikasi + signallar", pk_f6:"Operatorlar bo'yicha dashboard", pk_f7:"CRM integratsiya",
      pk_f8:"Biznes dagi hamma narsa", pk_f9:"Individual mezonlar va integratsiya", pk_f10:"Shaxsiy menejer",
      price_note:"Aniq narx qo'ng'iroqlar hajmi va telefoniyangizga bog'liq — demoda hisoblab beramiz.",
      cta_eyebrow:"Demo", cta_title:"Taxmin qilishni bas qiling. <em>Nazoratni qo'lga oling.</em>",
      cta_sub:"Qo'ng'iroqlar analitikasini bir kundan kamroq vaqtda ishga tushiramiz. Birinchi demo — bepul.",
      cta_btn:"Demoga yozilish",
      cb1:"Bir kundan kam ishga tushirish", cb2:"100% qo'ng'iroq nazoratda", cb3:"Jarayonlarga o'zgarishsiz", cb4:"RU va UZ tilida qo'llab-quvvatlash",
      f_tag:"Sotuv bo'limining 100% qo'ng'irog'ini tinglaydigan va yo'qotishlarni topadigan AI-analitika.",
      f_page:"Sahifa", foot_contact:"Bog'lanish", foot_rights:"© 2026 Techna. Barcha huquqlar himoyalangan.", foot_loc:"Toshkent, O'zbekiston",
      form_title:"Demoga yozilish", form_sub:"Qo'ng'iroqlar analitikasi demosi bepul. Raqamingizni qoldiring — 1 ish kuni ichida bog'lanamiz.",
      form_name:"Ismingiz", form_errname:"Ismingizni kiriting", form_phone:"Telefon raqam", form_errphone:"To'g'ri raqam kiriting",
      form_pbx:"Qaysi telefoniyadan foydalanasiz?", form_pbx_other:"Boshqa / bilmayman",
      form_send:"Demoga yozilish", form_or:"yoki", form_tg:"Telegramda yozing", form_note:"Raqamingiz uchinchi shaxslarga berilmaydi",
      ok_h:"Qabul qilindi", ok_sub:"1 ish kuni ichida bog'lanamiz.", ok_tg:"Hoziroq Telegramda yozing",
      fab_online:"onlayn · darrov javob beradi", fab_msg:"Savolingiz bormi? Telegramda darrov javob beramiz 👋",
      fab_write:"Telegramda yozish", fab_teaser:"Salom! 👋 Qo'ng'iroqlar analitikasi haqida savolingiz bormi? Yozing!"
    },
    ru:{
      nav_problem:"Проблема", nav_features:"Возможности", nav_how:"Как работает", nav_price:"Тарифы",
      intro_hi:"Добро пожаловать", intro_sub:"AI-аналитика звонков",
      prod_now:"Здесь", prod_bot_t:"Bot Messages AI", prod_bot_d:"AI-ответы в Instagram и Telegram",
      prod_voice_t:"Voice Analytics", prod_voice_d:"AI-анализ 100% звонков",
      prod_calls_t:"Outgoing Calls AI", prod_calls_d:"Исходящие звонки AI-голосом",
      cta_try:"Смотреть демо", cta_try_plain:"Смотреть демо",
      hero_eyebrow:"Аналитика звонков · AI",
      hero_lead:"Не 2% выборка вручную — 100% звонков отдела продаж. AI расшифровывает, оценивает и показывает, где именно вы теряете деньги.",
      hero_how:"В чём проблема",
      hero_trust1:"Подключение за <b>30 минут</b>", hero_trust2:"Первые инсайты — через час",
      vp_title:"Обзор качества звонков", vp_sub:"Сводный анализ всех звонков: продажи и поддержка.",
      vp_badge:"Все звонки", vp_ring:"Средний балл", vp_succ:"УСПЕШНОСТЬ", vp_of:"из",
      vt_all:"Все", vt_sale:"Продажа", vt_call:"Перезвон", vt_push:"Дожим", vt_serv:"Сервис", vt_compl:"Жалобы",
      vp_k1:"Проанализировано", vp_k2:"Решено успешно", vp_k3:"Комплаенс", vp_k4:"Требуют проверки", vp_vs:"vs. пред. период",
      vp_out:"Исходы обращений", vp_l1:"Перезвонить", vp_l2:"Отказ", vp_l3:"Решено", vp_l4:"Назначен визит",
      vp_foot:"Пример интерфейса · цифры условные",
      cr_eyebrow:"Аналитика по критериям", cr_title:"Видно, <em>что западает</em> — и у кого.",
      cr_lead:"Каждый критерий скрипта — с баллом, долей прохождения и разбивкой по операторам. Сразу ясно, где учить команду.",
      cr_h:"Аналитика по критериям", cr_pack:"Продажа", cr_sub:"Показатели эффективности по критериям оценки звонков", cr_xls:"Выгрузить XLS",
      cr_k1:"Средний балл", cr_k2:"Доля прохождения", cr_k3:"Критериев", cr_k4:"Операторов",
      cr_rank:"Рейтинг критериев", cr_rank_s:"Отсортирован по среднему баллу",
      cr_c_crit:"Критерий", cr_c_score:"Балл", cr_c_pass:"Прохождение", cr_c_calls:"Звонков",
      cr_dist:"Распределение оценок", cr_dist_s:"Отлично / Хорошо / Удов. / Плохо", cr_calls:"звонков",
      cr_lg1:"Отлично (≥80%)", cr_lg2:"Хорошо (60-79%)", cr_lg3:"Удов. (40-59%)", cr_lg4:"Плохо (<40%)",
      cr_coach:"Возможности для коучинга", cr_best:"Лучшие показатели",
      cr_ops:"Сравнение операторов по критериям", cr_ops_s:"Средний балл по каждому критерию для каждого оператора", cr_op:"Оператор",
      crit_dialog:"Управление диалогом", crit_qual:"Квалификация", crit_price:"Озвучивание стоимости", crit_close:"Закрытие",
      crit_present:"Презентация продукта", crit_needs:"Выявление потребностей", crit_greet:"Приветствие", crit_next:"Следующий шаг",
      crit_obj:"Работа с возражениями", crit_trial:"Предложение пробного действия", crit_invite:"Приглашение на встречу",
      live_eyebrow:"Разбор звонка", live_title:"Каждый звонок — <em>расшифрован и оценён.</em>",
      live_lead:"AI слушает запись, размечает ключевые моменты и выставляет баллы по вашим критериям.",
      lc_out:"Исходящий", lc_cat:"Сервисная поддержка", lc_pass:"Пройден", lc_hotlead:"Горячий лид", lc_editflags:"Изменить флаги",
      lc_tab1:"Анализ", lc_tab2:"Транскрипт", lc_tab3:"Детали",
      lc_summary:"Клиент обратился с просьбой помочь в разборке и переносе беговой дорожки из одной комнаты в другую. Оператор уточнил локацию, зафиксировал имя клиента и пообещал передать контакт мастерам для обратной связи по стоимости и времени работ.",
      lc_why:"Почему не 100%?", lc_crit:"Оценки по критериям",
      lc_c1:"Приветствие и контекст повторного контакта", lc_c2:"Подтверждение параметров встречи", lc_c3:"Ответ и помощь (включая оплату)",
      lc_c4:"Эмпатия и сервис", lc_c5:"Закрытие", lc_c6:"Управление диалогом",
      m_all:"Звонков под контролем", m_manual:"Слушали вручную раньше", m_hour:"До первого инсайта", m_hour_u:"час",
      m_night:"Подключение к телефонии", m_night_v:"30 мин",
      prob_eyebrow:"Проблема", prob_title:"Бизнес видит цифры, но <em>не понимает причины.</em>",
      prob_lead:"Ваша команда ведёт сотни звонков в день — вы видите результат, но не процесс.",
      prob_noreview:"нет оценки",
      prob1_t:"Звонки остаются неуслышанными", prob1_d:"Вручную вы слушаете 2% звонков. Остальные 98% — чёрный ящик, включая звонки, где ушли клиенты.",
      prob2_t:"Операторы работают вслепую", prob2_d:"Один выполняет план, другой проваливает. Причины неизвестны — никто не слушал.",
      prob3_t:"Деньги утекают незаметно", prob3_d:"Упущенная сделка здесь. Слабый скрипт там. В сумме — дыра в выручке, которую никто не видит.",
      cur_sum:"сум",
      why_eyebrow:"Что делает", why_title:"Контролирует, анализирует, <em>обучает.</em>",
      why_lead:"Слушает 100% звонков отдела продаж и показывает, где именно вы теряете деньги.",
      pf1_t:"100% звонков под контролем", pf1_d:"Не 2% выборка. Каждый звонок расшифрован и оценён.",
      pf2_t:"Контроль регламентов", pf2_d:"Нарушения и риски — на каждом звонке, автоматически.",
      pf3_t:"Аналитика продаж", pf3_d:"Сигналы к допродаже — прямо из транскриптов звонков.",
      pf4_t:"Поиск по транскриптам", pf4_d:"Любое слово или номер — за секунды по всем звонкам.",
      dash_t:"Менеджер · анализ звонков", dash_calls:"звонков сегодня", dash_flag:"помечено", dash_avg:"средний балл",
      dash_topic:"Продажи / Возврат · 5:12",
      dash_tag1:"Нарушение SLA по возврату", dash_tag2:"Сигнал к Pro-апгрейду", dash_tag3:"Упомянул конкурента",
      dash_s1:"Регламент", dash_s2:"Эмпатия", dash_s3:"Соответствие",
      int_eyebrow:"Интеграции", int_title:"Подключается к <em>вашей телефонии.</em>",
      int_lead:"Работает с популярными АТС Узбекистана и СНГ — или загружайте записи напрямую.",
      int_note:"— или загружайте записи звонков напрямую, без интеграции.",
      how_eyebrow:"Как работает", how_title:"Подключение за 30 минут. <em>Первые инсайты — через час.</em>",
      how_lead:"От нуля до работы — без изменений в процессах вашей команды.",
      hw1_t:"Подключение", hw1_d:"Подключаем вашу телефонию. Без изменений в процессах.", hw1_w:"Старт · 0 мин",
      hw2_t:"AI слушает", hw2_d:"Каждый звонок — расшифровка и оценка по вашим критериям.", hw2_w:"30 мин",
      hw3_t:"Ищет потери", hw3_d:"Риски, горячие лиды, причины отказов — на одном экране.", hw3_w:"1 час",
      hw4_t:"Действуете и растёте", hw4_d:"Конкретные рекомендации. Выручка растёт, нагрузка падает.", hw4_w:"далее",
      price_eyebrow:"Тарифы", price_title:"По объёму звонков. <em>Без скрытых платежей.</em>",
      price_lead:"Тариф зависит от количества звонков в месяц. Демо — бесплатно.",
      price_ask:"По запросу", pk_pop:"Популярный", pk_cta:"Получить демо",
      pk_start_l:"до 1 000 звонков / мес", pk_biz_l:"до 5 000 звонков / мес", pk_ent_l:"Неограниченный объём",
      pk_f1:"100% транскрипция + оценка", pk_f2:"Контроль рисков и регламентов", pk_f3:"Поиск по транскриптам",
      pk_f4:"Всё из Start", pk_f5:"Аналитика продаж + сигналы", pk_f6:"Дашборд по операторам", pk_f7:"Интеграция с CRM",
      pk_f8:"Всё из Бизнес", pk_f9:"Индивидуальные критерии и интеграция", pk_f10:"Персональный менеджер",
      price_note:"Точная цена зависит от объёма звонков и вашей телефонии — рассчитаем на демо.",
      cta_eyebrow:"Демо", cta_title:"Хватит гадать. <em>Возьмите контроль.</em>",
      cta_sub:"Запустим аналитику звонков меньше чем за день. Первое демо — бесплатно.",
      cta_btn:"Записаться на демо",
      cb1:"Запуск меньше чем за день", cb2:"100% звонков под контролем", cb3:"Без изменений в процессах", cb4:"Поддержка на RU и UZ",
      f_tag:"AI-аналитика, которая слушает 100% звонков отдела продаж и находит потери.",
      f_page:"Страницы", foot_contact:"Связаться", foot_rights:"© 2026 Techna. Все права защищены.", foot_loc:"Ташкент, Узбекистан",
      form_title:"Записаться на демо", form_sub:"Демо аналитики звонков — бесплатно. Оставьте номер — свяжемся в течение 1 рабочего дня.",
      form_name:"Ваше имя", form_errname:"Введите имя", form_phone:"Телефон", form_errphone:"Введите корректный номер",
      form_pbx:"Какую телефонию используете?", form_pbx_other:"Другая / не знаю",
      form_send:"Записаться на демо", form_or:"или", form_tg:"Написать в Telegram", form_note:"Ваш номер не передаётся третьим лицам",
      ok_h:"Принято", ok_sub:"Свяжемся в течение 1 рабочего дня.", ok_tg:"Написать в Telegram сейчас",
      fab_online:"онлайн · ответим сразу", fab_msg:"Есть вопрос? Ответим сразу в Telegram 👋",
      fab_write:"Написать в Telegram", fab_teaser:"Привет! 👋 Есть вопросы об аналитике звонков? Пишите!"
    },
    en:{
      nav_problem:"Problem", nav_features:"Features", nav_how:"How it works", nav_price:"Pricing",
      intro_hi:"Welcome", intro_sub:"AI call analytics",
      prod_now:"You are here", prod_bot_t:"Bot Messages AI", prod_bot_d:"AI replies on Instagram & Telegram",
      prod_voice_t:"Voice Analytics", prod_voice_d:"AI analysis of 100% of calls",
      prod_calls_t:"Outgoing Calls AI", prod_calls_d:"Outbound calls with an AI voice",
      cta_try:"Watch demo", cta_try_plain:"Watch demo",
      hero_eyebrow:"Call analytics · AI",
      hero_lead:"Not a 2% manual sample — 100% of your sales calls. AI transcribes, scores and shows exactly where you're losing money.",
      hero_how:"What's the problem",
      hero_trust1:"Connect in <b>30 minutes</b>", hero_trust2:"First insights in an hour",
      vp_title:"Call quality overview", vp_sub:"Combined analysis of all calls: sales and support.",
      vp_badge:"All calls", vp_ring:"Average score", vp_succ:"SUCCESS RATE", vp_of:"of",
      vt_all:"All", vt_sale:"Sales", vt_call:"Call back", vt_push:"Follow-up", vt_serv:"Service", vt_compl:"Complaints",
      vp_k1:"Analyzed", vp_k2:"Resolved successfully", vp_k3:"Compliance", vp_k4:"Need review", vp_vs:"vs. prev. period",
      vp_out:"Call outcomes", vp_l1:"Call back", vp_l2:"Refused", vp_l3:"Resolved", vp_l4:"Visit booked",
      vp_foot:"Sample interface · illustrative numbers",
      cr_eyebrow:"Criteria analytics", cr_title:"See <em>what's slipping</em> — and with whom.",
      cr_lead:"Every script criterion — with its score, pass rate and per-operator breakdown. It's instantly clear where to coach the team.",
      cr_h:"Criteria analytics", cr_pack:"Sales", cr_sub:"Performance metrics across call scoring criteria", cr_xls:"Export XLS",
      cr_k1:"Average score", cr_k2:"Pass rate", cr_k3:"Criteria", cr_k4:"Operators",
      cr_rank:"Criteria ranking", cr_rank_s:"Sorted by average score",
      cr_c_crit:"Criterion", cr_c_score:"Score", cr_c_pass:"Pass", cr_c_calls:"Calls",
      cr_dist:"Score distribution", cr_dist_s:"Excellent / Good / Fair / Poor", cr_calls:"calls",
      cr_lg1:"Excellent (≥80%)", cr_lg2:"Good (60-79%)", cr_lg3:"Fair (40-59%)", cr_lg4:"Poor (<40%)",
      cr_coach:"Coaching opportunities", cr_best:"Top performers",
      cr_ops:"Operator comparison by criteria", cr_ops_s:"Average score per criterion for each operator", cr_op:"Operator",
      crit_dialog:"Dialogue management", crit_qual:"Qualification", crit_price:"Stating the price", crit_close:"Closing",
      crit_present:"Product presentation", crit_needs:"Needs discovery", crit_greet:"Greeting", crit_next:"Next step",
      crit_obj:"Objection handling", crit_trial:"Trial action offer", crit_invite:"Meeting invitation",
      live_eyebrow:"Call breakdown", live_title:"Every call — <em>transcribed and scored.</em>",
      live_lead:"AI listens to the recording, marks the key moments and scores it by your criteria.",
      lc_out:"Outgoing", lc_cat:"Service support", lc_pass:"Passed", lc_hotlead:"Hot lead", lc_editflags:"Edit flags",
      lc_tab1:"Analysis", lc_tab2:"Transcript", lc_tab3:"Details",
      lc_summary:"The customer asked for help disassembling and moving a treadmill from one room to another. The operator clarified the location, recorded the customer's name and promised to pass the contact to technicians for follow-up on cost and timing.",
      lc_why:"Why not 100%?", lc_crit:"Criteria scores",
      lc_c1:"Greeting and repeat-contact context", lc_c2:"Confirming meeting details", lc_c3:"Answer and help (including payment)",
      lc_c4:"Empathy and service", lc_c5:"Closing", lc_c6:"Dialogue management",
      m_all:"Calls under control", m_manual:"Listened manually before", m_hour:"To first insight", m_hour_u:"hour",
      m_night:"Connect to telephony", m_night_v:"30 min",
      prob_eyebrow:"Problem", prob_title:"Business sees the numbers but <em>not the reasons.</em>",
      prob_lead:"Your team makes hundreds of calls a day — you see the result, not the process.",
      prob_noreview:"no review",
      prob1_t:"Calls go unheard", prob1_d:"Manually you listen to 2% of calls. The other 98% is a black box — including calls where customers walked away.",
      prob2_t:"Operators work blind", prob2_d:"One hits the plan, another misses it. The reasons are unknown — nobody listened.",
      prob3_t:"Money leaks unnoticed", prob3_d:"A lost deal here. A weak script there. Together — a hole in revenue no one sees.",
      cur_sum:"so'm",
      why_eyebrow:"What it does", why_title:"Controls, analyzes, <em>coaches.</em>",
      why_lead:"Listens to 100% of your sales calls and shows exactly where you're losing money.",
      pf1_t:"100% of calls under control", pf1_d:"Not a 2% sample. Every call is transcribed and scored.",
      pf2_t:"Compliance control", pf2_d:"Violations and risks — on every call, automatically.",
      pf3_t:"Sales analytics", pf3_d:"Upsell signals — straight from call transcripts.",
      pf4_t:"Transcript search", pf4_d:"Any word or number — across all calls in seconds.",
      dash_t:"Manager · call analysis", dash_calls:"calls today", dash_flag:"flagged", dash_avg:"average score",
      dash_topic:"Sales / Return · 5:12",
      dash_tag1:"Return SLA breached", dash_tag2:"Pro-upgrade signal", dash_tag3:"Mentioned a competitor",
      dash_s1:"Compliance", dash_s2:"Empathy", dash_s3:"Fit",
      int_eyebrow:"Integrations", int_title:"Connects to <em>your telephony.</em>",
      int_lead:"Works with popular PBX systems across Uzbekistan and the CIS — or upload recordings directly.",
      int_note:"— or upload call recordings directly, without integration.",
      how_eyebrow:"How it works", how_title:"Connect in 30 minutes. <em>First insights in an hour.</em>",
      how_lead:"From zero to running — with no changes to your team's processes.",
      hw1_t:"Connect", hw1_d:"We connect your telephony. No changes to your processes.", hw1_w:"Start · 0 min",
      hw2_t:"AI listens", hw2_d:"Every call — transcribed and scored by your criteria.", hw2_w:"30 min",
      hw3_t:"Finds losses", hw3_d:"Risks, hot leads, reasons for refusals — on one screen.", hw3_w:"1 hour",
      hw4_t:"You act and grow", hw4_d:"Concrete recommendations. Revenue grows, workload drops.", hw4_w:"onward",
      price_eyebrow:"Pricing", price_title:"By call volume. <em>No hidden fees.</em>",
      price_lead:"Your plan depends on monthly call volume. Demo — free.",
      price_ask:"On request", pk_pop:"Popular", pk_cta:"Get a demo",
      pk_start_l:"up to 1,000 calls / mo", pk_biz_l:"up to 5,000 calls / mo", pk_ent_l:"Unlimited volume",
      pk_f1:"100% transcription + scoring", pk_f2:"Risk & compliance control", pk_f3:"Transcript search",
      pk_f4:"Everything in Start", pk_f5:"Sales analytics + signals", pk_f6:"Per-operator dashboard", pk_f7:"CRM integration",
      pk_f8:"Everything in Business", pk_f9:"Custom criteria & integration", pk_f10:"Dedicated manager",
      price_note:"The exact price depends on call volume and your telephony — we'll calculate it on the demo.",
      cta_eyebrow:"Demo", cta_title:"Stop guessing. <em>Take control.</em>",
      cta_sub:"We'll launch call analytics in under a day. First demo — free.",
      cta_btn:"Book a demo",
      cb1:"Launch in under a day", cb2:"100% of calls under control", cb3:"No process changes", cb4:"Support in RU and UZ",
      f_tag:"AI analytics that listens to 100% of your sales calls and finds the losses.",
      f_page:"Pages", foot_contact:"Contact", foot_rights:"© 2026 Techna. All rights reserved.", foot_loc:"Tashkent, Uzbekistan",
      form_title:"Book a demo", form_sub:"Call analytics demo — free. Leave your number and we'll reach out within 1 business day.",
      form_name:"Your name", form_errname:"Enter your name", form_phone:"Phone", form_errphone:"Enter a valid number",
      form_pbx:"Which telephony do you use?", form_pbx_other:"Other / not sure",
      form_send:"Book a demo", form_or:"or", form_tg:"Message on Telegram", form_note:"Your number is not shared with third parties",
      ok_h:"Received", ok_sub:"We'll reach out within 1 business day.", ok_tg:"Message on Telegram now",
      fab_online:"online · instant reply", fab_msg:"Got a question? We reply instantly on Telegram 👋",
      fab_write:"Message on Telegram", fab_teaser:"Hi! 👋 Questions about call analytics? Message me!"
    }
  };

  let cur = localStorage.getItem('techna_lang') || 'uz';
  window.__lang = cur;

  function apply(lang){
    const d=T[lang]||T.uz;
    document.querySelectorAll('[data-i18n]').forEach(el=>{
      const k=el.getAttribute('data-i18n'); if(d[k]!=null) el.textContent=d[k];
    });
    document.querySelectorAll('[data-i18n-html]').forEach(el=>{
      const k=el.getAttribute('data-i18n-html'); if(d[k]!=null) el.innerHTML=d[k];
    });
    document.documentElement.lang = lang;
    document.querySelectorAll('#lang button').forEach(b=>b.classList.toggle('on',b.dataset.lang===lang));
    window.__lang=lang;
    localStorage.setItem('techna_lang',lang);
    window.dispatchEvent(new CustomEvent('langchange',{detail:lang}));
  }

  document.querySelectorAll('#lang button').forEach(b=>{
    b.addEventListener('click',()=>apply(b.dataset.lang));
  });

  apply(cur);
  window.__applyLang=apply;
})();
</script>
<script>
// ── модал: демо-форма ──
(function(){
  const TG_USER=window.TECHNA_TG;
  const mask=document.getElementById('mask');
  const modal=document.getElementById('modal');
  const mForm=document.getElementById('mForm');
  const mOk=document.getElementById('mOk');
  const fName=document.getElementById('fName');
  const fPhone=document.getElementById('fPhone');
  const fCh=document.getElementById('fCh');
  const eName=document.getElementById('eName');
  const ePhone=document.getElementById('ePhone');
  let lastFocus=null;

  function open(){
    lastFocus=document.activeElement;
    mask.classList.add('on');
    document.body.style.overflow='hidden';
    setTimeout(()=>fName.focus(),320);
  }
  function close(){
    mask.classList.remove('on');
    document.body.style.overflow='';
    lastFocus&&lastFocus.focus();
    setTimeout(()=>{ mForm.style.display='';mOk.style.display='none'; },300);
  }

  // все CTA открывают модал (по href, а не по тексту)
  document.querySelectorAll('a[href="#cta"]').forEach(a=>{
    a.addEventListener('click',e=>{e.preventDefault();open()});
  });
  document.getElementById('mClose').addEventListener('click',close);
  mask.addEventListener('click',e=>{if(e.target===mask)close()});
  addEventListener('keydown',e=>{if(e.key==='Escape'&&mask.classList.contains('on'))close()});

  // маска телефона +998 XX XXX XX XX
  fPhone.addEventListener('input',()=>{
    let d=fPhone.value.replace(/\D/g,'');
    if(d.startsWith('998')) d=d.slice(3);
    d=d.slice(0,9);
    let out='+998';
    if(d.length) out+=' '+d.slice(0,2);
    if(d.length>2) out+=' '+d.slice(2,5);
    if(d.length>5) out+=' '+d.slice(5,7);
    if(d.length>7) out+=' '+d.slice(7,9);
    fPhone.value=out;
    fPhone.classList.remove('bad'); ePhone.classList.remove('on');
  });
  fPhone.addEventListener('focus',()=>{ if(!fPhone.value) fPhone.value='+998 '; });
  fName.addEventListener('input',()=>{fName.classList.remove('bad');eName.classList.remove('on')});

  const digits=v=>v.replace(/\D/g,'');

  document.getElementById('fSend').addEventListener('click',()=>{
    let ok=true;
    if(fName.value.trim().length<2){ fName.classList.add('bad');eName.classList.add('on');ok=false; }
    if(digits(fPhone.value).length!==12){ fPhone.classList.add('bad');ePhone.classList.add('on');ok=false; }
    if(!ok){ (fName.classList.contains('bad')?fName:fPhone).focus(); return; }

    window.sendLead && window.sendLead({
      source: "Voice — форма демо",
      name: fName.value.trim(),
      phone: fPhone.value.trim(),
      pbx: fCh.value
    });

    const lang=(window.__lang||'uz');
    const greet={
      uz:"Assalomu alaykum! Techna Voice — qo'ng'iroqlar analitikasi haqida ma'lumot olmoqchiman. Qanday ulash mumkin?",
      ru:"Здравствуйте! Хочу получить информацию о Techna Voice — аналитике звонков. Как можно подключить?",
      en:"Hello! I'd like to get information about Techna Voice — call analytics. How can I connect it?"
    };
    const msg=encodeURIComponent(greet[lang]||greet.uz);

    mForm.style.display='none';
    mOk.style.display='';
    mOk.querySelectorAll('a').forEach(a=>a.href='https://t.me/'+TG_USER+'?text='+msg);
  });
})();
</script>
<script>
// ── меню продуктов ──
(function(){
  const prod=document.getElementById('prod');
  const btn=document.getElementById('prodBtn');
  if(!prod||!btn) return;
  function close(){ prod.classList.remove('open'); btn.setAttribute('aria-expanded','false'); }
  btn.addEventListener('click',e=>{
    e.stopPropagation();
    const open=prod.classList.toggle('open');
    btn.setAttribute('aria-expanded', open?'true':'false');
  });
  document.addEventListener('click',e=>{ if(!prod.contains(e.target)) close(); });
  addEventListener('keydown',e=>{ if(e.key==='Escape') close(); });
})();


// ── мобильное меню (бургер) ──
(function(){
  const burger=document.getElementById('burger');
  const mnav=document.getElementById('mobileNav');
  if(!burger||!mnav) return;
  function close(){ burger.classList.remove('open'); mnav.classList.remove('open'); burger.setAttribute('aria-expanded','false'); }
  function toggle(){
    const open=mnav.classList.toggle('open');
    burger.classList.toggle('open',open);
    burger.setAttribute('aria-expanded', open?'true':'false');
  }
  burger.addEventListener('click',e=>{ e.stopPropagation(); toggle(); });
  mnav.querySelectorAll('a').forEach(a=>a.addEventListener('click',close));
  document.addEventListener('click',e=>{ if(!mnav.contains(e.target) && !burger.contains(e.target)) close(); });
  addEventListener('keydown',e=>{ if(e.key==='Escape') close(); });
  // при возврате на десктоп — закрыть, чтобы панель не висела
  addEventListener('resize',()=>{ if(innerWidth>940) close(); });
})();


// ── переключатель темы ──
(function(){
  const KEY='techna_theme';
  const saved=localStorage.getItem(KEY)||'light';
  document.documentElement.setAttribute('data-theme',saved);
  const btn=document.getElementById('themeBtn');
  if(btn) btn.addEventListener('click',()=>{
    const cur=document.documentElement.getAttribute('data-theme')==='dark'?'light':'dark';
    document.documentElement.setAttribute('data-theme',cur);
    localStorage.setItem(KEY,cur);
  });
})();
</script>
<script>
/* welcome intro: блокируем скролл, убираем оверлей после анимации */
(function(){
  const intro=document.getElementById('intro');
  if(!intro) return;
  document.documentElement.style.overflow='hidden';
  const reduce=matchMedia('(prefers-reduced-motion:reduce)').matches;
  const dur=reduce?2100:3300;   // общая длительность до полного ухода
  setTimeout(()=>{
    intro.classList.add('done');
    document.documentElement.style.overflow='';
  }, dur);
  // на всякий случай — клик по заставке пропускает её
  intro.addEventListener('click',()=>{
    intro.classList.add('done');
    document.documentElement.style.overflow='';
  });
})();
</script>
<script>
/* плавающий бот Текна: клик → окошко с переходом в Telegram */
(function(){
  const fab=document.getElementById('fab');
  if(!fab) return;
  const btn=document.getElementById('fabBtn');
  const closeX=document.getElementById('fabX');
  const tg=document.getElementById('fabTg');
  const TG_USER_FAB=window.TECHNA_TG;
  const lang=window.__lang||'uz';
  const line=(lang==='ru'?'Здравствуйте! У меня вопрос по Techna AI'
            :lang==='en'?'Hi! I have a question about Techna AI'
            :'Salom! Techna AI bo\'yicha savolim bor');
  function setTg(){
    const l=window.__lang||'uz';
    const t=(l==='ru'?'Здравствуйте! У меня вопрос по Techna AI'
           :l==='en'?'Hi! I have a question about Techna AI'
           :'Salom! Techna AI bo\'yicha savolim bor');
    tg.href='https://t.me/'+TG_USER_FAB+'?text='+encodeURIComponent(t);
  }
  setTg();
  window.addEventListener('langchange',setTg);

  function toggle(){ fab.classList.toggle('open'); fab.classList.remove('teaser-on'); }
  function close(){ fab.classList.remove('open'); }
  btn.addEventListener('click',toggle);
  closeX.addEventListener('click',e=>{ e.stopPropagation(); close(); });
  document.addEventListener('keydown',e=>{ if(e.key==='Escape') close(); });
  document.addEventListener('click',e=>{ if(!fab.contains(e.target)) close(); });

  // тизер-облачко через 10 секунд
  const teaser=document.getElementById('fabTeaser');
  const teaserX=document.getElementById('fabTeaserX');
  let teaserShown=false;
  try{ if(sessionStorage.getItem('fabTeaserClosed')) teaserShown=true; }catch(e){}
  function showTeaser(){
    if(teaserShown || fab.classList.contains('open')) return;
    teaserShown=true;
    fab.classList.add('teaser-on');
    // сам скрыть через 12 сек, если не тронули
    setTimeout(()=>fab.classList.remove('teaser-on'), 12000);
  }
  function hideTeaser(){
    fab.classList.remove('teaser-on');
    try{ sessionStorage.setItem('fabTeaserClosed','1'); }catch(e){}
  }
  // клик по облачку → открыть окошко
  teaser.addEventListener('click',e=>{
    if(e.target===teaserX || teaserX.contains(e.target)) return;
    fab.classList.remove('teaser-on'); fab.classList.add('open');
  });
  teaser.addEventListener('keydown',e=>{ if(e.key==='Enter'){ fab.classList.remove('teaser-on'); fab.classList.add('open'); } });
  teaserX.addEventListener('click',e=>{ e.stopPropagation(); hideTeaser(); });
  setTimeout(showTeaser, 10000);
})();
</script>

</body>
</html>
