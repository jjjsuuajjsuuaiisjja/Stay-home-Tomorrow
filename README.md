<!DOCTYPE html>
<html lang="ms">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Surprise</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Segoe UI,Arial,sans-serif;
}

body{
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(135deg,#4facfe,#00f2fe);
    overflow:hidden;
}

.card{
    width:360px;
    background:white;
    padding:35px;
    border-radius:20px;
    text-align:center;
    box-shadow:0 15px 35px rgba(0,0,0,.25);
}

h1{
    color:#333;
    margin-bottom:15px;
}

p{
    color:#666;
    margin-bottom:25px;
}

button{
    padding:15px 45px;
    border:none;
    border-radius:50px;
    background:#007BFF;
    color:white;
    font-size:20px;
    cursor:pointer;
    transition:.3s;
}

button:hover{
    transform:scale(1.08);
    background:#0056d6;
}

#result{
    margin-top:30px;
    font-size:30px;
    font-weight:bold;
    color:#ff0066;
    display:none;
    animation:pop .6s ease;
}

@keyframes pop{
    0%{
        transform:scale(.3);
        opacity:0;
    }
    100%{
        transform:scale(1);
        opacity:1;
    }
}

.confetti{
    position:fixed;
    font-size:30px;
    animation:fall 3s linear forwards;
}

@keyframes fall{
    from{
        transform:translateY(-100px);
    }
    to{
        transform:translateY(110vh) rotate(720deg);
        opacity:0;
    }
}
</style>
</head>

<body>

<div class="card">
    <h1>🎁 Surprise</h1>
    <p>Tekan butang di bawah.</p>

    <button onclick="showMessage()">MULA</button>

    <div id="result">
        🎉 Esok duduk rumah je! 🎉
    </div>
</div>

<script>
function showMessage(){

    document.getElementById("result").style.display="block";

    const emoji=["🎉","✨","🎊","💖","⭐"];

    for(let i=0;i<40;i++){

        let e=document.createElement("div");
        e.className="confetti";
        e.innerHTML=emoji[Math.floor(Math.random()*emoji.length)];

        e.style.left=Math.random()*100+"vw";
        e.style.animationDuration=(Math.random()*2+2)+"s";

        document.body.appendChild(e);

        setTimeout(()=>e.remove(),4000);
    }
}
</script>

</body>
</html>
