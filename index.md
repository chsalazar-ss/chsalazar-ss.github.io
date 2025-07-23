<html>
	<body>
		<script type='text/javascript'>
			function initEmbeddedMessaging() {
				try {
					embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'
					embeddedservice_bootstrap.settings.hideChatButtonOnLoad = true;
					embeddedservice_bootstrap.init(
						'00DWL000002fiFF',
						'Demo_Service',
						'https://firstadvantage--fulltest.sandbox.my.site.com/ESWDemoService1744238318661',
						{
							scrt2URL: 'https://firstadvantage--fulltest.sandbox.my.salesforce-scrt.com'
						}
					);
				} catch (err) {
					console.error('Error loading Embedded Messaging: ', err);
				}
			};
		</script>
		<script type='text/javascript' src='https://firstadvantage--fulltest.sandbox.my.site.com/ESWDemoService1744238318661/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'>	
		</script>
		<div style="position: fixed; bottom: 35px; right: 35px; border-radius: 40px; background: #1F7A4D; cursor: pointer; color: white">
			<div onclick="launchChat()" id = "chatBtn" style="display:flex;align-items:center;justify-content:center;">
		        	<img 
			         src="https://firstadvantage--fulltest.sandbox.my.salesforce.com/sfc/dist/version/renditionDownload?rendition=ORIGINAL_Png&versionId=068WL000005P1UH&operationContext=DELIVERY&contentId=05TWL000009hSS5&page=0&d=/a/WL000000DnUL/C3BPS.5dSnMjeTIL_IfY7VhmS4hEEjF97LojVjVVLxg&oid=00DWL000002fiFF&dpt=null&viewId="
			         style="border-radius: 50%; float:left; margin: 5px;"
			         height="50px"
			         width="50px"/>
			       <h3 style="float:right;margin:auto;">Chat with an expert</h3>
		         </div>
		</div>
		<script>
			function launchChat() {
			   embeddedservice_bootstrap.utilAPI.launchChat()
			       .then(() => {
					console.log(
				       		'Successfully launched Messaging'
				   	);
				   	var chatBtn =  document.getElementById("chatBtn");
					chatBtn.style.display = "none";	
				       	embeddedservice_bootstrap.utilAPI.showChatButton();
			       }).catch(() => {
				   console.log(
				       'Some error occurred when launching Messaging'
				   );
			       }).finally(() => {
				   console.log(
				       'Successfully launched Messaging - Finally'
				   );
			       });
		       }
		</script>
		<script type="text/javascript"> 
			window.addEventListener("onEmbeddedMessagingWindowClosed", () => {
				console.log("Received the onEmbeddedMessagingWindowClosed event.");				
				var chatBtn =  document.getElementById("chatBtn");
				chatBtn.style.display = "block";	
			});
		</script>
   	</body>
</html>
