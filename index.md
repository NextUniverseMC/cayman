---
layout: default
---

## <i class="twa twa-ballot-box-with-ballot"></i> Vote
Vote for the server to restart, and the minigame you want (or go out on a limb with a random game).

## <i class="twa twa-chart-with-upwards-trend"></i> Majority Rules
When a majority is reached the server will begin the countdown.

## <i class="twa twa-game-die"></i> Time to decide
The server will then pick the game, if a game has 80% of the vote, there is an 20% chance there will be a random game.

## <i class="twa twa-rainbow"></i> Profit
Players are then dropped into the new minigame, don't like it? Just vote again!

<script>
  $(document).ready(function() {
    //feed to parse
    var feed = "https://forums.nextuniverse.org/forums/announcements/index.rss";
    
    $.ajax(feed, {
        accepts:{
            xml:"application/rss+xml"
        },
        dataType:"xml",
        success:function(data) {
            //Credit: http://stackoverflow.com/questions/10943544/how-to-parse-an-rss-feed-using-javascript

            $(data).find("item").each(function () { // or "item" or whatever suits your feed
                var el = $(this);
                console.log("------------------------");
                console.log("title      : " + el.find("title").text());
                console.log("link       : " + el.find("link").text());
                console.log("content: " + el.find("content\\:encoded").text());
                console.log("content: " + el.find("encoded").text());
            });
    

        }   
    });
    
});
</script>
