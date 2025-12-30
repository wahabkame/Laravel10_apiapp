# Laravel10_apiapp
## Laravel10 Project ( API building &amp; RESTful API )

 **in the beginning, Make Laravel-10 project ::**
  ``` Laravel
  composer create-project laravel/laravel:^10.0 apiapp
  ``` 

1- First , write in bash to start API- passport :
``` Laravel
    composer require laravel/passport
    php artisun migrate
    php artisun passport:install
``` 

you have to modify some code : 

2- in folder (config) , file (app.php) :
  in provider section : 
  
  ``` Laravel
  Laravel\Passport\PassportServiceProvider::class
  ``` 

3- in folder (models) , file (user.php) :
   change "sanctum" to "Passport"
   ``` Laravel
  Use laravel\Passport\HasApiTokens
  ``` 

4-in folder (providers) , file (AuthServiceProvider.php) :
  write  in the beginning of the page :
  ``` Laravel
  use laravel\Passport\Passport
  ``` 
``` Laravel
then modify :
 Protected $policies=[ 'App\Models=>' ']
 ``` 

then wite in boot function :
``` Laravel
 Public Function boot [  $this->registerpolicies(); ]
 ```

--------------------------------------------------
## then we have to make model & migration
``` Laravel
  php artisun make:model  -
 ```
then we need to write inputs in migration 
then we neet to write it in models
``` Laravel
 protected $fillable['']
 ```
  and then we neet to wirte :
``` Laravel
 php artisun migrate
 ```

### donot forget to modify PHPmyadmin
--------------------------------------------------
## and then we to make token +Salt

  ``` Laravel
 ->createToken ('salt')->accessToken;
return response ()->json ([])
 ```

--------------------------------------------------
## some syntax have to write :
 ``` Laravel
 use validator
::fails()
::find()
::make()
::create()
::errors()
->save()
->delete()
Route::post()
Route::middleware(['auth:api'])
bcrypt($request->password);
 ```

--------------------------------------------------
## to understand the structure of the projects:
 1- we make two models ( user , products )
    user have three inputs ( name , password , email )
    products have two input ( name , details)

 2- we make two controllers : 
    productscontroller , authusercontroller.

 3- we make CRUD (Store, index , Edit , Update)
    we use Resources    

