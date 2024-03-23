1. Clone this repo and enable Github Actions in the settings.
2. I am not sure if URLs are different per region, so here is how to copy yours.<br>
   - Go to Steam Deck refurbished website: https://store.steampowered.com/sale/steamdeckrefurbished.
   - Open dev tools, and in the network tab filter by Ftetch/XHR and select one of the GET requests that look like this:<br>
       ``` v1?origin=https:%2F%2Fstore.steampowered.com&input_protobuf_encoded=COGVNxICUEw%3D``` <br>
   - Now copy full URL, they should be ordered top to bottom, 64GB then 256GB and then 512GB. You can block requests and then see which buttons disappear when page refreshes to verify. <br>
   - Here is an URL for EU 512GB: ``` https://api.steampowered.com/IPhysicalGoodsService/CheckInventoryAvailableByPackage/v1?origin=https:%2F%2Fstore.steampowered.com&input_protobuf_encoded=COOVNxICUEw%3D ```
3. When you have the URL, go to repo setting -> secrets -> actions and then add STEAM_DECK_URL with your URL.
4. Now you have to set up Telegram notify plugin: https://github.com/marketplace/actions/telegram-notify.
   - If you prefer other notification methods (whatsapp, sms etc.) you have to change the plugin.
5. Once you have token and URL, you add them as secrets TELEGRAM_TOKEN and TELEGRAM_TO.
6. Then you can run this action manually, if everything is set up correctly you should get a message from the bot ```Steam Deck available```.
7. Now, this action will run every ~15 minutes, but it's not guaranteed on free accounts.
