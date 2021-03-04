namespace :greeting do # now if we want to call a task like hello we need to type the nameSpacer before it like greeting:hello

desc 'outputs hello to the terminal'
task :hello do
  puts "hello from Rake!"
end

desc 'outputs hola to the terminal'
task :hola do
  puts "hola de Rake!"
end

end # end of nameSpace

# import the evnvironment folder so that the `task :migrate will work`
task :environment do
  require_relative './config/environment'
end

# not when we require :environment we get the student class since the Student class was Require call for it in the environment.rb file
desc 'drop into the Pry console'
task :console => :environment do
  Pry.start
end


namespace :db do

  desc 'migrate changes to your database'
  # the => will run the :environment task before it Tries to run the .create_table function
  task :migrate => :environment do
    Student.create_table
  end

  desc 'seed the database with some dummy data'
  task :seed do
    require_relative './db/seeds.rb'
  end


end # end of name space
