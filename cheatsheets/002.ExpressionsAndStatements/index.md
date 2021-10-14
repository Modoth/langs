# Expressions And Statements

## Conditions, Loops and Jump

* SQL
```sql
if(win, tob, not2b) # ifnull, nullif
case win when true then '2b' else 'not 2b' end

IF n > m THEN SET s = '>';
ELSEIF n = m THEN SET s = '=';
ELSE SET s = '<';
END IF;

# IF THEN ELSEIF THEN ELSE ENF IF
# case statement: CASE WHEN THEN ELSE END CASE

WHILE v1 > 0 DO
  SET v1 = v1 - 1;
END WHILE;

# LOOP END LOOP
# REPEAT UNTIL END REPEAT
# WHILE DO END WHILE
# ITERATE label, LEAVE label
```

* Cpp
```cpp
win ? tob : not2b

// if constexpropt ( init-statementopt condition ) statement
// if constexpropt ( init-statementopt condition ) statement else statement
// switch ( init-statementopt condition ) statement; default, break

int array[5] = { 1, 2, 3, 4, 5 };
start: 
for (int& x : array)
	x *= 2;

// while ( condition ) statement
// do statement while ( expression ) ;
// for ( init-statement conditionopt ; expressionopt ) statement
// for ( init-statementopt for-range-declaration : for-range-initializer ) statement
// break; continue;

goto start
```
