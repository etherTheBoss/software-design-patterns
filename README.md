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
