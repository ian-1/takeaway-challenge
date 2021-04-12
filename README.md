Takeaway
==================
```
                            _________
              r==           |       |
           _  //            |  M.A. |   ))))
          |_)//(''''':      |       |
            //  \_____:_____.-------D     )))))
           //   | ===  |   /        \
       .:'//.   \ \=|   \ /  .:'':./    )))))
      :' // ':   \ \ ''..'--:'-.. ':
      '. '' .'    \:.....:--'.-'' .'
       ':..:'                ':..:'

```

**Takeaway** models and controls the flow of planes at an airport. The planes can land and take off provided that there is spare capacity at the airport and that the weather is not stormy. The weather is set using a random number generator. 

This program was built  using **TDD** as part of [**Makers Academy Coding Bootcamp's**]([http://makers.tech](http://makers.tech/)) Airport Challenge (from which this repository was forked on 2021-April-04).

In my tests I use **doubles** so one class spec is not testing against another class. I also use **stubs** to override random weather and ensure consistent test behaviour.

## Installation

This program is designed to be run from [irb](https://en.wikipedia.org/wiki/Interactive_Ruby_Shell) (or a similar interactive Ruby environment) and requires **Ruby version 2.6.5** - which will give you access to irb. If you are unsure if you have Ruby installed, or need help seeing the version you are using [codecademy](https://www.codecademy.com) provide this useful guide to [**setup Ruby**](https://www.codecademy.com/articles/ruby-setup). 

## Usage

```bash
# open irb
irb -r ./lib/airport -r ./lib/plane
# create a
irb(main):001 > 

```

Design
-----

### User Stories

Below are the user stories as worked out in collaboration with the client (these were provided in the challenge):

```
As a customer
So that I can check if I want to order something
I would like to see a list of dishes with prices

As a customer
So that I can order the meal I want
I would like to be able to select some number of several available dishes

As a customer
So that I can verify that my order is correct
I would like to check that the total I have been given matches the sum of the various dishes in my order

As a customer
So that I am reassured that my order will be delivered on time
I would like to receive a text such as "Thank you! Your order was placed and will be delivered before 18:52" after I have ordered
```

### Domain Model

| **Class**                           | Dish                               |
| ----------------------------------- | ---------------------------------- |
| **Properties (instance variables)** | name, price                        |
| **Actions (methods)**               |                                    |
|                                     |                                    |
| **Class**                           | **Order**                          |
| **Properties (instance variables)** | Dish_list, bill, delivery          |
| **Actions (methods)**               | add, remove, see_dishes, confirm   |
|                                     |                                    |
| **Class**                           | **Bill**                           |
| **Properties (instance variables)** | total                              |
| **Actions (methods)**               | Add, remove, matches_sum           |
|                                     |                                    |
| **Class**                           | **Delivery**                       |
| **Properties (instance variables)** | text, delivery_time                |
| **Actions (methods)**               | Send_text, calculate_delivery_time |
|                                     |                                    |
| **Class**                           | **TextMessage**                    |
| **Properties (instance variables)** | Text_content                       |
| **Actions (methods)**               | send                               |

## Running Tests

```bash
# To run tests
rspec
```

## Development / Contributing

This project was created as a learning exercise as part of the Makers Academy Coding Bootcamp. 

No further development is planned on this project and pull requests are not sought (sorry🤗).

















* Hints on functionality to implement:
  * Ensure you have a list of dishes with prices
  * The text should state that the order was placed successfully and that it will be delivered 1 hour from now, e.g. "Thank you! Your order was placed and will be delivered before 18:52".
  * The text sending functionality should be implemented using Twilio API. You'll need to register for it. It’s free.
  * Use the twilio-ruby gem to access the API
  * Use the Gemfile to manage your gems
  * Make sure that your Takeaway is thoroughly tested and that you use mocks and/or stubs, as necessary to not to send texts when your tests are run
  * However, if your Takeaway is loaded into IRB and the order is placed, the text should actually be sent
  * Note that you can only send texts in the same country as you have your account. I.e. if you have a UK account you can only send to UK numbers.
* Advanced! (have a go if you're feeling adventurous):
  * Implement the ability to place orders via text message.
* A free account on Twilio will only allow you to send texts to "verified" numbers. Use your mobile phone number, don't worry about the customer's mobile phone.

> :warning: **WARNING:** think twice before you push your **mobile number** or **Twilio API Key** to a public space like GitHub :eyes:
>
> :key: Now is a great time to think about security and how you can keep your private information secret. You might want to explore environment variables.


