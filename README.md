# MPIntegration
Custom Web Checkout integration using MercadoPago APIs.
Static frontend + Java Spark framework, which uses Jetty container.
Checkout types: Redirect, widget, iframe, custom checkout

### Routes
/ -> Landing site where different custom payments can be found

/api/preference -> JSON request, creates a preference. 

/api/payment  -> JSON request, creates a payment. 

### Sample request
```
{
	"email":"john@domain.com",
	"amount":100,
	"installments":1,
	"paymentMethodId":"master",
	"token":"b5ecde7e36fa605c3e1a1b3cf524197d",
	"paymentTypeId":"credit_card"
}
```


#### Navigate to webapp
http://localhost:8080/

#### Files description
pref1.html =  static html used for custom checkout
payflow.jade = template used for landing which shows multiple products and checkouts
responserenderer.jade = template used to show Payments API response after payment is done.
main.js = contains js functions to process custom checkout payment (card tokenization, sdkhandling in general). This also contains preferenceId

#### Routes
RoutesHandler.java = Defines controller's routes

POST */api/preference* = Preference creation
POST */api/payment* = Payment processing

