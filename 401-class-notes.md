# 401 Class Notes

```Python
class ForceUser:
  def attacking(self):
    return f'{self.name} is Force attacking!'
  
  def getting_hit(self):
    return f'{self.name} is being attacked!'

  @classmethod
  def get_count(cls):
    return JediMaster.count + SithLord.count



class SithLord(ForceUser):
  count = 0
  def __init__ (self, name='Random Lord'):
    self.name = 'Random Lord'
    SithLord.count += 1

# these are never going to change
# Not passing in any variables, no self, this is a method only on the class
  @staticmethod
  def get_code():
    return 'Peace is a lie, there is only PASSION.'

  @classmethod
  def get_count(cls):
    return cls.count




class JediMaster(ForceUser):
  count = 0
  def __init__ (self, name='Random Master'):
    self.name = 'Random Master'
    JediMaster.count += 1


# This is meant to only be user facing.
  def __str__(self):
    return f'{self.name} is in the House!'

# This is meant only for developers. Trying to determine how this instance is created. Not user facing.
  def __repr__(self):
    return f'JediMaster({self.name})'
    pint(player.__repr__{})

  
  def attacking(self):
    return f'{self.name} is Good Force attacking!'

  @staticmethod
  def get_code():
    return 'There is no emotion, there is PEACE.'


 @classmethod
  def get_count(cls):
    return cls.count

# The name of the file when called using dunder is the name of the file. Here the name is main. 
  if __name__ == '__main__':
    player = JediMaster()
    player = JediMaster('Luke)
    print(player.__repr__())


```

Fixtures - typically go at the end of your testing code

```Python
@pytest.fixture
def luke():
  return JediMaster("Luke")

@pytest.fixture
def vader():
  return JediMaster("Darth Vader)

@pytest.fixture
def counter_reset():
  JediMaster.count = 0
  SithLord.count = 0
  ```


Tests

Make it pass, then make sure it works for DRY code

```Python
from starwars.starwars import JediMaster, SithLord, ForceUser
def test_jed_master_name_luke_new(luke):
  actual = luke.name
  expected = 'Luke'
  assert actual == expected
  ```

```Python
def test_jedi_master_attacking(luke):
  actual = luke.attacking()
  expected = 'Luke is Force attacking!'
  assert actual == expected
  ```

```Python
def test_jedi_master_attacking():
  player = JediMaster('Obi)
  actual = player.attacking()
  expected = 'Obi is Force attacking!'
  assert actual == expected
  ```


```Python
def test_jedi_master_attacking():
  player = JediMaster()
  actual = luke.attacking()
  expected = 'Luke is Force attacking!'
  assert actual == expected
  ```

```Python
def test_sith_lord