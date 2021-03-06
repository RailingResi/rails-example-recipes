Recipes
=======

a ruby on rails 4.1 example app
to learn about the asset pipeline.

clone this repository, then

    bundle
    rake db:migrate
    rails server

now point your browser at the homepage at http://localhost:3000/
or at http://localhost:3000/todo.html 

There is a [demo site](https://frozen-oasis-65001.herokuapp.com/) of
the solution on heroku

TODO:

#1. Load seed data

What is seed data? Where is the actual file located? And what was that rake task to load it?

Seed data is a file to feed the database with default values.
The file is located in db/seeds.rb.
The Rake task: rails db:seed

#2. Create HTML
Study the draft: which parts of the html go into the layout? the view? a partial? Study the layout that's already there: which parts do you need to preserve?

Don't forget to replace the links with link_to - or better yet link_to_unless_current

This step should be a git commit!

    <nav>
        <ul  class="navigation">
          <li><%= link_to_unless_current "Home", root_path %></li>
          <li><%= link_to_unless_current "All Recipes", recipes_path%></li>
          <li><%= link_to_unless_current "Search Recipe", search_recipes_path%></li>
          <li><%= link_to_unless_current "New Recipe", new_recipe_path%></li>
        </ul>
      </nav>
      <article>
        <%= yield %>
      </article>
    </nav>
    
#3. Move CSS and images over to Asset Pipeline
Which part of the existing Stylesheet should be turned into sass? Use a converter. Which part should remain plain css? Just copy it over. Don't forget to test in your browser!

There is a svg image and a pixel image in the draft. Move both over to the asset pipeline and use

This step should be a git commit!

- We left the mediaquery part in the css. All other Parts are now in the sass file. 
- We had to import the files in the application.css

#4. Add a header image
Pick a free image to be the header image of this app. Choose an image that is available in a size of at least 2000px width.
    
Create a version with 1000px width and one with 2000px width

Add them as background images to the header. Use url(<%= asset_path 'header.jpg' %>) in the css or sass file.

#5. Assets in production 
    //precompile assetfiles
    $ rake assets:precompile
    
    //deploy on heroku
    $ git push heroku master
    
    //db migrate
    $ heroku run rake db:migrate
    
    //db add data
    $ heroku run rake db:seed
  

#Deployed on Heroku

https://foodrecipedathe.herokuapp.com/

    

