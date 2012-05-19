!SLIDE tinycode

# Helpers #

	@@@ javascript
	Handlebars.registerHelper('titlelize', function(string) {
		string = string.split('_').join(' ');
		string.toLowerCase().replace(/\b[a-z]/g, function(letter) {
			letter.toUpperCase();
		});
	});
	
	{
		variable_name: "underscored_variable_name"
	}
	
	<h1>{{#titlelize variable_name}}</h1>
	
	<h1>Underscored Variable Name</h1>