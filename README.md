# Tea Subscription
![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

#### Overview
This app creates a Rails API for a tea subscription service. There are 3 endpoints: to get a list of subscriptions, to create a subscription and to cancel a subscription

#### Schema
![tea_subscription_db](https://user-images.githubusercontent.com/83252572/190515705-cc3ec9eb-8bd5-488d-83c0-d0af32e9abc1.png)

#### Local Set Up
- `fork` then `git clone` this repository
- `cd tea_subsription` into the root directory
- `bundle install` to install dependencies
- `rails db:{create,migrate,seed}`
- `rails s` to start your server on `localhost:3000`

#### Framework
<p>
  <img src="https://img.shields.io/badge/Ruby%20On%20Rails-b81818.svg?&style=flat&logo=rubyonrails&logoColor=white" />
</p>

#### Languages
<p>
  <img src="https://img.shields.io/badge/Ruby-CC0000.svg?&style=flaste&logo=ruby&logoColor=white" />
</p>

#### Tools
<p>
  <img src="https://img.shields.io/badge/Atom-66595C.svg?&style=flaste&logo=atom&logoColor=white" />  
  <img src="https://img.shields.io/badge/Git-F05032.svg?&style=flaste&logo=git&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub-181717.svg?&style=flaste&logo=github&logoColor=white" />
  </br>
  <img src="https://img.shields.io/badge/Postman-FF6E4F.svg?&style=flat&logo=postman&logoColor=white" />
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1.svg?&style=flaste&logo=postgresql&logoColor=white" />
</p>

#### Gems
<p>
  <img src="https://img.shields.io/badge/rspec--rails-b81818.svg?&style=flaste&logo=rubygems&logoColor=white" />
  <img src="https://img.shields.io/badge/pry-b81818.svg?&style=flaste&logo=rubygems&logoColor=white" />  
  <img src="https://img.shields.io/badge/simplecov-b81818.svg?&style=flaste&logo=rubygems&logoColor=white" />  
</p>

#### Development Principles
<p>
  <img src="https://img.shields.io/badge/OOP-b81818.svg?&style=flaste&logo=OOP&logoColor=white" />
  <img src="https://img.shields.io/badge/TDD-b87818.svg?&style=flaste&logo=TDD&logoColor=white" />
  <img src="https://img.shields.io/badge/MVC-b8b018.svg?&style=flaste&logo=MVC&logoColor=white" />
  <img src="https://img.shields.io/badge/REST-33b818.svg?&style=flaste&logo=REST&logoColor=white" />  
</p>

## Endpoints

1)   #### Request
`GET /api/v1/customers/1/subscriptions`
#### Response
```json
{
    "data": [
        {
            "id": "1",
            "type": "subscription",
            "attributes": {
                "customer_id": 1,
                "tea_id": 1,
                "title": "My Dongding Subscription",
                "price": 5.75,
                "status": "active",
                "frequency": "monthly"
            }
        },
        {
            "id": "2",
            "type": "subscription",
            "attributes": {
                "customer_id": 1,
                "tea_id": 2,
                "title": "My Shincha Subscription",
                "price": 6.9,
                "status": "canceled",
                "frequency": "annually"
            }
        }
    ]
}
```

2)    #### Request
`POST /api/v1/customers/1/subscriptions`
##### Request Body
```json
    {
      "customer_id": 1,
      "tea_id": 1,
      "title": "tea.title",
      "price": 6.9,
      "status": "active",
      "frequency": "annually"
    }
```
#### Response
```json
{
    "data": {
        "id": "14",
        "type": "subscription",
        "attributes": {
            "customer_id": 1,
            "tea_id": 1,
            "title": "tea.title",
            "price": 6.9,
            "status": "active",
            "frequency": "annually"
        }
    }
}
```

3)  #### Request
`PATCH /api/v1/customers/1/subscriptions/1`
##### Request Body
```json
   { 
   "status": "canceled" 
   }
```
#### Response
```json
{
    "data": {
        "id": "4",
        "type": "subscription",
        "attributes": {
            "customer_id": 1,
            "tea_id": 1,
            "title": "tea.title",
            "price": 6.9,
            "status": "canceled",
            "frequency": "annually"
        }
    }
}
```

#### Errors Handling

 #### Request
`PATCH /api/v1/customers/1/subscriptions/1`

##### Request Body
```json
   { 
   "status": "transferred" 
   }
```

#### Response
```
{
    "error": "invalid status"
}
```

#### Simplecov Test Coverage

![Screen Shot 2022-09-15 at 6 09 36 PM](https://user-images.githubusercontent.com/83252572/190530007-3323e223-a83c-4e58-86e6-086d5672c84c.png)

#### Postman Link

[](https://www.getpostman.com/collections/4121fc243381bef29818)


