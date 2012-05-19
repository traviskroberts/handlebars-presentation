!SLIDE

# Bonus! #

	* Representative Views
		* github.com/mdub/representative_view
		* super easy json/xml views
	* JS Routes
		* github.com/railsware/js-routes
		* rails routes in js

!SLIDE small

# Representative View #

	@@@ ruby
	class UsersController < ApplicationController
		respond_to :xml, :json
		
		def index
			@users = User.all
		end
	end

!SLIDE

# Representative View #

	@@@ ruby
	"/apps/views/users/index.rep"
	
	r.list_of :users, @users do |user|
		r.element :name
		r.element :email
		r.element :phone
		r.element :address, user.full_address
	end

!SLIDE small

# JS Routes #

	@@@ javascript
	"/app/assets/javascripts/application.js.coffee"
	
	#= require routes
	
	Routes.users_path()
