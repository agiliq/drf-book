# Book Name: Building APIs with Django and Django Rest Framework

*Building APIs to power your mobile and web apps using Django, Django rest framework and other modern tools.*

### Expectation from readers

* Familiarity with Django in general. Should know how ORM, Models and Views work.
* Familiarity with function based views as well as class based views.
* No familiarity with REST required
* No familiarity with Django rest framework required


## Chapter 1: [Why use apis]

GOAL of this chapter: Why should I bother with apis. Can't I work without apis.

* Why and when apis is needed
	* Why apis needed for mobile apps and not needed for web apps
	* eg: Zomato web app might not require any api. But Zomato mobile app would require it. Explain this example in detail.

* A brief discussion about the app we will be developing. We will be developing an app which tracks expenses by users of a company, associates expenses with users, allows categorising expenses etc.


## Chapter 2: [Expenses app without REST framework]

GOAL: Demonstrate the pain involved in writing api endpoints without a REST library.

We will build an app without using any thing other than Django. Plain HttpResponse, json.dumps and validations in views.

### Requirement from this app

* Most basic app. Only one model called Expense.
* We need ability to create and view expenses from the mobile. So we need REST endpoints.
* Without authentication and authorization
* Simple things like GET and POST

### Demonstrate the effort required to do these without DRF

* Using model_to_dict and content_type
* Explicit conversions to json
* Demonstrate how painful it is without DRF
* No logically appropriate place for validation

## Chapter 3: [Expenses app with DRF]

GOAL: Explain usefulness of DRF. DRF makes things simpler, maintainable and organised.

[Step 1]
* Use JSON handling capabilities of DRF, api_view decorator and a serializer.
* Method based views

[Step 2]
* Only extend from APIView. Doesn't use mixins or generic views here.

## Chapter 4: [Basic expense app]

GOAL: Explain ModelSerializer, APIView, Request, Response, status codes

* Basic app: No authentication, no authorization, no relation to other model.
* Any unauthenticated user can see all the expenses
* Any unauthenticated user can create an expense
* Any unauthenticated user can do PUT on expense
* Any unauthenticated user can do PATCH on expense. Explaining PATCH vs PUT
* Consuming API with Postman

## Chapter 5: [Authentication and Authorization]

GOAL: Providing security to api endpoints

* Authentication vs Authorization meaning and example.
* Only logged in users can view all the expenses.
* All api calls behind authentication
* Since all api calls behind authentication, so add it in settings.
* Keep login view without authentication.
* Only superusers can POST.

## Chapter 6: [Mixins and Generic Views]

GOAL: Achieving more with less line of code.

* Extend from mixins.
* Overriding mixin methods
* Extend from generic views
* Overriding generic view methods

## Chapter 7: [Handling relationships and more authorization]

* Add FK from Expense to User
* Associate logged in user with expense
* Not all attributes of model need to be passed. eg: User doesn't need to be pased explicitly in POST data.

[More authorization]
* A user can only see detail of his expense and can update or delete his expense.

## Creating ExpenseCategory and Expense in the same api call

* Create associated object in the same api call
* Api to create many to many relationship
* Get all expenses within a category.
* Keeping some fields read_only.

## Chapter 8: [Viewsets and routers]

* Demonstrate how viewsets and routers handle frequently used operations and further decrease lines of code.

## Chapter 9: [More]

* Using ListSerializer
* Creating multiple instances in a single api call
* Serializer in detail. Overriding serializer.save(), serializer.validate() etc to achieve extra validations.
* Running model validations before serializer save
* Filtering queryset in GET call
* Only get few fields instead of all fields
