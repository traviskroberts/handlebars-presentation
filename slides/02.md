!SLIDE tinycode

# Simplest Example #

	@@@ html
	<script id="entry-template" type="text/x-handlebars-template">
		<p>Hi, my name is {{name}}</p>
	</script>

	<div id="content"></div>

	<script type="text/javascript">
		var source = $('#entry-template').html();
		var template = Handlebars.compile(source);
		var output = template({name: 'Travis'});
		$('#content').html(output)
	</script>