// ==UserScript==
// @name         Youtube отписки
// @namespace    https://www.youtube.com/feed/channels
// @version      0.1
// @description  Youtube отписка от всех каналов
// @author       Master-Dzen
// @match        https://www.youtube.com/feed/channels
// @icon         https://www.google.com/s2/favicons?domain=tampermonkey.net
// @grant        none
// ==/UserScript==

var i = 0;
var count = document.querySelectorAll("ytd-channel-renderer:not(.ytd-item-section-renderer)");

myTimer();

function myTimer () {
	if (count == 0) return;

    el = document.querySelector('.ytd-subscribe-button-renderer');
    el.click();

    setTimeout(function () {
        var unSubBtn = document.getElementById("confirm-button").click();

		i++;
		count--;

        console.log(i + " unsubscribed");
        console.log(count + " remaining");

        setTimeout(function () {
			el = document.querySelector("ytd-channel-renderer");
            el.parentNode.removeChild(el);

            myTimer();
        }, 250);
    }, 250);
}
