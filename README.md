# Basic or Essentials

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
