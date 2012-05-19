!SLIDE

# Rails 3 #

## Asset Pipeline + CoffeeScript ##

* coffee-rails
* handlebars_assets

!SLIDE

# Templates #

* Templates live in /app/assets/javascripts/templates/
* handlebars_assets gives access to pre-compiled templates
* you can access a template via HandlebarsTemplates\["path/to/template"\]({arg: val})

!SLIDE smaller

# Example - CoffeeScript #

## /app/assets/javascripts/application.js.coffee

	@@@ javascript
	#= require jquery
	#= require handlebars.runtime
	#= require_tree ./templates
	
	$.ajax
		url: "/get_users"
		dataType: "json"
		success: (data) ->
			template = HandlebarsTemplates["templates/users"]({
				users: data
			})
			$("#content").html(template)

!SLIDE small

# Example - Handlebars Template #

## /app/assets/javascripts/templates/users.hbs

	@@@ html
	<ul>
		{{#each users}}
			<li>{{name}} - {{email}}</li>
		{{/each}}
	</ul>

!SLIDE smaller

# Using with JST Global #

## /app/assets/javascripts/templates/users.jst.hbs

	@@@ javascript
	#= require jquery
	#= require handlebars.runtime
	#= require_tree ./templates
	
	$.ajax
		url: "/get_users"
		dataType: "json"
		success: (data) ->
			template = JST["templates/users"]({users: data})
			$("#content").html(template)