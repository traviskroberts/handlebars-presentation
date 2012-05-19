!SLIDE

# Features of Handlebars #

!SLIDE small

# HTML Escaping #

	@@@ javascript
	{
		content: "<p>This is the content.</p>"
	}
	
	<div id="content">
		{{content}}
	</div>
	
	<div id="content">
		&lt;p&gt;This is the content.&lt;\p&gt;
	</div>

!SLIDE small

# HTML Escaping #

	@@@ javascript
	{
		content: "<p>This is the content.</p>"
	}
	
	<div id="content">
		{{{content}}}
	</div>
	
	<div id="content">
		<p>This is the content.</p>
	</div>

!SLIDE small

# each Block #

	@@@ javascript
	{
		tasks: [
			{name: "pay bills"},
			{name: "buy groceries"},
			{name: "mow the lawn"}
		]
	}
	
	<ul>
		{{#each tasks}}
			<li>{{name}}</li>
		{{/each}}
	</ul>

!SLIDE small

# with Block #

	@@@ javascript
	{
		name: "John Smith",
		task: {
			name: "mow the lawn",
			time: "2 hours"
		}
	}

	<h1>{{name}}</h1>
	{{#with task}}
		<p>
			You have to {{name}},
			which will take {{time}}
		</p>
	{{/with}}

!SLIDE small

# Alternate Way #

	@@@ javascript
	{
		name: "John Smith",
		task: {
			name: "mow the lawn",
			time: "2 hours"
		}
	}

	<h1>{{name}}</h1>
	<p>
		You have to {{task.name}},
		which will take {{task.time}}
	</p>

!SLIDE smaller

# if/unless Block #

	@@@ javascript
	{
		task: {
			name: "mow the lawn",
			time: "2 hours"
		},
		show_name: true,
		hide_time: false
	}

	{{#if show_name}}
		<h1>{{task.name}}</h1>
	{{/if}}
	
	{{#unless hide_time}}
		<p>Time: {{task.time}}</p>
	{{/unless}}
