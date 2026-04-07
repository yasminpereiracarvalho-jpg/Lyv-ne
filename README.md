[index.html](https://github.com/user-attachments/files/26554242/index.html)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<meta name="theme-color" content="#C9A96E">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="default">
<meta name="apple-mobile-web-app-title" content="Lyvène">
<meta name="description" content="Lyvène Experience — A jornada completa da paciente">
<title>Lyvène Experience</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Jost:wght@300;400;500&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0;-webkit-tap-highlight-color:transparent}
:root{
  --gold:#C9A96E;--gold-light:#E8D5B0;--gold-dark:#9A7A4A;
  --cream:#F5EFE6;--cream2:#FAF7F2;
  --ink:#1A1A1A;--ink2:#4A4A4A;--ink3:#8A8A8A;
  --white:#FFFFFF;--surface:#F8F5F0;
  --r:18px;--rs:12px;
}
html{height:100%;overflow:hidden}
body{font-family:'Jost',sans-serif;background:#e8e0d8;color:var(--ink);height:100%;display:flex;justify-content:center;align-items:center;overflow:hidden}

/* APP SHELL */
.app{width:100%;max-width:430px;height:100%;max-height:100vh;background:var(--white);position:relative;overflow:hidden;display:flex;flex-direction:column;box-shadow:0 0 60px rgba(0,0,0,0.12)}
@media(min-width:500px){
  .app{max-height:900px;border-radius:36px;box-shadow:0 32px 100px rgba(0,0,0,0.18)}
  body{background:linear-gradient(135deg,#e8e0d4,#d4c8b8)}
}

/* SCREENS */
.screen{display:none;flex-direction:column;flex:1;overflow:hidden}
.screen.active{display:flex}
.scroll-area{flex:1;overflow-y:auto;padding-bottom:12px;-webkit-overflow-scrolling:touch;overscroll-behavior:contain}
.scroll-area::-webkit-scrollbar{display:none}

/* TOP BAR */
.topbar{padding:52px 20px 14px;background:var(--white);border-bottom:0.5px solid #f0e8de;flex-shrink:0}
@media(min-width:500px){.topbar{padding-top:20px}}
.topbar h1{font-family:'Cormorant Garamond',serif;font-size:22px;font-weight:400;letter-spacing:2px;color:var(--gold-dark)}
.topbar .sub{font-size:10px;color:var(--ink3);letter-spacing:1.5px;text-transform:uppercase;margin-bottom:2px}
.topbar-row{display:flex;justify-content:space-between;align-items:center}

/* BOTTOM NAV */
.bottom-nav{background:var(--white);border-top:0.5px solid #e8dfd3;padding:10px 0 max(14px, env(safe-area-inset-bottom));display:flex;justify-content:space-around;align-items:center;flex-shrink:0}
.nav-item{display:flex;flex-direction:column;align-items:center;gap:3px;cursor:pointer;padding:4px 10px;border-radius:12px;transition:all 0.2s;border:none;background:none}
.nav-item svg{width:22px;height:22px;stroke:var(--ink3);fill:none;stroke-width:1.5;stroke-linecap:round;stroke-linejoin:round;transition:stroke 0.2s}
.nav-item span{font-size:9px;color:var(--ink3);letter-spacing:0.5px;font-family:'Jost',sans-serif;transition:color 0.2s}
.nav-item.active svg{stroke:var(--gold)}
.nav-item.active span{color:var(--gold)}
.nav-item:active{transform:scale(0.92)}

/* CARDS */
.card{background:var(--white);border:0.5px solid #e8dfd3;border-radius:var(--r);padding:18px;margin:0 16px 14px}
.card-gold{background:linear-gradient(135deg,#C9A96E 0%,#A07840 100%);color:white;border:none}
.card-dark{background:#1A1A1A;color:white;border:none}
.card-cream{background:var(--cream);border:0.5px solid #e0d4be}

/* TYPOGRAPHY */
.label{font-size:10px;letter-spacing:1.5px;text-transform:uppercase;color:var(--ink3);font-weight:400}
.value{font-size:15px;color:var(--ink);font-weight:400}
.caption{font-size:12px;color:var(--ink3);line-height:1.5}
.section-title{font-size:10px;letter-spacing:2px;text-transform:uppercase;color:var(--ink3);padding:0 16px;margin-bottom:10px;margin-top:6px;display:block}

/* BUTTONS */
.btn{display:inline-flex;align-items:center;justify-content:center;gap:8px;border-radius:50px;font-size:13px;font-family:'Jost',sans-serif;letter-spacing:0.5px;cursor:pointer;transition:all 0.2s;border:none;font-weight:400}
.btn-gold{background:var(--gold);color:white;padding:12px 24px;font-weight:500}
.btn-gold:active{background:var(--gold-dark)}
.btn-outline{background:transparent;border:1px solid var(--gold);color:var(--gold-dark);padding:10px 20px}
.btn-ghost{background:transparent;border:1px solid #e0d4be;color:var(--ink2);padding:10px 20px;font-size:12px}
.btn:active{transform:scale(0.96)}
.btn:disabled{opacity:0.4;cursor:not-allowed;transform:none}

/* PROGRESS BAR */
.prog-bar{height:4px;background:#f0e8de;border-radius:2px;overflow:hidden}
.prog-fill{height:100%;background:var(--gold);border-radius:2px;transition:width 0.6s ease}

/* BADGE */
.badge{display:inline-block;padding:3px 10px;border-radius:20px;font-size:10px;letter-spacing:0.5px;font-family:'Jost',sans-serif}
.badge-gold{background:#f5e8d0;color:#9A7A4A}
.badge-green{background:#e0f0e8;color:#2d6a4a}
.badge-pink{background:#f5e0ec;color:#8a3058}
.badge-blue{background:#e0eaf5;color:#2d4a8a}

/* AVATAR */
.avatar{border-radius:50%;background:linear-gradient(135deg,var(--gold-light),var(--gold));display:flex;align-items:center;justify-content:center;font-family:'Cormorant Garamond',serif;color:white;font-weight:600;flex-shrink:0}

/* CHECKLIST */
.check-item{display:flex;align-items:center;gap:12px;padding:12px 0;border-bottom:0.5px solid #f5f0e8;cursor:pointer}
.check-item:last-child{border-bottom:none}
.check-box{width:22px;height:22px;border-radius:6px;border:1.5px solid #d4c4a8;display:flex;align-items:center;justify-content:center;flex-shrink:0;transition:all 0.25s}
.check-box.done{background:var(--gold);border-color:var(--gold)}
.check-box.done::after{content:'✓';color:white;font-size:12px;line-height:1}
.check-text{font-size:14px;color:var(--ink);transition:all 0.2s}
.check-text.done{text-decoration:line-through;color:var(--ink3)}

/* CHAT */
.bubble{max-width:80%;padding:10px 14px;border-radius:18px;font-size:13px;line-height:1.55;margin:3px 0}
.bubble-sent{background:var(--gold);color:white;border-bottom-right-radius:4px;align-self:flex-end}
.bubble-recv{background:#f5f0e8;color:var(--ink);border-bottom-left-radius:4px;align-self:flex-start}

/* PROCEDURE CARDS */
.proc-card{display:flex;align-items:center;gap:12px;padding:14px;border:0.5px solid #e8dfd3;border-radius:14px;margin:0 16px 10px;cursor:pointer;transition:all 0.2s;background:white}
.proc-card:active{background:var(--cream);transform:scale(0.98)}
.proc-card.selected{border-color:var(--gold);background:var(--cream)}
.proc-icon{width:44px;height:44px;border-radius:12px;background:var(--cream);display:flex;align-items:center;justify-content:center;flex-shrink:0}
.proc-icon svg{width:22px;height:22px;stroke:var(--gold-dark);fill:none;stroke-width:1.5;stroke-linecap:round;stroke-linejoin:round}

/* STEP DOTS */
.steps{display:flex;gap:6px;padding:14px 16px 0}
.step-dot{flex:1;height:3px;border-radius:2px;background:#f0e8de;transition:background 0.35s}
.step-dot.active{background:var(--gold)}

/* SCROLL HORIZONTAL */
.scroll-h{display:flex;gap:12px;padding:0 16px;overflow-x:auto;scrollbar-width:none;-webkit-overflow-scrolling:touch}
.scroll-h::-webkit-scrollbar{display:none}

/* TIME SLOTS */
.slot{padding:9px 16px;border:1px solid #e8dfd3;border-radius:22px;font-size:13px;cursor:pointer;transition:all 0.2s;white-space:nowrap;font-family:'Jost',sans-serif;background:white}
.slot.selected{background:var(--ink);color:white;border-color:var(--ink)}
.slot.unavail{opacity:0.3;cursor:not-allowed}
.slot:not(.unavail):active{transform:scale(0.95)}

/* TOGGLES */
.toggle-row{display:flex;align-items:center;justify-content:space-between;padding:13px 0;border-bottom:0.5px solid #f5f0e8}
.toggle{width:42px;height:24px;border-radius:12px;background:#e0d4be;position:relative;cursor:pointer;transition:background 0.3s;flex-shrink:0}
.toggle.on{background:var(--gold)}
.toggle::after{content:'';width:18px;height:18px;background:white;border-radius:50%;position:absolute;top:3px;left:3px;transition:left 0.3s;box-shadow:0 1px 4px rgba(0,0,0,0.15)}
.toggle.on::after{left:21px}

/* INPUT */
.inp{width:100%;padding:12px 16px;border:1px solid #e0d4be;border-radius:14px;font-family:'Jost',sans-serif;font-size:14px;color:var(--ink);background:white;outline:none;transition:border-color 0.2s}
.inp:focus{border-color:var(--gold)}
select.inp{appearance:none;-webkit-appearance:none;cursor:pointer}

/* CHIPS */
.chip{padding:8px 16px;border:1px solid #e0d4be;border-radius:22px;font-size:12px;cursor:pointer;white-space:nowrap;background:white;transition:all 0.2s;font-family:'Jost',sans-serif}
.chip.sel{background:var(--ink);color:white;border-color:var(--ink)}
.chip:active{transform:scale(0.95)}

/* DIVIDER */
.divider{height:0.5px;background:#f0e8de;margin:2px 0}

/* EMOJI RATING */
.emoji-btn{font-size:24px;padding:9px 11px;border-radius:14px;border:1.5px solid #e8dfd3;background:white;cursor:pointer;transition:all 0.2s}
.emoji-btn.selected{border-color:var(--gold);background:var(--cream);transform:scale(1.15)}

/* COMPARISON SLIDER */
.compare-wrap{position:relative;overflow:hidden;border-radius:18px;aspect-ratio:1/1.1;background:#f0e8de;touch-action:none;user-select:none}
.compare-after{position:absolute;inset:0;background:linear-gradient(135deg,#e8d5c0,#c8a878);display:flex;align-items:center;justify-content:center}
.compare-before{position:absolute;top:0;left:0;bottom:0;width:50%;background:linear-gradient(135deg,#f5ede0,#e0c8a8);display:flex;align-items:center;justify-content:center;overflow:hidden}
.compare-divider{position:absolute;top:0;bottom:0;width:2px;background:white;cursor:ew-resize;z-index:5;left:50%}
.compare-handle{position:absolute;top:50%;transform:translate(-50%,-50%);width:34px;height:34px;border-radius:50%;background:white;display:flex;align-items:center;justify-content:center;box-shadow:0 2px 10px rgba(0,0,0,0.18)}
.face-emoji{font-size:72px;line-height:1;pointer-events:none;user-select:none}
.photo-label{font-size:10px;letter-spacing:1px;text-transform:uppercase;color:white;background:rgba(0,0,0,0.38);padding:5px 12px;border-radius:8px;position:absolute;bottom:12px}

/* PHOTO GRID */
.photo-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:6px}
.photo-slot{aspect-ratio:1;border-radius:10px;overflow:hidden;display:flex;align-items:center;justify-content:center;font-size:26px}

/* SUCCESS OVERLAY */
.success-overlay{position:absolute;inset:0;background:rgba(20,16,12,0.9);z-index:500;display:none;align-items:center;justify-content:center;flex-direction:column;gap:22px;backdrop-filter:blur(4px)}
.success-overlay.show{display:flex}
@keyframes pop{from{transform:scale(0);opacity:0}to{transform:scale(1);opacity:1}}
.success-circle{width:84px;height:84px;border-radius:50%;background:var(--gold);display:flex;align-items:center;justify-content:center;animation:pop 0.45s cubic-bezier(.175,.885,.32,1.275) forwards}
</style>
</head>
<body>
<div class="app" id="app">

  <!-- SUCCESS OVERLAY -->
  <div class="success-overlay" id="successOverlay">
    <div class="success-circle">
      <svg width="38" height="38" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>
    </div>
    <p style="color:white;font-family:'Cormorant Garamond',serif;font-size:28px;font-weight:300;text-align:center">Agendamento confirmado!</p>
    <p style="color:var(--gold-light);font-size:13px;letter-spacing:1px;text-align:center;padding:0 32px;line-height:1.6">Você receberá uma mensagem no WhatsApp com todos os detalhes ✨</p>
    <button class="btn btn-outline" style="border-color:var(--gold-light);color:var(--gold-light);margin-top:8px;padding:12px 28px" onclick="closeSuccess()">Voltar ao início</button>
  </div>

  <!-- ══════════════ HOME ══════════════ -->
  <div class="screen active" id="screen-home">
    <div class="topbar topbar-row">
      <div>
        <div class="sub">Lyvène Experience</div>
        <h1>Dashboard</h1>
      </div>
      <div class="avatar" style="width:42px;height:42px;font-size:17px">SM</div>
    </div>
    <div class="scroll-area" style="padding-top:18px">

      <!-- Welcome -->
      <div class="card card-gold" style="margin:0 16px 18px;position:relative;overflow:hidden">
        <div style="position:absolute;right:-24px;top:-24px;width:110px;height:110px;border-radius:50%;background:rgba(255,255,255,0.07)"></div>
        <div style="position:absolute;right:24px;bottom:-36px;width:70px;height:70px;border-radius:50%;background:rgba(255,255,255,0.05)"></div>
        <p style="font-size:10px;letter-spacing:2px;opacity:0.75;margin-bottom:5px">BOA TARDE</p>
        <p style="font-family:'Cormorant Garamond',serif;font-size:28px;font-weight:300;margin-bottom:6px">Sofia Mendes ✨</p>
        <p style="font-size:13px;opacity:0.85;line-height:1.5">Sua jornada de beleza continua aqui</p>
      </div>

      <!-- Next Appointment -->
      <span class="section-title">Próximo Agendamento</span>
      <div class="card">
        <div style="display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:14px">
          <div>
            <p class="label" style="margin-bottom:3px">Procedimento</p>
            <p style="font-size:16px;font-weight:500;color:var(--ink)">Bioestimulador de Colágeno</p>
          </div>
          <span class="badge badge-gold">Confirmado</span>
        </div>
        <div style="display:flex;gap:24px;margin-bottom:16px">
          <div><p class="label" style="margin-bottom:2px">Data</p><p class="value">14 Abr, Seg</p></div>
          <div><p class="label" style="margin-bottom:2px">Horário</p><p class="value">10h30</p></div>
          <div><p class="label" style="margin-bottom:2px">Profissional</p><p class="value">Dra. Lívia</p></div>
        </div>
        <div style="display:flex;gap:8px">
          <button class="btn btn-gold" style="flex:1;font-size:12px;padding:11px">Ver detalhes</button>
          <button class="btn btn-ghost" style="font-size:12px;padding:11px">Reagendar</button>
        </div>
      </div>

      <!-- Reminders -->
      <span class="section-title" style="margin-top:4px">Lembretes</span>
      <div class="scroll-h" style="padding-bottom:4px">
        <div style="min-width:210px;background:#f7f0fb;border-radius:18px;padding:16px;border:0.5px solid #e2d0ec;flex-shrink:0">
          <p style="font-size:10px;letter-spacing:1.5px;text-transform:uppercase;color:#7B3FA0;margin-bottom:8px">Botox</p>
          <p style="font-size:13px;color:#4a2060;margin-bottom:3px">Última: 20 Jan 2025</p>
          <p style="font-size:13px;color:#4a2060;font-weight:500;margin-bottom:12px">Próxima: Abr 2025</p>
          <span class="badge" style="background:#ead5f7;color:#7B3FA0">Retocar em breve</span>
        </div>
        <div style="min-width:210px;background:#edf7f2;border-radius:18px;padding:16px;border:0.5px solid #b8dece;flex-shrink:0">
          <p style="font-size:10px;letter-spacing:1.5px;text-transform:uppercase;color:#2d7a4a;margin-bottom:8px">Bioestimulador</p>
          <p style="font-size:13px;color:#1a4a2e;margin-bottom:4px">Sessão 2 de 3</p>
          <div class="prog-bar" style="margin-bottom:12px"><div class="prog-fill" style="width:66%"></div></div>
          <span class="badge" style="background:#bce8d0;color:#2d7a4a">Em andamento</span>
        </div>
        <div style="min-width:210px;background:#faf3e8;border-radius:18px;padding:16px;border:0.5px solid #e4d0b0;flex-shrink:0">
          <p style="font-size:10px;letter-spacing:1.5px;text-transform:uppercase;color:#9A7A4A;margin-bottom:8px">Skincare hoje</p>
          <p style="font-size:13px;color:#5a4020;margin-bottom:4px">3 de 6 itens</p>
          <div class="prog-bar" style="margin-bottom:12px"><div class="prog-fill" style="width:50%"></div></div>
          <span class="badge badge-gold">Em progresso</span>
        </div>
      </div>

      <!-- Protocol -->
      <span class="section-title" style="margin-top:18px">Protocolo Ativo</span>
      <div class="card card-dark">
        <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:14px">
          <div>
            <p style="font-size:10px;letter-spacing:1.5px;opacity:0.5;text-transform:uppercase;margin-bottom:5px">Protocolo</p>
            <p style="font-family:'Cormorant Garamond',serif;font-size:22px;font-weight:300;color:var(--gold-light)">Renovação Completa</p>
          </div>
          <div style="text-align:center;width:54px;height:54px;border-radius:50%;border:2.5px solid var(--gold);display:flex;align-items:center;justify-content:center;flex-direction:column;flex-shrink:0">
            <p style="font-size:16px;font-weight:500;color:var(--gold);line-height:1">72%</p>
            <p style="font-size:8px;opacity:0.45;color:white">feito</p>
          </div>
        </div>
        <div class="prog-bar" style="background:rgba(255,255,255,0.12);margin-bottom:14px"><div class="prog-fill" style="width:72%"></div></div>
        <div style="display:flex;gap:6px;flex-wrap:wrap">
          <span class="badge badge-gold">Bioestimulador</span>
          <span class="badge" style="background:rgba(255,255,255,0.1);color:rgba(255,255,255,0.65)">Skinbooster</span>
          <span class="badge" style="background:rgba(255,255,255,0.1);color:rgba(255,255,255,0.65)">Botox</span>
        </div>
      </div>

      <!-- Quick Actions -->
      <span class="section-title">Ações Rápidas</span>
      <div style="display:grid;grid-template-columns:1fr 1fr;gap:10px;padding:0 16px 28px">
        <button class="btn btn-gold" style="padding:0;border-radius:18px;flex-direction:column;gap:7px;height:84px" onclick="showScreen('scheduling')">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="4" width="18" height="18" rx="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>
          <span style="font-size:13px">Agendar</span>
        </button>
        <button class="btn btn-ghost" style="padding:0;border-radius:18px;flex-direction:column;gap:7px;height:84px" onclick="showScreen('evolution')">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#9A7A4A" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><polyline points="21 15 16 10 5 21"/></svg>
          <span style="font-size:13px;color:var(--ink2)">Evolução</span>
        </button>
        <button class="btn btn-ghost" style="padding:0;border-radius:18px;flex-direction:column;gap:7px;height:84px" onclick="showScreen('protocol')">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#9A7A4A" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/></svg>
          <span style="font-size:13px;color:var(--ink2)">Protocolo</span>
        </button>
        <button class="btn btn-ghost" style="padding:0;border-radius:18px;flex-direction:column;gap:7px;height:84px" onclick="showScreen('chat')">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#9A7A4A" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
          <span style="font-size:13px;color:var(--ink2)">Suporte</span>
        </button>
      </div>
    </div>
  </div>

  <!-- ══════════════ AGENDAMENTO ══════════════ -->
  <div class="screen" id="screen-scheduling">
    <div class="topbar">
      <div class="sub">Lyvène Experience</div>
      <h1>Agendamento</h1>
    </div>
    <div class="scroll-area" style="padding-top:4px">
      <div class="steps">
        <div class="step-dot active" id="d1"></div>
        <div class="step-dot" id="d2"></div>
        <div class="step-dot" id="d3"></div>
      </div>

      <!-- STEP 1: Procedure -->
      <div id="step1" style="padding-top:14px">
        <span class="section-title">Escolha o Procedimento</span>
        <div class="proc-card" onclick="selectProc(this,'Toxina Botulínica (Botox)')">
          <div class="proc-icon"><svg viewBox="0 0 24 24"><path d="M12 2L8 6H4l2 8H2l2 6h16l2-6h-4l2-8h-4L12 2z"/></svg></div>
          <div style="flex:1"><p style="font-size:14px;font-weight:500;color:var(--ink);margin-bottom:2px">Toxina Botulínica (Botox)</p><p class="caption">Suavização de rugas · 60 min</p></div>
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#c8b890" stroke-width="1.5"><polyline points="9 18 15 12 9 6"/></svg>
        </div>
        <div class="proc-card" onclick="selectProc(this,'Bioestimulador de Colágeno')">
          <div class="proc-icon"><svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><path d="M12 8v8M8 12h8"/></svg></div>
          <div style="flex:1"><p style="font-size:14px;font-weight:500;color:var(--ink);margin-bottom:2px">Bioestimulador de Colágeno</p><p class="caption">Estimulação de colágeno · 90 min</p></div>
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#c8b890" stroke-width="1.5"><polyline points="9 18 15 12 9 6"/></svg>
        </div>
        <div class="proc-card" onclick="selectProc(this,'Preenchimento Labial')">
          <div class="proc-icon"><svg viewBox="0 0 24 24"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/></svg></div>
          <div style="flex:1"><p style="font-size:14px;font-weight:500;color:var(--ink);margin-bottom:2px">Preenchimento Labial</p><p class="caption">Volumização dos lábios · 60 min</p></div>
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#c8b890" stroke-width="1.5"><polyline points="9 18 15 12 9 6"/></svg>
        </div>
        <div class="proc-card" onclick="selectProc(this,'Harmonização Facial Completa')">
          <div class="proc-icon"><svg viewBox="0 0 24 24"><circle cx="12" cy="8" r="4"/><path d="M4 20v-2a8 8 0 0 1 16 0v2"/></svg></div>
          <div style="flex:1"><p style="font-size:14px;font-weight:500;color:var(--ink);margin-bottom:2px">Harmonização Facial Completa</p><p class="caption">Protocolo completo · 120 min</p></div>
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#c8b890" stroke-width="1.5"><polyline points="9 18 15 12 9 6"/></svg>
        </div>
        <div class="proc-card" onclick="selectProc(this,'Skinbooster')">
          <div class="proc-icon"><svg viewBox="0 0 24 24"><path d="M12 2.69l5.66 5.66a8 8 0 1 1-11.31 0z"/></svg></div>
          <div style="flex:1"><p style="font-size:14px;font-weight:500;color:var(--ink);margin-bottom:2px">Skinbooster</p><p class="caption">Hidratação profunda · 60 min</p></div>
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#c8b890" stroke-width="1.5"><polyline points="9 18 15 12 9 6"/></svg>
        </div>
        <div class="proc-card" onclick="selectProc(this,'Fios de PDO')">
          <div class="proc-icon"><svg viewBox="0 0 24 24"><line x1="12" y1="2" x2="12" y2="22"/><path d="M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"/></svg></div>
          <div style="flex:1"><p style="font-size:14px;font-weight:500;color:var(--ink);margin-bottom:2px">Fios de PDO</p><p class="caption">Lifting não cirúrgico · 90 min</p></div>
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#c8b890" stroke-width="1.5"><polyline points="9 18 15 12 9 6"/></svg>
        </div>
        <div class="proc-card" onclick="selectProc(this,'Consulta de Avaliação')">
          <div class="proc-icon"><svg viewBox="0 0 24 24"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 13a19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 3.59 2h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L7.91 9.91a16 16 0 0 0 6.1 6.1l1.27-1.27a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/></svg></div>
          <div style="flex:1"><p style="font-size:14px;font-weight:500;color:var(--ink);margin-bottom:2px">Consulta de Avaliação</p><p class="caption" style="color:var(--gold-dark)">Gratuita · 45 min</p></div>
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#c8b890" stroke-width="1.5"><polyline points="9 18 15 12 9 6"/></svg>
        </div>
      </div>

      <!-- STEP 2: Date + Time -->
      <div id="step2" style="display:none;padding:14px 16px 0">
        <div class="card-cream" style="border-radius:14px;padding:14px 16px;margin-bottom:18px;display:flex;align-items:center;justify-content:space-between">
          <div><p class="label" style="margin-bottom:3px">Procedimento</p><p style="font-size:14px;font-weight:500;color:var(--ink)" id="proc-name-display">—</p></div>
          <button class="btn btn-ghost" style="font-size:11px;padding:7px 14px;border-radius:20px" onclick="goStep(1)">Alterar</button>
        </div>
        <p class="label" style="margin-bottom:10px">Selecione o dia</p>
        <div style="display:grid;grid-template-columns:repeat(7,1fr);gap:3px;margin-bottom:18px" id="calendar-days"></div>
        <p class="label" style="margin-bottom:10px">Horários disponíveis</p>
        <div style="display:flex;flex-wrap:wrap;gap:8px;margin-bottom:20px" id="time-slots">
          <div class="slot" onclick="pickSlot(this)">09h00</div>
          <div class="slot" onclick="pickSlot(this)">09h30</div>
          <div class="slot unavail">10h00</div>
          <div class="slot" onclick="pickSlot(this)">10h30</div>
          <div class="slot unavail">11h00</div>
          <div class="slot" onclick="pickSlot(this)">11h30</div>
          <div class="slot" onclick="pickSlot(this)">14h00</div>
          <div class="slot" onclick="pickSlot(this)">14h30</div>
          <div class="slot" onclick="pickSlot(this)">15h30</div>
          <div class="slot unavail">16h00</div>
          <div class="slot" onclick="pickSlot(this)">16h30</div>
          <div class="slot" onclick="pickSlot(this)">17h00</div>
        </div>
        <p class="label" style="margin-bottom:10px">Profissional</p>
        <select class="inp" style="margin-bottom:22px">
          <option>Qualquer disponível</option>
          <option>Dra. Lívia Carvalho</option>
          <option>Dra. Amanda Freitas</option>
        </select>
        <button class="btn btn-gold" style="width:100%;padding:15px;border-radius:16px;margin-bottom:16px" id="btn-step2" onclick="goStep(3)" disabled>Continuar</button>
      </div>

      <!-- STEP 3: Confirm -->
      <div id="step3" style="display:none;padding:14px 16px 0">
        <p style="font-family:'Cormorant Garamond',serif;font-size:24px;font-weight:300;margin-bottom:18px;color:var(--ink)">Confirmar Agendamento</p>
        <div class="card" style="margin:0 0 16px">
          <div class="toggle-row" style="padding-top:0"><span class="label">Procedimento</span><span style="font-size:13px;font-weight:500;color:var(--ink);text-align:right;max-width:58%" id="conf-proc">—</span></div>
          <div class="divider"></div>
          <div class="toggle-row"><span class="label">Data</span><span style="font-size:13px;color:var(--ink)" id="conf-date">—</span></div>
          <div class="divider"></div>
          <div class="toggle-row"><span class="label">Horário</span><span style="font-size:13px;color:var(--ink)" id="conf-time">—</span></div>
          <div class="divider"></div>
          <div class="toggle-row" style="border:none;padding-bottom:0"><span class="label">Profissional</span><span style="font-size:13px;color:var(--ink)">Dra. Lívia Carvalho</span></div>
        </div>
        <div class="card" style="margin:0 0 16px">
          <div class="toggle-row" style="padding-top:0"><span style="font-size:14px;color:var(--ink)">Lembrete 24h antes</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
          <div class="toggle-row"><span style="font-size:14px;color:var(--ink)">Lembrete 1h antes</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
          <div class="toggle-row" style="border:none;padding-bottom:0"><span style="font-size:14px;color:var(--ink)">Notificar via WhatsApp</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
        </div>
        <textarea class="inp" rows="3" placeholder="Observações ou pedido especial (opcional)..." style="margin-bottom:18px;resize:none"></textarea>
        <div style="display:flex;gap:10px;margin-bottom:24px">
          <button class="btn btn-ghost" style="flex:0.38;padding:14px;border-radius:16px" onclick="goStep(2)">Voltar</button>
          <button class="btn btn-gold" style="flex:1;padding:14px;border-radius:16px" onclick="confirmAppointment()">Confirmar</button>
        </div>
      </div>
    </div>
  </div>

  <!-- ══════════════ EVOLUÇÃO ══════════════ -->
  <div class="screen" id="screen-evolution">
    <div class="topbar">
      <div class="sub">Lyvène Experience</div>
      <h1>Minha Evolução</h1>
    </div>
    <div class="scroll-area" style="padding-top:18px">
      <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:10px;padding:0 16px;margin-bottom:18px">
        <div style="background:var(--cream);border-radius:16px;padding:16px;text-align:center"><p style="font-size:24px;font-weight:500;color:var(--gold-dark)">24</p><p style="font-size:10px;letter-spacing:1px;color:var(--ink3);text-transform:uppercase;margin-top:2px">Fotos</p></div>
        <div style="background:var(--cream);border-radius:16px;padding:16px;text-align:center"><p style="font-size:24px;font-weight:500;color:var(--gold-dark)">8</p><p style="font-size:10px;letter-spacing:1px;color:var(--ink3);text-transform:uppercase;margin-top:2px">Meses</p></div>
        <div style="background:var(--cream);border-radius:16px;padding:16px;text-align:center"><p style="font-size:24px;font-weight:500;color:var(--gold-dark)">6</p><p style="font-size:10px;letter-spacing:1px;color:var(--ink3);text-transform:uppercase;margin-top:2px">Sessões</p></div>
      </div>

      <span class="section-title">Antes & Depois</span>
      <div style="padding:0 16px;margin-bottom:18px">
        <div class="compare-wrap" id="compareWrap">
          <div class="compare-after" style="align-items:center;justify-content:center">
            <div class="face-emoji" style="opacity:0.88">🧖‍♀️</div>
            <span class="photo-label" style="right:12px">Depois · Mar 2025</span>
          </div>
          <div class="compare-before" id="compareLeft">
            <div class="face-emoji" style="opacity:0.55">🧖‍♀️</div>
            <span class="photo-label" style="left:12px">Antes · Jul 2024</span>
          </div>
          <div class="compare-divider" id="compareDivider">
            <div class="compare-handle">
              <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="#9A7A4A" stroke-width="2.5"><polyline points="15 18 9 12 15 6"/><polyline points="9 18 15 12 9 6" transform="translate(5,0)"/></svg>
            </div>
          </div>
        </div>
        <p style="font-size:11px;color:var(--ink3);text-align:center;margin-top:10px;letter-spacing:0.5px">← Arraste para comparar →</p>
      </div>

      <span class="section-title">Linha do Tempo</span>
      <div class="scroll-h" style="padding-bottom:10px;gap:8px">
        <div class="chip sel" onclick="chipSel(this)">Todos</div>
        <div class="chip" onclick="chipSel(this)">Botox</div>
        <div class="chip" onclick="chipSel(this)">Bioestimulador</div>
        <div class="chip" onclick="chipSel(this)">Skinbooster</div>
      </div>

      <div style="padding:14px 16px 0">
        <div style="border-left:2px solid var(--gold-light);padding-left:18px;margin-left:8px">
          <div style="margin-bottom:26px">
            <div style="display:flex;align-items:center;gap:8px;margin-bottom:12px">
              <div style="width:11px;height:11px;border-radius:50%;background:var(--gold);margin-left:-23px;flex-shrink:0;box-shadow:0 0 0 3px rgba(201,169,110,0.2)"></div>
              <p style="font-family:'Cormorant Garamond',serif;font-size:18px;font-weight:400">Março 2025</p>
              <span class="badge badge-green">Bioestimulador</span>
            </div>
            <div class="photo-grid">
              <div class="photo-slot" style="background:linear-gradient(135deg,#f2e2ca,#ddc090)"><span>🧖‍♀️</span></div>
              <div class="photo-slot" style="background:linear-gradient(135deg,#eadac2,#caa870)"><span>🧖‍♀️</span></div>
              <div class="photo-slot" style="background:linear-gradient(135deg,#f5eada,#e0c898)"><span>🧖‍♀️</span></div>
            </div>
          </div>
          <div style="margin-bottom:26px">
            <div style="display:flex;align-items:center;gap:8px;margin-bottom:12px">
              <div style="width:11px;height:11px;border-radius:50%;background:var(--gold-light);margin-left:-23px;flex-shrink:0"></div>
              <p style="font-family:'Cormorant Garamond',serif;font-size:18px;font-weight:400">Janeiro 2025</p>
              <span class="badge badge-pink">Botox</span>
            </div>
            <div class="photo-grid">
              <div class="photo-slot" style="background:linear-gradient(135deg,#ead8d8,#d8b0b0)"><span>🧖‍♀️</span></div>
              <div class="photo-slot" style="background:linear-gradient(135deg,#e2d0d0,#d0a8a8)"><span>🧖‍♀️</span></div>
              <div class="photo-slot" style="background:linear-gradient(135deg,#f0e0e0,#dcc0c0)"><span>🧖‍♀️</span></div>
            </div>
          </div>
          <div>
            <div style="display:flex;align-items:center;gap:8px;margin-bottom:12px">
              <div style="width:11px;height:11px;border-radius:50%;background:#d8d0c0;margin-left:-23px;flex-shrink:0"></div>
              <p style="font-family:'Cormorant Garamond',serif;font-size:18px;font-weight:400">Julho 2024</p>
              <span class="badge badge-blue">Avaliação</span>
            </div>
            <div class="photo-grid">
              <div class="photo-slot" style="background:linear-gradient(135deg,#d8d0e8,#b0a8cc)"><span>🧖‍♀️</span></div>
              <div class="photo-slot" style="background:linear-gradient(135deg,#d0c8e0,#a8a0c0)"><span>🧖‍♀️</span></div>
            </div>
          </div>
        </div>
      </div>

      <div style="padding:18px 16px 28px">
        <button class="btn btn-outline" style="width:100%;padding:16px;border-radius:18px;gap:10px">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M23 19a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h4l2-3h6l2 3h4a2 2 0 0 1 2 2z"/><circle cx="12" cy="13" r="4"/></svg>
          Registrar foto de hoje
        </button>
      </div>
    </div>
  </div>

  <!-- ══════════════ PROTOCOLO ══════════════ -->
  <div class="screen" id="screen-protocol">
    <div class="topbar">
      <div class="sub">Lyvène Experience</div>
      <h1>Meu Protocolo</h1>
    </div>
    <div class="scroll-area" style="padding-top:18px">
      <div class="card card-dark" style="margin:0 16px 18px;display:flex;justify-content:space-between;align-items:center">
        <div>
          <p style="font-size:10px;letter-spacing:1.5px;opacity:0.45;text-transform:uppercase;margin-bottom:6px">Protocolo Ativo</p>
          <p style="font-family:'Cormorant Garamond',serif;font-size:24px;color:var(--gold-light);font-weight:300">Renovação Completa</p>
          <p style="font-size:12px;opacity:0.4;margin-top:4px;color:white">Dra. Lívia Carvalho</p>
        </div>
        <div style="width:66px;height:66px;border-radius:50%;border:2.5px solid var(--gold);display:flex;align-items:center;justify-content:center;flex-direction:column;flex-shrink:0">
          <p style="font-size:18px;font-weight:500;color:var(--gold);line-height:1">72%</p>
          <p style="font-size:9px;opacity:0.4;color:white">feito</p>
        </div>
      </div>

      <span class="section-title">Checklist de Hoje</span>
      <div class="card" style="margin:0 16px 14px">
        <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:14px">
          <p style="font-size:14px;font-weight:500;color:var(--ink)">🌅 Rotina Manhã</p>
          <span class="badge badge-gold" id="mbadge">3 / 4</span>
        </div>
        <div class="check-item" onclick="tog(this,'mbadge',4)"><div class="check-box done"></div><span class="check-text done">Limpeza facial suave</span></div>
        <div class="check-item" onclick="tog(this,'mbadge',4)"><div class="check-box done"></div><span class="check-text done">Sérum Vitamina C — 3 gotas</span></div>
        <div class="check-item" onclick="tog(this,'mbadge',4)"><div class="check-box done"></div><span class="check-text done">Hidratante levinho</span></div>
        <div class="check-item" onclick="tog(this,'mbadge',4)"><div class="check-box"></div><span class="check-text">Protetor solar FPS 50+ ☀️</span></div>
      </div>
      <div class="card" style="margin:0 16px 14px">
        <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:14px">
          <p style="font-size:14px;font-weight:500;color:var(--ink)">🌙 Rotina Noite</p>
          <span class="badge" style="background:#f0e8de;color:var(--ink3)" id="nbadge">0 / 4</span>
        </div>
        <div class="check-item" onclick="tog(this,'nbadge',4)"><div class="check-box"></div><span class="check-text">Demaquilante / Óleo de limpeza</span></div>
        <div class="check-item" onclick="tog(this,'nbadge',4)"><div class="check-box"></div><span class="check-text">Limpeza facial</span></div>
        <div class="check-item" onclick="tog(this,'nbadge',4)"><div class="check-box"></div><span class="check-text">Sérum noturno ativo</span></div>
        <div class="check-item" onclick="tog(this,'nbadge',4)"><div class="check-box"></div><span class="check-text">Creme noturno / Sleeping mask</span></div>
      </div>
      <div class="card card-cream" style="margin:0 16px 18px;display:flex;align-items:center;gap:16px">
        <div style="font-size:38px">🔥</div>
        <div><p style="font-size:20px;font-weight:500;color:var(--gold-dark)">12 dias seguidos</p><p class="caption">Continue assim! Sua pele agradece 💛</p></div>
      </div>

      <span class="section-title">Procedimentos do Protocolo</span>
      <div style="padding:0 16px 10px;display:flex;flex-direction:column;gap:12px">
        <div class="card" style="margin:0">
          <div style="display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:8px"><p style="font-size:14px;font-weight:500;color:var(--ink)">Bioestimulador de Colágeno</p><span class="badge badge-gold">2/3 sessões</span></div>
          <p class="caption" style="margin-bottom:10px">Estimulação profunda · A cada 45 dias</p>
          <div class="prog-bar" style="margin-bottom:12px"><div class="prog-fill" style="width:66%"></div></div>
          <button class="btn btn-outline" style="font-size:12px;padding:9px 18px;border-radius:22px" onclick="showScreen('scheduling')">Agendar próxima sessão</button>
        </div>
        <div class="card" style="margin:0">
          <div style="display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:8px"><p style="font-size:14px;font-weight:500;color:var(--ink)">Skinbooster</p><span class="badge badge-blue">Pendente</span></div>
          <p class="caption" style="margin-bottom:10px">Hidratação profunda · 1 sessão</p>
          <div class="prog-bar" style="margin-bottom:12px"><div class="prog-fill" style="width:0%"></div></div>
          <button class="btn btn-outline" style="font-size:12px;padding:9px 18px;border-radius:22px" onclick="showScreen('scheduling')">Agendar sessão</button>
        </div>
        <div class="card" style="margin:0">
          <div style="display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:8px"><p style="font-size:14px;font-weight:500;color:var(--ink)">Toxina Botulínica</p><span class="badge badge-green">Concluído</span></div>
          <p class="caption" style="margin-bottom:10px">Retocar em Abril 2025</p>
          <div class="prog-bar"><div class="prog-fill" style="width:100%"></div></div>
        </div>
      </div>

      <span class="section-title" style="margin-top:6px">Cuidados Pós-Procedimento</span>
      <div class="card" style="margin:0 16px 28px">
        <p style="font-size:13px;font-weight:500;color:var(--gold-dark);margin-bottom:12px">Bioestimulador · realizado há 3 dias</p>
        <div style="display:grid;gap:10px">
          <div style="background:#e8f5ee;border-radius:12px;padding:12px 14px"><p style="font-size:10px;letter-spacing:1px;color:#2d7a4a;text-transform:uppercase;margin-bottom:5px">✅ Fazer</p><p style="font-size:13px;color:#1a4a2e;line-height:1.6">Compressa fria se houver inchaço · Hidratante suave · Protetor solar diariamente</p></div>
          <div style="background:#fde8e8;border-radius:12px;padding:12px 14px"><p style="font-size:10px;letter-spacing:1px;color:#9a2d2d;text-transform:uppercase;margin-bottom:5px">❌ Evitar</p><p style="font-size:13px;color:#5a1a1a;line-height:1.6">Sol direto · Sauna · Exercício intenso · Álcool nos primeiros 2 dias</p></div>
          <div style="background:#fff3e0;border-radius:12px;padding:12px 14px"><p style="font-size:10px;letter-spacing:1px;color:#9a6a2d;text-transform:uppercase;margin-bottom:5px">🚨 Contatar se</p><p style="font-size:13px;color:#5a3a10;line-height:1.6">Dor intensa · Hematoma crescente · Febre</p></div>
        </div>
        <button class="btn btn-outline" style="width:100%;margin-top:14px;padding:11px;font-size:12px;border-radius:22px;gap:7px" onclick="showScreen('chat')">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
          Falar com a clínica
        </button>
      </div>
    </div>
  </div>

  <!-- ══════════════ CHAT ══════════════ -->
  <div class="screen" id="screen-chat">
    <div class="topbar topbar-row">
      <div style="display:flex;align-items:center;gap:12px">
        <div class="avatar" style="width:38px;height:38px;font-size:13px">LX</div>
        <div>
          <p style="font-size:14px;font-weight:500;color:var(--ink)">Lyvène Experience</p>
          <div style="display:flex;align-items:center;gap:5px">
            <div style="width:7px;height:7px;border-radius:50%;background:#2d7a4a"></div>
            <p style="font-size:11px;color:var(--ink3)">Online · resp. em até 1h</p>
          </div>
        </div>
      </div>
    </div>
    <div class="scroll-area" style="padding:14px 16px 0" id="chat-scroll">
      <p class="section-title" style="padding:0;margin-bottom:10px">Sobre o que você precisa?</p>
      <div class="scroll-h" style="padding:0;margin-bottom:18px;gap:8px">
        <div class="chip sel" onclick="chipSel(this)">Dúvida pós-proc.</div>
        <div class="chip" onclick="chipSel(this)">Efeito colateral</div>
        <div class="chip" onclick="chipSel(this)">Resultado</div>
        <div class="chip" onclick="chipSel(this)">Produto</div>
        <div class="chip" onclick="chipSel(this)">Orçamento</div>
      </div>

      <div style="display:flex;flex-direction:column;gap:10px;margin-bottom:18px" id="chat-messages">
        <div style="display:flex;flex-direction:column;align-items:flex-start;gap:3px">
          <div class="bubble bubble-recv">Olá Sofia! 🌟 Em que posso te ajudar hoje?</div>
          <p style="font-size:10px;color:var(--ink3);padding:0 4px">Dra. Lívia · 14h32</p>
        </div>
        <div style="display:flex;flex-direction:column;align-items:flex-end;gap:3px">
          <div class="bubble bubble-sent">Tenho uma dúvida sobre o pós do bioestimulador 😊</div>
          <p style="font-size:10px;color:var(--ink3);padding:0 4px">14h35 · ✓✓</p>
        </div>
        <div style="display:flex;flex-direction:column;align-items:flex-start;gap:3px">
          <div class="bubble bubble-recv">Claro! Pode perguntar à vontade. O que está sentindo?</div>
          <p style="font-size:10px;color:var(--ink3);padding:0 4px">Dra. Lívia · 14h37</p>
        </div>
        <div style="display:flex;flex-direction:column;align-items:flex-end;gap:3px">
          <div class="bubble bubble-sent">Tem um pequeno inchaço no lado direito, é normal?</div>
          <p style="font-size:10px;color:var(--ink3);padding:0 4px">14h40 · ✓✓</p>
        </div>
        <div style="display:flex;flex-direction:column;align-items:flex-start;gap:3px">
          <div class="bubble bubble-recv">Sim, é totalmente normal! Nos primeiros 5 dias pode haver edema assimétrico. Aplique compressa fria por 10 min, 3x ao dia. Se persistir após 7 dias me avisa 💛</div>
          <p style="font-size:10px;color:var(--ink3);padding:0 4px">Dra. Lívia · 14h42</p>
        </div>
      </div>

      <div class="card card-cream" style="margin:0 0 14px">
        <p style="font-size:13px;font-weight:500;color:var(--ink);margin-bottom:14px">Como está se sentindo após o bioestimulador?</p>
        <div style="display:flex;gap:8px;justify-content:center;margin-bottom:10px">
          <button class="emoji-btn selected" onclick="selEmoji(this)">😊</button>
          <button class="emoji-btn" onclick="selEmoji(this)">🙂</button>
          <button class="emoji-btn" onclick="selEmoji(this)">😐</button>
          <button class="emoji-btn" onclick="selEmoji(this)">😟</button>
          <button class="emoji-btn" onclick="selEmoji(this)">😨</button>
        </div>
        <p style="font-size:10px;color:var(--ink3);text-align:center;letter-spacing:0.3px">Ótimo · Bem · Normal · Desconforto · Preocupada</p>
      </div>

      <div class="card" style="margin:0 0 8px;border:1px solid #c0e0c0;display:flex;align-items:center;gap:14px">
        <div style="width:42px;height:42px;border-radius:12px;background:#25D366;display:flex;align-items:center;justify-content:center;flex-shrink:0">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="white"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 0 1-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 0 1-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 0 1 2.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0 0 12.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 0 0 5.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 0 0-3.48-8.413Z"/></svg>
        </div>
        <div style="flex:1"><p style="font-size:14px;font-weight:500;color:var(--ink)">Prefere pelo WhatsApp?</p><p class="caption">Fale diretamente com a equipe</p></div>
        <button class="btn btn-ghost" style="font-size:12px;padding:8px 14px;border-radius:20px;border-color:#25D366;color:#1a7a1a">Abrir</button>
      </div>
      <div style="height:16px"></div>
    </div>
    <!-- Chat input -->
    <div style="padding:12px 16px max(16px, env(safe-area-inset-bottom));background:white;border-top:0.5px solid #f0e8de;display:flex;gap:10px;align-items:center;flex-shrink:0">
      <input class="inp" style="flex:1;padding:11px 16px;border-radius:28px;border-color:#e8dfd3" placeholder="Escreva sua mensagem..." id="chatInput">
      <button class="btn btn-gold" style="width:42px;height:42px;border-radius:50%;padding:0;flex-shrink:0" onclick="sendMsg()">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="22" y1="2" x2="11" y2="13"/><polygon points="22 2 15 22 11 13 2 9 22 2"/></svg>
      </button>
    </div>
  </div>

  <!-- ══════════════ PERFIL ══════════════ -->
  <div class="screen" id="screen-profile">
    <div class="topbar">
      <div class="sub">Lyvène Experience</div>
      <h1>Meu Perfil</h1>
    </div>
    <div class="scroll-area" style="padding-top:24px">
      <div style="text-align:center;padding:0 20px 24px">
        <div class="avatar" style="width:76px;height:76px;font-size:28px;margin:0 auto 14px">SM</div>
        <p style="font-family:'Cormorant Garamond',serif;font-size:26px;font-weight:400;color:var(--ink)">Sofia Mendes</p>
        <p class="caption" style="margin-bottom:10px">Paciente desde Julho 2024</p>
        <span class="badge badge-gold" style="font-size:11px">Premium</span>
      </div>

      <span class="section-title">Informações Pessoais</span>
      <div class="card" style="margin:0 16px 16px">
        <div class="toggle-row" style="padding-top:0"><span class="label">Nome</span><span style="font-size:13px;color:var(--ink)">Sofia Mendes</span></div>
        <div class="toggle-row"><span class="label">Nascimento</span><span style="font-size:13px;color:var(--ink)">12 Mar 1992</span></div>
        <div class="toggle-row"><span class="label">WhatsApp</span><span style="font-size:13px;color:var(--gold-dark)">(21) 99887-6655</span></div>
        <div class="toggle-row" style="border:none;padding-bottom:0"><span class="label">E-mail</span><span style="font-size:13px;color:var(--gold-dark)">sofia@email.com</span></div>
      </div>

      <span class="section-title">Saúde</span>
      <div class="card" style="margin:0 16px 16px">
        <div class="toggle-row" style="padding-top:0"><span class="label">Alergias</span><span style="font-size:13px;color:var(--ink)">Nenhuma conhecida</span></div>
        <div class="toggle-row" style="border:none;padding-bottom:0"><span class="label">Medicamentos</span><span style="font-size:13px;color:var(--ink)">Nenhum</span></div>
      </div>

      <span class="section-title">Meu Histórico</span>
      <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:10px;padding:0 16px;margin-bottom:18px">
        <div style="background:var(--cream);border-radius:16px;padding:16px;text-align:center"><p style="font-size:22px;font-weight:500;color:var(--gold-dark)">6</p><p style="font-size:10px;color:var(--ink3);margin-top:2px">Sessões</p></div>
        <div style="background:var(--cream);border-radius:16px;padding:16px;text-align:center"><p style="font-size:22px;font-weight:500;color:var(--gold-dark)">8</p><p style="font-size:10px;color:var(--ink3);margin-top:2px">Meses</p></div>
        <div style="background:var(--cream);border-radius:16px;padding:16px;text-align:center"><p style="font-size:22px;font-weight:500;color:var(--gold-dark)">12🔥</p><p style="font-size:10px;color:var(--ink3);margin-top:2px">Streak</p></div>
      </div>

      <span class="section-title">Notificações</span>
      <div class="card" style="margin:0 16px 16px">
        <div class="toggle-row" style="padding-top:0"><span style="font-size:14px;color:var(--ink)">Lembretes de agendamento</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
        <div class="toggle-row"><span style="font-size:14px;color:var(--ink)">Lembretes de retoque</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
        <div class="toggle-row"><span style="font-size:14px;color:var(--ink)">Checklist diário</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
        <div class="toggle-row" style="border:none;padding-bottom:0"><span style="font-size:14px;color:var(--ink)">Novidades e promoções</span><div class="toggle" onclick="this.classList.toggle('on')"></div></div>
      </div>

      <div style="padding:0 16px 32px;display:flex;flex-direction:column;gap:10px">
        <button class="btn btn-ghost" style="width:100%;padding:14px;border-radius:16px">Termos e Privacidade · LGPD</button>
        <button class="btn btn-ghost" style="width:100%;padding:14px;border-radius:16px;border-color:#e8d0d0;color:#9a3030">Sair da conta</button>
      </div>
    </div>
  </div>

  <!-- ══════════════ BOTTOM NAV ══════════════ -->
  <nav class="bottom-nav">
    <button class="nav-item active" id="nav-home" onclick="showScreen('home')">
      <svg viewBox="0 0 24 24"><path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>
      <span>Home</span>
    </button>
    <button class="nav-item" id="nav-scheduling" onclick="showScreen('scheduling')">
      <svg viewBox="0 0 24 24"><rect x="3" y="4" width="18" height="18" rx="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>
      <span>Agendar</span>
    </button>
    <button class="nav-item" id="nav-evolution" onclick="showScreen('evolution')">
      <svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><polyline points="21 15 16 10 5 21"/></svg>
      <span>Evolução</span>
    </button>
    <button class="nav-item" id="nav-protocol" onclick="showScreen('protocol')">
      <svg viewBox="0 0 24 24"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/></svg>
      <span>Protocolo</span>
    </button>
    <button class="nav-item" id="nav-chat" onclick="showScreen('chat')">
      <svg viewBox="0 0 24 24"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
      <span>Suporte</span>
    </button>
  </nav>
</div>

<script>
// ── STATE ──────────────────────────────────────────
let selProc='', selDate='', selTime='', curStep=1;
const MONTHS=['Jan','Fev','Mar','Abr','Mai','Jun','Jul','Ago','Set','Out','Nov','Dez'];
const DAYS=['Dom','Seg','Ter','Qua','Qui','Sex','Sáb'];
const DAYS_SHORT=['D','S','T','Q','Q','S','S'];

// ── NAVIGATION ─────────────────────────────────────
function showScreen(id){
  document.querySelectorAll('.screen').forEach(s=>s.classList.remove('active'));
  document.getElementById('screen-'+id).classList.add('active');
  document.querySelectorAll('.nav-item').forEach(n=>n.classList.remove('active'));
  const nav=document.getElementById('nav-'+id);
  if(nav) nav.classList.add('active');
  if(id==='scheduling'){curStep=1;renderStep(1);}
}

// ── SCHEDULING ─────────────────────────────────────
function goStep(n){curStep=n;renderStep(n);}

function renderStep(n){
  [1,2,3].forEach(i=>{
    document.getElementById('step'+i).style.display=i===n?'block':'none';
    document.getElementById('d'+i).classList.toggle('active',i<=n);
  });
}

function selectProc(el,name){
  selProc=name; selDate=''; selTime='';
  document.querySelectorAll('.proc-card').forEach(c=>c.classList.remove('selected'));
  el.classList.add('selected');
  document.getElementById('proc-name-display').textContent=name;
  document.getElementById('conf-proc').textContent=name;
  buildCal();
  setTimeout(()=>goStep(2),200);
}

function buildCal(){
  const cal=document.getElementById('calendar-days');
  const now=new Date(); const m=now.getMonth(); const y=now.getFullYear();
  const firstDay=new Date(y,m,1).getDay();
  const total=new Date(y,m+1,0).getDate();
  const today=now.getDate();
  let html=DAYS_SHORT.map(d=>`<div style="text-align:center;font-size:10px;color:var(--ink3);padding-bottom:6px;font-family:'Jost',sans-serif">${d}</div>`).join('');
  for(let i=0;i<firstDay;i++) html+='<div></div>';
  const skip=[7,13,20,27];
  for(let d=1;d<=total;d++){
    const past=d<today, unavail=skip.includes(d);
    let bg='transparent', color='var(--ink)', fw='400', onclick='', op='1';
    if(d===today){bg='var(--gold)';color='white';fw='500';onclick=`pickDay(this,${d})`;}
    else if(past||unavail){op='0.3';}
    else{onclick=`pickDay(this,${d})`;}
    html+=`<div onclick="${onclick}" class="cal-day" style="text-align:center;padding:7px 2px;border-radius:9px;font-size:13px;font-family:'Jost',sans-serif;cursor:${onclick?'pointer':'default'};background:${bg};color:${color};font-weight:${fw};opacity:${op};transition:all 0.2s">${d}</div>`;
  }
  cal.innerHTML=html;
}

function pickDay(el,d){
  document.querySelectorAll('.cal-day').forEach(c=>{
    c.style.background='transparent';c.style.color='var(--ink)';c.style.fontWeight='400';
  });
  el.style.background='var(--ink)';el.style.color='white';el.style.fontWeight='500';
  const now=new Date();
  selDate=d+' '+MONTHS[now.getMonth()]+', '+DAYS[new Date(now.getFullYear(),now.getMonth(),d).getDay()];
  document.getElementById('conf-date').textContent=selDate;
  checkStep2();
}

function pickSlot(el){
  if(el.classList.contains('unavail'))return;
  document.querySelectorAll('.slot').forEach(s=>s.classList.remove('selected'));
  el.classList.add('selected');
  selTime=el.textContent;
  document.getElementById('conf-time').textContent=selTime;
  checkStep2();
}

function checkStep2(){
  document.getElementById('btn-step2').disabled=!(selDate&&selTime);
}

function confirmAppointment(){
  document.getElementById('successOverlay').classList.add('show');
}

function closeSuccess(){
  document.getElementById('successOverlay').classList.remove('show');
  selProc='';selDate='';selTime='';
  showScreen('home');
}

// ── CHECKLIST ──────────────────────────────────────
function tog(row,badgeId,total){
  const box=row.querySelector('.check-box');
  const txt=row.querySelector('.check-text');
  box.classList.toggle('done');
  txt.classList.toggle('done');
  const parent=row.parentElement;
  const done=parent.querySelectorAll('.check-box.done').length;
  const badge=document.getElementById(badgeId);
  badge.textContent=done+' / '+total;
  badge.style.background=done===total?'#bce8d0':done>0?'#f5e8d0':'#f0e8de';
  badge.style.color=done===total?'#2d6a4a':done>0?'#9A7A4A':'var(--ink3)';
}

// ── COMPARISON SLIDER ──────────────────────────────
(function(){
  const wrap=document.getElementById('compareWrap');
  const left=document.getElementById('compareLeft');
  const div=document.getElementById('compareDivider');
  if(!wrap)return;
  let drag=false;
  const move=e=>{
    if(!drag)return;
    const r=wrap.getBoundingClientRect();
    const x=(e.touches?e.touches[0].clientX:e.clientX)-r.left;
    const pct=Math.max(8,Math.min(92,x/r.width*100));
    left.style.width=pct+'%';
    div.style.left=pct+'%';
  };
  wrap.addEventListener('mousedown',()=>drag=true);
  wrap.addEventListener('touchstart',()=>drag=true,{passive:true});
  document.addEventListener('mouseup',()=>drag=false);
  document.addEventListener('touchend',()=>drag=false);
  document.addEventListener('mousemove',move);
  document.addEventListener('touchmove',move,{passive:true});
})();

// ── CHAT ───────────────────────────────────────────
function sendMsg(){
  const inp=document.getElementById('chatInput');
  const txt=inp.value.trim();
  if(!txt)return;
  const msgs=document.getElementById('chat-messages');
  const now=new Date();
  const t=now.getHours()+'h'+String(now.getMinutes()).padStart(2,'0');
  msgs.innerHTML+=`<div style="display:flex;flex-direction:column;align-items:flex-end;gap:3px"><div class="bubble bubble-sent">${txt}</div><p style="font-size:10px;color:var(--ink3);padding:0 4px">${t} · ✓</p></div>`;
  inp.value='';
  document.getElementById('chat-scroll').scrollTop=9999;
}
document.addEventListener('DOMContentLoaded',()=>{
  const inp=document.getElementById('chatInput');
  if(inp) inp.addEventListener('keydown',e=>{if(e.key==='Enter'&&!e.shiftKey){e.preventDefault();sendMsg();}});
});

// ── UTILS ──────────────────────────────────────────
function chipSel(el){
  const container=el.parentElement;
  container.querySelectorAll('.chip').forEach(c=>c.classList.remove('sel'));
  el.classList.add('sel');
}
function selEmoji(el){
  el.closest('div').querySelectorAll('.emoji-btn').forEach(b=>b.classList.remove('selected'));
  el.classList.add('selected');
}

// Init
buildCal();
</script>
</body>
</html>
