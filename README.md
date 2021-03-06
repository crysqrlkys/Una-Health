# Una-Health

### Reasoning
#### Why django
Django is a web framework in python. I chose it because of:  

1. Admin Interface (To provide CRUD operations)
2. Testing Framework
3. ORM
4. Reusable django apps and packages 

#### Frameworks and packages
1. DRF - fast and convenient way to start your API

### How to run:
`docker-compose up`  
`docker-compose exec app python manage.py migrate`  

### Api
POST `api/upload/` - import levels info from csv file  
GET `api/v1/levels/<id>` - retrieve level info by id  
GET `api/v1/levels/?user_id=<user_id>` - get list of levels, if called with `user_id` filters by `user_id`

### Notes 
Use **Filters** button to apply filters (`sort`, `device timestamp`, `user_id`)  
For pagination use query params (`limit`, `offset`)

### Trade-offs
- I would use `Celery` to execute `import task` as a background process.
- I would provide more in depth documentation about filters, pagination and sorts.
- I would use permissions, auth, user model to provide secure access to endpoint.
- I would set up fixtures to easier reuse objects across tests.
- I would follow git flow to split project into `features` and name branches according to story purpose.