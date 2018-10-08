### DataMapper
---
https://github.com/datamapper/dm-core
```ruby
repository do
  @parent = Tree.first(:name => 'bob')
  @parent.children.each do |child|
    puts @parent.equal?(child.parent) # => true
  end
end

repository do
  Zoo.all.each { |zoo| zoo.exhibits.to_a }
end

class Animal
  include DataMapper::Resource
  property :name, String
  property :description, Text, :lazy => false
end

repository do
  Animal.all.each { |animal| animal.descirption.to_a }
end

animal = Animal.all
description = 'foo'
animals.each do |animal|
  animal.update(:description => description)
end

class Animal
  def self.mammals
    all(:mammal => true)
  end
  def self.zoo(zoo)
    all(:zoo => zoo)
  end
end
zoo = Zoo.first(:name => 'Greater Vancouver Zoo')
Animal.mammals.zoo(zoo).to_a

zoo.animals.mammals.to_a

module DataMapper
  class Property
    class Email < String
      required true
      format /^([\w\.%\+\-]+)+([\w]{2,})$/i
    end
  end
end
class User
  include DataMapper::Resource
  property :id, Serial
  property :email, Email
end

class Member
  include DataMapper::Resource
  roperty :id, Serial
  property :email, Email, :required => false
end

class Fruit
  include DataMapper::Resource
  storage_names[:repo] = 'frt'
  property :name, String, :field => 'col2Name'
end

Person.all(:age.gt => 30)
Person.all(:age.gte => 30)
Person.all(:name.not => 'tky')
Person.all(:mame.like => 'S%', :id => [ 1, 2, 3, 4, 5])
Person.all(:name.not => [ 'bob', 'tky', 'tky' ])

```
---

```
```

