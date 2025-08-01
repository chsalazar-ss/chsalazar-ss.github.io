<html>
	<body>		
		<div style="position: fixed; bottom: 35px; right: 35px; border-radius: 40px; background: #1F7A4D; cursor: pointer; color: white">
			<div onclick="launchChat()" id = "chatBtn" style="display:none;align-items:center;justify-content:center;">
				<img 
				 src="https://firstadvantage.my.salesforce.com/sfc/dist/version/renditionDownload?rendition=ORIGINAL_Png&versionId=068Vv00000QBS8V&operationContext=DELIVERY&contentId=05TVv00000VfOuR&page=0&d=/a/Vv000004eRC5/znAFp.h8fjJURg_UVU_SKeGFoAbqrArsRoUocss4VbE&oid=00D36000000Iv90&dpt=null&viewId="
				 style="border-radius: 50%; float:left; margin: 5px;"
				 height="50px"
				 width="50px"/>
			       <h3 style="float:right;margin:auto;">Chat with an expert</h3>
			 </div>
		</div>
		<script type='text/javascript'>
			function initEmbeddedMessaging() {
				try {
					embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'
					embeddedservice_bootstrap.settings.hideChatButtonOnLoad = true;						
					window.addEventListener( "onEmbeddedMessagingConversationOpened", ( event ) => {					
						console.log( "onEmbeddedMessagingConversationOpened" );
						launchChat();				
					});					
					window.addEventListener( "onEmbeddedMessagingButtonCreated ", ( event ) => {					
						console.log( "onEmbeddedMessagingButtonCreated " );		
					});
					embeddedservice_bootstrap.init(
						'00DWL000002fiFF',
						'Demo_Service',
						'https://firstadvantage--fulltest.sandbox.my.site.com/ESWDemoService1744238318661',
						{
							scrt2URL: 'https://firstadvantage--fulltest.sandbox.my.salesforce-scrt.com'
						}
					);					
					var chatBtn =  document.getElementById("chatBtn");
					chatBtn.style.display = "flex";	
				} catch (err) {
					console.error('Error loading Embedded Messaging: ', err);
				}
			};
		</script>
		<script type='text/javascript' src='https://firstadvantage--fulltest.sandbox.my.site.com/ESWDemoService1744238318661/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'>			
		</script>
		<script type="text/javascript"> 
			window.addEventListener("onEmbeddedMessagingWindowClosed", () => {
				console.log( "onEmbeddedMessagingWindowClosed" );
				var chatBtn =  document.getElementById("chatBtn");
				chatBtn.style.display = "flex";	
			}); 					
			window.addEventListener( "onEmbeddedMessagingWindowMinimized", ( event ) => {					
				console.log( "onEmbeddedMessagingWindowMinimized" );
				var chatBtn =  document.getElementById("chatBtn");
				chatBtn.style.display = "none";						
			});
		</script>
		<script>
			function launchChat() {
			   embeddedservice_bootstrap.utilAPI.launchChat()
			       .then(() => {
					console.log(
				       		'Successfully launched Messaging'
				   	);
				       	embeddedservice_bootstrap.utilAPI.showChatButton();
					var chatBtn =  document.getElementById("chatBtn");
					chatBtn.style.display = "none";	
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
   	</body>
</html>
