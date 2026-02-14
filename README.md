<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Our Love Story ❤️</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', sans-serif; }
    body {
      min-height: 100vh;
      background: linear-gradient(135deg, #ff758c, #ff7eb3);
      display: flex;
      align-items: center;
      justify-content: center;
      color: #fff;
    }
    .chat-box {
      width: 100%;
      max-width: 420px;
      background: rgba(255,255,255,0.15);
      backdrop-filter: blur(12px);
      border-radius: 20px;
      box-shadow: 0 20px 40px rgba(0,0,0,0.25);
      display: flex;
      flex-direction: column;
      overflow: hidden;
    }
    .header {
      padding: 15px;
      text-align: center;
      font-weight: bold;
      font-size: 1.1rem;
      background: rgba(0,0,0,0.15);
    }
    .messages {
      flex: 1;
      padding: 15px;
      overflow-y: auto;
    }
    .msg {
      max-width: 80%;
      margin-bottom: 12px;
      padding: 10px 14px;
      border-radius: 15px;
      line-height: 1.4;
      animation: fadeUp 0.5s ease;
    }
    .me {
      background: rgba(255,255,255,0.9);
      color: #ff4f81;
      margin-left: auto;
      border-bottom-right-radius: 5px;
    }
    .her {
      background: rgba(0,0,0,0.25);
      color: #fff;
      margin-right: auto;
      border-bottom-left-radius: 5px;
    }
    .image-msg img {
      width: 100%;
      border-radius: 12px;
      margin-top: 5px;
    }
    .controls {
      padding: 12px;
      text-align: center;
      background: rgba(0,0,0,0.15);
    }
    button {
      border: none;
      padding: 10px 20px;
      border-radius: 25px;
      font-size: 0.95rem;
      cursor: pointer;
      background: #fff;
      color: #ff4f81;
      transition: transform 0.2s ease;
    }
    button:hover { transform: scale(1.05); }
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>
  <div class="chat-box">
    <div class="header">MKE WANGU 💕</div>
    <div class="messages" id="messages"></div>

    <audio id="bgMusic" loop>
      <source src="music.mp3" type="audio/mpeg">
    </audio>

    <div class="controls">
      <button onclick="nextStory()">Next 💖</button>
    </div>
  </div>

  <div id="finalScene" style="display:none; position:fixed; top:0; left:0; right:0; bottom:0; align-items:center; justify-content:center; flex-direction:column; background:linear-gradient(135deg,#ff4f81,#ff9a9e); color:#fff; text-align:center; z-index:9999; animation:fadeUp 1.2s ease;">
    <h1 style="font-size:2.5rem; margin-bottom:15px;">I Love You, Riziki ❤️</h1>
    <p style="font-size:1.2rem; max-width:320px; line-height:1.6;">HUU NI MWANZO TUU, KWASABABU NAKUPENDA ZAID YA MTU YEYOTE HAPA DUNIANI NIMEKUCHAGUA WEWE UWE WANGU,
       WANGU WA MAISHA KUFA NA KUZIKANA. 
       Niliwaza ni zawadi gani nitakayo kupea, maana nataka mpenzi ufurahi, natumai hii imekupendeza mke wangu kaa ukijua mmeo sijiwezi juu yako nakupenda❤️
          .</p>
  </div>

<script>
  // Main love story timeline
  const story = [
    { who: 'me', text: 'Mambo Babe wangu Riziki ❤️ je unakumbuka tulionana wapi kwa mara ya kwanza mimi na wewe? Mwenzako Tangu siku ile nilipokuona, moyo wangu haujawahi kuwa ule ule tena' },
    { who: 'me', text: 'Bila shaka unakumbuka mpenzi ila ngoja nikukumbushe ili ujue namimi nakumbuka pia' },
    { who: 'image', src: 'photo1.jpg', caption: 'kwenye huu mbuyu ndo story yetu ilianzia, ulikuja zako kuuza msosi ukakutana na mimi tukakubaliana kwamba nakula nakula ntakulipa kwa halopesa  n hapo ndo nikapata namba yako💕💕💕 💫' },
    { who: 'image', src: 'photo5.jpg', caption: 'hii sura ilikuwa ishanichanga ivoo, hilo tabasamu na hayo macho💕💕💕 💫' },
    { who: 'me', text: 'Bas siku hiyo nilikuwa nimebakisha siku kadhaa PEMBA nilikuwa nishaichoka natamani kurudi unguja😂, basi nikajisemea ngoja  nitulie zangu nisije zama kukupenda bure halafu nikaenda UNGUJA na nisirud ena PEMBA  ' },
    { who: 'me', text: 'basi siku zikafika nikakata zangu tiket ya kwenda unguja, kumbens wewe uliichoka pemba ukawa unaikimbia Mungu akakuleta huko huko🤷‍♂️🤦‍♂️💕 akakuleta huko huko ninapoelekea, na ulipokuja nilipo nikajiuliza nataka Mungu anipe nn kingine, yaani huyu lazima ni Riziki yangu nikashindwa kukuomba namba pale pale kwenye umati nikasema nitakupata nje ' },
    { who: 'me', text: 'Lakin mda wa kutoka nikakutafuta nikakukosa , lakin nikakumbuka huyu nishawahi kumtumia pesana namba yake ninayo basi kupoteza muda nikakupigia  mtoto wa Bububu na ulivyokuwa Riziki yangu ukapokea  ' },
    { who: 'me', text: 'Hata sikukusubirisha nikakutongoza moja kwa moja😒 halafu ukanikataa na kunipenda siku inayofuata,  Basi tukaanza kuongea kidogo kidogo,mbaka tukazoeana, nikakualika kwangu  hukusita kuja nilivyokuwa sina nguvu juu yako nikakuchapa siku hiyo hiyo na ulivyo mtamu nikajisemea sikuachi kamwe katu ' },
    { who: 'image', src: 'photo2.jpg', caption: ' kichwani mwangu NIMEJAZA PICHA ZAKO🤦‍♂️, upendo wako daima unanifanya nikukumbuke🪬, nakukumis na kupenda kadri siku zinavyozidi kwenda 😍❤️😊' },
    { who: 'me', text: 'basi kila unaposoma ujumbe Huu jua Mimi nakupenda tena nakupenda sana.' },
    { who: 'image', src: 'photo4.jpg', caption: 'Sio tu nakukumbuka, bali kila pumzi ninayovuta inanikumbusha uwepo wako❤️' },
    { who: 'me', text: 'kila siku wewe husema mimi ni furaha yako lakini hujui tuu kuwa mimi Nilidhani najua maana ya furaha, mpaka pale ulipoingia kwenye maisha yangu, umenipatia furaha ambayo sijui niielezee vipi .' },
    { who: 'me', text: 'Kama mapenzi ni safari, basi wewe ndio ramani🗺️ na mwelekeo wangu,Umbali unaweza kututenganisha kwa macho👀, lakini kamwe hauwezi kuutenganisha moyo wangu na wako💓, Natumai huu sio mwisho wa hadithi yetu📖 …Huu ni mwanzo tuu na umbali baina yetu ni daraja🌉 ambalo tunatikiwa tulivuke kwa gharama yoyote ile sababu natamani kuwa mume wako halali wa ndoa .' },
    { who: 'me', text: 'Sasa Basi hii ndo zawadi yangu kwako siku ya leo,  Happy Valentine’s Day, my love , my wife, my everything💖' }
  ];

  const quotes = [
  
    'i love you... 💕',
   
  ];

  let index = 0;
  const messagesDiv = document.getElementById('messages');

  function typeMessage(element, text, i = 0) {
    if (i < text.length) {
      element.innerHTML += text.charAt(i);
      setTimeout(() => typeMessage(element, text, i + 1), 40);
    }
  }

  function nextStory() {
    const music = document.getElementById('bgMusic');
    if (music.paused) {
      music.volume = 0.4;
      music.play().catch(() => {});
    }

    if (index >= story.length) {
      document.getElementById('finalScene').style.display = 'flex';
      return;
    }

    const msgData = story[index];
    const msg = document.createElement('div');

    if (msgData.who === 'image') {
      msg.className = 'msg her image-msg';
      msg.innerHTML = `<div>${msgData.caption}</div><img src="${msgData.src}" />`;
      messagesDiv.appendChild(msg);
      messagesDiv.scrollTop = messagesDiv.scrollHeight;
      index++;
      return;
    }

    msg.className = 'msg ' + msgData.who;
    msg.innerHTML = '';
    typeMessage(msg, msgData.text);
    messagesDiv.appendChild(msg);
    messagesDiv.scrollTop = messagesDiv.scrollHeight;

    index++;

    // Insert a random quote every two steps
    if (index % 2 === 0) {
      const quote = document.createElement('div');
      quote.className = 'msg her';
      quote.style.opacity = '0.8';
      quote.innerText = quotes[Math.floor(Math.random() * quotes.length)];
      messagesDiv.appendChild(quote);
    }
  }
</script>
</body>
</html>
