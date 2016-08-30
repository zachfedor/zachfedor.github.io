---
layout: post
title:  "A Post That Has Everything"
date:   2016-01-07 07:40:30 -0500
author: zachfedor
categories: musings
---
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer ut commodo turpis, dapibus lobortis purus. Nulla vestibulum urna vitae sapien rutrum tristique. [Donec eleifend in eros](www.loremipsum.com "Lorem Ipsum Generator") vel posuere. Suspendisse ullamcorper dui sit amet ligula pellentesque dignissim ac vel mi. Suspendisse libero dui, pretium quis dui consequat, molestie vestibulum felis. Nulla faucibus, nisl quis cursus congue, arcu mi convallis lorem, in porttitor magna sapien vel dolor. Sed purus dolor, porttitor ac fringilla varius, vestibulum vel augue. Sed feugiat sapien non aliquet [dictum][reference-1].


[reference-1]: http://google.com/  "Let Me Google That For You"

Quisque malesuada *laoreet rhoncus*. Nunc velit justo, eleifend eget malesuada ut, dapibus ac nisl. Praesent mi nunc, pulvinar eget venenatis et, congue ac dolor. Mauris mi nibh, **sodales et accumsan vitae**, lacinia id erat. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Maecenas sit amet vulputate eros. Mauris maximus egestas quam eu ullamcorper. Proin turpis felis, pharetra nec lectus et, ullamcorper pellentesque sem.

---

Aliquam erat volutpat. Fusce ac facilisis `nisl`, sed sodales ante. Etiam `leo lorem`, vehicula vitae nunc vitae, posuere varius odio. Morbi congue nisi ac bibendum condimentum. Praesent sagittis tellus ut dui molestie, sodales varius sapien pellentesque. Nullam sed finibus arcu. Mauris nec enim ac arcu suscipit tincidunt. Donec tristique ex a tellus ornare scelerisque. Aliquam eu enim iaculis, mollis sapien ut, ultricies enim. Aliquam condimentum ipsum mi, molestie efficitur dolor consectetur ac. Suspendisse neque magna, bibendum sit amet aliquet at, fermentum et nibh. Suspendisse eu urna mollis, volutpat risus vel, pharetra eros. Vivamus rhoncus elit et pulvinar consequat. Phasellus ornare velit eget quam scelerisque, at tincidunt est varius. Maecenas eu hendrerit arcu.


- Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    - nested
        - nested twice
        - nested twice
    - nested
- Aliquam vestibulum libero eu fermentum ultrices.
- Quisque eu elit euismod ligula rutrum fermentum.
- Pellentesque tempor dolor ac rhoncus tincidunt.


Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer ut commodo turpis, dapibus lobortis purus. Nulla vestibulum urna vitae sapien rutrum tristique. Donec eleifend in eros vel posuere. Suspendisse ullamcorper dui sit amet ligula pellentesque dignissim ac vel mi. Suspendisse libero dui, pretium quis dui consequat, molestie vestibulum felis. Nulla faucibus, nisl quis cursus congue, arcu mi convallis lorem, in porttitor magna sapien vel dolor. Sed purus dolor, porttitor ac fringilla varius, vestibulum vel augue. Sed feugiat sapien non aliquet dictum.


1. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    1. nested
        1. nested twice
        1. nested twice
    1. nested
1. Aliquam vestibulum libero eu fermentum ultrices.
1. Quisque eu elit euismod ligula rutrum fermentum.
1. Pellentesque tempor dolor ac rhoncus tincidunt.


Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer ut commodo turpis, dapibus lobortis purus. Nulla vestibulum urna vitae sapien rutrum tristique. Donec eleifend in eros vel posuere. Suspendisse ullamcorper dui sit amet ligula pellentesque dignissim ac vel mi. Suspendisse libero dui, pretium quis dui consequat, molestie vestibulum felis. Nulla faucibus, nisl quis cursus congue, arcu mi convallis lorem, in porttitor magna sapien vel dolor. Sed purus dolor, porttitor ac fringilla varius, vestibulum vel augue. Sed feugiat sapien non aliquet dictum.


Block Quote:

> Donec eleifend in eros vel posuere. Suspendisse ullamcorper dui sit amet ligula pellentesque dignissim ac vel mi. Suspendisse libero dui, pretium quis dui consequat, molestie vestibulum felis.
> Donec eleifend in eros vel posuere. Suspendisse ullamcorper dui sit amet ligula pellentesque dignissim ac vel mi. Suspendisse libero dui, pretium quis dui consequat, molestie vestibulum felis.
>
> <span>-- <cite>Cicero</cite></span>

Aliquam erat volutpat. Fusce ac facilisis `nisl`, sed sodales ante. Etiam `leo lorem`, vehicula vitae nunc vitae, posuere varius odio. Morbi congue nisi ac bibendum condimentum. Praesent sagittis tellus ut dui molestie, sodales varius sapien pellentesque. Nullam sed finibus arcu. Mauris nec enim ac arcu suscipit tincidunt. Donec tristique ex a tellus ornare scelerisque. Aliquam eu enim iaculis, mollis sapien ut, ultricies enim. Aliquam condimentum ipsum mi, molestie efficitur dolor consectetur ac. Suspendisse neque magna, bibendum sit amet aliquet at, fermentum et nibh. Suspendisse eu urna mollis, volutpat risus vel, pharetra eros. Vivamus rhoncus elit et pulvinar consequat. Phasellus ornare velit eget quam scelerisque, at tincidunt est varius. Maecenas eu hendrerit arcu.


Here is a code block:

{% highlight ruby %}
require "gem"

string = "base16"
symbol = :base16
fixnum = 0
float  = 0.00
array  = Array.new
array  = ['chris', 85]
hash   = {"test" => "test"}
regexp = /[abc]/

# This is a comment
class Person

    attr_accessor :name

    def initialize(attributes = {})
        @name = attributes[:name]
    end

    def self.greet
        "hello"
    end
end

person1 = Person.new(:name => "Chris")
print Person::greet, " ", person1.name, "\n"
puts "another #{Person::greet} #{person1.name}"
{% endhighlight %}


Aliquam erat volutpat. Fusce ac facilisis `nisl`, sed sodales ante. Etiam `leo lorem`, vehicula vitae nunc vitae, posuere varius odio. Morbi congue nisi ac bibendum condimentum. Praesent sagittis tellus ut dui molestie, sodales varius sapien pellentesque. Nullam sed finibus arcu. Mauris nec enim ac arcu suscipit tincidunt. Donec tristique ex a tellus ornare scelerisque. Aliquam eu enim iaculis, mollis sapien ut, ultricies enim. Aliquam condimentum ipsum mi, molestie efficitur dolor consectetur ac. Suspendisse neque magna, bibendum sit amet aliquet at, fermentum et nibh. Suspendisse eu urna mollis, volutpat risus vel, pharetra eros. Vivamus rhoncus elit et pulvinar consequat. Phasellus ornare velit eget quam scelerisque, at tincidunt est varius. Maecenas eu hendrerit arcu.


# Heading 1

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6


---


# Fake Title

Quisque malesuada *laoreet rhoncus*. Nunc velit justo, eleifend eget malesuada ut, dapibus ac nisl. Praesent mi nunc, pulvinar eget venenatis et, congue ac dolor. Mauris mi nibh, **sodales et accumsan vitae**, lacinia id erat. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Maecenas sit amet vulputate eros. Mauris maximus egestas quam eu ullamcorper. Proin turpis felis, pharetra nec lectus et, ullamcorper pellentesque sem.


## This Is A Subheading

Quisque malesuada *laoreet rhoncus*. Nunc velit justo, eleifend eget malesuada ut, dapibus ac nisl. Praesent mi nunc, pulvinar eget venenatis et, congue ac dolor. Mauris mi nibh, **sodales et accumsan vitae**, lacinia id erat. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Maecenas sit amet vulputate eros. Mauris maximus egestas quam eu ullamcorper. Proin turpis felis, pharetra nec lectus et, ullamcorper pellentesque sem.


### Another Nested Subheading

Quisque malesuada *laoreet rhoncus*. Nunc velit justo, eleifend eget malesuada ut, dapibus ac nisl. Praesent mi nunc, pulvinar eget venenatis et, congue ac dolor. Mauris mi nibh, **sodales et accumsan vitae**, lacinia id erat. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Maecenas sit amet vulputate eros. Mauris maximus egestas quam eu ullamcorper. Proin turpis felis, pharetra nec lectus et, ullamcorper pellentesque sem.


## Back To A Subheading

Quisque malesuada *laoreet rhoncus*. Nunc velit justo, eleifend eget malesuada ut, dapibus ac nisl. Praesent mi nunc, pulvinar eget venenatis et, congue ac dolor. Mauris mi nibh, **sodales et accumsan vitae**, lacinia id erat. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Maecenas sit amet vulputate eros. Mauris maximus egestas quam eu ullamcorper. Proin turpis felis, pharetra nec lectus et, ullamcorper pellentesque sem.
