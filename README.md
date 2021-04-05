# Basic or Essentials (OOP)

### Coupling
 One class depends of another class called coupling.
 Ex : 
 ```
 class User
{
    public function store($fromData)
    {
        $form = new From();
        $form->post($fromData);
    }
}

class From
{
    protected $post;

    public function post($post)
    {
        $this->post = $_POST[$post];
    }

    public function val($type, $field)
    {
        $vlidate = new Validate();
        return $vlidate->{$type}($field);
    }
}

class Validate
{
    public function number($p)
    {
        if ( ! ctype_alnum($p));
        return false;
    }

    public function __call($n)
    {
        throw new Exception("This method does not exist: ". $n);
    }
}

  ```
  Here, From and Validate are the couple class cause From class is depends on Validate class.
  
  ### Encapsulation
  
  In a class, there will be access modifiers but the access modifiers will not be public but private so only this class can access them.
It won't be possible to change any value of those access modifiers. However, there will be getter and setter methods to get or
set the value of those access modifiers.

Ex:
  ```
class Account
{
    private $balance;

    public function setBalance($balance)
    {
        if (is_int($balance)) {
            return $this->balance = $balance;
        }
        return false;
    }

    public function getBalance()
    {
        return $this->balance;
    }
}
```

  ### Abstraction
  abstraction Abstraction is to reduce complexity .ding unnecessary details of a class.
  
  Ex:
```
class MailService
{
    public function sendEmail ($email, $body)
    {
        //code...
    }

    private function connect($data)
    {
        //Check connection with the connection data
        //code ....
    }

    private function authenticate($credentials)
    {
        //Check connection with the credentials
        //code ....
    }

    private function disconnect()
    {
        //Disconnect mail server
        //code ....
    }
}
```
Here, only sendMail method is public so it can be accessed from other scope but other methods are hidden (private). However, we can not create any instance of an
abstract class only we can extend it.

### Inheritance
Inheritance is the abilities to re-use code. We can use it by extends key word where we can use common methods.
Ex :
```
class UIControl
{
    public function enable()
    {
        //Code...
    }
}

class UseClass
{
    public function useTextBox()
    {
        $textBox = new TextBox();
        $textBox->enable();
    }
}
```

### Polymorphism
The ability of an object to take many forms. We use interface for the class signature and we implement in many different classes with different forms.

```
interface TaxCalculator
{
    public function taxCalculate();
}

class Tax2020 implements TaxCalculator
{

    public function taxCalculate()
    {
        return 100;
    }
}

class Tax2021 implements TaxCalculator
{
    public function taxCalculate()
    {
        return 155;
    }
}
```

  
