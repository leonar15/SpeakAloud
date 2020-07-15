# Select & Speak Bookmarklet
A privacy-focused bookmarklet to speak any text on a page using speech synthesis

## Bookmarklet code
```javascript
javascript:(function(){var e,t,n,o=document,a=window,i=o.getElementById("selectnspeak_bk_control"),l=[],s="",p=new SpeechSynthesisUtterance,c=a.speechSynthesis;function r(){var t,o,i;a.getSelection?s=a.getSelection().toString():(n=a.selection)&&"Text"==n.type&&(s=n.createRange().htmlText),d(),s.length?(p.text=s,p.voice=(t=e.selectedOptions,o=t&&t.length?e.selectedOptions[0].getAttribute("data-name"):"",i=null,l.some(e=>(i=e,e.name===o)),i),c.speak(p)):alert("Select & Speak: Please select some text before pressing play.")}function d(){c.cancel()}function x(e,t,n){var a=o.createElement(e);return t&&t.forEach(e=>{a.setAttribute(e[0],e[1])}),n&&(a.style.cssText=n),a}function g(e,t,n){var o=x("button",null,"margin:10px 5px;vertical-align:middle;height:32px;width:32px;background-color:white;color:black; border:1px solid #333;white-space:nowrap;padding:2px;border-radius: 6px;");return o.innerHTML=e,o.title=t,o.onclick=n,o}i?e=i.getelementsByTagName("select")[0]:((i=x("div",[["draggable",!0]])).id="selectnspeak_bk_control",i.style.cssText="font-family:sans-serif;border:1px solid #bdbdbd;padding: 6px 10px;position: fixed;top: 10px; left: 10px;background-color:rgba(236,236,236,0.9);width: 250px;text-align: center;z-index:9999999;box-shadow: 0px 0px 17px -3px rgba(255,255,255,1);font-size:16px;box-sizing:border-box;border-radius: 6px;",i.innerHTML='<div style="font-size:18px;font-weight:600;border-bottom:1px solid;padding: 7px 0;">Select &amp; Speak Controls</div>',(e=x("select")).style.cssText="width: 100%;",(t=o.createElement("option")).disabled=!0,t.textContent="Select a voice:",e.append(t),e.onchange=r,l=c.getVoices(),setTimeout((function(){(l=c.getVoices()).forEach(t=>{var n=x("option",[["data-lang",t.lang],["data-name",t.name]]);n.textContent=t.name+" ("+t.lang+")",t.default&&(n.selected=!0,n.textContent+=" -- DEFAULT"),e.append(n)})}),30),i.append(g("&#9654;","Speak current selection",r),g("&#10074; &#10074;","Pause/Unpause",(function(){c.speaking&&c.paused?c.resume():c.pause()})),g("&#9724;","Stop all playback",d),g("&times;","Stop playback & Close controls",(function(){d(),i.parentNode.removeChild(i)})),e),o.body.append(i)),r()}());
```

## How to Use
1. Create a new bookmark (e.g. bookmark this page) 
2. Right-click the bookmark in your bookmark bar and select "edit"
3. Copy & paste the bookmarklet code into the URL location, making sure to remove the prior content entirely
4. Change the bookmark label to "Select & Speak" (optional)
5. Select some text on any webpage, then click the bookmark you just made.
6. Enjoy!
