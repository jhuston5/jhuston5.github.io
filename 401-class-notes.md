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

Python
def test_sith_lord




# Game of Greed AKA Farkle

# Score a winning total of 10000 points with 6 6-sided dice

# Python Standard Library includes Counter and .most_common()

Counter can take a list and turn it into a dictionary with a count of each instance of a list item. Most common returns the item that is most often referenced.

Reference website: https://pymotw.com/3/

Steps to creating our Game of Greed
poetry new game-of-greed
mv README.rst README.md
poetry add --dev black flake8

move version_1 into tests
poetry shell
pytest

# Parametrizing Tests
# Decorator function to skip a test until you are ready to run it
@pytest.mark.skip('Pending')

create a new banker.py file
create a Banker Class and set it to pass.

create game_logic.py file
create a GameLogic Class and set it to pass
Add a static method called roll_dice()
```Python
def roll_dice(rolled_dice):
  return (3,)
  ```
If you are sending in a tuple, make sure to add in the comma so python knows it is a tuple.


# Print to Input
import builtins

_print = builtins.print
_input = builtins.input

builtins.print = _input
builtins.input = _print

Can control what's going on in the terminal temporarily.
Might need to override a dunder method or a dunder str with our own specific method.
'
def alter():
  builtins.print = _input
  builtins.input = _print

def alter_back():
  builtins.print = _print
  builtins.input = _input

if __name__ == '__main__':
  alter()

  alter_back()

```Python
from random import randint

def default_roll():
  return (randint(1,6), randint(1, 6))

def play_dice(roller=default_roller):
  while True:
    print('Enter r to roll or q to quit')
    choice = input('> )

    if choice == 'q':
      print('OK, bye')
      break

    else:
      roll = roller()
      roller_str = ''
      for num in roll:
        roller_str += str(num) + " "
      print(f'*** {roller_str}***')

if __name__ == '__main__':
  def mock_roller():
    # return (4, 3)
    return rolls.pop(0) if rolls else default_roller()

  play_dice(mock_riller)
```


Another Way to Do the Zip List Function

Stacks and Queues
Even though we can traverse pythonically, we won't

How do we access something in the middle of a stack?
ID the node you want to remove. Pop nodes off and put into a new stack until you hit the specified Node, then push the nodes from the new stack back onto the original stack.