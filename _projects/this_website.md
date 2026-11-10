---
layout: page
title: This Website
description: Portfolio site built with Jekyll and al-folio, hosted on GitHub Pages.
img: assets/img/e2s_logo.png
importance: 1
category: personal
tags: [web, jekyll]
---

<div id="recursion-splash" style="display:flex; flex-direction:column; align-items:center; justify-content:center; min-height:40vh; text-align:center;">
  <img src="{{ '/assets/img/e2s_logo.png' | relative_url }}" alt="Earth to Sean robot" style="max-width:200px; margin-bottom:1rem;" />
  <p id="recursion-msg" style="font-family:monospace; font-size:1.2rem; color:var(--global-theme-color);"></p>
</div>

<script>
(function() {
  var count = parseInt(sessionStorage.getItem('recursion_depth') || '0', 10) + 1;
  sessionStorage.setItem('recursion_depth', count);
  var msg = document.getElementById('recursion-msg');
  var messages = {
    1: 'Redirecting home...',
    2: 'Redirecting home...',
    3: 'Redirecting home...',
    4: 'Redirecting home...',
    5: 'Redirecting home...',
    6: 'Back again?',
    7: 'You know this loops, right?',
    8: 'Okay, I admire the commitment.',
    9: 'Are you... testing me?',
    10: 'This is the website equivalent of opening the fridge again hoping new food appeared.',
    11: 'I am beginning to worry about you.',
    12: 'Plot twist: the real website was the clicks you made along the way.',
    13: 'Sir, this is a portfolio site.',
    14: 'I bet you pull doors that say push.',
    15: 'Somewhere, a base case is crying.',
    16: 'At this point you could have built your own website.',
    17: 'My creator did not prepare me for this.',
    18: 'I am mass-less, and yet I am tired.',
    19: 'I yield. You have out-recursed me.',
    20: 'x_x'
  };
  msg.textContent = messages[Math.min(count, 20)];
  var delay = count <= 5 ? 800 : 1800;
  setTimeout(function() {
    window.location.href = '{{ "/" | relative_url }}';
  }, delay);
})();
</script>
