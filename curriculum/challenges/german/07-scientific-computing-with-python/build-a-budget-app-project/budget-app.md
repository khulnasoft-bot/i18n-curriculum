---
id: 5e44413e903586ffb414c94e
title: Build a Budget App Project
challengeType: 23
forumTopicId: 462361
dashedName: build-a-budget-app-project
---

# --description--

Complete the `Category` class. Es sollte in der Lage sein, Objekte basierend auf verschiedenen Haushaltskategorien, wie *food*, *clothing*, und *entertainment* zu instanziieren. Wenn Objekte erstellt werden, werden sie im Namen der Kategorie übergeben. Die Klasse sollte eine Instanzvariable namens `ledger` (Hauptbuch) haben, die eine Liste ist. Die Klasse sollte ebenfalls folgende Methoden enthalten:

- Eine `deposit`-Methode, die einen Betrag und eine Beschreibung annimmt. Wenn keine Beschreibung angegeben wird, sollte standardmäßig ein leerer String ausgegeben werden. The method should append an object to the ledger list in the form of `{'amount': amount, 'description': description}`.
- Eine `withdraw`-Methode, die der `deposit`-Methode ähnelt, bei der der übergebene Betrag jedoch als negative Zahl im Hauptbuch gespeichert werden soll. Wenn nicht genügend Mittel zur Verfügung stehen, sollte nichts zum Hauptbuch hinzugefügt werden. Diese Methode sollte `True` zurückgeben, wenn die Auszahlung stattgefunden hat, ansonsten sollte sie `False` ausgeben.
- Eine `get_balance`-Methode, die den aktuellen Saldo der Kategorie des Budgets auf der Grundlage der erfolgten Einzahlungen und Abhebungen zurückgibt.
- Eine `transfer`-Methode, die einen Betrag und eine andere Budgetkategorie als Argument akzeptiert. The method should add a withdrawal with the amount and the description 'Transfer to [Destination Budget Category]'. The method should then add a deposit to the other budget category with the amount and the description 'Transfer from [Source Budget Category]'. Wenn nicht genügend Mittel vorhanden sind, sollte in keinem der beiden Hauptbücher etwas hinzugefügt werden. Diese Methode sollte `True` zurückgeben, wenn die Auszahlung bereits stattgefunden hat und ansonsten `False` ausgeben.
- Eine `check_funds`-Methode, die einen Betrag als Argument akzeptiert. Es wird `False` zurückgegeben, wenn der Betrag größer ist als der Saldo der Budgetkategorie, ansonsten wird `True` zurückgegeben. Die Methode sollte sowohl von der `withdraw`-Methode und der `transfer`-Methode verwendet werden.

Wenn das Budgetobjekt ausgegeben wird, sollte es folgendes anzeigen:

- Eine Titelzeile mit 30 Zeichen, in der der Name der Kategorie in einer Zeile mit `*`-Zeichen zentriert ist.
- Eine Liste der Elemente im Hauptbuch. Jede Zeile sollte die Beschreibung und den Betrag anzeigen. Die ersten 23 Zeichen der Beschreibung sollten angezeigt werden, dann der Betrag. Der Betrag sollte rechts ausgerichtet sein, zwei Dezimalstellen enthalten und maximal 7 Zeichen anzeigen.
- Eine Zeile, die die Summe der Kategorie anzeigt.

Hier ist ein Anwendungsbeispiel:

```py
food = Category('Food')
food.deposit(1000, 'deposit')
food.withdraw(10.15, 'groceries')
food.withdraw(15.89, 'restaurant and more food for dessert')
clothing = Category('Clothing')
food.transfer(50, clothing)
print(food)
```

Und hier ist ein Beispiel für die Ausgabe:

```bash
*************Food*************
initial deposit        1000.00
groceries               -10.15
restaurant and more foo -15.89
Transfer to Clothing    -50.00
Total: 923.96
```

Neben der `Category`-Klasse, erstelle eine Funktion (außerhalb der Klasse) namens `create_spend_chart`, die eine Liste der Kategorien als Argument verwendet. Es sollte einen String zurückgeben, das ein Balkendiagramm ist.

Das Diagramm sollte den Prozentsatz jeder Kategorie anzeigen, die an die Funktion übergeben wurde. The percentage spent should be calculated only with withdrawals and not with deposits, and it should be the percentage of the amount spent for each category to the total spent for all categories. Unten auf der linken Seite des Diagramms sollten die Labels 0 - 100 stehen. The 'bars' in the bar chart should be made out of the 'o' character. Die Höhe jedes Balken sollte auf die nächstgelegene 10 abgerundet werden. Die horizontale Linie unter den Balken sollte zwei Leerzeichen hinter der Endleiste haben. Jeder Kategoriename sollte vertikal unterhalb des Balkens angegeben werden. There should be a title at the top that says 'Percentage spent by category'.

Die Funktion wird mit bis zu vier Kategorien getestet.

Schau dir die Beispielausgabe unten sehr genau an und stelle sicher, dass der Abstand der Ausgabe genau dem Beispiel entspricht.

```bash
Percentage spent by category
100|          
 90|          
 80|          
 70|          
 60| o        
 50| o        
 40| o        
 30| o        
 20| o  o     
 10| o  o  o  
  0| o  o  o  
    ----------
     F  C  A  
     o  l  u  
     o  o  t  
     d  t  o  
        h     
        i     
        n     
        g     
```

Note: open the browser console with F12 to see a more verbose output of the tests.

# --hints--

The `deposit` method should create a specific object in the ledger instance variable.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")

    def test_deposit(self):
        self.food.deposit(900, "deposit")
        actual = self.food.ledger[0]
        expected = {"amount": 900, "description": "deposit"}
        self.assertEqual(actual, expected, 'Expected "deposit" method to create a specific object in the ledger instance variable.')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

Der Aufruf der `deposit`-Methode ohne Beschreibung sollte eine leere Beschreibung erzeugen.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")

    def test_deposit_no_description(self):
        self.food.deposit(45.56)
        actual = self.food.ledger[0]
        expected = {"amount": 45.56, "description": ""}
        self.assertEqual(actual, expected, 'Expected calling "deposit" method with no description to create a blank description.')        
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The `withdraw` method should create a specific object in the `ledger` instance variable.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")

    def test_withdraw(self):
        self.food.deposit(900, "deposit")
        self.food.withdraw(45.67, "milk, cereal, eggs, bacon, bread")
        actual = self.food.ledger[1]
        expected = {"amount": -45.67, "description": "milk, cereal, eggs, bacon, bread"}
        self.assertEqual(actual, expected, 'Expected "withdraw" method to create a specific object in the ledger instance variable.')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

Der Aufruf der `withdraw`-Methode ohne Beschreibung sollte eine leere Beschreibung erzeugen.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")

    def test_withdraw_no_description(self):
        self.food.deposit(900, "deposit")
        good_withdraw = self.food.withdraw(45.67)
        actual = self.food.ledger[1]
        expected = {"amount": -45.67, "description": ""}
        self.assertEqual(actual, expected, 'Expected "withdraw" method with no description to create a blank description.')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The `withdraw` method should return `True` if the withdrawal took place.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")

    def test_withdraw_no_description(self):
        self.food.deposit(900, "deposit")
        good_withdraw = self.food.withdraw(45.67)
        self.assertEqual(good_withdraw, True, 'Expected "withdraw" method to return "True".')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

Calling `food.deposit(900, 'deposit')` and `food.withdraw(45.67, 'milk, cereal, eggs, bacon, bread')` should return a balance of `854.33`.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")

    def test_get_balance(self):
        self.food.deposit(900, "deposit")
        self.food.withdraw(45.67, "milk, cereal, eggs, bacon, bread")
        actual = self.food.get_balance()
        expected = 854.33
        self.assertEqual(actual, expected, 'Expected balance to be 854.33')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

Calling the `transfer` method on a category object should create a specific ledger item in that category object.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")
        self.entertainment = budget.Category("Entertainment")

    def test_transfer(self):
        self.food.deposit(900, "deposit")
        self.food.withdraw(45.67, "milk, cereal, eggs, bacon, bread")
        transfer_amount = 20
        good_transfer = self.food.transfer(transfer_amount, self.entertainment)
        actual = self.food.ledger[2]
        expected = {"amount": -transfer_amount, "description": "Transfer to Entertainment"}
        self.assertEqual(actual, expected, 'Expected "transfer" method to create a specific ledger item in food object.')
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The `transfer` method should return `True` if the transfer took place.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")
        self.entertainment = budget.Category("Entertainment")

    def test_transfer(self):
        self.food.deposit(900, "deposit")
        self.food.withdraw(45.67, "milk, cereal, eggs, bacon, bread")
        transfer_amount = 20 
        good_transfer = self.food.transfer(transfer_amount, self.entertainment)        
        self.assertEqual(good_transfer, True, 'Expected "transfer" method to return "True".')        
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

Calling `transfer` on a category object should reduce the balance in the category object.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")
        self.entertainment = budget.Category("Entertainment")

    def test_transfer(self):
        self.food.deposit(900, "deposit")
        self.food.withdraw(45.67, "milk, cereal, eggs, bacon, bread")
        transfer_amount = 20
        food_balance_before = self.food.get_balance()        
        good_transfer = self.food.transfer(transfer_amount, self.entertainment)
        food_balance_after = self.food.get_balance()
        self.assertEqual(food_balance_before - food_balance_after, transfer_amount, 'Expected "transfer" method to reduce balance in food object.')
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The `transfer` method should increase the balance of the category object passed as its argument.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")
        self.entertainment = budget.Category("Entertainment")

    def test_transfer(self):
        self.food.deposit(900, "deposit")
        self.food.withdraw(45.67, "milk, cereal, eggs, bacon, bread")
        transfer_amount = 20        
        entertainment_balance_before = self.entertainment.get_balance()
        good_transfer = self.food.transfer(transfer_amount, self.entertainment)        
        entertainment_balance_after = self.entertainment.get_balance()        
        self.assertEqual(entertainment_balance_after - entertainment_balance_before, transfer_amount, 'Expected "transfer" method to increase balance in entertainment object.')  
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The `transfer` method should create a specific ledger item in the category object passed as its argument.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")
        self.entertainment = budget.Category("Entertainment")

    def test_transfer(self):
        self.food.deposit(900, "deposit")
        self.food.withdraw(45.67, "milk, cereal, eggs, bacon, bread")
        transfer_amount = 20        
        good_transfer = self.food.transfer(transfer_amount, self.entertainment)
        actual = self.entertainment.ledger[0]
        expected = {"amount": transfer_amount, "description": "Transfer from Food"}
        self.assertEqual(actual, expected, 'Expected "transfer" method to create a specific ledger item in entertainment object.')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The `check_funds` method should return `False` if the amount passed to the method is greater than the category balance.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")

    def test_check_funds(self):
        self.food.deposit(10, "deposit")
        actual = self.food.check_funds(20)
        expected = False
        self.assertEqual(actual, expected, 'Expected "check_funds" method to be False')   
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The `check_funds` method should return `True` if the amount passed to the method is not greater than the category balance.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")

    def test_check_funds(self):
        self.food.deposit(10, "deposit")
        actual = self.food.check_funds(10)
        expected = True
        self.assertEqual(actual, expected, 'Expected "check_funds" method to be True')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The `withdraw` method should return `False` if the withdrawal didn't take place.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")

    def test_withdraw_no_funds(self):
        self.food.deposit(100, "deposit")
        good_withdraw = self.food.withdraw(100.10)
        self.assertEqual(good_withdraw, False, 'Expected "withdraw" method to return "False".')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The `transfer` method should return `False` if the transfer didn't take place.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")
        self.entertainment = budget.Category("Entertainment")

    def test_transfer_no_funds(self):
        self.food.deposit(100, "deposit")
        good_transfer = self.food.transfer(200, self.entertainment)
        self.assertEqual(good_transfer, False, 'Expected "transfer" method to return "False".')    
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

Printing a `Category` instance should give a different string representation of the object.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")
        self.entertainment = budget.Category("Entertainment")

    def test_to_string(self):
        self.food.deposit(900, "deposit")
        self.food.withdraw(45.67, "milk, cereal, eggs, bacon, bread")
        self.food.transfer(20, self.entertainment)
        actual = str(self.food)
        expected = "*************Food*************\\ndeposit                 900.00\\nmilk, cereal, eggs, bac -45.67\\nTransfer to Entertainme -20.00\\nTotal: 834.33"
        self.assertEqual(actual, expected, 'Expected different string representation of object.')
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module

reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`
    const out = runPython(testCode);
    assert(out);
  }
})
```

Title at the top of `create_spend_chart` chart should say `Percentage spent by category`.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")

    def test_create_spend_chart(self):
        self.food.deposit(900, "deposit")
        self.food.withdraw(105.55)
        chart = budget.create_spend_chart([self.food])
        expected = "Percentage spent by category"
        self.assertEqual(chart.split("\\n")[0], expected, "Chart should have correct title.")
`);

    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

`create_spend_chart` chart should have correct percentages down the left side.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")

    def test_create_spend_chart(self):
        self.food.deposit(900, "deposit")
        self.food.withdraw(105.55)
        chart = budget.create_spend_chart([self.food])
        percentages = ["100|", " 90|", " 80|", " 70|", " 60|", " 50|", " 40|", " 30|", " 20|", " 10|", "  0|"]
        for line, percent in zip(chart.split("\\n")[1:], percentages):
           self.assertTrue(line.startswith(percent), "Chart correct percentages in the vertical axis.")
`);

    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

The height of each bar on the `create_spend_chart` chart should be rounded down to the nearest 10.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")
        self.entertainment = budget.Category("Entertainment")
        self.business = budget.Category("Business")
        self.food.deposit(900, "deposit")
        self.entertainment.deposit(900, "deposit")
        self.business.deposit(900, "deposit")
        self.food.withdraw(78)
        self.entertainment.withdraw(22)
        self.business.withdraw(8)

    def test_create_spend_chart_rounding_close_to_upper_and_lower_ten(self):
        chart_lines = budget.create_spend_chart([self.food, self.entertainment]).split("\\n")[1:12]
        result_lines = '''100|
 90|
 80|
 70| o
 60| o
 50| o
 40| o
 30| o
 20| o  o
 10| o  o
  0| o  o'''.split("\\n")

        self.assertEqual(len(chart_lines), len(result_lines), "Lines missing in chart.")
        for actual, expected in zip(chart_lines, result_lines):
            self.assertTrue(actual.startswith(expected), "Expected different rounding of bars.")


    def test_create_spend_chart_rounding_single_digit(self):
        chart_lines = budget.create_spend_chart([self.business, self.food, self.entertainment]).split("\\n")[1:12]
        result_lines = '''100|
 90|
 80|
 70|    o
 60|    o
 50|    o
 40|    o
 30|    o
 20|    o  o
 10|    o  o
  0| o  o  o'''.split("\\n")

        self.assertEqual(len(chart_lines), len(result_lines), "Lines missing in chart.")
        for actual, expected in zip(chart_lines, result_lines):
            self.assertTrue(actual.startswith(expected), "Expected different rounding of bars.")
`);

    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

Each line in `create_spend_chart` chart should have the same length. Bars for different categories should be separated by two spaces, with additional two spaces after the final bar.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")
        self.entertainment = budget.Category("Entertainment")
        self.business = budget.Category("Business")
        self.food.deposit(900, "deposit")
        self.entertainment.deposit(900, "deposit")
        self.business.deposit(900, "deposit")
        self.food.withdraw(78)
        self.entertainment.withdraw(22)
        self.business.withdraw(8)


    def test_create_spend_chart_chart_lines_have_expected_length(self):
        chart_categories = [[self.food, self.entertainment], [self.business, self.food, self.entertainment]]

        expected_lengths = [len(line) for line in ["  0| o  o  ", "  0| o  o  o  "]]
        expected_chart_lines = 11

        for categories, expected_length in zip(chart_categories, expected_lengths):
            chart_lines = budget.create_spend_chart(categories).split("\\n")[1:12]

            self.assertEqual(len(chart_lines), expected_chart_lines, "Lines missing in chart.")
            for actual in chart_lines:
                self.assertEqual(len(actual), expected_length, "Expected different length of the chart line. Check that all spacing is exact.")
`);
    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

`create_spend_chart` should correctly show horizontal line below the bars. Using three `-` characters for each category, and in total going two characters past the final bar.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")
        self.entertainment = budget.Category("Entertainment")
        self.business = budget.Category("Business")
        self.food.deposit(900, "deposit")
        self.entertainment.deposit(900, "deposit")
        self.business.deposit(900, "deposit")
        self.food.withdraw(105.55)
        self.entertainment.withdraw(33.40)
        self.business.withdraw(10.99)

    def test_create_spend_chart_horizontal_bar(self):
        chart_categories = [[self.business], [self.business, self.food], [self.business, self.food, self.entertainment]]
        horizontal_lines = ["    ----", "    -------", "    ----------"]
        for categories, expected in zip(chart_categories, horizontal_lines):
            actual = budget.create_spend_chart(categories).split("\\n")[12]
            self.assertEqual(actual, expected, "Expected different horizontal bar. Check that all spacing is exact.")
`);

    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

`create_spend_chart` chart should not have new line character at the end.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")
        self.entertainment = budget.Category("Entertainment")
        self.business = budget.Category("Business")

    def test_create_spend_chart_no_ending_new_line(self):
        self.food.deposit(900, "deposit")
        self.entertainment.deposit(900, "deposit")
        self.business.deposit(900, "deposit")
        self.food.withdraw(105.55)
        self.entertainment.withdraw(33.40)
        self.business.withdraw(10.99)
        actual = budget.create_spend_chart([self.business, self.food, self.entertainment])
        self.assertFalse(actual.endswith("\\n"), "Expected chart to not have new line at the end.")
`);

    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

`create_spend_chart` chart should have each category name written vertically below the bar. Each line should have the same length, each category should be separated by two spaces, with additional two spaces after the final category.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")
        self.entertainment = budget.Category("Entertainment")
        self.business = budget.Category("Business")
        self.food.deposit(900, "deposit")
        self.entertainment.deposit(900, "deposit")
        self.business.deposit(900, "deposit")
        self.food.withdraw(105.55)
        self.entertainment.withdraw(33.40)
        self.business.withdraw(10.99)

    def test_create_spend_chart_names_two_categories(self):
        chart = budget.create_spend_chart([self.food, self.entertainment])
        actual = "\\n".join(chart.split("\\n")[13:]).rstrip("\\n")
        expected = "     F  E  \\n     o  n  \\n     o  t  \\n     d  e  \\n        r  \\n        t  \\n        a  \\n        i  \\n        n  \\n        m  \\n        e  \\n        n  \\n        t  "
        self.assertEqual(actual, expected, "Expected different category names written vertically below the bar. Check that all spacing is exact.")

    def test_create_spend_chart_names_three_categories(self):
        chart = budget.create_spend_chart([self.business, self.food, self.entertainment])
        actual = "\\n".join(chart.split("\\n")[13:]).rstrip("\\n")
        expected = "     B  F  E  \\n     u  o  n  \\n     s  o  t  \\n     i  d  e  \\n     n     r  \\n     e     t  \\n     s     a  \\n     s     i  \\n           n  \\n           m  \\n           e  \\n           n  \\n           t  "
        self.assertEqual(actual, expected, "Expected different category names written vertically below the bar. Check that all spacing is exact.")
`);

    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

`create_spend_chart` should print a different chart representation. Prüfe, ob alle Abstände genau eingehalten werden. Open your browser console with F12 for more details.

```js
({
  test: () => {
    pyodide.FS.writeFile('/home/pyodide/budget.py', code);
    pyodide.FS.writeFile('/home/pyodide/test_module.py',`
import unittest
import budget
from importlib import reload

reload(budget)
class UnitTests(unittest.TestCase):
    maxDiff = None
    def setUp(self):
        self.food = budget.Category("Food")
        self.entertainment = budget.Category("Entertainment")
        self.business = budget.Category("Business")

    def test_create_spend_chart(self):
        self.food.deposit(900, "deposit")
        self.entertainment.deposit(900, "deposit")
        self.business.deposit(900, "deposit")
        self.food.withdraw(105.55)
        self.entertainment.withdraw(33.40)
        self.business.withdraw(10.99)
        actual = budget.create_spend_chart([self.business, self.food, self.entertainment])
        expected = "Percentage spent by category\\n100|          \\n 90|          \\n 80|          \\n 70|    o     \\n 60|    o     \\n 50|    o     \\n 40|    o     \\n 30|    o     \\n 20|    o  o  \\n 10|    o  o  \\n  0| o  o  o  \\n    ----------\\n     B  F  E  \\n     u  o  n  \\n     s  o  t  \\n     i  d  e  \\n     n     r  \\n     e     t  \\n     s     a  \\n     s     i  \\n           n  \\n           m  \\n           e  \\n           n  \\n           t  "
        self.assertEqual(actual, expected, 'Expected different chart representation. Check that all spacing is exact.')
`);

    const testCode = `
from unittest import main
from importlib import reload
import test_module
reload(test_module)
t = main(module='test_module', exit=False)
t.result.wasSuccessful()
`;
    const out = runPython(testCode);
    assert(out);
  }
})
```

# --seed--

## --seed-contents--

```py
class Category:
    pass

def create_spend_chart(categories):
    pass
```

# --solutions--

```py
class Category:

    def __init__(self, name):
        self.name = name
        self.ledger = []
        self.balance = 0
        self.spent = 0

    def __str__(self):
        first_line = f'{self.name.center(30, "*")}\n'
        lines = ''
        total = f'Total: {format(self.balance, ".2f")}'

        for n in range(len(self.ledger)):
            descr = self.ledger[n]["description"][:23]
            am = format(float(self.ledger[n]["amount"]), ".2f")[:7]
            lines = lines + f'{descr:<23}{am:>7}\n'

        return f'{first_line}{lines}{total}'

    def deposit(self, amount, description=''):
        self.ledger.append({
            'amount': float(amount),
            'description': description
        })
        self.balance = self.balance + float(amount)

    def withdraw(self, amount, description=''):
        if self.check_funds(amount):
            self.ledger.append({
                'amount': -float(amount),
                'description': description
            })
            self.balance = self.balance - float(amount)
            self.spent = self.spent + float(amount)
            return True
        else:
            return False

    def get_balance(self):
        return self.balance

    def transfer(self, amount, category):
        if self.check_funds(amount):
            # withdraw
            self.ledger.append({
                'amount': -float(amount),
                'description': f'Transfer to {category.name}'
            })
            self.balance = self.balance - float(amount)
            # deposit
            category.deposit(amount, f'Transfer from {self.name}')

            return True
        else:
            return False

    def check_funds(self, amount):
        if float(amount) > self.balance:
            return False
        else:
            return True


def create_spend_chart(categories):
    total_expenses = 0
    obj = {}
    col1 = []
    str = []
    final_str = 'Percentage spent by category\n'
    label_max_length = 0
    label_strings = []

    for category in categories:
        total_expenses = total_expenses + category.spent
        obj[category.name] = {'expenses': category.spent}
        obj[category.name]['label'] = list(category.name)
        if len(obj[category.name]['label']) > label_max_length:
            label_max_length = len(obj[category.name]['label'])

    for category in categories:
        obj[category.name]['percent'] = (
            (category.spent / total_expenses * 100) // 10) * 10
        obj[category.name]['column'] = []
        for i in range(0, 110, 10):
            if obj[category.name]['percent'] >= i:
                obj[category.name]['column'].insert(0, 'o')
            else:
                obj[category.name]['column'].insert(0, ' ')

    for i in range(0, 110, 10):
        col1.insert(0, i)

    for i in range(11):
        str.append("")
        for key in obj:
            str[i] += (f'{obj[key]["column"][i]}  ')
        final_str += f'{col1[i]:>3}| {str[i]}\n'
    final_str += f'    {"-"*(1+3*len(obj))}\n   '

    for i in range(label_max_length):
        label_strings.append('  ')
        for k in obj:
            if len(obj[k]['label']) < label_max_length:
                obj[k]['label'].extend(
                    f'{" "*(label_max_length-len(obj[k]["label"]))}')

            label_strings[i] += f'{obj[k]["label"][i]}  '
        if i < label_max_length - 1:
            label_strings[i] += '\n   '
        final_str += label_strings[i]

    print(final_str)
    return (final_str)

```
