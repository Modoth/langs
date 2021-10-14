# Expressions And Statements

## Jumps
* SQl
```sql
GOTO label --Transact-SQL
```

* Cpp: `goto label`
```cpp
goto start
```

* Matlab
* Excel
* Perl
```pl
goto LABEL # EXPR or &FUNC_NAME
```

## Selections
* SQL
```sql
if(win, tob, not2b) # ifnull, nullif
case win when true then '2b' else 'not 2b' ed

# IF THEN ELSEIF THEN ELSE ENF IF
# CASE WHEN THEN ELSE END CASE
IF n > m THEN SET s = '>';
ELSEIF n = m THEN SET s = '=';
ELSE SET s = '<';
END IF;
```

* Cpp
```cpp
// if constexpropt ( init-statementopt condition ) statement
// if constexpropt ( init-statementopt condition ) statement else statement
// switch ( init-statementopt condition ) statement; default, break
```

* Matlab
```m
% if, elseif, else
% switch, case, otherwise
switch dayString
   case 'Monday'
      disp('Start of the work week')
   otherwise
      disp('Weekend!')
      end
```

* Excel
```fx
IF(C2=1,”Yes”,”No”)
IFS(A2>89,"A",A2>79,"B",A2>69,"C",A2>59,"D",TRUE,"F")

# IF(logical_test, value_if_true, [value_if_false])
# IFS(logical_test1, value_if_true1, [logical_test2, value_if_true2], [logical_test3, value_if_true3],…)
# SWITCH(expression, value1, result1, [default or value2, result2],…[default or value3, result3])
```

## Iterations
* SQL
```sql
# LOOP END LOOP
# REPEAT UNTIL END REPEAT
# WHILE DO END WHILE
# ITERATE label, LEAVE label
WHILE v1 > 0 DO
  SET v1 = v1 - 1;
END WHILE;
```
* Cpp
```cpp
// while ( condition ) statement
// do statement while ( expression ) ;
// for ( init-statement conditionopt ; expressionopt ) statement
// for ( init-statementopt for-range-declaration : for-range-initializer ) statement
// break; continue;
int array[5] = { 1, 2, 3, 4, 5 };
start: 
for (int& x : array)
	x *= 2;
```

* Malab
```m
% for
% while
% parfor
%  parfor loopvar = initval:endval; statements; end
%  parfor (loopvar = initval:endval, M); statements; end
% break, continue
for n = 2:6
    x(n) = 2 * x(n - 1);
end

parpool(3)
parfor i=1:3, c(:,i) = eig(rand(1000)); end
```

* Excel
```
# Loop to aggregate
# AGGREGATE(function_num, options, ref1, [ref2], …)
# AGGREGATE(function_num, options, array, [k])
# SUM, MAX, AVERAGE

AGGREGATE(14,3,A1:A100*(A1:A100>0),1) # 14: LARGE, 3: ignore hidden rows, error values, nested SUBTOTAL and AGGREGATE functions
```

## Exceptions
* SQL
```sql
DECLARE no_such_table CONDITION FOR 1051;
DECLARE CONTINUE HANDLER FOR no_such_table --CONTINUE|EXIT|UNDO
  BEGIN
    -- body of handler
  END;

DECLARE CONTINUE HANDLER FOR 1051
  BEGIN
    -- body of handler
  END;
```

* Cpp
```cpp
try {
  throw C();
} catch(const C p) {
  // handle character string exceptions here
}
```

* Matlab
```m
try
    a = notaFunction(5,6);
catch
    warning('Problem using function.  Assigning a value of 0.');
    a = 0;
end
```

* Excel
```
IFERROR (value, value_if_error)
```

## Others
* SQL
* Cpp
* Matlab
* Excel
* Perl

