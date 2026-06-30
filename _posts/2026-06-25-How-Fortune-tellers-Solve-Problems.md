---
layout: post
author: "Raf"
title: How Fortune-tellers Solve Problems
date: 2026-06-25
---

Last weekend a friend was visiting me here in Gifu city. Usually, when I have visitors, I take them to the same izakaya, where we drink highballs and eat a plate of raw cabbage and sesame oil. This evening, we'd decided to try something new and ordered crab butter toast, which I don't recommend. After a few _mikan sours_ (a citrus drink made with shochu) to get the taste of crab butter out of our mouths, we were ready to pay the bill and leave.

It's the start of the rainy season. Outside, the concrete drums in the rain while groups of drinkers shout to one another as they pass-by. In the short time that we search the stand by the door for our umbrellas, we're already wet. Halfway to the bus stop, we notice a tent that neither of us remember passing on the way in.

I read the kanji above the entrance- 占い師 _uranai-shi_.
"A fortune teller!" I tell my friend.

We've rarely seen fortune-tellers in the UK but it's a comparatively common profession here in Japan. After some chatter and a few more steps towards the bus-stop, we make the decision to turn around and go in. Neither of us have had our fortunes read before and I think of it as a potentially interesting cultural experience.

The woman that comes out is wearing a black blazer and a white shirt and looks to be in her sixties. She smiles and holds the flap of the tent open, ushering us in warmly. As we shake off our umbrellas and sit down she hurriedly minimises something on her ipad before sliding it to one side. The tent is lit by a string of dim LED lights. Surely there are better ways to make the interior more magical?

"My friend doesn't speak Japanese but I'll interpret for him," I explain to her.
Without hesitating she agrees and says she'll give us double the time to allow for me to interpret. Impressive. It's common when interpreting for a meeting for organisers to forget to double the time. She seems unexpectedly familiar with the process.

Over the next twenty minutes she uses my friend's date of birth, an app on her phone, and a deck of tarot cards to predict his future. Each time as I interpret between the two, I find myself reaching for the sort of English that feels appropriate for a fortune teller. And after a few minutes, it feels as though I'm part of shaping his prophecy. With each new card or question, she hints towards advice that ranges from very generic, "you are someone very capable of logical thinking and can let your emotions go unnoticed, ask yourself is this what I really want?" to very specific, "don't worry, you will get your visa before next week". By the end, my friend was hanging to every word and asking questions to squeeze out as much knowledge as possible. We both leave satisfied but for different reasons. The fortune teller bows to us in gratitude outside in the rain seeing us off.

"Is it worth thinking more about what she told me?" my friend asks seriously, as if everything we told him is definitively true.

Walking back through the rain, I wasn't any more convinced that this woman could predict the future. What was surprising to me, is how quickly a stranger could provide a new vocabulary for thinking about it, and one that relied entirely on chance for its value. For a few thousand yen and twenty minutes of his time, my friend left with a completely different way to think about his problems. Which to me, seemed more than a fair price.

![izakaya](/assets/images/izakaya.png)

<div id="ft-entrance" style="position: relative; height: 220px; margin: 2em 0;">
  <img src="{{ '/assets/images/kilroy.png' | absolute_url }}" id="ft-trigger" alt="A strange figure peers out" style="cursor: pointer; position: absolute; left: 85%; top: 0; height: 100px; width: auto; z-index: 5;">
</div>

<div class="ft-overlay" id="ftOverlay">
  <div class="wood"></div>
  <div class="shadow-figure"></div>
  <div class="dark-vignette"></div>
  <div class="candle-glow"></div>
  <div class="candle"><div class="flame"></div></div>
  <p class="ft-prompt">&ldquo;sit. let&rsquo;s play a game.&rdquo;</p>
</div>

<style>
  .ft-overlay {
    display: none;
    position: fixed;
    inset: 0;
    background: #050302;
    z-index: 9999;
    overflow: hidden;
  }
  .ft-overlay.active { display: block; }
  .ft-overlay .wood {
    position: absolute; inset: 0;
    background:
      repeating-linear-gradient(95deg, #1c130a 0px, #170f08 3px, #1c130a 6px),
      radial-gradient(ellipse at 50% 100%, rgba(80,50,20,0.15) 0%, transparent 60%);
  }
  .ft-overlay .shadow-figure {
    position: absolute; top: 0; left: 50%; transform: translateX(-50%);
    width: 420px; height: 240px;
    background: radial-gradient(ellipse at 50% 0%, rgba(0,0,0,0.9) 0%, transparent 70%);
  }
  .ft-overlay .dark-vignette {
    position: absolute; inset: 0;
    background: radial-gradient(ellipse at 50% 55%, rgba(0,0,0,0) 0%, #020100 88%);
  }
  .ft-overlay .candle-glow {
    position: absolute; bottom: 28%; left: 50%; transform: translateX(-50%);
    width: 280px; height: 280px;
    background: radial-gradient(circle, rgba(232,150,60,0.18) 0%, transparent 65%);
  }
  .ft-overlay .candle {
    position: absolute; bottom: 22%; left: 50%; transform: translateX(-50%);
    width: 10px; height: 44px;
    background: linear-gradient(180deg,#d8c49a,#9c8458);
  }
  .ft-overlay .flame {
    position: absolute; top: -16px; left: 50%; transform: translateX(-50%);
    width: 8px; height: 17px;
    background: radial-gradient(ellipse at 50% 75%, #ffcf6e 0%, #d4690f 65%, transparent 100%);
    border-radius: 50%;
    animation: ft-flicker 2.2s ease-in-out infinite;
  }
  @keyframes ft-flicker {
    0%,100% { transform: translateX(-50%) scaleY(1) skewX(0deg); opacity: 0.9; }
    35% { transform: translateX(-48%) scaleY(1.15) skewX(2deg); opacity: 1; }
    60% { transform: translateX(-52%) scaleY(0.92) skewX(-2deg); opacity: 0.85; }
  }
  .ft-overlay .ft-prompt {
    position: absolute; top: 30%; left: 50%; transform: translateX(-50%);
    color: #6b5a3e; font-size: 16px; letter-spacing: 0.08em; text-align: center;
    font-style: italic; text-shadow: 0 0 10px rgba(0,0,0,0.9);
    font-family: 'IM Fell English', serif;
  }
  .ft-overlay .cloud {
    position: absolute; background: rgba(90,70,50,0.35); border-radius: 50px;
    filter: blur(6px); opacity: 0;
    transition: transform 2.5s ease-out, opacity 2.5s ease-out;
  }
</style>

<script>
  document.getElementById('ft-trigger').addEventListener('click', function() {
    var overlay = document.getElementById('ftOverlay');
    overlay.classList.add('active');

    for (var i = 0; i < 8; i++) {
      var c = document.createElement('div');
      c.className = 'cloud';
      var w = 80 + Math.random() * 120;
      c.style.width = w + 'px';
      c.style.height = (w * 0.4) + 'px';
      c.style.left = (Math.random() * 80) + '%';
      c.style.top = (10 + Math.random() * 70) + '%';
      overlay.appendChild(c);
      (function(cloud, idx) {
        setTimeout(function() {
          cloud.style.opacity = '0.8';
          cloud.style.transform = 'translateY(' + (idx % 2 === 0 ? '-' : '') + '40px) translateX(' + (idx % 2 === 0 ? '-' : '') + '60px)';
        }, idx * 70);
      })(c, i);
    }

    setTimeout(function() {
      window.location.href = '{{ "/fortuneteller.html" | absolute_url }}';
    }, 2200);
  });
</script>
