# Stages

#Stage 1 :
Go https://www.youtube.com/feed/channels

#Stage 2 :
Open DevTools->Console (Inspect)

#Stage 3 :
Paste And Run JS Code 


------------JS CODE--------------

```
function youtubeUnsubscriber() {
    var count = document.querySelectorAll("ytd-channel-renderer:not(.ytd-item-section-renderer)").length;
    var randomDelay = 500;

    if(count == 0) return false;

    function unsubscribeVisible(randomDelay) {

        if (count == 0) {
            window.scrollTo(0,document.body.scrollHeight);
            setTimeout(function() {
                youtubeUnsubscriber();
            }, 10000)
        }

        //unsubscribeButton = document.querySelector('.style-scope.ytd-menu-service-item-renderer');
	document.querySelector('#notification-preference-button > ytd-subscription-notification-toggle-button-renderer-next > yt-button-shape > button > yt-touch-feedback-shape > div > div.yt-spec-touch-feedback-shape__fill').click();

	
        setTimeout(function () {
		try {
  document.querySelector('#items > ytd-menu-service-item-renderer:nth-child(4) > tp-yt-paper-item > yt-formatted-string').click();
} catch (error) {
  document.querySelector('#items > ytd-menu-service-item-renderer:nth-child(2) > tp-yt-paper-item > yt-formatted-string').click();
}
            
            count--;
            console.log("Fixed By GZA");

            setTimeout(function () {
		document.querySelector('#confirm-button > yt-button-shape > button > yt-touch-feedback-shape > div > div.yt-spec-touch-feedback-shape__fill').click();
                unsubscribedElement = document.querySelector("ytd-channel-renderer");
                unsubscribedElement.parentNode.removeChild(unsubscribedElement);
                unsubscribeVisible(randomDelay)
            }, randomDelay);
        }, randomDelay);
    }

    unsubscribeVisible(randomDelay);
}

youtubeUnsubscriber();

```
