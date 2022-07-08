# Rails Project #

  
### 1. setup the rails environment ###
run the following to setup the database as pg and skip the test
```
code ~/.railscr
```
Add the following
```
-T 
-d postgresql
--skip-turbolinks
```

### 2. run the following to install bundler ###
```
gem bundler
```

### 3. create a new rails project and database ###

```
rails new <project_name>
rails db:create
```

### 4. install gems ###
In ``Gemfile`` file add the following
```
gem 'faker', '~> 1.6', '>= 1.6.6'
gem 'pry-rails', '~> 0.3.9'
```
after save, run ``bundle`` to install gems

### (optional) modify controller generator setup ###
In ``app/config/application.rb`` file, add the following
```
config.generators do |g|
  g.helper = false
  g.assets = false
end
```
### 5. create home page controller ###
run the following in terminal
```
rails g controller home home
```
In ``config/routes.rb`` file, add the following to setup routes
```
root "welcome#home"
get 'welcome/home' => "welcome#home"
 ```

### 6. create model ###
```
rails g model <model_name> <attribute:attribute_type> <attribute:attribute_type>
```
example: 
```
rails g model project title:string description:text
```

run the following to migrate the files
```
rails db:migrate
```

``db/schema.rb``file should be updated (!important! always use migration files to update the shema instead of manually update)


### 7. validates the model ###
In ``app/models/<model_name>.rb``file, add the validation
refer to this website for more information: <a href= "https://guides.rubyonrails.org/active_record_validations.html">Active Record Validations</a>





