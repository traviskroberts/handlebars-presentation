!SLIDE smaller

# Context #

	@@@ javascript
	{
		user: "John Smith"
		tasks: [
			{name: "mow the lawn"},
			{name: "buy groceries"}
		]
	}

	{{#each tasks}}
		<p>
			Task: {{name}}<br />
			Assigned To: {{../user}}
		</p>
	{{/each}}
