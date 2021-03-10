# Masayuki Anekawa - FullStackEngineerChallenge
# Assumptions I made from requirements

## Security
This system seems to be used by internal employees, so it is realistic scenario that this system is not open to Internet and rarely attacked.
Plus, my strength is centered to frontend user interface and experience, not perfect security of product.

So I omitted security carefulness to some extent. It includes password reset, cross-site scripting, multi-factor authentication and even password authentication for employees.

The only password needed to run this webapp is for admin authentication.


## Subjects

Each subject has some attributes and can trigger some actions.

### Admin
An admin has:
* 1 unique id
* 1 password, stored as hash
* 1 unique email address

Admin can:
* add/remove/update/view employees
* add/update/view performance reviews
* assign 2 employees as reviewee and reviewer to create new performance review

### Employee
An employee has:
* 1 unique id
* 1 unique email address
* 1 name
* many feedback assignments as reviewer
* many feedback assignments as reviewee

Employees can:
* fill in and submit reviews that another employee requested to them

Employees can not:
* request another employee to write their performance review
* change their id, name or email
* deny requested performance review
* cancel review request once they sent to another employee
* update review content once they submitted


## Objects
Objects are owned by subjects, and sometimes are passed, updated and deleted by them.

### Review
A review has:
* 1 employee as reviewee
* 1 employee as reviewer
* 1 multiline text as content
* 1 date indicating when it's assigned to reviewer

## Scale
* Number of employees is 2 ~ 1000(1e3).
* Number of reviews for 1 employee as reviewer is 0 ~ 10.
* Number of reviews for 1 employee as reviewee is 0 ~ 10.
* Total number of reviewer is up to ~ 100000(1e5).



# Technology and design choices

## Environment: Docker
The portability of app environments matters, especially when it comes to transporting app code and running on others' machine.

## Language: Typescript
I selected Typescript, because of strong support of static types during development. Thanks to it, we can concentrate on writing effective code as long as the compiler not showing errors.

## Framework: nodejs + Fastify + Next.js + PostgreSQL + Prisma
Chose node.js for the base of the webapp.
Other frameworks on node can be curated easily using frourio.js.


# Areas of my strengths

## Technical Communication
- Wrote plain yet precise documentation of products before actual coding. In my opinion it's one of the most important skills of software engineers, because every product's requirement, schedule and budget is changed more frequently than most of engineers imagine.

## User Interface
* extremely intuitive and fast responsible interaction

## Functionality
- Hit all requirements
- Added even more user-friendly functions

## Speed
- According to audit from Chrome web tool, it's super fast.