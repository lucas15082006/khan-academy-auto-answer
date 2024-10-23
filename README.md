# khan-academy-auto-answer.user.js
Uso para fins educacionais
// ==UserScript==
// @name         Khan Academy Auto Answer
// @namespace    (https://pt.khanacademy.org/profile/me/teacher/kaid_396011344410263753786702/class/5832327845560320)
// @version      1.0
// @description  Auto answer para questões do Khan Academy
// @author       LUCAS
// @match        *(link unavailable)*
// @grant        none
// ==/UserScript==

(function() {
  'use strict';

  setInterval(function() {
    location.href = location.href;
    setTimeout(function() {
      var questions = document.querySelectorAll('.exercise-question');
      questions.forEach(function(question) {
        question.textContent = Math.random() < 0.5 ? 'Certo' : 'Errado';
      });
    }, 2000);
  }, 5000);
})();
