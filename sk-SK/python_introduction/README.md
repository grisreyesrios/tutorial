{% set warning_icon = '<span class="glyphicon glyphicon-exclamation-sign" style="color: red;" aria-hidden="true" data-toggle="tooltip" title="An error is expected when you run this command!" ></span>' %}

# Úvod do jazyka Python

> Časť tejto kapitoly je založená na tutoriáli Geek Girls Carrots (https://github.com/ggcarrots/django-carrots).

Poďme napísať nejaký kód!

## Python prompt

> Pre čitateľov doma: Táto kapitola je spracovaná v [Python Basics: Integers, Strings, Lists, Variables and Errors](https://www.youtube.com/watch?v=MO63L4s-20U) videu.

Aby sme mohli začať s Pythonom, musíte otvoriť *príkazový riadok* (angl. command line) na svojom počítači. Už by ste mali vedieť ako sa to robí -- naučili ste sa to v [ Úvode do príkazového riadku](../intro_to_command_line/README.md).

Ak ste hotoví, pokračujte s inštrukciami nižšie.

Chceme otvoriť Python konzolu, takže napíšte `python` na Windowse alebo `python3` na Mac OS alebo Linux a stlačte `enter`.

{% filename %}command-line{% endfilename %}

    $ python3
    Python 3.6.1 (...)
    Type "help", "copyright", "credits" or "license" for more information.
    >>>
    

## Váš prvý príkaz v Pythone!

Po spustení príkazu Python sa prompt zmenil na `>>>`. Pre nás to znamená, že odteraz by sme mali písať príkazy iba v jazyku Python. Nemusíte písať `>>>` - Python to urobí pre Vás.

Ak by ste chceli kedykoľvek ukončiť konzolu Pythonu, len napíšte `exit()` alebo môžete použiť aj skratku `Ctrl + Z` vo Windowse alebo `Ctrl + D` pre Mac/Linux. Potom už nebudete vidieť toto: `>>>`.

Zatiaľ nechceme opustiť Python konzolu. Chceme sa o nej dozvedieť viac. Začnime tým, že skúsime matematiku, napr. ` 2 + 3 `a stlač `enter`.

{% filename %}command-line{% endfilename %}

```python
>>> 2 + 3
5
```

Super! Vidíte ako vyskočilo riešenie? Python vie počítať! Môžete skúsiť aj ďalšie príkazy, ako:

- `4 * 5`
- `5 - 1`
- `40 / 2`

Aby sme vypočítali mocninu, povedzme 2 na tretiu, zadáme: {% filename %}command-line{% endfilename %}

```python
>>> 2 ** 3
8
```

Pobavte sa s tým trošku, potom sa vráťte späť . :)

Ako vidíte, Python je dobrá kalkulačka. A ak ste zvedaví, čo všetko ešte vie…

## Reťazce ("Stringy")

Čo tak tvoje meno? Napíš svoje meno v úvodzovkách:

{% filename %}command-line{% endfilename %}

```python
>>> "Ola" 
"Ola"
```

Práve si vytvorila svoj prvý reťazec! Je postupnosť znakov, ktoré môžu byť spracované počítačom. Reťazec musí vždy začínať a končíť s rovnakým znakom. Sú to jednoduché (`'`) alebo dvojité (`"`) úvodzovky (nie je medzi nimi žiadny rozdiel!). Úvodzovky naznačujú, že to čo je medzi nimi je reťazec (string).

Reťazce možno spájať dohromady. Skús toto:

{% filename %}command-line{% endfilename %}

```python
>>> "Ahoj" + "Ola" 
'Ahoj Ola'
```

You can also multiply strings with a number:

{% filename %}command-line{% endfilename %}

```python
>>> "Ola" * 3 
'OlaOlaOla'
```

If you need to put an apostrophe inside your string, you have two ways to do it.

Using double quotes:

{% filename %}command-line{% endfilename %}

```python
>>> "Runnin' down the hill" 
"Runnin' down the hill"
```

or escaping the apostrophe with a backslash (``):

{% filename %}command-line{% endfilename %}

```python
>>> 'Runnin\' down the hill' 
"Runnin' down the hill"
```

Nice, huh? To see your name in uppercase letters, simply type:

{% filename %}command-line{% endfilename %}

```python
>>> "Ola".upper() 
'OLA'
```

You just used the `upper` **method** on your string! A method (like `upper()`) is a sequence of instructions that Python has to perform on a given object (`"Ola"`) once you call it.

If you want to know the number of letters contained in your name, there is a **function** for that too!

{% filename %}command-line{% endfilename %}

```python
>>> len("Ola") 
3
```

Wonder why sometimes you call functions with a `.` at the end of a string (like `"Ola".upper()`) and sometimes you first call a function and place the string in parentheses? Well, in some cases, functions belong to objects, like `upper()`, which can only be performed on strings. In this case, we call the function a **method**. Other times, functions don't belong to anything specific and can be used on different types of objects, just like `len()`. That's why we're giving `"Ola"` as a parameter to the `len` function.

### Zhrnutie

OK, enough of strings. So far you've learned about:

- **prompt** - píšeme príkazy (kód) do Python promptu, z čoho dostaneme výsledky zase v jazyku Python
- **čísla a reťazce** - v Pythone sú čísla použité pre počítanie a reťazce pre textové objekty
- **operátory** - ako `+` alebo `*`, z daných hodnôt vyrobia novú hodnotu
- **funkcie** - napr. `upper()` alebo `len()`, vykonávajú činnosti na objektoch.

These are the basics of every programming language you learn. Ready for something harder? We bet you are!

## Chyby

Let's try something new. Can we get the length of a number the same way we could find out the length of our name? Type in `len(304023)` and hit `enter`:

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> len(304023)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: object of type 'int' has no len()
```

We got our first error! The {{ warning_icon }} icon is our way of giving you a heads up that the code you are about to run won't work as expected. Making mistakes (even intentional ones) are an important part of learning!

It says that objects of type "int" (integers, whole numbers) have no length. So what can we do now? Maybe we can write our number as a string? Strings have a length, right?

{% filename %}command-line{% endfilename %}

```python
>>> len(str(304023))
6
```

It worked! We used the `str` function inside of the `len` function. `str()` converts everything to strings.

- Funkcia `str` prevedie (konvertuje) všetko na **reťazce** (angl. string)
- Funkcia `int` prevedie všetko na **int** (celé čísla)

> Dôležité: je možné konvertovať čísla na reťazce, ale opačne sa to nedá vždy - inak čo by bolo napr. `int('hello')`?

## Premenné

An important concept in programming is variables. A variable is nothing more than a name for something so you can use it later. Programmers use these variables to store data, make their code more readable and so they don't have to keep remembering what things are.

Let's say we want to create a new variable called `name`:

{% filename %}command-line{% endfilename %}

```python
>>> meno = "Ola"
```

We type name equals Ola.

As you've noticed, your program didn't return anything like it did before. So how do we know that the variable actually exists? Simply enter `name` and hit `enter`:

{% filename %}command-line{% endfilename %}

```python
>>> meno
'Ola'
```

Yippee! Your first variable! :) You can always change what it refers to:

{% filename %}command-line{% endfilename %}

```python
>>> meno = "Sonja"
>>> meno
'Sonja'
```

You can use it in functions too:

{% filename %}command-line{% endfilename %}

```python
>>> len(meno)
5
```

Awesome, right? Of course, variables can be anything – numbers too! Try this:

{% filename %}command-line{% endfilename %}

```python
>>> a = 4
>>> b = 6
>>> a * b
24
```

But what if we used the wrong name? Can you guess what would happen? Let's try!

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> mesto = "Tokyo"
>>> mseto
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'mseto' is not defined
```

An error! As you can see, Python has different types of errors and this one is called a **NameError**. Python will give you this error if you try to use a variable that hasn't been defined yet. If you encounter this error later, check your code to see if you've mistyped any names.

Play with this for a while and see what you can do!

## Funkcia print

Try this:

{% filename %}command-line{% endfilename %}

```python
>>> meno = 'Maria'
>>> meno
'Maria'
>>> print(meno)
Maria
```

When you just type `name`, the Python interpreter responds with the string *representation* of the variable 'name', which is the letters M-a-r-i-a, surrounded by single quotes, ''. When you say `print(name)`, Python will "print" the contents of the variable to the screen, without the quotes, which is neater.

As we'll see later, `print()` is also useful when we want to print things from inside functions, or when we want to print things on multiple lines.

## Zoznamy

Beside strings and integers, Python has all sorts of different types of objects. Now we're going to introduce one called **list**. Lists are exactly what you think they are: objects which are lists of other objects. :)

Go ahead and create a list:

{% filename %}command-line{% endfilename %}

```python
>>> []
[]
```

Yes, this list is empty. Not very useful, right? Let's create a list of lottery numbers. We don't want to repeat ourselves all the time, so we will put it in a variable, too:

{% filename %}command-line{% endfilename %}

```python
>>> loteria = [3, 42, 12, 19, 30, 59]
```

All right, we have a list! What can we do with it? Let's see how many lottery numbers there are in a list. Do you have any idea which function you should use for that? You know this already!

{% filename %}command-line{% endfilename %}

```python
>>> len(loteria)
6
```

Yes! `len()` can give you a number of objects in a list. Handy, right? Maybe we will sort it now:

{% filename %}command-line{% endfilename %}

```python
>>> loteria.sort()
```

This doesn't return anything, it just changed the order in which the numbers appear in the list. Let's print it out again and see what happened:

{% filename %}command-line{% endfilename %}

```python
>>> print(loteria)
[3, 12, 19, 30, 42, 59]
```

As you can see, the numbers in your list are now sorted from the lowest to highest value. Congrats!

Maybe we want to reverse that order? Let's do that!

{% filename %}command-line{% endfilename %}

```python
>>> loteria.reverse()
>>> print(loteria)
[59, 42, 30, 19, 12, 3]
```

If you want to add something to your list, you can do this by typing this command:

{% filename %}command-line{% endfilename %}

```python
>>> loteria.append(199)
>>> print(loteria)
[59, 42, 30, 19, 12, 3, 199]
```

If you want to show only the first number, you can do this by using **indexes**. An index is the number that says where in a list an item occurs. Programmers prefer to start counting at 0, so the first object in your list is at index 0, the next one is at 1, and so on. Try this:

{% filename %}command-line{% endfilename %}

```python
>>> print(loteria[0])
59
>>> print(loteria[1])
42
```

As you can see, you can access different objects in your list by using the list's name and the object's index inside of square brackets.

To delete something from your list you will need to use **indexes** as we learned above and the `pop()` method. Let's try an example and reinforce what we learned previously; we will be deleting the first number of our list.

{% filename %}command-line{% endfilename %}

```python
>>> print(lottery)
[59, 42, 30, 19, 12, 3, 199]
>>> print(lottery[0])
59
>>> lottery.pop(0)
59
>>> print(lottery)
[42, 30, 19, 12, 3, 199]
```

That worked like a charm!

For extra fun, try some other indexes: 6, 7, 1000, -1, -6 or -1000. See if you can predict the result before trying the command. Do the results make sense?

You can find a list of all available list methods in this chapter of the Python documentation: https://docs.python.org/3/tutorial/datastructures.html

## Slovníky

> Pre čitateľov doma: Táto kapitola je spracovaná v [Python Basics: Dictionaries](https://www.youtube.com/watch?v=ZX1CVvZLE6c) videu.

A dictionary is similar to a list, but you access values by looking up a key instead of a numeric index. A key can be any string or number. The syntax to define an empty dictionary is:

{% filename %}command-line{% endfilename %}

```python
>>> {}
{}
```

This shows that you just created an empty dictionary. Hurray!

Now, try writing the following command (try substituting your own information, too):

{% filename %}command-line{% endfilename %}

```python
>>> ucastnicka = {'meno': 'Ola', 'krajina': 'Slovensko', 'oblubene_cisla': [7, 42, 92]}
```

With this command, you just created a variable named `participant` with three key–value pairs:

- Kľúč `meno` odkazuje na hodnotu `"Ola"` (objekt typu `reťazec/string`),
- `krajina` odkazuje na `"Slovensko"` (ďalší `reťazec`),
- a `oblubene_cisla` smeruje na `[7, 42, 92]` (`zoznam` s tromi číslami).

You can check the content of individual keys with this syntax:

{% filename %}command-line{% endfilename %}

```python
>>> print(ucastnicka['meno'])
Ola
```

See, it's similar to a list. But you don't need to remember the index – just the name.

What happens if we ask Python the value of a key that doesn't exist? Can you guess? Let's try it and see!

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> ucastnicka['vek']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'vek'
```

Look, another error! This one is a **KeyError**. Python is helpful and tells you that the key `'age'` doesn't exist in this dictionary.

When should you use a dictionary or a list? Well, that's a good point to ponder. Just have a solution in mind before looking at the answer in the next line.

- Potrebuješ zoradenú postupnosť položiek? Vyber si zoznam (list).
- Potrebuješ priraďovať hodnoty kľúčovým slovám, aby si si ich mohla efektívne (podľa kľúča) neskôr vyhľadať? Použi slovník (dictionary).

Dictionaries, like lists, are *mutable*, meaning that they can be changed after they are created. You can add new key–value pairs to a dictionary after it is created, like this:

{% filename %}command-line{% endfilename %}

```python
>>> ucastnicka['oblubeny_jazyk'] = 'Python'
```

Like lists, using the `len()` method on the dictionaries returns the number of key–value pairs in the dictionary. Go ahead and type in this command:

{% filename %}command-line{% endfilename %}

```python
>>> len(ucastnicka)
4
```

I hope it makes sense up to now. :) Ready for some more fun with dictionaries? Read on for some amazing things.

You can use the `pop()` method to delete an item in the dictionary. Say, if you want to delete the entry corresponding to the key `'favorite_numbers'`, just type in the following command:

{% filename %}command-line{% endfilename %}

```python
>>> participant.pop('favorite_numbers')
[7, 42, 92]
>>> participant
{'country': 'Poland', 'favorite_language': 'Python', 'name': 'Ola'}
```

As you can see from the output, the key–value pair corresponding to the 'favorite_numbers' key has been deleted.

As well as this, you can also change a value associated with an already-created key in the dictionary. Type this:

{% filename %}command-line{% endfilename %}

```python
>>> ucastnicka['krajina'] = 'Nemecko'
>>> ucastnicka
{'krajina': 'Nemecko', 'oblubeny_jazyk': 'Python', 'meno': 'Ola'}
```

As you can see, the value of the key `'country'` has been altered from `'Poland'` to `'Germany'`. :) Exciting? Hurrah! You just learned another amazing thing.

### Zhrnutie

Awesome! You know a lot about programming now. In this last part you learned about:

- **chyby** (angl. error) - teraz už vieš ako čítať a rozumieť chybám, ktoré sa zobrazia, ak Python nerozumie príkazu, ktorý mu zadáš
- **premenné** - názvy objektov, ktoré ti uľahčujú písanie kódu a robia tiež kód zrozumiteľnejším
- **zoznamy** (angl. list) - zoznam objektov uložených v určitom poradí
- **slovníky** (angl. dictionary) - objekty uložené v pároch kľúč-hodnota

Excited for the next part? :)

## Porovnávanie vecí

> Pre čitateľov doma: Táto kapitola je spracovaná v [Python Basics: Comparisons](https://www.youtube.com/watch?v=7bzxqIKYgf4) videu.

A big part of programming involves comparing things. What's the easiest thing to compare? Numbers, of course. Let's see how that works:

{% filename %}command-line{% endfilename %}

```python
>>> 5 > 2
True
>>> 3 < 1
False
>>> 5 > 2 * 2
True
>>> 1 == 1
True
>>> 5 != 2
True
```

We gave Python some numbers to compare. As you can see, not only can Python compare numbers, but it can also compare method results. Nice, huh?

Do you wonder why we put two equal signs `==` next to each other to compare if numbers are equal? We use a single `=` for assigning values to variables. You always, **always** need to put two of them – `==` – if you want to check if things are equal to each other. We can also state that things are unequal to each other. For that, we use the symbol `!=`, as shown in the example above.

Give Python two more tasks:

{% filename %}command-line{% endfilename %}

```python
>>> 6 >= 12 / 2
True
>>> 3 <= 2
False
```

We've seen `>` and `<`, but what do `>=` and `<=` mean? Read them like this:

- x `>` y znamená: x je väčšie ako y
- x `<` y znamená: x je menšie ako y
- x `<=` y znamená: x je menšie alebo sa rovná y
- x `> =` y znamená: x je väčšie alebo sa rovná y

Awesome! Wanna do one more? Try this:

{% filename %}command-line{% endfilename %}

```python
>>> 6 > 2 and 2 < 3
True
>>> 3 > 2 and 2 < 1
False
>>> 3 > 2 or 2 < 1
True
```

You can give Python as many numbers to compare as you want, and it will give you an answer! Pretty smart, right?

- **and** - ak použiješ operátor `and`, obidve porovnávané veci musia byť pravdivé (True), aby príkaz bol pravdivý (True)
- **or** - ak použiješ operátor `or`, stačí aby jedna z porovnávaných vecí bola pravdivá, aby bol celý príkaz pravda (True)

Have you heard of the expression "comparing apples to oranges"? Let's try the Python equivalent:

{% filename %}{{ warning_icon }} command-line{% endfilename %}

```python
>>> 1 > 'django'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: '>' not supported between instances of 'int' and 'str'
```

Here you see that just like in the expression, Python is not able to compare a number (`int`) and a string (`str`). Instead, it shows a **TypeError** and tells us the two types can't be compared together.

## Logické hodnoty (Boolean)

Incidentally, you just learned about a new type of object in Python. It's called **Boolean**.

There are only two Boolean objects:

- True
- False

But for Python to understand this, you need to always write it as 'True' (first letter uppercase, with the rest of the letters lowercased). **true, TRUE, and tRUE won't work – only True is correct.** (The same applies to 'False' as well, of course.)

Booleans can be variables, too! See here:

{% filename %}command-line{% endfilename %}

```python
>>> a = True
>>> a
True
```

You can also do it this way:

{% filename %}command-line{% endfilename %}

```python
>>> a = 2 > 5
>>> a
False
```

Practice and have fun with Booleans by trying to run the following commands:

- `True and True`
- `False and True`
- `True or 1 == 1`
- `1 != 2`

Congrats! Booleans are one of the coolest features in programming, and you just learned how to use them!

# Ulož to!

> Pre čitateľov doma: Táto kapitola je spracovaná v [Python Basics: Saving files and "If" statement](https://www.youtube.com/watch?v=dOAg6QVAxyk) videu.

So far we've been writing all our python code in the interpreter, which limits us to entering one line of code at a time. Normal programs are saved in files and executed by our programming language **interpreter** or **compiler**. So far we've been running our programs one line at a time in the Python **interpreter**. We're going to need more than one line of code for the next few tasks, so we'll quickly need to:

- Ukončiť interpreter Pythonu
- Otvoriť si zvolený editor kódu
- Uložiť v ňom nejaký kód do nového pythonského súboru
- Spustiť ho!

To exit from the Python interpreter that we've been using, simply type the `exit()` function

{% filename %}command-line{% endfilename %}

```python
>>> exit()
$
```

This will put you back into the command prompt.

Earlier, we picked out a code editor from the [code editor](../code_editor/README.md) section. We'll need to open the editor now and write some code into a new file:

{% filename %}editor{% endfilename %}

```python
print('Hello, Django girls!')
```

Obviously, you're a pretty seasoned Python developer now, so feel free to write some code that you've learned today.

Now we need to save the file and give it a descriptive name. Let's call the file **python_intro.py** and save it to your desktop. We can name the file anything we want, but the important part here is to make sure the file ends in **.py**. The **.py** extension tells our operating system that this is a **Python executable file** and Python can run it.

> **Poznámka** Všimni si jednu z najúžasnejších vecí editorov kódu: farby! V pythonskej konzole bolo všetko napísané jednou farbou, teraz však vidíš, že funkcia `print` je napísaná inou farbou ako reťazec. Toto sa nazýva "zvýraznenie syntaxe" a pri programovaní je to fakt užitočná vec. Farba výrazov ti môže pomôcť, ak máš neuzavretý reťazec či preklep v názve špeciálnych slov (ako napríklad `def` vo funkcii, ktorú uvidíme neskôr). Toto je jedným z dôvodov, prečo používame editor kódu. :)

With the file saved, it's time to run it! Using the skills you've learned in the command line section, use the terminal to **change directories** to the desktop.

<!--sec data-title="Change directory: OS X" data-id="python_OSX"
data-collapse=true ces-->

On a Mac, the command will look something like this:

{% filename %}command-line{% endfilename %}

    $ cd ~/Desktop
    

<!--endsec-->

<!--sec data-title="Change directory: Linux" data-id="python_linux"
data-collapse=true ces-->

On Linux, it will be like this (the word "Desktop" might be translated to your local language):

{% filename %}command-line{% endfilename %}

    $ cd ~/Desktop
    

<!--endsec-->

<!--sec data-title="Change directory: Windows Command Prompt" data-id="python_windows" data-collapse=true ces-->

On Windows Command Prompt, it will be like this:

{% filename %}command-line{% endfilename %}

    > cd %HomePath%\Desktop
    

<!--endsec-->

<!--sec data-title="Change directory: Windows Powershell" data-id="python_windowsPSH" data-collapse=true ces-->

And on Windows Powershell, it will be like this:

{% filename %}command-line{% endfilename %}

    > cd $Home\Desktop
    

<!--endsec-->

If you get stuck, just ask for help.

Now use Python to execute the code in the file like this:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Hello, Django girls!
    

Note: on Windows 'python3' is not recognized as a command. Instead, use 'python' to execute the file:

{% filename %}command-line{% endfilename %}

```python
> python python_intro.py
```

Alright! You just ran your first Python program that was saved to a file. Feel awesome?

You can now move on to an essential tool in programming:

## If … elif … else

Lots of things in code should be executed only when given conditions are met. That's why Python has something called **if statements**.

Replace the code in your **python_intro.py** file with this:

{% filename %}python_intro.py{% endfilename %}

```python
if 3 > 2:
```

If we were to save and run this, we'd see an error like this:

{% filename %}{{ warning_icon }} command-line{% endfilename %}

    $ python3 python_intro.py
    File "python_intro.py", line 2
             ^
    SyntaxError: unexpected EOF while parsing
    

Python expects us to give further instructions to it which are executed if the condition `3 > 2` turns out to be true (or `True` for that matter). Let’s try to make Python print “It works!”. Change your code in your **python_intro.py** file to this:

{% filename %}python_intro.py{% endfilename %}

```python
if 3 > 2:
    print('It works!')
```

Notice how we've indented the next line of code by 4 spaces? We need to do this so Python knows what code to run if the result is true. You can do one space, but nearly all Python programmers do 4 to make things look neat. A single `tab` will also count as 4 spaces.

Save it and give it another run:

{% filename %}command-line{% endfilename %}

```python
$ python3 python_intro.py
Funguje to!
```

Note: Remember that on Windows, 'python3' is not recognized as a command. From now on, replace 'python3' with 'python' to execute the file.

### Čo ak podmienka nie je pravdivá?

In previous examples, code was executed only when the conditions were True. But Python also has `elif` and `else` statements:

{% filename %}python_intro.py{% endfilename %}

```python
if 5 > 2:
    print('5 is indeed greater than 2')
else:
    print('5 is not greater than 2')
```

When this is run it will print out:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    5 je naozaj viac ako 2
    

If 2 were a greater number than 5, then the second command would be executed. Let's see how `elif` works:

{% filename %}python_intro.py{% endfilename %}

```python
name = 'Sonja'
if name == 'Ola':
    print('Ahoj Ola!')
elif name == 'Sonja':
    print('Ahoj Sonja!')
else:
    print('Ahoj neznama!')
```

and executed:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Ahoj Sonja!
    

See what happened there? `elif` lets you add extra conditions that run if the previous conditions fail.

You can add as many `elif` statements as you like after your initial `if` statement. For example:

{% filename %}python_intro.py{% endfilename %}

```python
volume = 57
if volume < 20:
    print("It's kinda quiet.")
elif 20 <= volume < 40:
    print("It's nice for background music")
elif 40 <= volume < 60:
    print("Perfect, I can hear all the details")
elif 60 <= volume < 80:
    print("Nice for parties")
elif 80 <= volume < 100:
    print("A bit loud!")
else:
    print("My ears are hurting! :(")
```

Python runs through each test in sequence and prints:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Super, pocujem vsetky detaily
    

## Komentáre

Comments are lines beginning with `#`. You can write whatever you want after the `#` and Python will ignore it. Comments can make your code easier for other people to understand.

Let's see how that looks:

{% filename %}python_intro.py{% endfilename %}

```python
# Change the volume if it's too loud or too quiet
if volume < 20 or volume > 80:
    volume = 50
    print("That's better!")
```

You don't need to write a comment for every line of code, but they are useful for explaining why your code is doing something, or providing a summary when it's doing something complex.

### Zhrnutie

In the last few exercises you learned about:

- **porovnávať veci** - v Pythone môžeš porovnávať veci pomocou znamienok `>`, `>=`, `==`, `<=`, `<` a operátorov `and`, `or`
- **Booleovské/logické premenné** - typ objektu, ktorý môže mať len jednu z dvoch hodnôt: `True` (pravda) alebo `False` (nepravda)
- **Ukladať súbory** - ukladanie kódu v súboroch, takže môžete spúšťať väčšie programy.
- **if... elif... else** - príkazy, ktoré ti umožňujú spustiť kód, iba ak sú splnené určité podmienky.
- **comments** - lines that Python won't run which let you document your code

Time for the last part of this chapter!

## Tvoje vlastné funkcie!

> Pre čitateľov doma: Táto kapitola je spracovaná v [Python Basics: Functions](https://www.youtube.com/watch?v=5owr-6suOl0) videu.

Remember functions like `len()` that you can execute in Python? Well, good news – you will learn how to write your own functions now!

A function is a sequence of instructions that Python should execute. Each function in Python starts with the keyword `def`, is given a name, and can have some parameters. Let's give it a go. Replace the code in **python_intro.py** with the following:

{% filename %}python_intro.py{% endfilename %}

```python
def hi():
    print('Ahoj!')
    print('Ako sa mas?')

hi()
```

Okay, our first function is ready!

You may wonder why we've written the name of the function at the bottom of the file. This is because Python reads the file and executes it from top to bottom. So in order to use our function, we have to re-write it at the bottom.

Let's run this now and see what happens:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Ahoj!
    Ako sa mas?
    

Note: if it didn't work, don't panic! The output will help you to figure why:

- Ak sa ti zjaví `NameError`, to znamená, že si niečo chybne napísala, takže by si mala overiť, že si použila rovnaké meno, keď si vytvárala pomocou `def hi()` a keď si ju zavolala pomocou `hi()`.
- Ak sa ti zjaví `IndentationError`, uisti sa, že oba `print` riadky, majú rovnaký počet medzier od začiatku riadku: python vyžaduje aby všetky riadky boli pedatne zarovnané.
- Ak nevidíš žiaden výstup, tak sa pozri či posledné `hi()` *nie je* odsadené - ak je, ten riadok sa stal súčasťou funkcie a nikdy nedojde k jeho spusteniu.

Let's build our first function with parameters. We will use the previous example – a function that says 'hi' to the person running it – with a name:

{% filename %}python_intro.py{% endfilename %}

```python
def hi(name):
```

As you can see, we now gave our function a parameter that we called `name`:

{% filename %}python_intro.py{% endfilename %}

```python
def hi(meno):
    if meno == 'Ola':
        print('Ahoj Ola!')
    elif meno == 'Sonja':
        print('Ahoj Sonja!')
    else:
        print('Ahoj neznama!')

hi()
```

Remember: The `print` function is indented four spaces within the `if` statement. This is because the function runs when the condition is met. Let's see how it works now:

{% filename %}{{ warning_icon }} command-line{% endfilename %}

    $ python3 python_intro.py
    Traceback (most recent call last):
    File "python_intro.py", line 10, in <module>
      hi()
    TypeError: hi() missing 1 required positional argument: 'meno'
    

Oops, an error. Luckily, Python gives us a pretty useful error message. It tells us that the function `hi()` (the one we defined) has one required argument (called `name`) and that we forgot to pass it when calling the function. Let's fix it at the bottom of the file:

{% filename %}python_intro.py{% endfilename %}

```python
hi("Ola")
```

And run it again:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Ahoj Ola!
    

And if we change the name?

{% filename %}python_intro.py{% endfilename %}

```python
hi("Sonja")
```

And run it:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Ahoj Sonja!
    

Now, what do you think will happen if you write another name in there? (Not Ola or Sonja.) Give it a try and see if you're right. It should print out this:

{% filename %}command-line{% endfilename %}

    Ahoj neznáma!
    

This is awesome, right? This way you don't have to repeat yourself every time you want to change the name of the person the function is supposed to greet. And that's exactly why we need functions – you never want to repeat your code!

Let's do something smarter – there are more names than two, and writing a condition for each would be hard, right?

{% filename %}python_intro.py{% endfilename %}

```python
def hi(meno):
    print('Ahoj ' + meno + '!')

hi("Katka")
```

Let's call the code now:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Ahoj Katka!
    

Congratulations! You just learned how to write functions! :)

## Cykly

> Pre čitateľov doma: Táto kapitola je spracovaná v [Python Basics: For Loop](https://www.youtube.com/watch?v=aEA6Rc86HF0) videu.

This is the last part already. That was quick, right? :)

Programmers don't like to repeat themselves. Programming is all about automating things, so we don't want to greet every person by their name manually, right? That's where loops come in handy.

Still remember lists? Let's do a list of girls:

{% filename %}python_intro.py{% endfilename %}

```python
dievcata = ['Katka', 'Monika', 'Zuzka', 'Ola', 'Ty']
```

We want to greet all of them by their name. We have the `hi` function to do that, so let's use it in a loop:

{% filename %}python_intro.py{% endfilename %}

```python
for meno in dievcata:
```

The `for` statement behaves similarly to the `if` statement; code below both of these need to be indented four spaces.

Here is the full code that will be in the file:

{% filename %}python_intro.py{% endfilename %}

```python
def hi(meno):
    print('Ahoj ' + meno + '!')

dievcata = ['Katka', 'Monika', 'Zuzka', 'Ola', 'Ty']
for meno in dievcata:
    hi(meno)
    print('Dalsie dievca')
```

And when we run it:

{% filename %}command-line{% endfilename %}

    $ python3 python_intro.py
    Ahoj Katka!
    Dalsie dievca
    Ahoj Monika!
    Dalsie dievca
    Ahoj Zuzka!
    Dalsie dievca
    Ahoj Ola!
    Dalsie dievca
    Ahoj Ty!
    Dalsie dievca
    

As you can see, everything you put inside a `for` statement with an indent will be repeated for every element of the list `girls`.

You can also use `for` on numbers using the `range` function:

{% filename %}python_intro.py{% endfilename %}

```python
for i in range(1, 6):
    print(i)
```

Which would print:

{% filename %}command-line{% endfilename %}

    1
    2
    3
    4
    5
    

`range` is a function that creates a list of numbers following one after the other (these numbers are provided by you as parameters).

Note that the second of these two numbers is not included in the list that is output by Python (meaning `range(1, 6)` counts from 1 to 5, but does not include the number 6). That is because "range" is half-open, and by that we mean it includes the first value, but not the last.

## Zhrnutie

That's it. **You totally rock!** This was a tricky chapter, so you should feel proud of yourself. We're definitely proud of you for making it this far!

For official and full python tutorial visit https://docs.python.org/3/tutorial/. This will give you a more thorough and complete study of the language. Cheers :)

You might want to briefly do something else – stretch, walk around for a bit, rest your eyes – before going on to the next chapter. :)

![Cupcake](images/cupcake.png)