# Decimal
## Implementation of the decimal type (just like in c#)

### The value_type field contains information about the type of number, with the s21_NORMAL_VALUE value, the bits array contains a number, with other values, all elements of the bits array are 0  

### Arithmetic Operators

| Operator name | Operators  | Function | 
| ------ | ------ | ------ |
| Addition | + | s21_decimal s21_add(s21_decimal, s21_decimal) |
| Subtraction | - | s21_decimal s21_sub(s21_decimal, s21_decimal) |
| Multiplication | * | s21_decimal s21_mul(s21_decimal, s21_decimal) | 
| Division | / | s21_decimal s21_div(s21_decimal, s21_decimal) |
| Modulo | Mod | s21_decimal s21_mod(s21_decimal, s21_decimal) |

If an error occurs during the operation, the error type is written to the value_type variable  

### Comparison Operators

| Operator name | Operators  | Function | 
| ------ | ------ | ------ |
| Less than | < | int s21_is_less(s21_decimal, s21_decimal) |
| Less than or equal to | <= | int s21_is_less_or_equal(s21_decimal, s21_decimal) | 
| Greater than | > |  int s21_is_greater(s21_decimal, s21_decimal) |
| Greater than or equal to | >= | int s21_is_greater_or_equal(s21_decimal, s21_decimal) | 
| Equal to | == |  int s21_is_equal(s21_decimal, s21_decimal) |
| Not equal to | != |  int s21_is_not_equal(s21_decimal, s21_decimal) |

Return value:
- 0 - TRUE
- 1 - FALSE

### Convertors and parsers

| Convertor/parser | Function | 
| ------ | ------ |
| From int  | int s21_from_int_to_decimal(int src, s21_decimal *dst) |
| From float  | int s21_from_float_to_decimal(float src, s21_decimal *dst) |
| To int  | int s21_from_decimal_to_int(s21_decimal src, int *dst) |
| To float  | int s21_from_decimal_to_float(s21_decimal src, float *dst) |

Return value - code error:
- 0 - SUCCESS
- 1 - CONVERTING ERROR

*Note on the conversion of a float type number:*
- *If the numbers are outside the range of their type (|x| > 7.9e28 or 0 < |x| < 1e-28) or are equal to infinity, return an error*
- *When processing a number with the float type, convert all the digits contained in it*

### Another functions

| Description | Function | 
| ------ | ------ |
| Rounds a specified Decimal number to the closest integer toward negative infinity. | s21_decimal s21_floor(s21_decimal) |	
| Rounds a decimal value to the nearest integer. | s21_decimal s21_round(s21_decimal) |
| Returns the integral digits of the specified Decimal; any fractional digits are discarded. | s21_decimal s21_truncate(s21_decimal) |
| Returns the result of multiplying the specified Decimal value by negative one. | s21_decimal s21_negate(s21_decimal) |
