# fh-homework-08

1) What is an Object?  Please write your answer below.

	An object is an instance of a class which allows you to define methods on it in order to get information or perform an action. Everything in Ruby is considered an object.


2) What is a Class?  Please write your answer below.

	A class represents a blueprint in which objects can be created from. It consists of a group of method definitions.


3) What's the difference between a class and module?

	You can instantiate objects from a class but not from a module. Modules are used to extend the functionality of a class


4) What does the self mean in the Ruby language? Please write your answer below.

	It refers to the default or current object when called on in different contexts.  There is only one current object or self depending on what context it is in.


5) What is a block as defined in the Ruby language?

A block is a chunk of code enclosed either in a do...end clause or within brackets that you can invoke from methods.  Blocks can be invoked inside methods using a yield statement.


Given the following:
hash = { a: 1, b: 2, c: 3, e: 4, f: 5, g: 6, h: 7, i: 8, j: 9, k: 0 }
Please answer the following questions:

6) How would I get the value of 'f'?  Please write your answer below.

    hash[f]

7) How would I add the key, 'l', with a value of 11 to the 'hash'?  Please write your answer below.

    hash[l] = 11


8) Write a method, sum_hash_values, which takes all the values of a hash produces a total.  Please write your answer below.

    def sum_hash_values( some_hash )
      sum = 0
      some_hash.values.each do |value|
        sum += value
      end
      sum
    end


9) Write a method, sum_hash_odd_values, which takes all of the odd values of a hash produces a total.  Please write your answer below.

    def sum_hash_odd_values( some_hash )
      sum = 0
      some_hash.values.each do |value|
        sum += value if value % 2 == 1
      end
      sum
    end

Note: Please don't use any Ruby Standard library methods.


10)  What's the difference between a Hash vs Array in the Ruby language?  Write your answer below.

	A Hash is a data structure that is a collection of key/value pairs
	whereas an Array is an ordered collection of any objects.

	The elements of a Hash are indexed through arbitrary keys of any type
	whereas an array is done via integers.



11)  Write a method to determine whether not a string is a palindrome using
     recursion?  

     def is_palindrome?( some_string )
        _palindrome?( some_string, 0, some_string.length - 1 )
     end

     def _palindrome?( some_string, head_index, tail_index )
        return if head_index == tail_index || head_index  > tail_index 

        if some_string[head_index] == some_string[tail_index]
          head_index += 1
          tail_index -= 1      
          _palindrome?( some_string, head_index, tail_index )
        else
          false
        end
     end


     > is_palindrome( "bob" )
     => true

     > is_palindrome( "frank" )
     => false

     > is_palindrome( "pop" )
     => true

     > is_palindrome( "xxxx yyyy xxxx" )
     => true

     Note: Please don't use any Ruby Standard library methods.  Your solution
           should not be using map, each, for, while, and so on.

12)  Given an array write a method to compute the length of an array
     using recursion.

      def length( array , count=0)
         if array[count].nil?
            count
          else
            count += 1 
            length( array, count )
          end
      end


     Note: Please don't use any Ruby Standard library methods.  Your solution
           should not be using map, each, for, while, and so on.

13)  Given an array write a method to compute the length of an array
     using iteration.

    def length( array )
      count = 0
      while ! array[count].nil?
        count += 1
      end
      count
    end


    Note: Please don't use any Ruby Standard library methods.

14) computes the power of number with a given exponent using recursion

    def power(number, exponent)
      if exponent == 0
        1
      else
        number * power(number, exponent-1)
      end
    end

    Note: Please don't use any Ruby Standard library methods.  Your solution
          should not be using map, each, for, while, and so on.


15)  Consider the following two methods:

      ```
      def times_four(arg1);
       puts arg1 * 4;
      end
      ```

      ```
      def multiply(arg1, arg2);
        puts arg1 * arg2;
      end
      ```

      What will be the result of each of the following lines of code:

      times_four 5      => please write your answer here
      times_four(5)     => 20
      times_four (5)    => 20
      multiply 1, 2     => 2
      multiply(1, 2)    => 2
      multiply (1, 2)   => syntax error

16) What is the convention for methods which end with a question mark? e.g. #all?, #kind_of?, directory?

  a) They should always require arguments.

  b) They should always return a boolean value.

  c) They should always report a value of the object they're being called on.



17) For the string class, what's the difference between "#slice" and "#slice!"?

  a) None, "#slice" is just an alias for "@slice!".

  b) There is no "#slice!" method in Ruby on Rails.

  c) "#slice" returns a new object, "#slice!" destructively updates - mutates - the object's value.



18) Given the Ruby expression `a, b = b, a` where a = 5 and b = 6\. What's the value of 'a' and 'b' after the expression is executed?

  a) a = 5, b = 6

  b) a = 6, b = 5

  c) a = 6, b = 6



Git Core

19)  What are the steps (i.e. commands) to initialize a local Git repository? Please write your answer below.

cd into root directory of of application
git init

20)  What's the command to stage a file using Git? Please write your answer below.
	
	git add <file_name>

21)  What are the necessary commands to setup a local repository so that one can push to Github.com? Please write your answer below.

cd into root directory of application
git init
git add .
git commit -am “Initial commit”
login to github.com
click Add New Repository and give it name
copy/paste instructions on Github to set up existing repository

22)  What does `git checkout branch-name` do? Please write your answer below.
	
	This creates a new branch separate from the master branch where
	someone can develop code in isolation. For example a team can use a
	branch dedicated for a specific feature or workflow.
	
23)  What does `git checkout -b branch-name` do? Please write your answer below.
	
	This creates a new branch and switches to it immediately



24)  What does `git branch -D branch-name` do? Please write your answer below.
	
	This is an alias for git branch --delete --force, which removes a branch
	regardless of its merge status



25)  What does `git merge branch-name` do where `branch-name` is a sub branch of `master`? Please explain your answer below.
	
	This merges the code from the sub branch into the master branch meaning
	any revisions/additions from the sub branch are applied to the master






RSpec Core

26)  What is TDD?
	TDD stands for test driven development.  It is a methodology where
	emphasis is placed heavily on writing out test/specifications
	during development to ensure code is working properly. The general
	concept involves writing the test out, writing enough code to make it
fail, rewriting it enough to make it pass, and then refactoring the code. This is commonly known as the red, green, refactor cycle.



27)  What is RSpec? Please write your answer below?

	RSpec is a Ruby and Ruby on Rails testing framework that focuses
	on providing libraries for use in TDD.




28)  Given the following Spec

    ```
    describe Person do

      it 'should be valid' do
        person = Person.new( 'John', 'Doe')

        expect( person ).to_not be_nil
      end

    end
    ```

    Write the implementation below which will make this test pass.

class Person
  def initialize(first_name, last_name)
  end
end


    Note:  It may be better to run locally on your system for correctness?



29)  Continuing with the previous spec write an example for testing a method `full_name`.

 
    describe Person do
  it '.full_name' do
    person = Person.new( 'John', 'Doe')

    expect( person.full_name ).to eq('John Doe') 
  end
    end
 

    Note:  If you created a person with the first name of `John` and the last name of
       `Doe`, then the `full_name` should generate `John Doe`.



30)  Write the implementation code which passes the example we created in (29). Please write your answer below.

class Person
  def initialize(first_name, last_name)
    @first_name = first_name
    @last_name = last_name
  end

  def full_name
    @first_name + " " + @last_name
  end
end


    Note:  If you created a person with the first name of `John` and the last name of
           `Doe`, then the `full_name` should generate `John Doe`.



31)  Continuing with the previous spec write an example for testing a method `reversed_full_name`.


    describe Person do
  it '.reversed_full_name' do
    person = Person.new( 'John', 'Doe')
    full_name = person.full_name

    expect( person.reversed_full_name ).to eq('Doe, John')
  end
    end


    Note:  If you created a person with the first name of `John` and the last name of
           `Doe`, then the `reversed_full_name` should generate `Doe, John`.



32)  Write the implementation code which passes the example we created in (31). Please write your answer below.

class Person
  def initialize(first_name, last_name)
    @first_name = first_name
    @last_name = last_name
  end

  def full_name
    @first_name + " " + @last_name
  end

  def reversed_full_name
    @last_name + ", " + @first_name
  end
end


    Note: If you created a person with the first name of `John` and the last name of `Doe`, then the `reversed_full_name` should generate `Doe, John`.



33)  Write the example and implementation code which passes the following examples.

    ```
    describe Person do

      it '#first_name' do
        person = Person.new( 'John', 'Doe')

        expect( person.first_name ).to eq(‘John’)
      end

      it '#last_name' do
        person = Person.new( 'John', 'Doe')

        expect( person.last_name ).to eq(‘Doe’)
      end

    end

class Person

  attr_reader :first_name, :last_name
  def initialize(first_name, last_name)
    @first_name = first_name
    @last_name = last_name
  end

  def full_name
    @first_name + " " + @last_name
  end

  def reversed_full_name
    @last_name + ", " + @first_name
  end

end



34) Add a `middle_name` method to our `Person` class. Rewrite all the examples using the information from the above.

describe Person do

  it '#initialize' do
    person = Person.new( 'John', 'Middle', 'Doe')

    expect( person ).to_not be_nil
  end

  it '.full_name' do
    person = Person.new( 'John', 'Middle', 'Doe')

    expect( person.full_name ).to eq('John Middle Doe') 
  end

  it '.reversed_full_name' do
    person = Person.new( 'John', 'Middle', 'Doe')
    full_name = person.full_name

    expect( person.reversed_full_name ).to eq('Doe, John Middle')
  end

  it '#first_name' do
    person = Person.new( 'John', 'Middle', 'Doe')

    expect( person.first_name ).to eq('John')
  end

  it '#last_name' do
    person = Person.new( 'John', 'Middle', 'Doe')

    expect( person.last_name ).to eq('Doe')
  end

  it '#middle_name' do
    person = Person.new( 'John', 'Middle', 'Doe')

    expect( person.middle_name ).to eq('Middle')
  end

end






Rails Core

35)  Please explain M in model view controller (MVC) within the Ruby on Rails
     Framework? For example, what's the role of the model.  Write your answer below in your own words.
	
	The model contains the data and business logic of the MVC framework.  It
	allows you to get the necessary data for displaying a particular output and 
is stored in a database.  The model can represent an arbitrary entity.



36)  Please explain V in model view controller (MVC) within the Ruby on Rails
     Framework? For example, what's the role of the view. Write your answer below in your own words.

	The view in the MVC framework contains all the code for outputting
	what is shown in the browser.  In Ruby on Rails, the view can use a
	combination of HTML and ERB template files to display content in the
	browser.



37)  Please explain C in model view controller (MVC) within the Ruby on Rails
     Framework? For example, what's the role of the controller. Write your answer below in your own words.

	The controller is like the middleman between the model and view layers
	of the MVC framework.  Its job is to acquire data from the model layer and
	store it as instance variables which could then be passed into views. It
	also contains all the actions used in the REST api (create, read, update
	, destroy, etc. )




38)  Use the Rails generator to produce a model called Actor which has the
     following fields:

     - first_name  - string
     - middle_name - string
     - last_name   - string

     Please write the command below.
		
rails generate model Actor first_name:string middle_name:string last_name:string



39)  Implement the Actor class using Ruby.  Write your answer below.  

class CreateActors < ActiveRecord::Migration[5.1]
  def change
    create_table :actors do |t|
      t.string :first_name
      t.string :middle_name
      t.string :last_name

      t.timestamps
    end
  end
end



40)  Use the Rails generator to produce a model called Movie which has the
     following fields:

     - actor_id   - integer
     - name       - string
     - release_on - date

    Please write the command below.

rails generate actor_id:integer name:string release_on:date



41)  Implement the Movie class using Ruby.  Write your answer below.

class CreateMovies < ActiveRecord::Migration[5.1]
  def change
    create_table :movies do |t|
      t.integer :actor_id
      t.string  :name
      t.date    :release_on

      t.timestamps
    end
  end
end



42)  Use the Rails generator to produce a model called Filmography which has the following fields:

     - actor_id - integer
     - movie_id - integer

     Note:  This is our join model which we'll be able to associate a
            given actor to a movie.

	rails generate model Filmography actor:references movie:references



43)  Implement the Filmography class using Ruby.  Write your answer below.

class CreateFilmographies < ActiveRecord::Migration[5.1]
  def change
    create_table :filmographies |t|
      t.integer :actor_id
      t.integer :movie_id
    
      t.timestamps
    end
  end
end



44)  Update the Actor model with the proper associations for accessing its'
     filmographies and movies.  Write the updated model below.

class Actor < ApplicationRecord
  has_many :filmographies
  has_many :movies, through: :filmographies
end



45)  Update the Movie model with the proper associations for accessing its'
     filmographies and actors.  Write the updated model below.  

class Movie < ApplicationRecord
  has_many :filmographies
  has_many :actors, through: :filmographies
end



46)  Using the information from (43) - (45), write a Rails query which
     would give one all the movies for a given Actor.  Please write
     your answer below.

@actor = Actor.find(params[:id])
@movies = @actor.filmographies.movies



47)  Using the information from (43) - (45), write a Rails query which
     would give one all the actors which starred in a given Movie.  Please
     write your answer below.

@movie = Movie.find(params[:id])
@actors = @movie.filmographies.actors
