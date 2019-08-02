# repo
`rails new repo -d mysql`

Configuramos database.yml para mysql

```
   default: &default
   adapter: mysql2
   encoding: utf8
   pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
   username: user
   password: *********
   socket: /var/run/mysqld/mysqld.sock
   ```
 
 Crear base de datos
 
 `rake db:create`
 
Iniciar servidor

```
rails s
rails server -b ip
``` 
Crea un controlador welcome y una vista index

`rails generate controller welcome index`

No modificar nada en el controlador
app/controllers/welcome_controller.rb

```
class WelcomeController < ApplicationController
  def index
  end
end
```
Modificar la vista
app/views/welcome/index.html.erb

`<h1>Hello, Rails!</h1>`

Añadir root :to => "welcome#index" para la raiz localhost:3000 en
config/routes.rb

```
Rails.application.routes.draw do
  get 'welcome/index'  
  root :to => "welcome#index"
end 
```

