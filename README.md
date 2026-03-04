<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ezzeldin Amr Abdelghane – Cybersecurity Specialist</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=JetBrains+Mono:wght@300;400;500;700&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js"></script>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}

/* ══ THEME VARIABLES ══ */
[data-theme="dark"]{
  --bg:#020912;--surf:#07101c;--surf2:#0b1622;--brd:#172535;
  --txt:#dceeff;--txt2:#a8c8e8;--mut:#3d6b8a;--mxo:.04;
  --acc:#00e5ff;--acc2:#7c3aed;--grn:#00ff88;--red:#ff4466;--ylw:#ffd700;--org:#ff8c42;
  --bar-bg:rgba(0,229,255,.08);--card-shadow:rgba(0,229,255,.06);
  --cli-bg:#010810;--cli-border:#0d2035;--cli-txt:#c8e8ff;
}
[data-theme="light"]{
  --bg:#f0f5fc;--surf:#ffffff;--surf2:#e8eef8;--brd:#c8d8ea;
  --txt:#061428;--txt2:#1e3a5a;--mut:#6688aa;--mxo:.015;
  --acc:#0088cc;--acc2:#6d28d9;--grn:#00a855;--red:#e03050;--ylw:#c08800;--org:#c05010;
  --bar-bg:rgba(0,136,204,.1);--card-shadow:rgba(0,136,204,.08);
  --cli-bg:#f8faff;--cli-border:#c8d8ea;--cli-txt:#061428;
}
:root{--mono:'JetBrains Mono',monospace;--dis:'Syne',sans-serif;--r:12px}

html,body{height:100%;overflow:hidden}
body{background:var(--bg);color:var(--txt);font-family:var(--mono);cursor:none;transition:background .35s,color .35s}

/* ══ MATRIX ══ */
#mx{position:fixed;inset:0;z-index:0;opacity:var(--mxo);pointer-events:none;transition:opacity .4s}

/* ══ CURSOR ══ */
#cur{width:8px;height:8px;background:var(--acc);border-radius:50%;position:fixed;pointer-events:none;z-index:9999;mix-blend-mode:difference;transform:translate(-50%,-50%)}
#cur-r{width:28px;height:28px;border:1.5px solid var(--acc);opacity:.4;border-radius:50%;position:fixed;pointer-events:none;z-index:9998;transform:translate(-50%,-50%)}

/* ══ LOADER ══ */
#loader{position:fixed;inset:0;z-index:9500;background:var(--bg);display:flex;flex-direction:column;align-items:center;justify-content:center;gap:18px}
.ld-brand{font-size:11px;letter-spacing:.35em;color:var(--mut);text-transform:uppercase}
.ld-p{font-family:var(--dis);font-size:54px;font-weight:800;color:var(--acc);letter-spacing:-.04em;line-height:1}
.ld-bw{width:220px;height:1px;background:var(--brd);overflow:hidden}
.ld-b{height:100%;background:linear-gradient(90deg,var(--acc),var(--acc2));width:0}
.ld-t{font-size:10px;color:var(--mut);letter-spacing:.22em;text-transform:uppercase}

/* ══ TOP BAR ══ */
#bar{position:fixed;top:0;left:0;right:0;z-index:800;background:rgba(2,9,18,.88);border-bottom:1px solid var(--brd);backdrop-filter:blur(20px);display:flex;align-items:center;justify-content:space-between;padding:0 28px;height:52px;transition:background .35s,border-color .35s}
[data-theme="light"] #bar{background:rgba(240,245,252,.92)}
.brand{font-family:var(--dis);font-size:13px;color:var(--acc);letter-spacing:.05em;display:flex;align-items:center;gap:9px;text-decoration:none;cursor:none}
.bdot{width:7px;height:7px;border-radius:50%;background:var(--grn);box-shadow:0 0 10px var(--grn);animation:pulse 2s infinite}
@keyframes pulse{0%,100%{box-shadow:0 0 8px var(--grn)}50%{box-shadow:0 0 20px var(--grn)}}

.bar-right{display:flex;align-items:center;gap:8px}
.bar-btn{font-size:10px;font-family:var(--mono);padding:5px 13px;border-radius:5px;cursor:none;letter-spacing:.1em;text-transform:uppercase;transition:all .2s;border:1px solid var(--brd);background:transparent;color:var(--mut);display:flex;align-items:center;gap:6px}
.bar-btn:hover{border-color:var(--acc);color:var(--acc);background:var(--bar-bg)}
.bar-btn.active-mode{border-color:var(--acc);color:var(--acc);background:var(--bar-bg)}
.theme-btn{width:34px;height:34px;padding:0;justify-content:center}
#back-btn{display:none}
#page-title{font-size:10px;color:var(--acc);letter-spacing:.22em;text-transform:uppercase;opacity:0}

/* ══ PROGRESS BAR ══ */
#prog{position:fixed;top:52px;left:0;right:0;height:2px;background:var(--brd);z-index:700}
#prog-b{height:100%;background:linear-gradient(90deg,var(--acc),var(--acc2));width:0;transition:width .08s}

/* ══ SOCIAL SIDEBAR ══ */
#soc{position:fixed;left:16px;top:0;bottom:0;z-index:900;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:3px}
.soc-ln{width:1px;height:44px;background:linear-gradient(to bottom,transparent,var(--brd));flex-shrink:0}
.soc-ln-b{background:linear-gradient(to top,transparent,var(--brd))}
.si{width:36px;height:36px;display:flex;align-items:center;justify-content:center;color:var(--mut);text-decoration:none;border-radius:8px;transition:color .2s,background .2s,transform .2s;position:relative;flex-shrink:0;cursor:none}
.si:hover{color:var(--acc);background:var(--bar-bg);transform:translateX(4px)}
.si svg{width:16px;height:16px;display:block}
.si-tip{position:absolute;left:calc(100% + 10px);top:50%;transform:translateY(-50%);background:var(--surf2);border:1px solid var(--brd);color:var(--txt2);font-size:10px;padding:3px 9px;border-radius:4px;white-space:nowrap;pointer-events:none;opacity:0;transition:opacity .18s;letter-spacing:.05em}
.si:hover .si-tip{opacity:1}

/* ══ APP ══ */
#app{position:fixed;inset:0;top:54px;overflow:hidden}

/* ══ HOME ══ */
#pg-home{position:absolute;inset:0;overflow-y:auto;overflow-x:hidden;padding:0 clamp(60px,9vw,140px) 80px clamp(80px,12vw,180px);scrollbar-width:thin;scrollbar-color:var(--brd) transparent}
.home-hero{min-height:calc(100vh - 56px);display:flex;align-items:center}
.home-content{flex:1;max-width:640px}
.eyebrow{display:flex;align-items:center;gap:14px;margin-bottom:22px}
.ey-line{width:0;height:1px;background:linear-gradient(90deg,var(--acc),transparent)}
.ey-txt{font-size:10px;letter-spacing:.3em;text-transform:uppercase;color:var(--acc);opacity:0}
.home-h1{font-family:var(--dis);font-size:clamp(46px,7.5vw,96px);font-weight:800;line-height:.88;letter-spacing:-.04em;margin-bottom:10px}
.h1-name{display:block;clip-path:inset(0 0 100% 0);color:var(--txt)}
.h1-sur{display:block;clip-path:inset(0 0 100% 0);color:var(--acc)}
.home-role{font-size:clamp(11px,1.1vw,13px);color:var(--mut);letter-spacing:.18em;text-transform:uppercase;margin-bottom:26px;opacity:0}
.home-sub{font-size:13px;color:var(--txt2);max-width:490px;line-height:1.9;margin-bottom:32px;opacity:0;border-left:2px solid var(--brd);padding-left:18px}
.home-meta{display:flex;flex-wrap:wrap;gap:10px 22px;opacity:0;margin-bottom:38px}
.hm{font-size:11px;color:var(--mut);display:flex;align-items:center;gap:7px}
.hml{color:var(--acc);font-size:9px;letter-spacing:.1em;text-transform:uppercase}
.status-chip{display:inline-flex;align-items:center;gap:9px;border:1px solid rgba(0,255,136,.25);border-radius:20px;padding:7px 15px;background:rgba(0,255,136,.04);font-size:10px;color:var(--grn);letter-spacing:.12em;text-transform:uppercase;opacity:0;margin-bottom:24px}
.sdot{width:6px;height:6px;border-radius:50%;background:var(--grn);animation:sg 2s infinite}
@keyframes sg{0%,100%{box-shadow:0 0 6px var(--grn)}50%{box-shadow:0 0 16px var(--grn)}}
.hero-btns{display:flex;gap:11px;opacity:0;flex-wrap:wrap;margin-bottom:0}
.hbtn{display:inline-flex;align-items:center;gap:8px;padding:11px 20px;font-family:var(--mono);font-size:11px;letter-spacing:.1em;text-transform:uppercase;border-radius:6px;text-decoration:none;transition:all .25s;cursor:none}
.hbtn-p{background:linear-gradient(135deg,var(--acc),#0088bb);color:#020912;font-weight:700;box-shadow:0 0 20px rgba(0,229,255,.18)}
.hbtn-p:hover{box-shadow:0 0 36px rgba(0,229,255,.38);transform:translateY(-2px)}
.hbtn-s{border:1px solid var(--brd);color:var(--txt2)}
.hbtn-s:hover{border-color:var(--acc);color:var(--acc);background:var(--bar-bg)}
.hero-stats{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;margin-top:56px;padding-top:40px;border-top:1px solid var(--brd)}
.hstat{text-align:center}
.hstat-n{font-family:var(--dis);font-size:26px;font-weight:800;color:var(--acc);line-height:1}
.hstat-l{font-size:9px;color:var(--mut);letter-spacing:.1em;text-transform:uppercase;margin-top:3px}

/* ══ NAV CARDS ══ */
.nav-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(190px,1fr));gap:13px;margin-top:56px}
.nc{background:var(--surf);border:1px solid var(--brd);border-radius:var(--r);padding:20px 18px;cursor:none;position:relative;overflow:hidden;transition:transform .35s cubic-bezier(.22,1,.36,1),border-color .3s,box-shadow .3s,background .35s;user-select:none}
.nc::before{content:'';position:absolute;inset:0;opacity:0;transition:opacity .3s;background:radial-gradient(circle at 30% 40%,var(--bar-bg),transparent 70%)}
.nc::after{content:'';position:absolute;top:0;left:0;right:0;height:2px;transform:scaleX(0);transform-origin:left;transition:transform .4s cubic-bezier(.22,1,.36,1)}
.nc:hover{transform:translateY(-7px)}.nc:hover::before{opacity:1}.nc:hover::after{transform:scaleX(1)}
.nc-0::after{background:linear-gradient(90deg,var(--acc),#0099bb)}.nc-1::after{background:linear-gradient(90deg,var(--acc2),#a855f7)}
.nc-2::after{background:linear-gradient(90deg,var(--grn),#00aa55)}.nc-3::after{background:linear-gradient(90deg,var(--ylw),var(--org))}
.nc-4::after{background:linear-gradient(90deg,var(--org),var(--red))}.nc-5::after{background:linear-gradient(90deg,var(--acc),var(--acc2))}
.nc-0:hover{border-color:rgba(0,229,255,.35);box-shadow:0 20px 40px var(--card-shadow)}
.nc-1:hover{border-color:rgba(124,58,237,.35)}.nc-2:hover{border-color:rgba(0,255,136,.35)}
.nc-3:hover{border-color:rgba(255,215,0,.3)}.nc-4:hover{border-color:rgba(255,140,66,.3)}
.nc-5:hover{border-color:rgba(0,229,255,.35)}
.nc-ico{font-size:22px;margin-bottom:12px}.nc-num{font-size:9px;color:var(--mut);letter-spacing:.2em;margin-bottom:4px}
.nc-name{font-family:var(--dis);font-size:14px;font-weight:700;margin-bottom:4px;color:var(--txt)}
.nc-hint{font-size:10px;color:var(--mut);line-height:1.5}
.nc-arr{position:absolute;right:14px;bottom:14px;color:var(--mut);font-size:13px;transition:all .25s}
.nc:hover .nc-arr{color:var(--acc);transform:translate(3px,-3px)}

/* ══ PAGE OVERLAY ══ */
.pov{position:absolute;inset:0;background:var(--bg);z-index:100;display:none;overflow-y:auto;padding:40px clamp(18px,5vw,88px) 80px clamp(44px,7vw,108px);scrollbar-width:thin;scrollbar-color:var(--brd) transparent;transition:background .35s}
.pov::-webkit-scrollbar{width:4px}.pov::-webkit-scrollbar-thumb{background:var(--brd);border-radius:2px}
.ph{margin-bottom:40px}
.ph-label{font-size:10px;color:var(--mut);letter-spacing:.2em;text-transform:uppercase;margin-bottom:7px;display:flex;align-items:center;gap:11px}
.ph-label::after{content:'';flex:0 0 30px;height:1px;background:var(--brd)}
.ph-h{font-family:var(--dis);font-size:clamp(28px,4.5vw,54px);font-weight:800;letter-spacing:-.035em;line-height:1}
.ph-h .c{color:var(--acc)}
.ph-div{height:1px;background:linear-gradient(90deg,var(--acc),rgba(0,229,255,.1),transparent);margin-top:18px}

/* ══ SUMMARY ══ */
.sum-grid{display:grid;grid-template-columns:1fr 265px;gap:28px;align-items:start}
.sum-box{border:1px solid var(--brd);border-left:3px solid var(--acc);border-radius:0 var(--r) var(--r) 0;padding:28px 32px;background:var(--surf);font-size:13px;line-height:1.95;color:var(--txt2);position:relative;transition:background .35s,border-color .35s}
.sum-box::after{content:'// profile.txt';position:absolute;top:12px;right:16px;font-size:9px;color:var(--brd);letter-spacing:.1em}
.hl{color:var(--txt);font-weight:500}.hla{color:var(--acc)}
.sum-aside{display:flex;flex-direction:column;gap:10px}
.stat-card{background:var(--surf);border:1px solid var(--brd);border-radius:var(--r);padding:16px 18px;text-align:center;transition:all .25s,background .35s;position:relative;overflow:hidden}
.stat-card::before{content:'';position:absolute;bottom:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--acc),var(--acc2));transform:scaleX(0);transition:transform .3s}
.stat-card:hover{border-color:rgba(0,229,255,.3);transform:translateY(-3px)}.stat-card:hover::before{transform:scaleX(1)}
.stat-n{font-family:var(--dis);font-size:28px;font-weight:800;color:var(--acc);line-height:1}
.stat-l{font-size:9px;color:var(--mut);letter-spacing:.1em;margin-top:3px}

/* ══ EXPERIENCE ══ */
.tl{position:relative}
.tl-line{position:absolute;left:162px;top:0;bottom:0;width:1px;background:linear-gradient(to bottom,var(--acc),rgba(0,229,255,.05))}
.tli{display:grid;grid-template-columns:162px 1fr;padding-bottom:44px;position:relative}
.tli:last-child{padding-bottom:0}
.tl-date{font-size:10px;color:var(--mut);text-align:right;padding:5px 22px 0 0;line-height:1.55}
.tl-badge{display:inline-block;padding:2px 7px;border-radius:3px;font-size:9px;letter-spacing:.1em;text-transform:uppercase;margin-bottom:5px;background:rgba(0,255,136,.08);color:var(--grn);border:1px solid rgba(0,255,136,.2)}
.tl-body{padding-left:32px;position:relative}
.tl-body::before{content:'';position:absolute;left:-4px;top:8px;width:8px;height:8px;border-radius:50%;background:var(--bg);border:2px solid var(--acc);box-shadow:0 0 10px rgba(0,229,255,.4);transition:box-shadow .25s}
.tli:hover .tl-body::before{box-shadow:0 0 20px rgba(0,229,255,.8)}
.tl-role{font-size:13px;font-weight:700;color:var(--txt);margin-bottom:2px}
.tl-comp{font-size:11px;color:var(--acc);margin-bottom:10px;letter-spacing:.04em}
.tl-ul{list-style:none}
.tl-ul li{font-size:11px;color:var(--txt2);padding-left:15px;position:relative;margin-bottom:4px;line-height:1.7}
.tl-ul li::before{content:'▸';position:absolute;left:0;color:var(--acc);font-size:10px;top:2px}

/* ══ EDUCATION ══ */
.edu-list{display:flex;flex-direction:column;gap:14px}
.edu-c{background:var(--surf);border:1px solid var(--brd);border-radius:var(--r);padding:24px 28px;transition:all .3s cubic-bezier(.22,1,.36,1),background .35s;position:relative;overflow:hidden}
.edu-c::before{content:'';position:absolute;left:0;top:0;bottom:0;width:3px;background:linear-gradient(to bottom,var(--acc),var(--acc2));transform:scaleY(0);transform-origin:top;transition:transform .35s}
.edu-c:hover{transform:translateX(7px);border-color:rgba(0,229,255,.3)}.edu-c:hover::before{transform:scaleY(1)}
.edu-top{display:flex;justify-content:space-between;align-items:flex-start;gap:14px;margin-bottom:8px}
.edu-deg{font-family:var(--dis);font-size:14px;font-weight:700;color:var(--txt);line-height:1.3}
.edu-yr{font-size:10px;color:var(--mut);letter-spacing:.1em;flex-shrink:0;margin-top:2px}
.edu-sch{font-size:11px;color:var(--acc);margin-bottom:10px}
.edu-tags{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:10px}
.tag{font-size:9px;padding:2px 9px;border-radius:3px;border:1px solid;letter-spacing:.07em;text-transform:uppercase}
.tca{border-color:rgba(0,229,255,.3);color:var(--acc);background:rgba(0,229,255,.04)}
.tg{border-color:rgba(0,255,136,.3);color:var(--grn);background:rgba(0,255,136,.04)}
.tp{border-color:rgba(124,58,237,.3);color:#a78bfa;background:rgba(124,58,237,.04)}
.ty{border-color:rgba(255,215,0,.25);color:var(--ylw);background:rgba(255,215,0,.04)}
.tm{border-color:var(--brd);color:var(--mut)}
.edu-note{font-size:11px;color:var(--mut);line-height:1.65;padding-left:12px;border-left:1px solid var(--brd)}
.edu-note strong{color:var(--txt2)}
.courses-wrap{margin-top:32px}
.courses-label{font-size:10px;color:var(--mut);letter-spacing:.2em;text-transform:uppercase;margin-bottom:13px;display:flex;align-items:center;gap:11px}
.courses-label::after{content:'';flex:1;height:1px;background:var(--brd)}
.courses-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(215px,1fr));gap:9px}
.course-c{background:var(--surf);border:1px solid var(--brd);border-radius:8px;padding:12px 15px;display:flex;align-items:center;gap:11px;transition:all .22s,background .35s;cursor:default}
.course-c:hover{border-color:rgba(0,229,255,.25);transform:translateY(-2px);background:var(--surf2)}
.c-ico{width:30px;height:30px;border-radius:6px;display:flex;align-items:center;justify-content:center;font-size:14px;flex-shrink:0;background:var(--bar-bg);border:1px solid rgba(0,229,255,.1)}
.c-name{font-size:11px;color:var(--txt);line-height:1.3;margin-bottom:1px}
.c-org{font-size:9px;color:var(--mut);letter-spacing:.05em}

/* ══ PROJECTS ══ */
.proj-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(268px,1fr));gap:16px}
.proj-c{background:var(--surf);border:1px solid var(--brd);border-radius:var(--r);padding:24px;position:relative;overflow:hidden;transition:transform .35s cubic-bezier(.22,1,.36,1),border-color .35s,box-shadow .35s,background .35s;cursor:none}
.proj-c::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--acc),var(--acc2));transform:scaleX(0);transform-origin:left;transition:transform .4s cubic-bezier(.22,1,.36,1)}
.proj-c:hover{transform:translateY(-8px);border-color:rgba(0,229,255,.2);box-shadow:0 22px 44px rgba(0,0,0,.4)}.proj-c:hover::before{transform:scaleX(1)}
.proj-scan{position:absolute;left:0;right:0;height:40px;background:linear-gradient(transparent,rgba(0,229,255,.04),transparent);top:-40px;pointer-events:none}
.proj-c:hover .proj-scan{animation:scan 1.8s linear infinite}
@keyframes scan{0%{top:-40px}100%{top:calc(100% + 40px)}}
.proj-head{display:flex;align-items:flex-start;justify-content:space-between;margin-bottom:12px}
.proj-ico{font-size:24px}
.proj-badge{font-size:9px;padding:2px 8px;border-radius:3px;letter-spacing:.08em;text-transform:uppercase}
.pb-done{border:1px solid rgba(0,255,136,.3);color:var(--grn);background:rgba(0,255,136,.05)}
.pb-wip{border:1px solid rgba(255,215,0,.3);color:var(--ylw);background:rgba(255,215,0,.05)}
.pb-res{border:1px solid rgba(124,58,237,.3);color:#a78bfa;background:rgba(124,58,237,.05)}
.pn{font-size:13px;font-weight:700;margin-bottom:5px;color:var(--txt)}
.pd{font-size:11px;color:var(--txt2);line-height:1.7;margin-bottom:14px}
.ps{display:flex;flex-wrap:wrap;gap:5px}
.pt{font-size:9px;padding:2px 8px;background:var(--bar-bg);border:1px solid rgba(0,229,255,.12);color:rgba(0,180,220,.9);border-radius:3px;letter-spacing:.04em}

/* ══ SKILLS ══ */
.skills-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:14px;margin-bottom:44px}
.sg{background:var(--surf);border:1px solid var(--brd);border-radius:var(--r);padding:18px;transition:border-color .25s,transform .25s,background .35s}
.sg:hover{border-color:rgba(0,229,255,.22);transform:translateY(-2px)}
.sg-label{font-size:9px;text-transform:uppercase;letter-spacing:.22em;color:var(--acc);margin-bottom:12px;display:flex;align-items:center;gap:9px}
.sg-label::after{content:'';flex:1;height:1px;background:var(--brd)}
.chips{display:flex;flex-wrap:wrap;gap:5px}
.chip{font-size:10px;padding:4px 10px;background:var(--surf2);border:1px solid var(--brd);border-radius:14px;color:var(--txt2);transition:all .2s;cursor:default}
.chip:hover{border-color:rgba(0,229,255,.4);color:var(--acc);background:var(--bar-bg);transform:scale(1.04)}

/* ══ SKILLS BARS ══ */
.skills-bars-wrap{margin-bottom:44px}
.bars-label{font-size:10px;color:var(--mut);letter-spacing:.2em;text-transform:uppercase;margin-bottom:16px;display:flex;align-items:center;gap:11px}
.bars-label::after{content:'';flex:1;height:1px;background:var(--brd)}
.bar-row{display:flex;align-items:center;gap:16px;margin-bottom:12px}
.bar-name{font-size:11px;color:var(--txt2);width:160px;flex-shrink:0}
.bar-track{flex:1;height:6px;background:var(--brd);border-radius:3px;overflow:hidden}
.bar-fill{height:100%;border-radius:3px;width:0;background:linear-gradient(90deg,var(--acc),var(--acc2));transition:width 1.2s cubic-bezier(.22,1,.36,1)}
.bar-pct{font-size:10px;color:var(--acc);width:36px;text-align:right;flex-shrink:0}

/* ══ CERTS ══ */
.certs-label{font-size:10px;color:var(--mut);letter-spacing:.2em;text-transform:uppercase;margin-bottom:14px;display:flex;align-items:center;gap:11px}
.certs-label::after{content:'';flex:1;height:1px;background:var(--brd)}
.certs-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:10px}
.cci{display:flex;align-items:center;gap:12px;padding:13px 16px;background:var(--surf);border:1px solid var(--brd);border-radius:8px;transition:all .25s,background .35s;position:relative;overflow:hidden}
.cci::before{content:'';position:absolute;left:0;top:0;bottom:0;width:2px;background:linear-gradient(to bottom,var(--acc),var(--acc2));transform:scaleY(0);transform-origin:top;transition:transform .3s}
.cci:hover{border-color:rgba(0,229,255,.28);transform:translateX(4px)}.cci:hover::before{transform:scaleY(1)}
.ci{width:32px;height:32px;border-radius:7px;background:var(--bar-bg);border:1px solid rgba(0,229,255,.1);display:flex;align-items:center;justify-content:center;font-size:14px;flex-shrink:0}
.cn{font-size:11px;color:var(--txt2);line-height:1.4}

/* ══ ANALYSIS PAGE ══ */
.analysis-grid{display:grid;grid-template-columns:1fr 1fr;gap:20px;margin-bottom:32px}
.an-card{background:var(--surf);border:1px solid var(--brd);border-radius:var(--r);padding:22px;transition:background .35s,border-color .35s}
.an-title{font-size:10px;color:var(--acc);letter-spacing:.2em;text-transform:uppercase;margin-bottom:16px;display:flex;align-items:center;gap:9px}
.an-title::after{content:'';flex:1;height:1px;background:var(--brd)}
/* Radar chart */
.radar-wrap{display:flex;justify-content:center;align-items:center;padding:10px 0}
canvas#radar{max-width:220px}
/* Timeline mini */
.timeline-mini{display:flex;flex-direction:column;gap:8px}
.tm-item{display:flex;gap:12px;align-items:flex-start}
.tm-dot{width:8px;height:8px;border-radius:50%;background:var(--acc);flex-shrink:0;margin-top:3px;box-shadow:0 0 8px rgba(0,229,255,.5)}
.tm-yr{font-size:10px;color:var(--acc);min-width:44px;letter-spacing:.06em}
.tm-txt{font-size:11px;color:var(--txt2);line-height:1.5}
/* Domain bars */
.domain-row{margin-bottom:11px}
.domain-head{display:flex;justify-content:space-between;margin-bottom:5px}
.domain-name{font-size:11px;color:var(--txt2)}
.domain-pct{font-size:10px;color:var(--acc)}
.domain-bar{height:5px;background:var(--brd);border-radius:3px;overflow:hidden}
.domain-fill{height:100%;border-radius:3px;width:0;transition:width 1.3s cubic-bezier(.22,1,.36,1)}
/* Tech stack bubbles */
.tech-bubbles{display:flex;flex-wrap:wrap;gap:7px}
.tb{font-size:10px;padding:5px 12px;border-radius:20px;border:1px solid;transition:all .2s;cursor:default}
.tb:hover{transform:scale(1.07)}
.tb-blue{border-color:rgba(0,229,255,.3);color:var(--acc);background:rgba(0,229,255,.05)}
.tb-purple{border-color:rgba(124,58,237,.3);color:#a78bfa;background:rgba(124,58,237,.05)}
.tb-green{border-color:rgba(0,255,136,.3);color:var(--grn);background:rgba(0,255,136,.05)}
.tb-yellow{border-color:rgba(255,215,0,.25);color:var(--ylw);background:rgba(255,215,0,.04)}

/* ══ CONTACT ══ */
.contact-layout{display:grid;grid-template-columns:1fr 1.1fr;gap:52px;align-items:start}
.contact-l h3{font-family:var(--dis);font-size:clamp(22px,3.5vw,38px);font-weight:800;letter-spacing:-.03em;line-height:1.1;margin-bottom:14px}
.contact-l h3 .c{color:var(--acc)}
.contact-l p{font-size:12px;color:var(--txt2);line-height:1.9;margin-bottom:24px}
.ctab{display:flex;flex-direction:column;gap:9px;margin-bottom:24px}
.cta{display:inline-flex;align-items:center;gap:8px;padding:11px 20px;border:1px solid var(--acc);color:var(--acc);border-radius:6px;font-family:var(--mono);font-size:11px;letter-spacing:.1em;text-transform:uppercase;text-decoration:none;transition:all .25s;cursor:none}
.cta:hover{background:var(--acc);color:#020912;box-shadow:0 0 24px rgba(0,229,255,.3)}
.cta-s{border-color:var(--brd);color:var(--txt2)}
.cta-s:hover{border-color:var(--acc);color:var(--acc);background:var(--bar-bg)}
.cinfo{display:flex;flex-direction:column;gap:8px;padding:16px;background:var(--surf);border:1px solid var(--brd);border-radius:var(--r)}
.ci-row{display:flex;align-items:center;gap:10px;font-size:11px;color:var(--txt2)}
.ci-lbl{font-size:9px;color:var(--mut);letter-spacing:.14em;text-transform:uppercase;width:50px;flex-shrink:0}
.contact-r{display:flex;flex-direction:column;gap:9px}
.clc{display:flex;align-items:center;gap:13px;padding:13px 16px;background:var(--surf2);border:1px solid var(--brd);border-radius:var(--r);text-decoration:none;transition:all .25s,background .35s;position:relative;overflow:hidden;cursor:none}
.clc::after{content:'↗';position:absolute;right:14px;color:var(--acc);font-size:12px;opacity:0;transform:translate(-5px,5px);transition:all .22s}
.clc:hover{border-color:rgba(0,229,255,.3);transform:translateY(-3px);box-shadow:0 10px 26px rgba(0,0,0,.3)}.clc:hover::after{opacity:1;transform:translate(0,0)}
.clic{width:38px;height:38px;border-radius:8px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.clic.fb{background:rgba(24,119,242,.1);border:1px solid rgba(24,119,242,.22)}
.clic.li{background:rgba(10,102,194,.1);border:1px solid rgba(10,102,194,.22)}
.clic.ig{background:rgba(225,48,108,.1);border:1px solid rgba(225,48,108,.22)}
.clic.wa{background:rgba(37,211,102,.1);border:1px solid rgba(37,211,102,.22)}
.clic.gm{background:rgba(234,67,53,.1);border:1px solid rgba(234,67,53,.22)}
.cl-inf{flex:1}.cl-p{font-size:9px;text-transform:uppercase;letter-spacing:.12em;margin-bottom:1px}
.cl-p.fb{color:#4a9ff5}.cl-p.li{color:#5ba4e3}.cl-p.ig{color:#e1306c}.cl-p.wa{color:#25d366}.cl-p.gm{color:#ea4335}
.cl-h{font-size:11px;color:var(--txt2)}

/* ══ CLI TERMINAL ══ */
#cli{position:fixed;inset:0;top:52px;z-index:600;background:var(--cli-bg);display:none;flex-direction:column;font-family:var(--mono);transition:background .35s}
.cli-header{background:var(--surf);border-bottom:1px solid var(--cli-border);padding:10px 24px;display:flex;align-items:center;gap:12px;flex-shrink:0}
.cli-dots{display:flex;gap:6px}
.cli-dot{width:12px;height:12px;border-radius:50%}
.cli-dot-r{background:#ff5f57}.cli-dot-y{background:#ffbd2e}.cli-dot-g{background:#28c840}
.cli-title{font-size:11px;color:var(--mut);letter-spacing:.1em;flex:1;text-align:center}
.cli-hint{font-size:10px;color:var(--mut)}
#cli-output{flex:1;overflow-y:auto;padding:20px 24px;scrollbar-width:thin;scrollbar-color:var(--brd) transparent;display:flex;flex-direction:column;gap:0}
.cli-line{font-size:12px;line-height:1.7;white-space:pre-wrap;word-break:break-word}
.cli-cmd{color:var(--acc)}.cli-resp{color:var(--cli-txt)}.cli-err{color:var(--red)}
.cli-h{color:var(--acc);font-weight:700}.cli-dim{color:var(--mut)}.cli-grn{color:var(--grn)}.cli-ylw{color:var(--ylw)}.cli-pur{color:#a78bfa}
.cli-input-row{border-top:1px solid var(--cli-border);padding:12px 24px;display:flex;align-items:center;gap:10px;flex-shrink:0;background:var(--surf)}
.cli-prompt{color:var(--acc);font-size:13px;flex-shrink:0;display:flex;align-items:center;gap:6px}
.cli-prompt-path{color:var(--grn);font-size:11px}
#cli-in{background:transparent;border:none;outline:none;color:var(--txt);font-family:var(--mono);font-size:12px;flex:1;caret-color:var(--acc)}
.cli-cursor-blink{display:inline-block;width:8px;height:14px;background:var(--acc);animation:blink 1s step-end infinite;vertical-align:text-bottom}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}

/* ══ RESPONSIVE ══ */
@media(max-width:760px){
  #soc{display:none}
  .sum-grid,.analysis-grid,.contact-layout{grid-template-columns:1fr;gap:22px}
  .tl-line{left:0}.tli{grid-template-columns:1fr}
  .tl-date{text-align:left;padding:0 0 5px 16px}.tl-body{padding-left:16px}
  #pg-home{padding:0 16px 60px 16px}.pov{padding:32px 16px 60px}
  .hero-stats{grid-template-columns:repeat(2,1fr)}
  .bar-name{width:110px}
}
@media(max-width:480px){.nav-grid{grid-template-columns:1fr 1fr}.home-h1{font-size:42px}}
</style>
</head>
<body>
<canvas id="mx"></canvas>
<div id="cur"></div><div id="cur-r"></div>

<!-- LOADER -->
<div id="loader">
  <div class="ld-brand">Portfolio v4.0</div>
  <div class="ld-p" id="ld-p">0%</div>
  <div class="ld-bw"><div class="ld-b" id="ld-b"></div></div>
  <div class="ld-t" id="ld-t">Booting system...</div>
</div>

<!-- TOP BAR -->
<div id="bar">
  <a class="brand" href="#" onclick="goHome();return false">
    <div class="bdot"></div>EZZ.AMR
    <span style="color:var(--mut);font-size:10px;margin-left:2px">// v4</span>
  </a>
  <div class="bar-right">
    <div id="page-title"></div>
    <button class="bar-btn" id="normal-btn" onclick="setMode('normal')">⊞ Normal</button>
    <button class="bar-btn" id="cli-btn" onclick="setMode('cli')">▶ CLI</button>
    <button class="bar-btn theme-btn" id="theme-btn" onclick="toggleTheme()" title="Toggle theme">☀</button>
    <button class="bar-btn" id="back-btn" onclick="goHome()">← Back</button>
  </div>
</div>
<div id="prog"><div id="prog-b"></div></div>

<!-- SOCIAL SIDEBAR -->
<nav id="soc">
  <div class="soc-ln"></div>
  <a class="si" href="https://www.facebook.com/ezz206" target="_blank" rel="noopener" aria-label="Facebook">
    <svg viewBox="0 0 24 24" fill="currentColor"><path d="M22 12c0-5.523-4.477-10-10-10S2 6.477 2 12c0 4.991 3.657 9.128 8.438 9.878v-6.987H7.898V12h2.54V9.797c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.243 0-1.63.771-1.63 1.562V12h2.773l-.443 2.89h-2.33v6.988C18.343 21.128 22 16.991 22 12z"/></svg>
    <span class="si-tip">Facebook</span></a>
  <a class="si" href="https://www.linkedin.com/in/ezzeldin-amr-32ab31318" target="_blank" rel="noopener" aria-label="LinkedIn">
    <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
    <span class="si-tip">LinkedIn</span></a>
  <a class="si" href="https://www.instagram.com/ezzeldin_amr" target="_blank" rel="noopener" aria-label="Instagram">
    <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/></svg>
    <span class="si-tip">Instagram</span></a>
  <a class="si" href="https://wa.me/201286314553" target="_blank" rel="noopener" aria-label="WhatsApp">
    <svg viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
    <span class="si-tip">WhatsApp</span></a>
  <a class="si" href="mailto:ezz9432@gmail.com" aria-label="Gmail">
    <svg viewBox="0 0 24 24" fill="currentColor"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-.9.732-1.636 1.636-1.636h.749L12 11.73l9.615-7.909h.749A1.636 1.636 0 0124 5.457z"/></svg>
    <span class="si-tip">Gmail</span></a>
  <div class="soc-ln soc-ln-b"></div>
</nav>

<!-- CLI TERMINAL -->
<div id="cli">
  <div class="cli-header">
    <div class="cli-dots">
      <div class="cli-dot cli-dot-r"></div>
      <div class="cli-dot cli-dot-y"></div>
      <div class="cli-dot cli-dot-g"></div>
    </div>
    <div class="cli-title">ezzeldin@portfolio:~$ — Terminal Mode</div>
    <div class="cli-hint">Tab=autocomplete · ↑↓=history · ESC=normal mode</div>
  </div>
  <div id="cli-output"></div>
  <div class="cli-input-row">
    <span class="cli-prompt">
      <span class="cli-prompt-path">ezzeldin@portfolio</span>:<span style="color:var(--acc)">~</span>$
    </span>
    <input id="cli-in" type="text" autocomplete="off" autocorrect="off" spellcheck="false" placeholder="type 'help' to start...">
  </div>
</div>

<!-- APP -->
<div id="app">

  <!-- ══ HOME ══ -->
  <div id="pg-home">
    <div class="home-hero">
      <div class="home-content">
        <div class="status-chip" id="schip"><div class="sdot"></div>Open to Work · Available Now</div>
        <div class="eyebrow"><div class="ey-line" id="eyl"></div><div class="ey-txt" id="eyt">Cybersecurity &amp; IT Specialist</div></div>
        <div class="home-h1">
          <span class="h1-name" id="h1a">EZZELDIN</span>
          <span class="h1-sur" id="h1b">AMR</span>
        </div>
        <p class="home-role" id="hrole">SOC Operations · Penetration Testing · Medical OT · Network Security</p>
        <p class="home-sub" id="hsub">Cybersecurity specialist protecting hospital IT/OT infrastructure, conducting penetration tests, and operating SOC environments. Skilled in Python, network defence, and digital forensics.</p>
        <div class="home-meta" id="hmet">
          <div class="hm"><span class="hml">Loc</span>Sherouk, Egypt</div>
          <div class="hm"><span class="hml">Tel</span>+201286314553</div>
          <div class="hm"><span class="hml">Mail</span>ezz9432@gmail.com</div>
          <div class="hm"><span class="hml">GPA</span>3.30 · Benha University</div>
        </div>
        <div class="hero-btns" id="hbtns">
          <a class="hbtn hbtn-p" href="mailto:ezz9432@gmail.com">
            <svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-.9.732-1.636 1.636-1.636h.749L12 11.73l9.615-7.909h.749A1.636 1.636 0 0124 5.457z"/></svg>Hire Me
          </a>
          <a class="hbtn hbtn-s" href="https://www.linkedin.com/in/ezzeldin-amr-32ab31318" target="_blank" rel="noopener">LinkedIn ↗</a>
          <a class="hbtn hbtn-s" href="#" onclick="goPage('analysis');return false">Analysis ↗</a>
        </div>
        <div class="hero-stats" id="hstats">
          <div class="hstat"><div class="hstat-n">5+</div><div class="hstat-l">Yrs Experience</div></div>
          <div class="hstat"><div class="hstat-n">3.30</div><div class="hstat-l">GPA Score</div></div>
          <div class="hstat"><div class="hstat-n">5</div><div class="hstat-l">Projects Built</div></div>
          <div class="hstat"><div class="hstat-n">4</div><div class="hstat-l">Certifications</div></div>
        </div>
      </div>
    </div>
    <div class="nav-grid" id="nav-cards">
      <div class="nc nc-0" onclick="goPage('summary')"><div class="nc-ico">👤</div><div class="nc-num">01</div><div class="nc-name">Summary</div><div class="nc-hint">Profile &amp; highlights</div><div class="nc-arr">↗</div></div>
      <div class="nc nc-1" onclick="goPage('experience')"><div class="nc-ico">💼</div><div class="nc-num">02</div><div class="nc-name">Experience</div><div class="nc-hint">Work history &amp; roles</div><div class="nc-arr">↗</div></div>
      <div class="nc nc-2" onclick="goPage('education')"><div class="nc-ico">🎓</div><div class="nc-num">03</div><div class="nc-name">Education</div><div class="nc-hint">Academic background</div><div class="nc-arr">↗</div></div>
      <div class="nc nc-3" onclick="goPage('projects')"><div class="nc-ico">🛠️</div><div class="nc-num">04</div><div class="nc-name">Projects</div><div class="nc-hint">Notable builds</div><div class="nc-arr">↗</div></div>
      <div class="nc nc-4" onclick="goPage('skills')"><div class="nc-ico">⚡</div><div class="nc-num">05</div><div class="nc-name">Skills</div><div class="nc-hint">Technical arsenal</div><div class="nc-arr">↗</div></div>
      <div class="nc nc-5" onclick="goPage('analysis')"><div class="nc-ico">📊</div><div class="nc-num">06</div><div class="nc-name">Analysis</div><div class="nc-hint">Visual skill insights</div><div class="nc-arr">↗</div></div>
      <div class="nc nc-0" onclick="goPage('contact')"><div class="nc-ico">📡</div><div class="nc-num">07</div><div class="nc-name">Contact</div><div class="nc-hint">Reach out · social</div><div class="nc-arr">↗</div></div>
    </div>
  </div>

  <!-- ══ SUMMARY ══ -->
  <div class="pov" id="pg-summary">
    <div class="ph"><div class="ph-label">01 / Summary</div><div class="ph-h">About <span class="c">Me</span></div><div class="ph-div"></div></div>
    <div class="sum-grid">
      <div class="sum-box">
        Cybersecurity &amp; IT Specialist with a strong foundation in <span class="hla">Network Security</span>, <span class="hla">SOC Operations</span>, and <span class="hla">Penetration Testing</span>. Currently protecting a hospital's IT and <span class="hl">Medical OT infrastructure</span> in Egypt — ensuring network segmentation, system uptime, and compliance with cybersecurity best practices.<br><br>
        Experienced in <span class="hl">secure backend development</span> using Python and Laravel, with an academic track record recognised by a <span class="hla">Grade A+</span> graduation project in AI-powered OMR grading. Holds certifications across SOC analysis, ethical hacking, and network administration.<br><br>
        Passionate about bridging the gap between <span class="hl">operational technology</span> and information security — bringing both technical depth and the communication skills that modern security teams demand.
      </div>
      <div class="sum-aside">
        <div class="stat-card"><div class="stat-n">5+</div><div class="stat-l">Years in IT &amp; Security</div></div>
        <div class="stat-card"><div class="stat-n">3.30</div><div class="stat-l">GPA · Benha University</div></div>
        <div class="stat-card"><div class="stat-n">A+</div><div class="stat-l">Graduation Project Grade</div></div>
        <div class="stat-card"><div class="stat-n">4</div><div class="stat-l">Professional Certifications</div></div>
        <div class="stat-card"><div class="stat-n">5</div><div class="stat-l">Projects Delivered</div></div>
      </div>
    </div>
  </div>

  <!-- ══ EXPERIENCE ══ -->
  <div class="pov" id="pg-experience">
    <div class="ph"><div class="ph-label">02 / Experience</div><div class="ph-h">Work <span class="c">History</span></div><div class="ph-div"></div></div>
    <div class="tl">
      <div class="tl-line"></div>
      <div class="tli">
        <div class="tl-date"><div class="tl-badge">Current</div><br>Jan 2026 – Present</div>
        <div class="tl-body">
          <div class="tl-role">IT &amp; Medical OT Specialist</div><div class="tl-comp">Hospital Environment · Egypt</div>
          <ul class="tl-ul">
            <li>Manage full IT infrastructure including servers, endpoints, and network equipment.</li>
            <li>Secure medical devices and OT-connected systems (PACS, DICOM workflows).</li>
            <li>Design and implement network segmentation to isolate clinical from administrative zones.</li>
            <li>Monitor systems via SIEM, respond to incidents, and maintain 99%+ uptime SLA.</li>
            <li>Apply NIST and IEC 62443 cybersecurity controls within the healthcare environment.</li>
            <li>Produce technical documentation, risk assessments, and security audit reports.</li>
          </ul>
        </div>
      </div>
      <div class="tli">
        <div class="tl-date">2019 – Present</div>
        <div class="tl-body">
          <div class="tl-role">Programming Instructor</div><div class="tl-comp">Education · Ages 6–18</div>
          <ul class="tl-ul">
            <li>Design and deliver project-based programming curriculum for students aged 6–18.</li>
            <li>Cover Python, Scratch, and computational thinking fundamentals.</li>
            <li>Build students' logical problem-solving and creative technology skills.</li>
          </ul>
        </div>
      </div>
      <div class="tli">
        <div class="tl-date">Aug–Sep 2021</div>
        <div class="tl-body">
          <div class="tl-role">IT Intern</div><div class="tl-comp">Banque Misr · Cairo, Egypt</div>
          <ul class="tl-ul">
            <li>Supported day-to-day system operations and secure banking workflows.</li>
            <li>Assisted in IT monitoring, helpdesk tickets, and technical support tasks.</li>
            <li>Gained exposure to financial-sector security policies and compliance procedures.</li>
          </ul>
        </div>
      </div>
      <div class="tli">
        <div class="tl-date">Jan–Feb 2020</div>
        <div class="tl-body">
          <div class="tl-role">IT Intern</div><div class="tl-comp">Petrojet · Egypt</div>
          <ul class="tl-ul">
            <li>Assisted IT teams with SAP ERP system operations and user support.</li>
            <li>Supported secure data handling and internal system processes.</li>
          </ul>
        </div>
      </div>
      <div class="tli">
        <div class="tl-date">Jun–Jul 2019</div>
        <div class="tl-body">
          <div class="tl-role">Data Center Intern</div><div class="tl-comp">Petrojet · Egypt</div>
          <ul class="tl-ul">
            <li>Supported data center monitoring and enterprise network operations.</li>
            <li>Learned enterprise infrastructure, rack management, and cabling fundamentals.</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

  <!-- ══ EDUCATION ══ -->
  <div class="pov" id="pg-education">
    <div class="ph"><div class="ph-label">03 / Education</div><div class="ph-h">Academic <span class="c">Background</span></div><div class="ph-div"></div></div>
    <div class="edu-list">
      <div class="edu-c">
        <div class="edu-top"><div><div class="edu-deg">B.Sc. Information Security &amp; Digital Forensics</div><div class="edu-sch">Benha University — Faculty of Computers &amp; Informatics</div></div><div class="edu-yr">2023 – 2025</div></div>
        <div class="edu-tags"><span class="tag tg">GPA: 3.30</span><span class="tag ty">Graduation Project: A+</span><span class="tag tca">Information Security</span><span class="tag tp">Digital Forensics</span></div>
        <div class="edu-note"><strong>Graduation Project: OMR Auto Grading System</strong> — AI-powered bubble sheet detection using Python, OpenCV, and NumPy. Fully automated scoring with high-accuracy contour detection. Awarded <strong>Grade A+</strong> by faculty committee.</div>
      </div>
      <div class="edu-c">
        <div class="edu-top"><div><div class="edu-deg">Cyber Security Track Program</div><div class="edu-sch">Benha University — Specialisation Track</div></div><div class="edu-yr">2023 – 2025</div></div>
        <div class="edu-tags"><span class="tag tca">SOC Analysis</span><span class="tag tp">Penetration Testing</span><span class="tag tca">Network Defence</span><span class="tag tm">Blue Team</span></div>
        <div class="edu-note">Intensive track covering offensive and defensive security — hands-on labs in vulnerability scanning, SIEM tuning, malware analysis, and incident response workflows.</div>
      </div>
      <div class="edu-c">
        <div class="edu-top"><div><div class="edu-deg">General Studies</div><div class="edu-sch">Ain Shams University</div></div><div class="edu-yr">2021 – 2023</div></div>
        <div class="edu-tags"><span class="tag tm">Foundation Studies</span><span class="tag tm">Science &amp; Technology</span></div>
      </div>
    </div>
    <div class="courses-wrap">
      <div class="courses-label">Professional Certifications</div>
      <div class="courses-grid">
        <div class="course-c"><div class="c-ico">🔵</div><div><div class="c-name">Cyber Security Diploma — Blue Team (SOC Analyst)</div><div class="c-org">Professional Certification</div></div></div>
        <div class="course-c"><div class="c-ico">🌐</div><div><div class="c-name">CCNA &amp; Network Security Certificate</div><div class="c-org">Cisco Networking Academy</div></div></div>
        <div class="course-c"><div class="c-ico">🔴</div><div><div class="c-name">Certified Assistant Penetration Tester (CAPT)</div><div class="c-org">Red Team Certification</div></div></div>
        <div class="course-c"><div class="c-ico">📊</div><div><div class="c-name">Data Analysis Nanodegree</div><div class="c-org">Udacity</div></div></div>
      </div>
    </div>
  </div>

  <!-- ══ PROJECTS ══ -->
  <div class="pov" id="pg-projects">
    <div class="ph"><div class="ph-label">04 / Projects</div><div class="ph-h">Notable <span class="c">Builds</span></div><div class="ph-div"></div></div>
    <div class="proj-grid">
      <div class="proj-c"><div class="proj-scan"></div><div class="proj-head"><div class="proj-ico">🤖</div><span class="proj-badge pb-done">Grade A+</span></div><div class="pn">OMR Auto Grading System</div><div class="pd">AI-powered bubble sheet grading using computer vision. Detects filled circles with high accuracy via contour analysis — zero human intervention. Graduation project.</div><div class="ps"><span class="pt">Python</span><span class="pt">OpenCV</span><span class="pt">NumPy</span><span class="pt">AI/ML</span><span class="pt">Image Processing</span></div></div>
      <div class="proj-c"><div class="proj-scan"></div><div class="proj-head"><div class="proj-ico">🎓</div><span class="proj-badge pb-done">Completed</span></div><div class="pn">E-Learning Platform</div><div class="pd">Full secure backend with role-based authentication (student/instructor/admin), relational schema design, and REST API endpoints for course management.</div><div class="ps"><span class="pt">Laravel</span><span class="pt">PHP</span><span class="pt">MySQL</span><span class="pt">REST API</span><span class="pt">Auth</span></div></div>
      <div class="proj-c"><div class="proj-scan"></div><div class="proj-head"><div class="proj-ico">🛡️</div><span class="proj-badge pb-res">Research</span></div><div class="pn">Cybersecurity AV Research Tool</div><div class="pd">Research tool exploring malware detection and prevention. Analyzes signature-based vs behaviour-based detection approaches and common evasion strategies.</div><div class="ps"><span class="pt">Malware Analysis</span><span class="pt">Python</span><span class="pt">Detection</span></div></div>
      <div class="proj-c"><div class="proj-scan"></div><div class="proj-head"><div class="proj-ico">💰</div><span class="proj-badge pb-done">Completed</span></div><div class="pn">Financial Manager App</div><div class="pd">Mobile electronic wallet with real-time transaction tracking, Firebase cloud storage, and secure user authentication.</div><div class="ps"><span class="pt">Java</span><span class="pt">Firebase</span><span class="pt">Android</span></div></div>
      <div class="proj-c"><div class="proj-scan"></div><div class="proj-head"><div class="proj-ico">📝</div><span class="proj-badge pb-wip">In Progress</span></div><div class="pn">Automatic Test Evaluator</div><div class="pd">Ongoing academic system extending the OMR project toward multi-question type support under faculty supervision.</div><div class="ps"><span class="pt">Automation</span><span class="pt">Computer Vision</span><span class="pt">Academic</span></div></div>
    </div>
  </div>

  <!-- ══ SKILLS ══ -->
  <div class="pov" id="pg-skills">
    <div class="ph"><div class="ph-label">05 / Skills</div><div class="ph-h">Technical <span class="c">Arsenal</span></div><div class="ph-div"></div></div>
    <div class="skills-grid">
      <div class="sg"><div class="sg-label">Cybersecurity</div><div class="chips"><span class="chip">OWASP Top 10</span><span class="chip">Pen Testing</span><span class="chip">Vuln. Assessment</span><span class="chip">SIEM – Splunk</span><span class="chip">Wazuh</span><span class="chip">Incident Response</span><span class="chip">Digital Forensics</span><span class="chip">Cryptography</span><span class="chip">Secure Coding</span></div></div>
      <div class="sg"><div class="sg-label">Networking</div><div class="chips"><span class="chip">TCP/IP</span><span class="chip">Subnetting</span><span class="chip">VLANs</span><span class="chip">NAT</span><span class="chip">OSPF</span><span class="chip">Firewall Policies</span><span class="chip">VPN</span><span class="chip">Network Security</span></div></div>
      <div class="sg"><div class="sg-label">Security Tools</div><div class="chips"><span class="chip">Nmap</span><span class="chip">Metasploit</span><span class="chip">Burp Suite</span><span class="chip">Wireshark</span><span class="chip">Hydra</span><span class="chip">John the Ripper</span><span class="chip">theHarvester</span><span class="chip">Maltego</span></div></div>
      <div class="sg"><div class="sg-label">Programming</div><div class="chips"><span class="chip">Python</span><span class="chip">C / C++</span><span class="chip">C#</span><span class="chip">PHP (Laravel)</span><span class="chip">Java</span><span class="chip">SQL / MySQL</span></div></div>
      <div class="sg"><div class="sg-label">Medical OT / IT</div><div class="chips"><span class="chip">OT Security</span><span class="chip">Network Segmentation</span><span class="chip">IT Infrastructure</span><span class="chip">Hospital IT</span><span class="chip">IEC 62443</span><span class="chip">NIST CSF</span></div></div>
      <div class="sg"><div class="sg-label">Soft Skills</div><div class="chips"><span class="chip">Technical Reporting</span><span class="chip">Team Collaboration</span><span class="chip">Problem Solving</span><span class="chip">Teaching</span><span class="chip">Documentation</span></div></div>
    </div>
    <div class="skills-bars-wrap">
      <div class="bars-label">Proficiency Levels</div>
      <div id="skill-bars">
        <div class="bar-row"><div class="bar-name">Network Security</div><div class="bar-track"><div class="bar-fill" data-pct="90"></div></div><div class="bar-pct">90%</div></div>
        <div class="bar-row"><div class="bar-name">Penetration Testing</div><div class="bar-track"><div class="bar-fill" data-pct="82"></div></div><div class="bar-pct">82%</div></div>
        <div class="bar-row"><div class="bar-name">SOC / SIEM</div><div class="bar-track"><div class="bar-fill" data-pct="85"></div></div><div class="bar-pct">85%</div></div>
        <div class="bar-row"><div class="bar-name">Python</div><div class="bar-track"><div class="bar-fill" data-pct="80"></div></div><div class="bar-pct">80%</div></div>
        <div class="bar-row"><div class="bar-name">Digital Forensics</div><div class="bar-track"><div class="bar-fill" data-pct="72"></div></div><div class="bar-pct">72%</div></div>
        <div class="bar-row"><div class="bar-name">Medical OT</div><div class="bar-track"><div class="bar-fill" data-pct="78"></div></div><div class="bar-pct">78%</div></div>
        <div class="bar-row"><div class="bar-name">Laravel / PHP</div><div class="bar-track"><div class="bar-fill" data-pct="70"></div></div><div class="bar-pct">70%</div></div>
      </div>
    </div>
    <div class="certs-label">Certifications</div>
    <div class="certs-grid">
      <div class="cci"><div class="ci">🔵</div><div class="cn">Cyber Security Diploma – Blue Team (SOC Analyst)</div></div>
      <div class="cci"><div class="ci">🌐</div><div class="cn">CCNA &amp; Network Security Certificate</div></div>
      <div class="cci"><div class="ci">🔴</div><div class="cn">Certified Assistant Penetration Tester (CAPT)</div></div>
      <div class="cci"><div class="ci">📊</div><div class="cn">Data Analysis Nanodegree – Udacity</div></div>
    </div>
  </div>

  <!-- ══ ANALYSIS ══ -->
  <div class="pov" id="pg-analysis">
    <div class="ph"><div class="ph-label">06 / Analysis</div><div class="ph-h">Skills <span class="c">Insights</span></div><div class="ph-div"></div></div>
    <div class="analysis-grid">
      <div class="an-card">
        <div class="an-title">Domain Expertise</div>
        <div class="domain-row"><div class="domain-head"><span class="domain-name">Cybersecurity &amp; SOC</span><span class="domain-pct">90%</span></div><div class="domain-bar"><div class="domain-fill" data-pct="90" style="background:linear-gradient(90deg,#00e5ff,#0088bb)"></div></div></div>
        <div class="domain-row"><div class="domain-head"><span class="domain-name">Network Security</span><span class="domain-pct">88%</span></div><div class="domain-bar"><div class="domain-fill" data-pct="88" style="background:linear-gradient(90deg,#7c3aed,#a855f7)"></div></div></div>
        <div class="domain-row"><div class="domain-head"><span class="domain-name">Penetration Testing</span><span class="domain-pct">82%</span></div><div class="domain-bar"><div class="domain-fill" data-pct="82" style="background:linear-gradient(90deg,#00ff88,#00aa55)"></div></div></div>
        <div class="domain-row"><div class="domain-head"><span class="domain-name">Medical OT Security</span><span class="domain-pct">78%</span></div><div class="domain-bar"><div class="domain-fill" data-pct="78" style="background:linear-gradient(90deg,#ffd700,#ff8c42)"></div></div></div>
        <div class="domain-row"><div class="domain-head"><span class="domain-name">Backend Development</span><span class="domain-pct">72%</span></div><div class="domain-bar"><div class="domain-fill" data-pct="72" style="background:linear-gradient(90deg,#ff4466,#ff8c42)"></div></div></div>
        <div class="domain-row"><div class="domain-head"><span class="domain-name">Digital Forensics</span><span class="domain-pct">70%</span></div><div class="domain-bar"><div class="domain-fill" data-pct="70" style="background:linear-gradient(90deg,#a78bfa,#7c3aed)"></div></div></div>
      </div>
      <div class="an-card">
        <div class="an-title">Career Timeline</div>
        <div class="timeline-mini">
          <div class="tm-item"><div class="tm-dot"></div><span class="tm-yr">2026</span><span class="tm-txt">IT &amp; Medical OT Specialist — Hospital (Current)</span></div>
          <div class="tm-item"><div class="tm-dot" style="background:var(--acc2)"></div><span class="tm-yr">2025</span><span class="tm-txt">B.Sc. Info Security &amp; Digital Forensics — Graduated (GPA 3.30, A+)</span></div>
          <div class="tm-item"><div class="tm-dot" style="background:var(--grn)"></div><span class="tm-yr">2023</span><span class="tm-txt">Enrolled Cyber Security Track + CAPT Certification</span></div>
          <div class="tm-item"><div class="tm-dot" style="background:var(--ylw)"></div><span class="tm-yr">2021</span><span class="tm-txt">IT Intern at Banque Misr · Started teaching programming</span></div>
          <div class="tm-item"><div class="tm-dot" style="background:var(--org)"></div><span class="tm-yr">2020</span><span class="tm-txt">IT Intern — Petrojet (SAP operations)</span></div>
          <div class="tm-item"><div class="tm-dot" style="background:var(--red)"></div><span class="tm-yr">2019</span><span class="tm-txt">Data Center Intern — Petrojet · CCNA Certification</span></div>
        </div>
      </div>
      <div class="an-card">
        <div class="an-title">Technology Stack</div>
        <div class="tech-bubbles">
          <span class="tb tb-blue">Python</span><span class="tb tb-blue">Nmap</span><span class="tb tb-blue">Burp Suite</span><span class="tb tb-blue">Wireshark</span>
          <span class="tb tb-purple">Metasploit</span><span class="tb tb-purple">Splunk</span><span class="tb tb-purple">Wazuh</span><span class="tb tb-purple">Maltego</span>
          <span class="tb tb-green">Laravel</span><span class="tb tb-green">MySQL</span><span class="tb tb-green">Java</span><span class="tb tb-green">OpenCV</span>
          <span class="tb tb-yellow">C/C++</span><span class="tb tb-yellow">Hydra</span><span class="tb tb-yellow">John the Ripper</span>
          <span class="tb tb-blue">theHarvester</span><span class="tb tb-purple">C#</span><span class="tb tb-green">Firebase</span>
        </div>
      </div>
      <div class="an-card">
        <div class="an-title">Key Strengths</div>
        <div class="timeline-mini">
          <div class="tm-item"><div class="tm-dot" style="background:var(--acc)"></div><span class="tm-yr" style="min-width:16px"></span><span class="tm-txt"><strong style="color:var(--acc)">Healthcare Security</strong> — Rare combination of IT + OT + clinical security expertise</span></div>
          <div class="tm-item"><div class="tm-dot" style="background:var(--acc2)"></div><span class="tm-yr" style="min-width:16px"></span><span class="tm-txt"><strong style="color:#a78bfa">Blue &amp; Red Team</strong> — Certified in both SOC analysis and penetration testing</span></div>
          <div class="tm-item"><div class="tm-dot" style="background:var(--grn)"></div><span class="tm-yr" style="min-width:16px"></span><span class="tm-txt"><strong style="color:var(--grn)">Education Background</strong> — Teaching skills make for exceptional documentation &amp; communication</span></div>
          <div class="tm-item"><div class="tm-dot" style="background:var(--ylw)"></div><span class="tm-yr" style="min-width:16px"></span><span class="tm-txt"><strong style="color:var(--ylw)">AI + Security</strong> — Applied machine learning to a real security-adjacent problem (OMR)</span></div>
        </div>
      </div>
    </div>
  </div>

  <!-- ══ CONTACT ══ -->
  <div class="pov" id="pg-contact">
    <div class="ph"><div class="ph-label">07 / Contact</div><div class="ph-h">Let's <span class="c">Connect</span></div><div class="ph-div"></div></div>
    <div class="contact-layout">
      <div class="contact-l">
        <h3>Open to<br><span class="c">Opportunities</span></h3>
        <p>Looking for roles in Cybersecurity, SOC Analysis, Penetration Testing, or IT/OT Security. Available immediately.</p>
        <div class="ctab">
          <a class="cta" href="mailto:ezz9432@gmail.com"><svg width="12" height="12" viewBox="0 0 24 24" fill="currentColor"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-.9.732-1.636 1.636-1.636h.749L12 11.73l9.615-7.909h.749A1.636 1.636 0 0124 5.457z"/></svg>Send Email</a>
          <a class="cta cta-s" href="https://wa.me/201286314553" target="_blank" rel="noopener">WhatsApp ↗</a>
        </div>
        <div class="cinfo">
          <div class="ci-row"><span class="ci-lbl">Phone</span>+201286314553</div>
          <div class="ci-row"><span class="ci-lbl">Email</span>ezz9432@gmail.com</div>
          <div class="ci-row"><span class="ci-lbl">Location</span>Sherouk, Egypt</div>
          <div class="ci-row"><span class="ci-lbl">Status</span><span style="color:var(--grn)">● Available Now</span></div>
        </div>
      </div>
      <div class="contact-r">
        <a class="clc" href="https://www.facebook.com/ezz206" target="_blank" rel="noopener"><div class="clic fb"><svg width="17" height="17" viewBox="0 0 24 24" fill="#4a9ff5"><path d="M22 12c0-5.523-4.477-10-10-10S2 6.477 2 12c0 4.991 3.657 9.128 8.438 9.878v-6.987H7.898V12h2.54V9.797c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.243 0-1.63.771-1.63 1.562V12h2.773l-.443 2.89h-2.33v6.988C18.343 21.128 22 16.991 22 12z"/></svg></div><div class="cl-inf"><div class="cl-p fb">Facebook</div><div class="cl-h">fb.com/ezz206</div></div></a>
        <a class="clc" href="https://www.linkedin.com/in/ezzeldin-amr-32ab31318" target="_blank" rel="noopener"><div class="clic li"><svg width="17" height="17" viewBox="0 0 24 24" fill="#5ba4e3"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg></div><div class="cl-inf"><div class="cl-p li">LinkedIn</div><div class="cl-h">Ezzeldin Amr</div></div></a>
        <a class="clc" href="https://www.instagram.com/ezzeldin_amr" target="_blank" rel="noopener"><div class="clic ig"><svg width="17" height="17" viewBox="0 0 24 24" fill="#e1306c"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/></svg></div><div class="cl-inf"><div class="cl-p ig">Instagram</div><div class="cl-h">@ezzeldin_amr</div></div></a>
        <a class="clc" href="https://wa.me/201286314553" target="_blank" rel="noopener"><div class="clic wa"><svg width="17" height="17" viewBox="0 0 24 24" fill="#25d366"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg></div><div class="cl-inf"><div class="cl-p wa">WhatsApp</div><div class="cl-h">+201286314553</div></div></a>
        <a class="clc" href="mailto:ezz9432@gmail.com"><div class="clic gm"><svg width="17" height="17" viewBox="0 0 24 24" fill="#ea4335"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-.9.732-1.636 1.636-1.636h.749L12 11.73l9.615-7.909h.749A1.636 1.636 0 0124 5.457z"/></svg></div><div class="cl-inf"><div class="cl-p gm">Gmail</div><div class="cl-h">ezz9432@gmail.com</div></div></a>
      </div>
    </div>
  </div>

</div><!-- /app -->

<script>
gsap.registerPlugin(ScrollTrigger);

/* ══ MATRIX ══ */
const cv=document.getElementById('mx'),cx=cv.getContext('2d');
const CHARS='アイウエオカキクケコ0123456789ABCDEF</>[]{}#@!%';
const FS=14;let cols,drops;
function initMx(){cv.width=innerWidth;cv.height=innerHeight;cols=Math.floor(cv.width/FS);drops=Array(cols).fill(1)}
initMx();window.addEventListener('resize',initMx);
setInterval(()=>{
  cx.fillStyle='rgba(2,9,18,.055)';cx.fillRect(0,0,cv.width,cv.height);
  for(let i=0;i<drops.length;i++){
    cx.fillStyle=Math.random()>.97?'#00ff88':'rgba(0,229,255,.45)';
    cx.font=FS+'px JetBrains Mono,monospace';
    cx.fillText(CHARS[Math.floor(Math.random()*CHARS.length)],i*FS,drops[i]*FS);
    if(drops[i]*FS>cv.height&&Math.random()>.976)drops[i]=0;
    drops[i]++;
  }
},58);

/* ══ CURSOR ══ */
const cur=document.getElementById('cur'),cr=document.getElementById('cur-r');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY});
(function tick(){cur.style.left=mx+'px';cur.style.top=my+'px';rx+=(mx-rx)*.11;ry+=(my-ry)*.11;cr.style.left=rx+'px';cr.style.top=ry+'px';requestAnimationFrame(tick)})();

/* ══ THEME ══ */
function toggleTheme(){
  const html=document.documentElement;
  const isDark=html.getAttribute('data-theme')==='dark';
  html.setAttribute('data-theme',isDark?'light':'dark');
  document.getElementById('theme-btn').textContent=isDark?'🌙':'☀';
}

/* ══ MODE ══ */
let currentMode='normal';
function setMode(m){
  currentMode=m;
  const cli=document.getElementById('cli');
  const app=document.getElementById('app');
  if(m==='cli'){
    cli.style.display='flex';
    app.style.display='none';
    document.getElementById('normal-btn').classList.remove('active-mode');
    document.getElementById('cli-btn').classList.add('active-mode');
    document.getElementById('cli-in').focus();
    if(!cliBooted){bootCLI();cliBooted=true;}
  } else {
    cli.style.display='none';
    app.style.display='block';
    document.getElementById('normal-btn').classList.add('active-mode');
    document.getElementById('cli-btn').classList.remove('active-mode');
  }
}

/* ══ LOADER ══ */
const ldMsgs=['Booting system...','Loading modules...','Decrypting assets...','Access granted ✓'];
let pct=0;
const pEl=document.getElementById('ld-p'),bEl=document.getElementById('ld-b'),tEl=document.getElementById('ld-t');
const ldT=setInterval(()=>{
  pct+=Math.random()*9+2;if(pct>100)pct=100;
  pEl.textContent=Math.floor(pct)+'%';bEl.style.width=pct+'%';
  tEl.textContent=ldMsgs[Math.min(3,Math.floor(pct/28))];
  if(pct>=100){clearInterval(ldT);setTimeout(()=>{gsap.to('#loader',{opacity:0,duration:.5,onComplete:()=>{document.getElementById('loader').style.display='none';launchHero()}})},350)}
},55);

function launchHero(){
  setMode('normal');
  const tl=gsap.timeline();
  tl.to('#schip',{opacity:1,duration:.5,ease:'power3.out'})
    .to('#eyl',{width:44,duration:.6,ease:'power2.out'},'-=.1')
    .to('#eyt',{opacity:1,duration:.4},'-=.2')
    .to('#h1a',{clipPath:'inset(0 0 0% 0)',duration:.75,ease:'power4.out'},'-=.1')
    .to('#h1b',{clipPath:'inset(0 0 0% 0)',duration:.75,ease:'power4.out'},'-=.55')
    .to('#hrole',{opacity:1,duration:.5},'-=.3')
    .to('#hsub',{opacity:1,duration:.55},'-=.2')
    .to('#hmet',{opacity:1,duration:.5},'-=.2')
    .to('#hbtns',{opacity:1,duration:.5},'-=.2');
  gsap.from('.hstat',{opacity:0,y:18,stagger:.09,duration:.5,delay:1.4,ease:'power3.out'});
  gsap.from('.nc',{opacity:0,y:32,stagger:.07,duration:.5,delay:1.6,ease:'power3.out'});
}

/* ══ SKILL BARS ══ */
function animateBars(pageId){
  const bars=document.querySelectorAll('#pg-'+pageId+' .bar-fill, #pg-'+pageId+' .domain-fill');
  setTimeout(()=>{bars.forEach(b=>{b.style.width=(b.dataset.pct||'0')+'%'})},300);
}

/* ══ NAV ══ */
let active=null;
const NAMES={summary:'Summary',experience:'Experience',education:'Education',projects:'Projects',skills:'Skills',analysis:'Analysis',contact:'Contact'};

function goPage(id){
  const ov=document.getElementById('pg-'+id);
  const home=document.getElementById('pg-home');
  active=id;
  gsap.set(ov,{display:'block',opacity:0,x:'4%'});
  ov.scrollTop=0;
  document.getElementById('prog-b').style.width='0';
  document.getElementById('back-btn').style.display='flex';
  const pt=document.getElementById('page-title');pt.textContent=NAMES[id];
  gsap.timeline()
    .to(home,{x:'-6%',opacity:0,duration:.38,ease:'power3.in'})
    .to(ov,{opacity:1,x:'0%',duration:.42,ease:'power3.out'},'-=.1');
  gsap.to(pt,{opacity:1,duration:.3,delay:.18});
  if(id==='skills'||id==='analysis')animateBars(id);
}

function goHome(){
  if(!active)return;
  const ov=document.getElementById('pg-'+active);
  const home=document.getElementById('pg-home');
  const pt=document.getElementById('page-title');
  gsap.timeline({onComplete:()=>{gsap.set(ov,{display:'none'});gsap.set(ov,{clearProps:'opacity,x'});active=null;document.getElementById('prog-b').style.width='0'}})
    .to(ov,{opacity:0,x:'4%',duration:.35,ease:'power3.in'})
    .fromTo(home,{x:'-6%',opacity:0},{x:'0%',opacity:1,duration:.4,ease:'power3.out'},'-=.08');
  document.getElementById('back-btn').style.display='none';
  gsap.to(pt,{opacity:0,duration:.2});
}

document.querySelectorAll('.pov').forEach(pg=>{pg.addEventListener('scroll',()=>{const p=pg.scrollTop/(pg.scrollHeight-pg.clientHeight)*100;document.getElementById('prog-b').style.width=p+'%'})});
document.addEventListener('keydown',e=>{if(e.key==='Escape'){if(currentMode==='cli')setMode('normal');else if(active)goHome()}});

/* ══ CLI ENGINE ══ */
let cliBooted=false;
let cliHistory=[],cliHistIdx=-1;
const CMDS=['help','whoami','summary','experience','education','projects','skills','certifications','contact','clear','exit','ls','date'];

const D={
  whoami:`<span class="cli-grn">Ezzeldin Amr Abdelghane</span>
  Role     : Cybersecurity & IT Specialist
  Location : Sherouk, Egypt 🇪🇬
  Email    : ezz9432@gmail.com
  Phone    : +201286314553
  LinkedIn : linkedin.com/in/ezzeldin-amr-32ab31318
  Status   : <span class="cli-grn">● Open to Work — Available Now</span>`,

  summary:`<span class="cli-h">// PROFESSIONAL SUMMARY</span>
Cybersecurity & IT Specialist with 5+ years across SOC operations,
penetration testing, network security, and Medical OT environments.
Currently securing hospital IT infrastructure in Egypt.

<span class="cli-ylw">Highlights:</span>
  → B.Sc. Information Security & Digital Forensics (GPA 3.30, A+)
  → CAPT Certified · CCNA · SOC Analyst Diploma · Udacity Nanodegree
  → Hands-on with Splunk, Wazuh, Metasploit, Burp Suite, Nmap
  → Secure backend: Python, Laravel, MySQL
  → Medical OT: NIST CSF, IEC 62443 frameworks`,

  experience:`<span class="cli-h">// WORK EXPERIENCE</span>

<span class="cli-grn">IT & Medical OT Specialist</span> — Hospital, Egypt  <span class="cli-dim">[Jan 2026 – Present]</span>
  → Manage IT infrastructure, servers, network equipment
  → Secure OT-connected medical devices (PACS, DICOM)
  → Network segmentation · SIEM monitoring · Incident response
  → Apply NIST & IEC 62443 controls in healthcare environment

<span class="cli-grn">Programming Instructor</span>  <span class="cli-dim">[2019 – Present]</span>
  → Python & Scratch curriculum for students aged 6–18

<span class="cli-grn">IT Intern</span> — Banque Misr  <span class="cli-dim">[Aug–Sep 2021]</span>
  → System operations, IT monitoring, banking workflows

<span class="cli-grn">IT Intern</span> — Petrojet  <span class="cli-dim">[Jan–Feb 2020]</span>
  → SAP ERP support, secure data handling

<span class="cli-grn">Data Center Intern</span> — Petrojet  <span class="cli-dim">[Jun–Jul 2019]</span>
  → Data center monitoring, enterprise network ops`,

  education:`<span class="cli-h">// EDUCATION</span>

<span class="cli-grn">B.Sc. Information Security & Digital Forensics</span>
  Benha University — Faculty of Computers & Informatics
  Year: 2023–2025 | GPA: <span class="cli-ylw">3.30</span> | Grad Project: <span class="cli-ylw">A+</span>
  Project: OMR Auto Grading System (Python, OpenCV, NumPy)

<span class="cli-grn">Cyber Security Track Program</span>
  Benha University | 2023–2025
  Focus: SOC, Pen Testing, Network Defence, Blue Team

<span class="cli-grn">General Studies</span>
  Ain Shams University | 2021–2023`,

  projects:`<span class="cli-h">// PROJECTS</span>

<span class="cli-grn">[1] OMR Auto Grading System</span>  <span class="cli-ylw">Grade: A+</span>
    AI bubble-sheet grading · Python · OpenCV · NumPy

<span class="cli-grn">[2] E-Learning Platform</span>
    Secure backend, role-based auth · Laravel · PHP · MySQL

<span class="cli-grn">[3] Cybersecurity AV Research Tool</span>  <span class="cli-pur">[Research]</span>
    Malware detection & prevention study · Python

<span class="cli-grn">[4] Financial Manager App</span>
    Electronic wallet · Java · Firebase · Android

<span class="cli-grn">[5] Automatic Test Evaluator</span>  <span class="cli-ylw">[In Progress]</span>
    Multi-question exam evaluation under faculty supervision`,

  skills:`<span class="cli-h">// TECHNICAL SKILLS</span>

<span class="cli-ylw">Cybersecurity:</span>
  OWASP Top 10, Pen Testing, Vuln. Assessment, SIEM (Splunk, Wazuh)
  Incident Response, Digital Forensics, Cryptography, Secure Coding

<span class="cli-ylw">Networking:</span>
  TCP/IP, Subnetting, VLANs, NAT, OSPF, Firewall Policies, VPN

<span class="cli-ylw">Tools:</span>
  Nmap, Metasploit, Burp Suite, Wireshark, Hydra,
  John the Ripper, theHarvester, Maltego

<span class="cli-ylw">Programming:</span>
  Python, C/C++, C#, PHP (Laravel), Java, SQL/MySQL

<span class="cli-ylw">Medical OT / IT:</span>
  OT Security, Network Segmentation, IEC 62443, NIST CSF`,

  certifications:`<span class="cli-h">// CERTIFICATIONS</span>

  🔵  Cyber Security Diploma — Blue Team (SOC Analyst)
  🌐  CCNA & Network Security Certificate
  🔴  Certified Assistant Penetration Tester (CAPT)
  📊  Data Analysis Nanodegree — Udacity`,

  contact:`<span class="cli-h">// CONTACT INFO</span>

  📧  ezz9432@gmail.com
  📞  +201286314553
  📍  Sherouk, Egypt
  💼  linkedin.com/in/ezzeldin-amr-32ab31318
  📘  facebook.com/ezz206
  📸  instagram.com/ezzeldin_amr
  💬  wa.me/201286314553

  <span class="cli-grn">Status: ● Open to Work · Available Immediately</span>`,

  ls:`<span class="cli-dim">drwxr-xr-x</span>  summary/
<span class="cli-dim">drwxr-xr-x</span>  experience/
<span class="cli-dim">drwxr-xr-x</span>  education/
<span class="cli-dim">drwxr-xr-x</span>  projects/
<span class="cli-dim">drwxr-xr-x</span>  skills/
<span class="cli-dim">drwxr-xr-x</span>  certifications/
<span class="cli-dim">drwxr-xr-x</span>  contact/
<span class="cli-dim">-rw-r--r--</span>  profile.txt
<span class="cli-dim">-rw-r--r--</span>  resume.pdf`,

  help:`<span class="cli-h">// AVAILABLE COMMANDS</span>

  <span class="cli-grn">whoami</span>          → Who is Ezzeldin?
  <span class="cli-grn">summary</span>         → Professional overview
  <span class="cli-grn">experience</span>      → Full work history
  <span class="cli-grn">education</span>       → Academic background
  <span class="cli-grn">projects</span>        → Notable builds
  <span class="cli-grn">skills</span>          → Technical skills
  <span class="cli-grn">certifications</span>  → Professional certs
  <span class="cli-grn">contact</span>         → Contact & social links
  <span class="cli-grn">ls</span>              → List sections
  <span class="cli-grn">date</span>            → Current date/time
  <span class="cli-grn">clear</span>           → Clear terminal
  <span class="cli-grn">exit</span>            → Back to Normal mode

  <span class="cli-dim">Tip: Tab=autocomplete · ↑↓=command history</span>`
};

function cliPrint(html,cls='cli-resp'){
  const el=document.createElement('div');
  el.className='cli-line '+cls;
  el.innerHTML=html;
  document.getElementById('cli-output').appendChild(el);
  const out=document.getElementById('cli-output');
  out.scrollTop=out.scrollHeight;
}

function bootCLI(){
  cliPrint(`<span class="cli-grn">
███████╗███████╗███████╗
██╔════╝╚══███╔╝╚══███╔╝
█████╗    ███╔╝   ███╔╝
██╔══╝   ███╔╝   ███╔╝
███████╗███████╗███████╗
╚══════╝╚══════╝╚══════╝</span>`);
  cliPrint(`<span class="cli-h">Ezzeldin Amr — Cybersecurity & IT Specialist</span>`);
  cliPrint(`<span class="cli-dim">Portfolio Terminal v4.0 · Type 'help' for commands</span>`);
  cliPrint('');
}

function runCLI(cmd){
  cmd=cmd.trim().toLowerCase();
  if(!cmd)return;
  cliHistory.unshift(cmd);cliHistIdx=-1;
  cliPrint(`<span class="cli-cmd">$ ${cmd}</span>`);
  if(cmd==='clear'){document.getElementById('cli-output').innerHTML='';bootCLI();return}
  if(cmd==='exit'){setMode('normal');return}
  if(cmd==='date'){cliPrint(new Date().toString());return}
  if(D[cmd]){cliPrint(D[cmd]);cliPrint('');}
  else{
    const matches=CMDS.filter(c=>c.startsWith(cmd));
    if(matches.length)cliPrint(`<span class="cli-dim">Did you mean: ${matches.join(', ')} ?</span>`);
    else cliPrint(`<span class="cli-err">command not found: ${cmd} · type 'help'</span>`);
  }
}

const inp=document.getElementById('cli-in');
inp.addEventListener('keydown',e=>{
  if(e.key==='Enter'){const v=inp.value;inp.value='';runCLI(v);}
  else if(e.key==='Tab'){
    e.preventDefault();
    const v=inp.value.trim().toLowerCase();
    const matches=CMDS.filter(c=>c.startsWith(v));
    if(matches.length===1)inp.value=matches[0];
    else if(matches.length>1)cliPrint(`<span class="cli-dim">→ ${matches.join('  ')}</span>`);
  }
  else if(e.key==='ArrowUp'){e.preventDefault();if(cliHistIdx<cliHistory.length-1){cliHistIdx++;inp.value=cliHistory[cliHistIdx]||''}}
  else if(e.key==='ArrowDown'){e.preventDefault();if(cliHistIdx>0){cliHistIdx--;inp.value=cliHistory[cliHistIdx]||''}else{cliHistIdx=-1;inp.value=''}}
});
document.getElementById('cli').addEventListener('click',()=>inp.focus());
</script>
</body>
</html>
