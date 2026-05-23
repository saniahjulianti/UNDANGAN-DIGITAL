<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>The Wedding of Davi & Saniah</title>
    
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Playfair+Display:ital,wght@0,700;1,700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    
    <style>
        :root{
    --gold: #c5a059;
    --gold-soft: rgba(197,160,89,0.75);
    --gold-fade: rgba(197,160,89,0.4);

    --text-main: rgba(255,255,255,0.9);
    --text-soft: rgba(255,255,255,0.65);

    --glass: rgba(255,255,255,0.06);
    --glass-border: rgba(197,160,89,0.25);
}
        /* ===== COVER PREMIUM ===== */

#envelope{
    position: fixed;
    inset: 0;
    z-index: 99999;

    background:
       linear-gradient(
    rgba(0,0,0,0.15),
    rgba(0,0,0,0.25)
)
        url(sanie.jpeg);

    background-size: cover;
    background-position: center;
    overflow: hidden;

    display:flex;
    flex-direction:column;
    justify-content:space-between;
    align-items:center;
}

#envelope::after{
    content:'';

    position:absolute;
    inset:0;

    background-image:
        radial-gradient(circle, rgba(255,215,120,0.7) 1px, transparent 1px);

    background-size: 120px 120px;

    opacity:.25;

    animation: sparkleMove 12s linear infinite;
}


.invite-text{
    color: rgba(255,255,255,0.75);

    font-size: 11px;

    letter-spacing: 0.45em;

    text-transform: uppercase;

    margin-bottom: 22px;
}
.premium-heading{
    font-family: 'Playfair Display', serif;

    font-size: 34px;
    font-weight: 700;

    letter-spacing: 14px;
    text-transform: uppercase;

    background: linear-gradient(
        180deg,
        #fff7d6 0%,
        #f3d98b 40%,
        #c5a059 100%
    );

    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;

    text-shadow:
        0 0 10px rgba(243,217,139,0.25),
        0 0 25px rgba(197,160,89,0.15);

    position: relative;

    display: inline-block;

    padding-bottom: 14px;

    animation: fadeLuxury 3s ease-in-out infinite alternate;
}

/* garis bawah elegan */
.premium-heading::after{
    content:'';

    position:absolute;

    left:50%;
    bottom:0;

    transform:translateX(-50%);

    width:120px;
    height:2px;

    background: linear-gradient(
        90deg,
        transparent,
        #d4af63,
        transparent
    );
}

/* mobile */
@media(max-width:768px){

    .premium-heading{
        font-size:20px;
        letter-spacing:8px;
    }

    .premium-heading::after{
        width:80px;
    }

}

/* tombol dalam box */
.invite-box .open-btn{
    width: 100%;

    display: flex;
    align-items: center;
    justify-content: center;

    gap: 10px;
}
/* BOX UNDANGAN */
.invite-box{
    width: 100%;
    max-width: 420px;

    padding: 30px 25px;

    border-radius: 30px;

    background: rgba(255,255,255,0.08);

    backdrop-filter: blur(18px);

    border: 1px solid rgba(255,255,255,0.15);

    box-shadow:
        0 10px 40px rgba(0,0,0,0.35),
        inset 0 1px 1px rgba(255,255,255,0.08);

    text-align: center;
}

@keyframes sparkleMove{
    from{
        transform:translateY(0);
    }

    to{
        transform:translateY(80px);
    }
}

.cover-title{
    position:relative;
    overflow:hidden;
}
.cover-title::after{
    content:'';
    position:absolute;
    top:0;
    left:-120%;
    width:50%;
    height:100%;

    background:linear-gradient(
        120deg,
        transparent,
        rgba(255,255,255,0.5),
        transparent
    );

    transform:skewX(-20deg);

    animation:shineTitle 5s infinite;
}

@keyframes shineTitle{
    100%{
        left:180%;
    }
}
/* efek glow background */
#envelope::before{
    content:'';

    position:absolute;
    inset:0;

    background:
        radial-gradient(
            circle at top,
            rgba(197,160,89,0.18),
            transparent 45%
        );

    animation: glowMove 8s ease-in-out infinite alternate;
}

@keyframes glowMove{

    from{
        transform:scale(1);
    }

    to{
        transform:scale(1.2);
    }

}

/* subtitle */
.cover-subtitle{

    font-family:'Playfair Display', serif;

    color:#f3d98b;

    letter-spacing:10px;

    text-transform:uppercase;

    font-size:15px;

    text-shadow:
        0 0 10px rgba(243,217,139,0.35);

    animation: fadeLuxury 3s ease-in-out infinite alternate;
}

/* nama */
.cover-title{
    font-family:'Dancing Script', cursive;
    font-size:95px;
    line-height:1.1;

    background: linear-gradient(
        180deg,
        #fff,
        #f3d98b,
        #c5a059
    );

    -webkit-background-clip:text;
    -webkit-text-fill-color:transparent;

    text-shadow:
        0 10px 30px rgba(0,0,0,0.6),
        0 0 30px rgba(255,255,255,0.1);

    animation: fadeUp 1.5s ease;
}
.cover-title span{
    color:#e7c06a;
    padding:0 10px;
}

/* tanggal */
.cover-date{

    margin-top:20px;

    font-family:'Playfair Display', serif;

    color:#f3d98b;

    font-size:18px;

    letter-spacing:4px;

    font-style:italic;

    opacity:.9;
}

/* tombol */
.open-btn{

    background: linear-gradient(
        135deg,
        #c5a059,
        #e7c06a
    );

    color:white;

    padding:16px 42px;

    border-radius:999px;

    font-weight:700;

    letter-spacing:3px;

    text-transform:uppercase;

    box-shadow:
        0 15px 35px rgba(197,160,89,0.35);

    transition:.4s ease;
}

.open-btn:hover{

    transform:
        translateY(-5px)
        scale(1.03);

    box-shadow:
        0 20px 45px rgba(197,160,89,0.45);

}

/* animasi */
@keyframes fadeLuxury{

    from{
        opacity:.7;
        letter-spacing:8px;
    }

    to{
        opacity:1;
        letter-spacing:12px;
    }

}

@keyframes fadeUp{

    from{
        opacity:0;
        transform:
            translateY(40px)
            scale(.95);
    }

    to{
        opacity:1;
        transform:
            translateY(0)
            scale(1);
    }

}

/* MOBILE */
@media(max-width:768px){

    .cover-title{
        font-size:62px;
    }

    .cover-subtitle{
        font-size:12px;
        letter-spacing:6px;
    }

    .cover-date{
        font-size:14px;
        letter-spacing:3px;
    }

    .open-btn{
        padding:14px 30px;
        font-size:12px;
    }

}
        * { scroll-behavior: smooth; }
        :root { 
            --primary: #c5a059; 
            --bg-body: #000; 
            --text-main: #fff; 
            --card-bg: rgba(255, 255, 255, 0.05);
            --overlay-color: rgba(0, 0, 0, 0.6);
        }
        
        .light-mode { 
            --bg-body: #fdfaf3; 
            --text-main: #2c2c2c; 
            --card-bg: rgba(255, 255, 255, 0.7);
            --overlay-color: rgba(255, 255, 255, 0.5);
        }

        body { font-family: 'Poppins', sans-serif; background-color: var(--bg-body); color: var(--text-main); transition: all 0.5s ease; overflow-x: hidden; width: 100%; }
        .font-wedding { font-family: 'Dancing Script', cursive; }
        .font-elegant { font-family: 'Playfair Display', serif; }
        
        .clickable-effect { transition: transform 0.1s active, filter 0.2s; cursor: pointer; }
        .clickable-effect:active { transform: scale(0.92) !important; }

        #rose-container { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 9999; }
        .rose-leaf { position: absolute; font-size: 24px; filter: drop-shadow(0 0 5px rgba(255,0,0,0.3)); animation: fall linear infinite; }
        @keyframes fall {
            0% { transform: translateY(-10vh) rotate(0deg) scale(0.5); opacity: 0; }
            10% { opacity: 1; }
            100% { transform: translateY(110vh) rotate(360deg) scale(1.2); opacity: 0; }
        }
html, body{
    touch-action: pan-y;
    overflow-x: hidden;
}

#lightbox,
#lightbox img{
    touch-action: none;
}

        #particle-canvas { position: fixed; top: 0; left: 0; pointer-events: none; z-index: 10000; }

#main-content {
    background:
        linear-gradient(
            rgba(0,0,0,0.35),
            rgba(0,0,0,0.45)
        ),
        url('saniah.jpeg');

    background-size: cover;
    background-position: center;
    background-attachment: fixed;

    opacity: 0;
    display: none;
    z-index: 1;
}

#main-content::before{
    content:'';
    position: fixed;
    inset:0;

    background:
        radial-gradient(
            circle at top,
            rgba(212,175,99,0.18),
            transparent 45%
        ),
        radial-gradient(
            circle at bottom,
            rgba(197,160,89,0.12),
            transparent 40%
        );

    pointer-events:none;
    z-index:-1;
}

#main-content::before{
    content:'';
    position: fixed;
    inset:0;

    background:
        radial-gradient(
            circle at top,
            rgba(212,175,99,0.18),
            transparent 45%
        ),
        radial-gradient(
            circle at bottom,
            rgba(197,160,89,0.12),
            transparent 40%
        );

    pointer-events:none;
    z-index:-1;
}
        #main-content.visible { opacity: 1; display: block; }

        .bg-section { position: relative; min-height: 100vh; display: flex; flex-direction: column; justify-content: center; align-items: center; padding: 80px 20px; z-index: 5; }
        .overlay { background: var(--overlay-color); position: absolute; inset: 0; z-index: -1; transition: background 0.5s ease; }
        .content { z-index: 10; text-align: center; width: 100%; max-width: 800px; position: relative; }

        #envelope { 
            position: fixed; inset: 0; z-index: 99999; 
            background: linear-gradient(rgba(0,0,0,0.3), rgba(0,0,0,0.7)), url(saniah.jpeg); 
            background-size: cover; background-position: center; 
            display: flex; flex-direction: column; align-items: center; justify-content: space-between;
            padding: 8vh 0; transition: all 1.2s cubic-bezier(0.19, 1, 0.22, 1);
        }

        .reveal-text { opacity: 0; transform: translateY(30px); }

        /* --- Updated Enhanced Scroll Indicator --- */
        .scroll-indicator-container {
            margin-top: 50px;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 12px;
            opacity: 0;
            transform: translateY(20px);
            transition: all 1s ease 2.5s; /* Muncul perlahan setelah animasi teks */
        }
        
        #main-content.visible .scroll-indicator-container {
            opacity: 1;
            transform: translateY(0);
        }

        .mouse-outline {
            width: 28px;
            height: 45px;
            border: 2px solid var(--primary);
            border-radius: 20px;
            position: relative;
            display: flex;
            justify-content: center;
        }

        .mouse-wheel {
            width: 4px;
            height: 8px;
            background: var(--primary);
            border-radius: 2px;
            position: absolute;
            top: 10px;
            animation: mouse-scroll-anim 1.6s infinite;
        }

        .arrow-scroll span {
            display: block;
            width: 10px;
            height: 10px;
            border-bottom: 2px solid var(--primary);
            border-right: 2px solid var(--primary);
            transform: rotate(45deg);
            margin: -4px 0;
            animation: arrow-scroll-anim 1.6s infinite;
        }

        .arrow-scroll span:nth-child(2) { animation-delay: 0.2s; }
        .arrow-scroll span:nth-child(3) { animation-delay: 0.4s; }

        @keyframes mouse-scroll-anim {
            0% { opacity: 1; transform: translateY(0); }
            100% { opacity: 0; transform: translateY(15px); }
        }

        @keyframes arrow-scroll-anim {
            0% { opacity: 0; transform: rotate(45deg) translate(-5px, -5px); }
            50% { opacity: 1; }
            100% { opacity: 0; transform: rotate(45deg) translate(5px, 5px); }
        }

        .float-container { position: fixed; bottom: 25px; right: 25px; z-index: 9999; display: none; flex-direction: column; gap: 15px; }
        .float-btn { width: 50px; height: 50px; display: flex; align-items: center; justify-content: center; border-radius: 50%; cursor: pointer; background: var(--primary); color: white; box-shadow: 0 4px 15px rgba(0,0,0,0.4); font-size: 20px; transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
        .float-btn:hover { transform: translateY(-5px); }
        .float-btn:active { transform: scale(0.8) rotate(-10deg); }

        .couple-img { width: 180px; height: 180px; border-radius: 50%; border: 4px solid var(--primary); margin: 0 auto 20px; object-fit: cover; }
        .gold-card { border: 1px solid rgba(197, 160, 89, 0.3); padding: 40px 30px; border-radius: 30px; background: var(--card-bg); backdrop-filter: blur(15px); transition: all 0.5s ease; color: var(--text-main); position: relative; z-index: 20; }
        /* ===== WEDDING GIFT ===== */

.gift-card{
    position: relative;
    overflow: hidden;

    padding: 40px 30px;
    border-radius: 28px;

    background: rgba(255,255,255,0.08);

    backdrop-filter: blur(18px);

    border: 1px solid rgba(197,160,89,0.25);

    box-shadow:
        0 10px 30px rgba(0,0,0,0.35),
        inset 0 1px 1px rgba(255,255,255,0.05);

    transition: all .4s ease;
}

.gift-card:hover{
    transform: translateY(-8px);
    border-color: rgba(197,160,89,0.6);

    box-shadow:
        0 20px 40px rgba(0,0,0,0.45),
        0 0 20px rgba(197,160,89,0.15);
}

.gift-card::before{
    content:'';

    position:absolute;
    top:-50%;
    right:-50%;

    width:250px;
    height:250px;

    background: radial-gradient(
        circle,
        rgba(197,160,89,0.15),
        transparent 70%
    );
}

.gift-icon{
    font-size: 34px;
    margin-bottom: 15px;
}

.bank-name{
    color: #d4af63;
    font-size: 15px;
    letter-spacing: 4px;
    font-weight: 700;
    margin-bottom: 15px;
}

.rekening-number{
    font-size: 34px;
    font-weight: 700;
    letter-spacing: 3px;
    margin-bottom: 10px;
    color: white;
}

.rekening-name{
    opacity: .7;
    margin-bottom: 25px;
}

.alamat-text{
    font-size: 18px;
    line-height: 1.8;
    font-weight: 500;
    max-width: 700px;
    margin: auto;
    margin-bottom: 15px;
}

.gift-btn{
    background: linear-gradient(
        135deg,
        #c5a059,
        #e5bd6a
    );

    color: white;

    padding: 12px 28px;

    border-radius: 999px;

    font-size: 13px;
    font-weight: 700;

    letter-spacing: 1px;

    transition: .3s;
}

.gift-btn:hover{
    transform: scale(1.05);
    box-shadow: 0 10px 25px rgba(197,160,89,0.35);
}
        #rsvpForm input, #rsvpForm select, #rsvpForm textarea, #rsvpForm button {
            position: relative;
            z-index: 30;
            pointer-events: auto !important;
        }

        .gallery-container { position: relative; width: 100%; height: 450px; perspective: 1000px; display: flex; align-items: center; justify-content: center; overflow: visible; touch-action: none; }
        #drag-container, #spin-container { position: relative; display: flex; margin: auto; transform-style: preserve-3d; transform: rotateX(-10deg); }
        .img-wrapper { position: absolute; left: 0; top: 0; width: 100%; height: 100%; transform-style: preserve-3d; }
        .img-wrapper img { width: 100%; height: 100%; box-shadow: 0 0 8px #fff; border: 2px solid var(--primary); border-radius: 10px; cursor: pointer; transition: 0.3s; -webkit-box-reflect: below 10px linear-gradient(transparent, transparent, #0005); }

        #lightbox { 
            position: fixed; inset: 0; background: rgba(0,0,0,0); z-index: 999999; 
            display: none; flex-direction: column; align-items: center; justify-content: center; 
            backdrop-filter: blur(0px); transition: background 0.5s ease;
        }
        #lightbox-img { 
            max-width: 90%; max-height: 70%; border: 4px solid var(--primary); 
            border-radius: 15px; box-shadow: 0 20px 50px rgba(0,0,0,0.5);
            opacity: 0; transform: scale(0.5);
        }
        .btn-close-zoom { 
            background: var(--primary); color: white; padding: 12px 35px; border-radius: 50px; 
            margin-top: 30px; font-weight: bold; cursor: pointer; opacity: 0; transform: translateY(20px);
            transition: 0.3s;
        }

        .btn-copy {
            background: var(--primary);
            color: white; padding: 5px 15px; border-radius: 20px; font-size: 12px; margin-top: 10px;
            cursor: pointer; transition: 0.3s; z-index: 30; position: relative;
        }

        .btn-maps {
            position: relative;
            background: linear-gradient(45deg, #c5a059, #e9bc66);
            color: white; padding: 15px 40px; border-radius: 50px; font-weight: 700; text-transform: uppercase;
            font-size: 14px; box-shadow: 0 10px 20px rgba(197, 160, 89, 0.3); display: inline-flex; align-items: center; gap: 10px; text-decoration: none; z-index: 30;
            transition: 0.3s;
        }
        .btn-pulse { animation: pulse-animation 2s infinite; }
        @keyframes pulse-animation {
            0% { box-shadow: 0 0 0 0px rgba(197, 160, 89, 0.4); }
            70% { box-shadow: 0 0 0 20px rgba(197, 160, 89, 0); }
            100% { box-shadow: 0 0 0 0px rgba(197, 160, 89, 0); }
        }
      /* FOTO PASANGAN */

.couple-img{
    width: 100%;
    max-width: 280px;

    height: 360px;

    object-fit: cover;
    object-position: center top;

    border-radius: 30px;

    border: 4px solid #c5a059;

    display: block;
    margin: auto;

    box-shadow:
        0 20px 40px rgba(0,0,0,0.45),
        0 0 25px rgba(197,160,89,0.25);

    transition: .4s ease;
}

.couple-img:hover{
    transform: translateY(-8px) scale(1.03);

    box-shadow:
        0 30px 60px rgba(0,0,0,0.55),
        0 0 35px rgba(197,160,89,0.4);
}

/* MOBILE */
@media(max-width:768px){

    .couple-img{
        max-width: 230px;
        height: 300px;
    }

    .open-btn{
    position: relative;
    overflow: hidden;
}

.open-btn::before{
    content:'';
    position:absolute;
    top:0;
    left:-120%;
    width:80px;
    height:100%;
    background:rgba(255,255,255,0.35);
    transform:skewX(-25deg);

    animation: shine 3s infinite;
}

@keyframes shine{
    0%{
        left:-120%;
    }

    100%{
        left:140%;
    }
}
html, body{
    overflow-x: hidden;
    width: 100%;
}

#main-content,
.bg-section,
.content{
    width: 100%;
    overflow-x: hidden;
}

@media(max-width:768px){

    .cover-title{
        font-size:52px !important;
    }

    .premium-heading{
        letter-spacing:4px !important;
    }

    .invite-box{
        max-width:90%;
        margin:auto;
    }

}
#countdown .gold-card{
    min-height:120px;
}

#countdown h3{
    display:flex;
    align-items:center;
    justify-content:center;
}
#countdown .gold-card{
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;

    min-height:120px;
    padding:20px 10px;

    text-align:center;
}

#countdown h3{
    width:100%;
    display:flex;
    justify-content:center;
    align-items:center;

    line-height:1;
    margin:0;
}

#countdown p{
    margin-top:10px;
}
.credit-box{

    width:100%;
    max-width:520px;

    display:flex;
    justify-content:center;
    align-items:center;
    flex-wrap:wrap;

    gap:12px;

    text-align:center;

    padding:18px 24px;

    border-radius:999px;

    background:rgba(255,255,255,0.08);

    border:1px solid rgba(197,160,89,0.3);

    backdrop-filter:blur(12px);

    margin:auto;

    box-shadow:
        0 10px 25px rgba(0,0,0,0.25);
}

.credit-text{
    opacity:.7;
    letter-spacing:3px;
    font-size:12px;
}

.credit-name{
    color:#c5a059;
    font-weight:bold;
    letter-spacing:3px;
}

.credit-line{
    width:1px;
    height:18px;
    background:rgba(255,255,255,0.25);
}

.credit-ig{
    display:flex;
    align-items:center;
    gap:8px;

    text-decoration:none;
    color:white;

    transition:.3s;
}

.credit-ig:hover{
    color:#e1306c;
}

.ig-user{
    letter-spacing:2px;
    font-size:11px;
}

@media(max-width:768px){

    .credit-box{

        border-radius:25px;

        padding:18px;

        gap:8px;
    }

}
/* ===== CREDIT PREMIUM ===== */

.credit-section{
    width:100%;
    padding:60px 20px;

    display:flex;
    justify-content:center;
    align-items:center;
}

/* KECILIN CREDIT */

.credit-premium{
    width: 100%;
    max-width: 520px;
    margin: auto;

    display: flex;
    align-items: center;
    justify-content: center;
    gap: 18px;

    padding: 18px 20px;

    border-radius: 25px;

    background: rgba(255,255,255,0.08);
    border: 1px solid rgba(197,160,89,0.3);

    backdrop-filter: blur(12px);

    box-shadow: 0 10px 25px rgba(0,0,0,0.25);
}

.credit-designer,
.credit-instagram{

    max-width:220px;
    padding:12px 14px;
}

.credit-brand{
    font-size:24px;
    letter-spacing:3px;
}

.credit-label{
    font-size:9px;
    letter-spacing:3px;
}

.credit-role{
    font-size:8px;
    letter-spacing:2px;
}

.ig-icon{
    width:38px;
    height:38px;
    font-size:18px;
    border-radius:12px;
}

.ig-title{
    font-size:8px;
    letter-spacing:2px;
}

.ig-username{
    font-size:13px;
}

.credit-divider{
    height:35px;
}

/* MOBILE */
@media(max-width:768px){

    .credit-premium{
        max-width:280px;
        padding:12px;
    }

}
    background:
        radial-gradient(
            circle,
            rgba(197,160,89,0.22),
            transparent 70%
        );

    top:-100px;
    right:-80px;

    pointer-events:none;
}

/* kiri */
.credit-left{
    text-align:center;
}

.credit-label{

    font-size:11px;

    letter-spacing:5px;

    text-transform:uppercase;

    opacity:.7;

    margin-bottom:5px;
}

.credit-brand{

    font-size:38px;

    font-weight:700;

    letter-spacing:4px;

    color:#d4af63;

    font-family:'Playfair Display', serif;

    text-shadow:
        0 0 15px rgba(212,175,99,0.35);
}

/* garis */
.credit-divider{
    width: 2px;
    height: 60px;
    background: linear-gradient(
        transparent,
        rgba(255,255,255,0.6),
        transparent
    );
}

/* instagram box */
.credit-instagram{

    display:flex;
    align-items:center;
    gap:15px;

    padding:14px 22px;

    border-radius:18px;

    text-decoration:none;

    background:
        linear-gradient(
            135deg,
            rgba(255,255,255,0.08),
            rgba(255,255,255,0.03)
        );

    border:1px solid rgba(255,255,255,0.08);

    transition:.35s ease;
}

.credit-instagram:hover{

    transform:
        translateY(-5px)
        scale(1.03);

    border-color:#e1306c;

    box-shadow:
        0 15px 35px rgba(225,48,108,0.25);
}

/* icon */
.ig-icon{

    width:52px;
    height:52px;

    display:flex;
    align-items:center;
    justify-content:center;

    border-radius:16px;

    font-size:24px;

    background:
        linear-gradient(
            135deg,
            #833ab4,
            #fd1d1d,
            #fcb045
        );

    box-shadow:
        0 8px 20px rgba(225,48,108,0.35);
}

/* text */
.ig-text{
    display:flex;
    flex-direction:column;
}
.text-gold-soft{
    color: rgba(197,160,89,0.8);
    letter-spacing: 0.25em;
    text-transform: uppercase;
    font-size: 12px;
}

.ig-title{

    font-size:11px;

    letter-spacing:4px;

    text-transform:uppercase;

    color:rgba(255,255,255,0.6);

    margin-bottom:3px;
}

.ig-username{

    font-size:18px;

    font-weight:700;

    color:white;

    letter-spacing:1px;
}

/* MOBILE */
@media(max-width:768px){

    .credit-premium{

        flex-direction:column;

        gap:18px;

        padding:25px 20px;

        border-radius:25px;
    }

    .credit-divider{

        width:70%;
        height:1px;
    }

    .credit-brand{
        font-size:30px;
    }

    .credit-instagram{
        width:100%;
        justify-content:center;
    }

}
/* BOX DESIGNER */

.credit-designer{

    display:flex;
    flex-direction:column;
    align-items:center;
    justify-content:center;

    padding:18px 26px;

    border-radius:22px;

    min-width:220px;

    background:
        linear-gradient(
            135deg,
            rgba(255,255,255,0.08),
            rgba(255,255,255,0.03)
        );

    border:1px solid rgba(197,160,89,0.25);

    box-shadow:
        0 10px 25px rgba(0,0,0,0.25),
        inset 0 1px 1px rgba(255,255,255,0.08);

    backdrop-filter:blur(14px);

    position:relative;

    overflow:hidden;
}

/* glow */
.credit-designer::before{

    content:'';

    position:absolute;

    width:160px;
    height:160px;

    background:
        radial-gradient(
            circle,
            rgba(197,160,89,0.18),
            transparent 70%
        );

    top:-70px;
    right:-60px;
}


/* hover */
.credit-designer:hover{

    transform:
        translateY(-5px);

    transition:.35s ease;

    border-color:rgba(197,160,89,0.5);

    box-shadow:
        0 20px 35px rgba(0,0,0,0.35),
        0 0 20px rgba(197,160,89,0.15);
}
/* CREDIT BOX */
.credit-premium{

    max-width:480px;

    gap:14px;

    padding:16px 18px;

    border-radius:22px;
}

/* DESIGNER BOX */
.credit-designer{

    padding:12px 18px;

    min-width:100px;

    border-radius:16px;
}

/* FRN */
.credit-brand{

    font-size:24px;

    letter-spacing:5px;
}

/* DESIGN BY */
.credit-label{

    font-size:9px;

    letter-spacing:3px;
}

/* INSTAGRAM BOX */
.credit-instagram{

    gap:10px;

    padding:10px 14px;

    border-radius:14px;
}

/* ICON IG */
.ig-icon{

    width:38px;
    height:38px;

    font-size:18px;
}

/* TEXT IG */
.ig-title{

    font-size:9px;

    letter-spacing:2px;
}

.ig-username{

    font-size:14px;
}


@media(max-width:768px){
    .credit-premium{
        flex-direction: column;
        gap: 14px;
    }

    .credit-divider{
        width: 80%;
        height: 1px;
    }
}
.scroll-nav.show{
    opacity: 1;
    transform: translateY(0);
}
.scroll-nav{
    position: fixed;
    right: 20px;
    bottom: 200px; /* ⬅ dinaikin biar tidak nabrak tombol lain */

    display: flex;
    flex-direction: column;
    gap: 12px;
    z-index: 99999;

    opacity: 0;
    transform: translateY(20px);
    transition: 0.4s ease;
}

@media(max-width:768px){
    .scroll-nav{
        right: 14px;
        bottom: 240px; /* lebih tinggi di HP biar gak nabrak */
    }
}

.scroll-btn{
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: rgba(197,160,89,0.9);
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    cursor: pointer;
    box-shadow: 0 10px 25px rgba(0,0,0,0.3);
    transition: 0.3s ease;
    backdrop-filter: blur(10px);
}

.scroll-btn:hover{
    transform: scale(1.1);
}
.wa-label{
    font-family: 'Playfair Display', serif;
    font-size: 12px;
    letter-spacing: 0.35em;
    text-transform: lowercase;

    color: rgba(243, 217, 139, 0.75);

    text-align: center;

    margin-bottom: 12px;

    opacity: 0.85;
}
.wa-label::after{
    content: "";
    display: block;
    width: 60px;
    height: 1px;
    margin: 10px auto 0;

    background: linear-gradient(
        90deg,
        transparent,
        #c5a059,
        transparent
    );

    opacity: 0.6;
}
    </style>
</head>

    <!-- NAVBAR -->
    <body class="overflow-hidden">
    <div id="rose-container"></div>
    <canvas id="particle-canvas"></canvas>

    <audio id="bgMusic" loop>
        <source src="tiara.mp3" type="audio/mpeg">
    </audio>

    <div id="lightbox" onclick="closeLightbox()" class="clickable-effect">
    <img id="lightbox-img" src="sanie.jpeg" alt="Zoom">
    <div class="btn-close-zoom shadow-lg">KEMBALI KE GALERI</div>
    </div>
    <div id="float-controls" class="float-container">
        <div id="theme-btn" class="float-btn shadow-xl" onclick="toggleTheme()">🌙</div>
        <div id="music-btn" class="float-btn shadow-xl" onclick="toggleMusic()">🎵</div>
    </div>
    <!-- SCROLL NAV BUTTON -->
    <div id="scrollNav" class="scroll-nav">
    <div class="scroll-btn" onclick="scrollUp()">⬆</div>
    <div class="scroll-btn" onclick="scrollDown()">⬇</div>
</div>

   
<div id="envelope">

<div class="text-center">
<h2 class="premium-heading">
    The Wedding Of
</h2>
</div>
    
        <!-- konten tengah -->
        <div class="relative z-20 text-center px-6 mt-20">
    
            <p class="text-white/70 tracking-[0.4em] uppercase text-xs mb-5">
                Save The Date
            </p>
    
            <h1 class="cover-title">
                Davi
                <span>&</span>
                Saniah
            </h1>
    
            <p class="cover-date">
                Minggu, 31 Mei 2026
            </p>
    
            <!-- garis -->
            <div class="flex items-center justify-center gap-4 mt-8">
    
                <div class="w-16 h-[1px] bg-amber-400/50"></div>
    
                <div class="text-amber-300 text-xl">
                    ✦
                </div>
    
                <div class="w-16 h-[1px] bg-amber-400/50"></div>
    
            </div>
    
        </div>
    
        <!-- BOTTOM BOX -->
<div class="relative z-20 mb-12 px-6 w-full flex justify-center">

    <div class="invite-box">

        <p class="invite-text">
            KEPADA YTH. BAPAK/IBU/SAUDARA/I
        </p>

        <button onclick="openInvitation()"
            class="open-btn clickable-effect">

            <span class="mr-2">📩</span>
            Buka Undangan

        </button>

    </div>

</div>
    
    </div>
    <main id="main-content">
        <section class="bg-section">
            <div class="overlay"></div>
            
            <div class="content">
                <h2 id="hero-name" class="font-wedding text-6xl md:text-8xl text-amber-500 mb-2 reveal-text">Davi & Saniah</h2>
                <div id="hero-line" class="w-20 h-0.5 bg-amber-500 mx-auto mb-6 reveal-text"></div>
                <p id="hero-date" class="font-elegant text-xl tracking-[0.4em] italic reveal-text">Minggu, 31 Mei 2026</p>
                
                <!-- NEW AESTHETIC SCROLL INDICATOR -->
                <div class="scroll-indicator-container">
                    <div class="mouse-outline">
                        <div class="mouse-wheel"></div>
                    </div>
                    <div class="arrow-scroll">
                        <span></span>
                        <span></span>
                        <span></span>
                    </div>
                    <p class="text-[10px] uppercase tracking-[0.3em] opacity-60 mt-2">Scroll Down</p>
                </div>
            </div>
        </section>

        <section class="bg-section">
            <div class="overlay"></div>
            <div class="content px-6">
                <div class="gold-card" data-aos="fade-up">
                    <h3 class="text-3xl mb-6 text-amber-200 font-elegant italic">وَمِنْ اٰيٰتِهٖٓ اَنْ خَلَقَ لَكُمْ مِّنْ اَنْفُسِكُمْ اَزْوَاجًا لِّتَسْكُنُوْٓا اِلَيْهَا وَجَعَلَ بَيْنَكُمْ مَّوَدَّةً وَّرَحْمَةًۗ اِنَّ فِيْ ذٰلِكَ لَاٰيٰتٍ لِّقَوْمٍ يَّتَفَكَّرُوْنَ</h3>
                    <p class="italic text-lg leading-relaxed font-elegant px-2">
                        "Dan di antara tanda-tanda (kebesaran)-Nya ialah Dia menciptakan pasangan-pasangan untukmu dari jenismu sendiri, agar kamu cenderung dan merasa tenteram kepadanya."
                    </p>
                    <p class="mt-8 font-bold text-amber-500 tracking-widest text-sm">— QS. AR-RUM: 21</p>
                </div>
            </div>
        </section>

        <section class="bg-section">
            <div class="overlay"></div>
        
            <div class="content max-w-6xl mx-auto px-6">
        
                <div class="grid md:grid-cols-2 gap-10 items-center">
        
                    <!-- PRIA -->
                    <div class="gold-card text-center" data-aos="fade-right">
        
                        <div class="relative inline-block">
        
                            <img src="davi.jpeg"
                                 class="couple-img"
                                 alt="Davi">
        
                            <div class="absolute inset-0 rounded-[30px] border border-amber-300/40"></div>
        
                        </div>
        
                        <h4 class="font-wedding text-5xl text-amber-400 mt-5 mb-3">
                            Davi Setiawan
                        </h4>
        
                        <div class="w-20 h-[2px] bg-amber-500 mx-auto mb-4"></div>
        
                        <p class="text-sm uppercase tracking-wider opacity-80 leading-7">
                            Putra dari <br>
                            Bapak Uus Lustiawan & Ibu Nunung Nurhayati
                        </p>
        
                    </div>
        
                    <!-- WANITA -->
                    <div class="gold-card text-center" data-aos="fade-left">
        
                        <div class="relative inline-block">
        
                            <img src="sani.jpeg"
                                 class="couple-img"
                                 alt="Saniah">
        
                            <div class="absolute inset-0 rounded-[30px] border border-amber-300/40"></div>
        
                        </div>
        
                        <h4 class="font-wedding text-5xl text-amber-400 mt-5 mb-3">
                            Saniah Julianti
                        </h4>
        
                        <div class="w-20 h-[2px] bg-amber-500 mx-auto mb-4"></div>
        
                        <p class="text-sm uppercase tracking-wider opacity-80 leading-7">
                            Putri dari <br>
                            Bapak Aris & Ibu Kelly Aprillia
                        </p>
        
                    </div>
        
                </div>
            </div>
        </section>
        <section class="bg-section">
            <div class="overlay"></div>
            <div class="content px-6 !max-w-xl">
                <h2 class="font-wedding text-6xl text-amber-500 mb-10" data-aos="fade-up">Waktu Pelaksanaan</h2>
                <div class="relative bg-white/5 backdrop-blur-md border-l-4 border-amber-500 p-8 text-center rounded-r-2xl shadow-xl" data-aos="fade-up">
                    <h3 class="font-elegant text-3xl text-white mb-2">Akad & Resepsi</h3>
                    <p class="text-amber-200 mb-6 italic">Minggu, 31 Mei 2026 | 09.00 - Selesai</p>
                    <div id="countdown" class="mt-8 reveal-text">
                        <div class="grid grid-cols-4 gap-3 max-w-2xl mx-auto">
                    
                        <div class="gold-card py-4 flex flex-col items-center justify-center">
    <h3 id="days" class="text-2xl md:text-5xl font-bold text-amber-400 leading-none">
        0
    </h3>

    <p class="text-xs uppercase tracking-widest mt-2">
        Hari
    </p>
</div>

<div class="gold-card py-4 flex flex-col items-center justify-center">
    <h3 id="hours" class="text-2xl md:text-5xl font-bold text-amber-400 leading-none">
        0
    </h3>

    <p class="text-xs uppercase tracking-widest mt-2">
        Jam
    </p>
</div>

<div class="gold-card py-4 flex flex-col items-center justify-center">
    <h3 id="minutes" class="text-2xl md:text-5xl font-bold text-amber-400 leading-none">
        0
    </h3>

    <p class="text-xs uppercase tracking-widest mt-2">
        Menit
    </p>
</div>

<div class="gold-card py-4 flex flex-col items-center justify-center">
    <h3 id="seconds" class="text-2xl md:text-5xl font-bold text-amber-400 leading-none">
        0
    </h3>

    <p class="text-xs uppercase tracking-widest mt-2">
        Detik
    </p>
</div>
                        </section>
                        <section class="bg-section">
                            <div class="overlay"></div>
                            <div class="content px-6 !max-w-xl">
                                <h2 class="font-wedding text-6xl text-amber-500 mb-10" data-aos="fade-up">Tempat Pelaksanaan</h2>
                                <div class="relative bg-white/5 backdrop-blur-md border-l-4 border-amber-500 p-8 text-center rounded-r-2xl shadow-xl" data-aos="fade-up">
                                    <p class="text-amber-200 mb-6 italic">Jl. He Sukma Kp. Bitung Ratna Rt01/02 Ds. Bitung Sari Kec. Ciawi Kab. Bogor 16720
                                    </p>
                                    
                    <div class="mt-6 rounded-2xl overflow-hidden border-2 border-amber-500 shadow-2xl">
                        <iframe
                            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3962.6974164621693!2d106.84445939999999!3d-6.684354400000001!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e69c91434d38b35%3A0xc2095aecc23b1eba!2sR.A%20ALIF!5e0!3m2!1sid!2sid!4v1779476946863!5m2!1sid!2sid"
                            width="100%"
                            height="320"
                            style="border:0;"
                            allowfullscreen=""
                            loading="lazy">
                        </iframe>
                    </div>
                    
                    <div class="mt-5">
                        <a href="https://maps.app.goo.gl/QGJ4iciZ1UucqKKc8" 
                           target="_blank" 
                           class="btn-maps btn-pulse clickable-effect">
                            📍 BUKA GOOGLE MAPS
                        </a>
                    </div>
                </div>
            </div>
        </section>

        <section class="bg-section">
            <div class="overlay"></div>
        
            <div class="content px-6">
                <div class="max-w-md mx-auto gold-card" data-aos="fade-up">
        
                    <h2 class="font-wedding text-4xl text-amber-500 mb-8 text-center">
                        Buku Tamu
                    </h2>
        
                    <form id="rsvpForm" class="text-left space-y-4">
        
                        <div>
                            <label class="text-xs uppercase tracking-widest text-amber-200">
                                Nama Lengkap
                            </label>
        
                            <input 
                                type="text"
                                name="nama"
                                placeholder="Masukkan nama Anda"
                                class="w-full p-3 rounded-lg bg-white/10 border border-amber-500/30 text-white outline-none focus:border-amber-500 transition-all"
                                required>
                        </div>
        
                        <div>
                            <label class="text-xs uppercase tracking-widest text-amber-200">
                                Konfirmasi Kehadiran
                            </label>
        
                            <select
                                id="statusKehadiran"
                                name="kehadiran"
                                class="clickable-effect w-full p-3 rounded-lg bg-black text-white border border-amber-500/30 outline-none transition-all cursor-pointer">
        
                                <option value="Hadir">
                                    Saya Akan Hadir
                                </option>
        
                                <option value="Tidak Hadir">
                                    Berhalangan Hadir
                                </option>
        
                            </select>
                        </div>
        
                        <div id="jumlahContainer">
        
                            <label class="text-xs uppercase tracking-widest text-amber-200">
                                Jumlah Tamu
                            </label>
        
                            <select
                                name="jumlah"
                                class="clickable-effect w-full p-3 rounded-lg bg-black text-white border border-amber-500/30 outline-none cursor-pointer">
        
                                <option value="1">1 Orang</option>
                                <option value="2">2 Orang</option>
                                <option value="3">3 Orang</option>
                                <option value="4">4 Orang</option>
        
                            </select>
        
                        </div>
        
                        <div>
        
                            <label class="text-xs uppercase tracking-widest text-amber-200">
                                Ucapan & Doa
                            </label>
        
                            <textarea
                                name="ucapan"
                                placeholder="Tuliskan pesan manis Anda..."
                                class="w-full p-3 rounded-lg bg-white/10 border border-amber-500/30 text-white outline-none focus:border-amber-500 transition-all"
                                rows="3"></textarea>
        
                        </div>
                      <p class="wa-label">
                        kirim wa ke :
                    </p>
                        <!-- BUTTON WA DAVI -->
                        <button
                            type="button"
                            onclick="sendWA('davi')"
                            class="clickable-effect w-full bg-amber-600 py-3 rounded-xl font-bold text-white shadow-lg hover:bg-amber-500 transition-all cursor-pointer">
        
                            Davi Setiawan
        
                        </button>
        
                        <!-- BUTTON WA SANIAH -->
                        <button
                            type="button"
                            onclick="sendWA('saniah')"
                            class="clickable-effect w-full bg-pink-600 py-3 rounded-xl font-bold text-white shadow-lg hover:bg-pink-500 transition-all cursor-pointer">
        
                            Saniah Julianti
        
                        </button>
        
                    </form>
                </div>
            </div>
        </section>

        <section class="bg-section">
            <div class="overlay"></div>
        
            <div class="content px-6">
                <h2 class="font-wedding text-5xl md:text-6xl text-amber-400 mb-14"
                    data-aos="fade-up">
                    Wedding Gift
                </h2>
        
                <div class="grid md:grid-cols-2 gap-8 max-w-5xl mx-auto">
        
                    <!-- CARD BCA 1 -->
                    <div class="gift-card" data-aos="zoom-in">
                        <div class="gift-icon">💳</div>
        
                        <h3 class="bank-name">BANK BCA</h3>
        
                        <p class="rekening-number">
                            6821846801
                        </p>
        
                        <p class="rekening-name">
                            a/n Davi Setiawan
                        </p>
        
                        <button
                            onclick="copyToClipboard('6821846801', this)"
                            class="gift-btn clickable-effect">
                            SALIN NOMOR
                        </button>
                    </div>
        
                    <!-- CARD BCA 2 -->
                    <div class="gift-card" data-aos="zoom-in" data-aos-delay="200">
                        <div class="gift-icon">💳</div>
        
                        <h3 class="bank-name">BANK BCA</h3>
        
                        <p class="rekening-number">
                            6821989393
                        </p>
        
                        <p class="rekening-name">
                            a/n Saniah Julianti
                        </p>
        
                        <button
                            onclick="copyToClipboard('6821989393', this)"
                            class="gift-btn clickable-effect">
                            SALIN NOMOR
                        </button>
                    </div>
        
                    <!-- ALAMAT -->
                    <div class="gift-card md:col-span-2"
                         data-aos="fade-up">
        
                        <div class="gift-icon">📍</div>
        
                        <h3 class="bank-name">
                            LOKASI AKAD
                        </h3>
        
                        <p class="alamat-text">
                            Jl. He Sukma Kp. Bitung Ratna RT01/02
                            Ds. Bitung Sari Kec. Ciawi
                            Kab. Bogor 16720
                        </p>
    
                        <button
                            onclick="copyToClipboard('Jl. He Sukma Kp. Bitung Ratna RT01/02 Ds. Bitung Sari Kec. Ciawi Kab. Bogor 16720', this)"
                            class="gift-btn clickable-effect">
                            SALIN ALAMAT
                        </button>

                    </div>
        
                </div>
            </div>
        </section>

        <section class="bg-section overflow-hidden">
            <div class="overlay"></div>
            <div class="content px-4 w-full">
                <h2 class="font-wedding text-5xl text-amber-500 mb-20" data-aos="fade-up">Our Moments</h2>
                <div class="gallery-container">
                    <div id="drag-container">
                        <div id="spin-container">
                            <div class="img-wrapper"><img src="1.jpeg" onclick="handleImgClick(this)" class="clickable-effect"></div>
                            <div class="img-wrapper"><img src="2.jpeg" onclick="handleImgClick(this)" class="clickable-effect"></div>
                            <div class="img-wrapper"><img src="3.jpeg" onclick="handleImgClick(this)" class="clickable-effect"></div>
                            <div class="img-wrapper"><img src="4.jpeg" onclick="handleImgClick(this)" class="clickable-effect"></div>
                        </div>
                    </div>
                </div>
                <p class="text-xs opacity-50 mt-10 italic">Bukan tentang seberapa lama bersama, tapi seberapa berarti setiap momennya<br>#MeggahNyaPernikahan</p>
            </div>
        </section>
        <!-- DOA PENGANTIN -->
<section class="bg-section">
    <div class="overlay"></div>

    <div class="content px-6">

        <div class="gold-card max-w-3xl mx-auto text-center"
             data-aos="zoom-in">

            <h2 class="font-wedding text-5xl md:text-6xl text-amber-400 mb-6">
                Doa Pengantin
            </h2>

            <div class="w-24 h-[2px] bg-amber-500 mx-auto mb-8"></div>

            <p class="text-3xl leading-loose text-amber-100 font-elegant mb-8">
                بَارَكَ اللّٰهُ لَكَ وَبَارَكَ عَلَيْكَ وَجَمَعَ بَيْنَكُمَا فِيْ خَيْرٍ
            </p>

            <p class="italic text-lg leading-relaxed opacity-90 mb-6">
                "Semoga Allah memberkahimu ketika bahagia dan ketika susah,
                serta mengumpulkan kalian berdua dalam kebaikan."
            </p>

            <p class="tracking-[0.3em] text-xs uppercase text-amber-300">
                HR. Abu Dawud & Tirmidzi
            </p>

            <div class="mt-10 text-sm opacity-70 leading-8">
                Menjadi sebuah kebahagiaan bagi kami apabila
                Bapak/Ibu/Saudara/i berkenan hadir dan memberikan doa restu
                untuk pernikahan kami.
            </div>

        </div>
<!-- CREDIT -->
<section class="credit-section">

    <div class="credit-premium">

        <!-- DESIGNER (tanpa box) -->
        <div class="credit-left">
            <span class="credit-label">Design By</span>
            <span class="credit-brand">FRN</span>
        </div>

        <div class="credit-divider"></div>

        <!-- INSTAGRAM (tetap pakai box) -->
        <a href="https://instagram.com/frhan29_"
           target="_blank"
           class="credit-instagram">

            <div class="ig-icon">
                🅾
            </div>

            <div class="ig-text">

                <span class="ig-title">
                    Instagram
                </span>

                <span class="ig-username">
                    @frhan29_
                </span>

            </div>

        </a>

    </div>

</section>


    </main>

    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        AOS.init({ duration: 1200, once: false });

        function sendWA(target) {

const form = document.getElementById('rsvpForm');

const nama = form.nama.value;
const kehadiran = form.kehadiran.value;
const jumlah = form.jumlah.value;
const ucapan = form.ucapan.value;

let nomorWA = '';

// NOMOR TUJUAN
if(target === 'davi'){
    nomorWA = '6288213415205';
} else {
    nomorWA = '6283189350061'; // NOMOR SANIAH
}

// FORMAT PESAN
const pesan = `✨ KONFIRMASI KEHADIRAN ✨

👤 Nama: ${nama}
📌 Kehadiran: ${kehadiran}
👥 Jumlah Tamu: ${kehadiran === 'Tidak Hadir' ? '-' : jumlah}

💌 Ucapan & Doa:
${ucapan}

Terima kasih 🙏`;

const url = `https://wa.me/${nomorWA}?text=${encodeURIComponent(pesan)}`;

window.location.href = url;
}

        // --- White Leaf Particle Effect ---
        const canvas = document.getElementById('particle-canvas');
        const ctx = canvas.getContext('2d');
        let particles = [];

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();

        class LeafParticle {
            constructor(x, y) {
                this.x = x;
                this.y = y;
                this.size = Math.random() * 5 + 2; 
                this.speedX = Math.random() * 3 - 1.5;
                this.speedY = Math.random() * 3 - 1.5;
                this.rotation = Math.random() * 360;
                this.rotationSpeed = Math.random() * 5;
                this.opacity = 1;
            }
            update() {
                this.x += this.speedX;
                this.y += this.speedY;
                this.rotation += this.rotationSpeed;
                this.opacity -= 0.015; 
            }
            draw() {
                ctx.save();
                ctx.translate(this.x, this.y);
                ctx.rotate((this.rotation * Math.PI) / 180);
                ctx.fillStyle = `rgba(255, 255, 255, ${this.opacity})`;
                ctx.beginPath();
                ctx.ellipse(0, 0, this.size, this.size / 2, 0, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        function createParticles(e) {
            const x = e.touches ? e.touches[0].clientX : e.clientX;
            const y = e.touches ? e.touches[0].clientY : e.clientY;
            for (let i = 0; i < 2; i++) {
                particles.push(new LeafParticle(x, y));
            }
        }
        window.addEventListener('mousemove', createParticles);
        window.addEventListener('touchmove', createParticles);

        function animateParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            for (let i = 0; i < particles.length; i++) {
                particles[i].update();
                particles[i].draw();
                if (particles[i].opacity <= 0) {
                    particles.splice(i, 1);
                    i--;
                }
            }
            requestAnimationFrame(animateParticles);
        }
        animateParticles();

        // Gallery 3D Logic
        let radius = 240;
        let rotateSpeed = -60;
        let imgWidth = 140;
        let imgHeight = 190;
        const odrag = document.getElementById('drag-container');
        const ospin = document.getElementById('spin-container');
        ospin.style.width = imgWidth + "px";
        ospin.style.height = imgHeight + "px";

        function init3DGallery() {
            const wrappers = ospin.getElementsByClassName('img-wrapper');
            for (let i = 0; i < wrappers.length; i++) {
                wrappers[i].style.transform = `rotateY(${i * (360 / wrappers.length)}deg) translateZ(${radius}px)`;
                wrappers[i].style.transition = "transform 1s " + (wrappers.length - i) / 4 + "s";
                wrappers[i].style.width = imgWidth + "px";
                wrappers[i].style.height = imgHeight + "px";
            }
        }

        let sX, sY, nX, nY, desX = 0, desY = 0, tX = 0, tY = 10;
        odrag.onpointerdown = function (e) {
            clearInterval(odrag.timer);
            sX = e.clientX; sY = e.clientY;
            odrag.onpointermove = function (e) {
                nX = e.clientX; nY = e.clientY;
                desX = nX - sX; desY = nY - sY;
                tX += desX * 0.1; tY += desY * 0.1;
                odrag.style.transform = `rotateX(${-tY}deg) rotateY(${tX}deg)`;
                sX = nX; sY = nY;
            };
            odrag.onpointerup = function () {
                this.onpointermove = this.onpointerup = null;
                odrag.timer = setInterval(function () {
                    desX *= 0.95; desY *= 0.95;
                    tX += desX * 0.1; tY += desY * 0.1;
                    odrag.style.transform = `rotateX(${-tY}deg) rotateY(${tX}deg)`;
                    if (Math.abs(desX) < 0.5 && Math.abs(desY) < 0.5) clearInterval(odrag.timer);
                }, 17);
            };
        };

    function handleImgClick(el) {

    const lb = document.getElementById('lightbox');

    const lbImg = document.getElementById('lightbox-img');

    const lbBtn = document.querySelector('.btn-close-zoom');

    lbImg.src = el.src;

    lb.style.display = 'flex';

    gsap.to(lb, {
        backgroundColor: "rgba(0,0,0,0.95)",
        backdropFilter: "blur(10px)",
        duration: 0.5
    });

    gsap.fromTo(
        lbImg,
        { scale: 0, opacity: 0, rotation: -15 },
        { scale: 1, opacity: 1, rotation: 0, duration: 0.8, ease: "back.out(1.7)" }
    );

    gsap.fromTo(
        lbBtn,
        { opacity: 0, y: 50 },
        { opacity: 1, y: 0, duration: 0.5, delay: 0.5 }
    );
}

        function closeLightbox() {
            const lb = document.getElementById('lightbox');
            const lbImg = document.getElementById('light.jpeg');
            gsap.to(lbImg, { scale: 0.5, opacity: 0, duration: 0.5, ease: "power2.in", onComplete: () => lb.style.display = 'none' });
            gsap.to(lb, { backgroundColor: "rgba(0,0,0,0)", backdropFilter: "blur(0px)", duration: 0.5 });
        }

        function openInvitation() {
            const env = document.getElementById('envelope');
            const main = document.getElementById('main-content');
            
            gsap.to("#env-top, #env-mid, #env-bottom", { opacity: 0, scale: 1.5, duration: 1, stagger: 0.1, ease: "power2.inOut" });
            gsap.to(env, { 
                scale: 2, 
                opacity: 0, 
                duration: 1.2, 
                ease: "power2.inOut", 
                onComplete: () => {
                    env.style.display = 'none';
                    main.classList.add('visible');
                    document.body.classList.remove('overflow-hidden');
                    document.getElementById('float-controls').style.display = 'flex';
                    document.getElementById('bgMusic').play();
                    gsap.to(".reveal-text", { opacity: 1, y: 0, duration: 1.5, stagger: 0.3, ease: "power4.out" });
                    init3DGallery();
                    setTimeout(() => { AOS.refresh(); }, 500);
                } 
            });
        }

        function copyToClipboard(text, btn) {
            navigator.clipboard.writeText(text).then(() => {
                const originalText = btn.innerHTML;
                btn.innerHTML = "✅ TERSALIN";
                btn.style.background = "#28a745";
                setTimeout(() => {
                    btn.innerHTML = originalText;
                    btn.style.background = "";
                }, 2000);
            });
        }

        document.getElementById('statusKehadiran').addEventListener('change', function() {
            const container = document.getElementById('jumlahContainer');
            container.style.display = this.value === 'Tidak Hadir' ? 'none' : 'block';
        });


        function toggleMusic() {
            const audio = document.getElementById('bgMusic');
            const btn = document.getElementById('music-btn');
            if (audio.paused) {
                audio.play();
                btn.innerHTML = "🎵";
                btn.classList.remove('opacity-50');
            } else {
                audio.pause();
                btn.innerHTML = "🔇";
                btn.classList.add('opacity-50');
            }
        }

        function toggleTheme() {
            const body = document.body;
            const btn = document.getElementById('theme-btn');
            body.classList.toggle('light-mode');
            btn.innerHTML = body.classList.contains('light-mode') ? "☀️" : "🌙";
            gsap.fromTo(btn, {rotate: 0}, {rotate: 360, duration: 0.5});
        }

        function createRose() {
            const rc = document.getElementById('rose-container');
            if(!rc) return;
            const rose = document.createElement('div');
            rose.classList.add('rose-leaf');
            rose.innerHTML = '🌹';
            rose.style.left = Math.random() * 100 + "vw";
            rose.style.animationDuration = Math.random() * 3 + 4 + "s";
            rc.appendChild(rose);
            setTimeout(() => rose.remove(), 6000);
        }
        setInterval(createRose, 500);

        ospin.style.animation = `spinRevert ${Math.abs(rotateSpeed)}s infinite linear`;
        const style = document.createElement('style');
        style.innerHTML = `@keyframes spinRevert { from { transform: rotateY(360deg); } to { transform: rotateY(0deg); } }`;
        document.head.appendChild(style);

        const weddingDate = new Date("May 30, 2026 09:00:00 GMT+0700").getTime();
function scrollUp(){
    window.scrollBy({
        top: -600,
        behavior: 'smooth'
    });
}

function scrollDown(){
    window.scrollBy({
        top: 600,
        behavior: 'smooth'
    });
}

function updateCountdown() {

    const now = new Date().getTime();
    const distance = weddingDate - now;

    if (distance < 0) {

        document.getElementById("countdown").innerHTML = `
            <div class="gold-card text-center py-6">
                <h2 class="font-wedding text-4xl text-amber-400">
                    Acara Sedang Berlangsung 🎉
                </h2>
            </div>
        `;

        return;
    }

    const days = Math.floor(distance / (1000 * 60 * 60 * 24));

    const hours = Math.floor(
        (distance % (1000 * 60 * 60 * 24)) /
        (1000 * 60 * 60)
    );

    const minutes = Math.floor(
        (distance % (1000 * 60 * 60)) /
        (1000 * 60)
    );

    const seconds = Math.floor(
        (distance % (1000 * 60)) / 1000
    );

    document.getElementById("days").innerHTML =
        String(days).padStart(2, '0');

    document.getElementById("hours").innerHTML =
        String(hours).padStart(2, '0');

    document.getElementById("minutes").innerHTML =
        String(minutes).padStart(2, '0');

    document.getElementById("seconds").innerHTML =
        String(seconds).padStart(2, '0');
}
document.addEventListener("DOMContentLoaded", () => {
    const scrollNav = document.querySelector(".scroll-nav");

    window.addEventListener("scroll", () => {
        if (!scrollNav) return;

        if (window.scrollY > 300) {
            scrollNav.classList.add("show");
        } else {
            scrollNav.classList.remove("show");
        }
    });
});
updateCountdown();

setInterval(updateCountdown, 1000);
    </script>
