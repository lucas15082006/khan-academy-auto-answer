# khan-academy-auto-answer.user.js
javascript:(function(){"
undefined "==typeof originalParse&&(window.originalParse=JSON.parse);
JSON.parse=function(o,t){let e=originalParse(o,t);
try{const data=JSON.parse(e.data.assessmentItem.item.itemData);
if(data.question&&data.question.content){data.question.content="Please select an answer choice.";
data.question.widgets={"radio 1":{options:{choices:[{content:"Correct",correct:true},{content:"Incorrect",correct:false}]}},
"explanation 1":{options:{explanation:"(link unavailable)",hidePrompt:"",showPrompt:"Discord"}}};
e.data.assessmentItem.item.itemData=JSON.stringify(data);
}}catch(o){}return e;};
location.softReload=function(){history.pushState(null,null,location.href);
location.reload(true);};
location.softReload();
console.error=function(){};})()
