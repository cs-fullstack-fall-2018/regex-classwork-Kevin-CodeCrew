# Classwork for Regular Expressions

## Write Regular Expressions to satisfy the following:

1. Match on the letter grades A+, B-, D using Character Sets []
Test Data: A, B-, B+, D, A-, A+, C, D+
```
/A\+|B-|D(?![\-+])/g
```
2. Match only phone numbe/rs in the format 901-555-2112 us/gmiing Character Ranges
Test Data: 901.555.1234, 270-555-4523, 901-555-9876, (502) 554-2613 
```
/([0-9]{3})-([0-9]{3})-([0-9]{4})/
```
3. Match all occurences of XYZ regardless of case
Test Data: ABC, xYz, XYZ, xyz, dEf, MLK
```
/xyz/gi
```
4. Write the JavaScript to reformat phone numbers from 901-555-2112 to (901) 555-2112

```
var test_data = "901-555-2112, 502-554-2613, 270-554-9001";

var myregexp = /([0-9]{3})-([0-9]{3})-([0-9]{4})/g;
var match = myregexp.exec(test_data);

while (match != null) {  
    if (match) {
        console.log('('+match[1]+') ' +match[2]+'-'+match[3]) ;
        match = myregexp.exec(test_data);
    }
}

```
