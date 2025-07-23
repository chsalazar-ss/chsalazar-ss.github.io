<html>
	<body>
		<script type='text/javascript'>
			function initEmbeddedMessaging() {
				try {
					embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'
		
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
		<script type='text/javascript' src='https://firstadvantage--fulltest.sandbox.my.site.com/ESWDemoService1744238318661/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>
   	</body>
</html>
