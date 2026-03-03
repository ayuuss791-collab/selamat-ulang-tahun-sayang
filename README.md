# selamat-ulang-tahun-sayang
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>FAIZ ADIBI ❤️ 10 Maret</title>

<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:'Segoe UI', sans-serif;}

body{
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    text-align:center;
    color:white;
    overflow:hidden;
    background: linear-gradient(135deg,#ff758c,#ff7eb3,#8e2de2,#4a00e0);
}

.container{
    max-width:350px;
    padding:25px;
    background:rgba(0,0,0,0.4);
    border-radius:20px;
    backdrop-filter:blur(10px);
}

h1{font-size:22px;margin-bottom:15px;}
p{font-size:16px;line-height:1.6;}

.tap{margin-top:20px;font-size:13px;opacity:0.7;}

.sticker{
    position:absolute;
    font-size:28px;
    animation:floatUp 4s linear forwards;
}

@keyframes floatUp{
    0%{transform:translateY(0);opacity:1;}
    100%{transform:translateY(-300px);opacity:0;}
}
</style>
</head>

<body onclick="nextSlide()">

<div class="container" id="content">
    <h1>Hai FAIZ ADIBI ❤️</h1>
    <p id="text">Aku punya sesuatu buat kamu...</p>
    <div class="tap">Tap di mana saja ✨</div>
</div>

<script>

let slide = 0;

const slides = [
"Katanya 10 Maret itu cuma tanggal biasa... tapi buat aku itu hari lahirnya laki-laki paling spesial 🤍",
"Kalau ulang tahun itu nambah umur, semoga kamu juga nambah sabar buat hadapi aku 😌",
"Aku nggak butuh yang sempurna. Aku cuma butuh kamu… yang selalu jadi rumah buat aku 💙",
"Dan sebelum lanjut... aku cuma mau bilang: aku bersyukur banget punya kamu 🥺"
];

function nextSlide(){
    slide++;

    if(slide <= slides.length){
        document.getElementById("text").innerHTML = slides[slide-1];
        createSticker();
    }

    if(slide === slides.length){
        setTimeout(showBirthday,1000);
    }
}

function showBirthday(){
    document.getElementById("content").innerHTML = `
        <h1>Happy 21st Birthday 🎂</h1>
        <h2 style="color:#ffd369;">FAIZ ADIBI</h2>
        <p>
        10 Maret 2005 kamu lahir ke dunia ini.  
        Semoga umur baru ini penuh kebahagiaan, rezeki, dan kesehatan 🤍
        </p>
    `;

    confetti({particleCount:200,spread:120,origin:{y:0.6}});
    createStickerBurst();

    setTimeout(showPrank,3000);
}

function showPrank(){
    document.getElementById("content").innerHTML = `
        <h1>Eh BOONG 😭</h1>
        <p>
        Umur kamu yang bener 22 ya??  
        KTP kamu kamu mudakan ya?? 😏
        </p>
    `;

    confetti({particleCount:150,spread:150,origin:{y:0.5}});
    createStickerBurst();

    setTimeout(showAnniversary,3000);
}

function showAnniversary(){
    document.getElementById("content").innerHTML = `
        <h1>Happy Anniversary 💍✨</h1>
        <p>
        Dan yang paling penting...  
        10 Maret bukan cuma ulang tahun kamu.  

        Itu juga hari dimana kita memulai cerita kita.  
        Hari dimana aku punya kamu secara resmi 🤍  

        Terima kasih sudah bertahan sejauh ini.  
        Semoga hubungan kita makin kuat, makin dewasa,  
        dan selalu penuh cinta.  

        Aku sayang kamu, FAIZ ADIBI 💙
        </p>
    `;

    confetti({particleCount:250,spread:150,origin:{y:0.6}});
    createStickerBurst();
}

/* STIKER */
function createSticker(){
    const emojis = ["💖","✨","🎉","💘","🥰","🌸","💍"];
    const sticker = document.createElement("div");
    sticker.className="sticker";
    sticker.innerText=emojis[Math.floor(Math.random()*emojis.length)];
    sticker.style.left=Math.random()*100+"vw";
    sticker.style.top="80vh";
    document.body.appendChild(sticker);
    setTimeout(()=>sticker.remove(),4000);
}

function createStickerBurst(){
    for(let i=0;i<12;i++){
        createSticker();
    }
}

</script>

</body>
</html>
