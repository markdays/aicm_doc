.. _strategy-express:

==================
表达式运算
==================

运算符&语句
=========================

表达式求值程序支持以下基本功能算术运算、函数及过程:

.. csv-table::
  :widths: 20, 60

  "类型", "标量, 向量, 字符串"
  "基本操作", "+, -, *, /, %, ^"
  "赋值", ":=, +=, -=, *=, /=, %="
  "等式&不等式", "=, ==, <>, !=, <, <=, >, >="
  "逻辑操作", "and, mand, mor, nand, nor, not, or, shl, shr, xnor, xor, true, false"
  "函数", "abs, avg, ceil, clamp, equal, erf, erfc,  exp, expm1, floor, frac,  log,

  log10, log1p,  log2, logn,  max,  min,  mul,  ncdf,  nequal,  root, round,

  roundn, sgn, sqrt, sum, swap, trunc"
  "三角函数", "acos, acosh, asin, asinh, atan, atanh,  atan2, cos,  cosh, cot,  csc,

  sec,  sin, sinc,  sinh, tan, tanh, hypot, rad2deg, deg2grad,  deg2rad, grad2deg"
  "控制结构", "if-then-else, switch-case, return"
  "循环语句", "while, for, repeat-until, break, continue"

表达式示例
============================

算数运算符
-------------------------------

.. csv-table::
  :header: "运算符", "示例"
  :widths: 20, 60

  "\+", "相加 (eg: x + y)"
  "\-", "相减 (eg: x - y)"
  "\*", "Multiplication between x and y.  (eg: x * y)"
  "/", "Division between x and y.  (eg: x / y)"
  "%", "Modulus of x with respect to y.  (eg: x % y)"
  "^", "x to the power of y.  (eg: x ^ y)"
  ":=", "Assign the value of x to y. Where y is either a variable or vector type.  (eg: y := x)"
  "+=", "Increment x by the value of the expression on the right hand side. Where x is either a variable or vector type.  (eg: x += abs(y - z))"
  "-=", "Decrement x by the value of the expression on the right hand side. Where x is either a variable or vector type. (eg: x[i] -= abs(y + z))"
  "*=", "Assign the multiplication of x by the value of the expression on the righthand side to x. Where x is either a variable or vector type.  (eg: x *= abs(y / z))"
  "/=", "Assign the division of x by the value of the expression on the right-hand side to x. Where x is either a variable or vector type.  (eg: x[i + j] /= abs(y * z))"
  "%=", "Assign x modulo the value of the expression on the right hand side to x. Where x is either a variable or vector type.  (eg: x[2] %= y ^ 2)"

等于&不等式
-------------------------------

.. csv-table::
  :header: "运算符", "示例"
  :widths: 20, 60

  "== or =", "True only if x is strictly equal to y. (eg: x == y)"
  "<> or !=", "True only if x does not equal y. (eg: x <> y or x != y)"
  "<", "True only if x is less than y. (eg: x < y)"
  "<=", "True only if x is less than or equal to y. (eg: x <= y)"
  ">", "True only if x is greater than y. (eg: x > y)"
  ">=", "True only if x greater than or equal to y. (eg: x >= y)"

布尔运算符
-------------------------------

.. csv-table::
  :header: "运算符", "示例"
  :widths: 20, 60

  "true ", "True state or any value other than zero (typically 1)."
  "false", "False state, value of exactly zero."
  "and  ", "Logical AND, True only if x and y are both true.(eg: x and y)"
  "mand ", "Multi-input logical AND, True only if all inputs are true. Left to right short-circuiting of expressions. (eg: mand(x > y, z < w, u or v, w and x))"
  "mor  ", "Multi-input logical OR, True if at least one of the inputs are true. Left to right short-circuiting of expressions.  (eg: mor(x > y, z < w, u or v, w and x))"
  "nand ", "Logical NAND, True only if either x or y is false. (eg: x nand y)"
  "nor  ", "Logical NOR, True only if the result of x or y is false (eg: x nor y)"
  "not  ", "Logical NOT, Negate the logical sense of the input. (eg: not(x and y) == x nand y)"
  "or   ", "Logical OR, True if either x or y is true. (eg: x or y)"
  "xor  ", "Logical XOR, True only if the logical states of x and y differ.  (eg: x xor y)"
  "xnor ", "Logical XNOR, True iff the biconditional of x and y is satisfied.  (eg: x xnor y)"
  "&    ", "Similar to AND but with left to right expression short circuiting optimisation.  (eg: (x & y) == (y and x))"
  "\|   ", "Similar to OR but with left to right expression short circuiting optimisation.  (eg: (x | y) == (y or x))"

通用函数
-------------------------------

.. csv-table::
  :header: "函数", "示例"
  :widths: 20, 60

  "abs    ", "Absolute value of x.  (eg: abs(x))"
  "avg    ", "Average of all the inputs. (eg: avg(x,y,z,w,u,v) == (x + y + z + w + u + v) / 6)"
  "ceil   ", "Smallest integer that is greater than or equal to x."
  "clamp  ", "Clamp x in range between r0 and r1, where r0 < r1. (eg: clamp(r0,x,r1))"
  "equal  ", "Equality test between x and y using normalised epsilon"
  "erf    ", "Error function of x.  (eg: erf(x))"
  "erfc   ", "Complimentary error function of x.  (eg: erfc(x))"
  "exp    ", "e to the power of x.  (eg: exp(x))"
  "expm1  ", "e to the power of x minus 1, where x is very small. (eg: expm1(x))"
  "floor  ", "Largest integer that is less than or equal to x. (eg: floor(x))"
  "frac   ", "Fractional portion of x.  (eg: frac(x))"
  "hypot  ", "Hypotenuse of x and y (eg: hypot(x,y) = sqrt(x*x + y*y))"
  "iclamp ", "Inverse-clamp x outside of the range r0 and r1. Where r0 < r1. If x is within the range it will snap to the closest bound. (eg: iclamp(r0,x,r1)"
  "inrange", "In-range returns 'true' when x is within the range r0 and r1. Where r0 < r1.  (eg: inrange(r0,x,r1)"
  "log    ", "Natural logarithm of x.  (eg: log(x)) "
  "log10  ", "Base 10 logarithm of x.  (eg: log10(x))"
  "log1p  ", "Natural logarithm of 1 + x, where x is very small. (eg: log1p(x))"
  "log2   ", "Base 2 logarithm of x.  (eg: log2(x))"
  "logn   ", "Base N logarithm of x. where n is a positive integer. (eg: logn(x,8))"
  "max    ", "Largest value of all the inputs. (eg: max(x,y,z,w,u,v))"
  "min    ", "Smallest value of all the inputs. (eg: min(x,y,z,w,u))"
  "mul    ", "Product of all the inputs. (eg: mul(x,y,z,w,u,v,t) == (x * y * z * w * u * v * t))"
  "ncdf   ", "Normal cumulative distribution function.  (eg: ncdf(x))"
  "nequal ", "Not-equal test between x and y using normalised epsilon"
  "pow    ", "x to the power of y.  (eg: pow(x,y) == x ^ y)"
  "root   ", "Nth-Root of x. where n is a positive integer. (eg: root(x,3) == x^(1/3))"
  "round  ", "Round x to the nearest integer.  (eg: round(x))"
  "roundn ", "Round x to n decimal places  (eg: roundn(x,3)) where n > 0 and is an integer. (eg: roundn(1.2345678,4) == 1.2346)"
  "sgn    ", "Sign of x, -1 where x < 0, +1 where x > 0, else zero. (eg: sgn(x))"
  "sqrt   ", "Square root of x, where x >= 0.  (eg: sqrt(x))"
  "sum    ", "Sum of all the inputs. (eg: sum(x,y,z,w,u,v,t) == (x + y + z + w + u + v + t))"
  "swap   ", "Swap the values of the variables x and y and return the"
  "<=>    ", "current value of y.  (eg: swap(x,y) or x <=> y)"
  "trunc  ", "Integer portion of x.  (eg: trunc(x))"

三角函数
-------------------------------

.. csv-table::
  :header: "函数", "示例"
  :widths: 20, 60

  "acos    ", "Arc cosine of x expressed in radians. Interval [-1,+1] (eg: acos(x))"
  "acosh   ", "Inverse hyperbolic cosine of x expressed in radians.  (eg: acosh(x))"
  "asin    ", "Arc sine of x expressed in radians. Interval [-1,+1] (eg: asin(x))"
  "asinh   ", "Inverse hyperbolic sine of x expressed in radians. (eg: asinh(x))"
  "atan    ", "Arc tangent of x expressed in radians. Interval [-1,+1] (eg: atan(x))"
  "atan2   ", "Arc tangent of (x / y) expressed in radians. [-pi,+pi] eg: atan2(x,y)"
  "atanh   ", "Inverse hyperbolic tangent of x expressed in radians. (eg: atanh(x))"
  "cos     ", "Cosine of x.  (eg: cos(x))"
  "cosh    ", "Hyperbolic cosine of x.  (eg: cosh(x))"
  "cot     ", "Cotangent of x.  (eg: cot(x))"
  "csc     ", "Cosecant of x.  (eg: csc(x))"
  "sec     ", "Secant of x.  (eg: sec(x))"
  "sin     ", "Sine of x.  (eg: sin(x))"
  "sinc    ", "Sine cardinal of x.  (eg: sinc(x))"
  "sinh    ", "Hyperbolic sine of x.  (eg: sinh(x))"
  "tan     ", "Tangent of x.  (eg: tan(x))"
  "tanh    ", "Hyperbolic tangent of x.  (eg: tanh(x))"
  "deg2rad ", "Convert x from degrees to radians.  (eg: deg2rad(x))"
  "deg2grad", "Convert x from degrees to gradians.  (eg: deg2grad(x))"
  "rad2deg ", "Convert x from radians to degrees.  (eg: rad2deg(x))"
  "grad2deg", "Convert x from gradians to degrees.  (eg: grad2deg(x))"

控制结构语句
-------------------------------

+----------+---------------------------------------------------------+
| 结构     | 示例                                                    |
+----------+---------------------------------------------------------+
| if       | 1. if (x, y, z)                                         |
|          | 2. if ((x + 1) > 2y, z + 1, w / v)                      |
|          | 3. if (x > y) z;                                        |
|          | 4. if (x <= 2*y) { z + w };                             |
+----------+---------------------------------------------------------+
| if-else  | 1. if (x > y) z; else w;                                |
|          | 2. if (x > y) z; else if (w != u) v;                    |
|          | 3. if (x < y) { z; w + 1; } else u;                     |
|          | 4. if ((x != y) and (z > w))                            |
|          |    {                                                    |
|          |      y := sin(x) / u;                                   |
|          |      z := w + 1;                                        |
|          |    }                                                    |
|          |    else if (x > (z + 1))                                |
|          |    {                                                    |
|          |      w := abs (x - y) + z;                              |
|          |      u := (x + 1) > 2y ? 2u : 3u;                       |
|          |    }                                                    |
+----------+---------------------------------------------------------+
| switch   | switch                                                  |
|          | {                                                       |
|          |   case x > (y + z) : 2 * x / abs(y - z);                |
|          |   case x < 3       : sin(x + y);                        |
|          |   default          : 1 + x;                             |
|          | }                                                       |
+----------+---------------------------------------------------------+
| while    | while ((x -= 1) > 0)                                    |
|          | {                                                       |
|          |   y := x + z;                                           |
|          |   w := u + y;                                           |
|          | }                                                       |
+----------+---------------------------------------------------------+
| repeat/  | repeat                                                  |
| until    |   y := x + z;                                           |
|          |   w := u + y;                                           |
|          | until ((x += 1) > 100)                                  |
+----------+---------------------------------------------------------+
| for      | for (var x := 0; (x < n) and (x != y); x += 1)          |
|          | {                                                       |
|          |   y := y + x / 2 - z;                                   |
|          |   w := u + y;                                           |
|          | }                                                       |
+----------+---------------------------------------------------------+
| break    | while ((i += 1) < 10)                                   |
| break[]  | {                                                       |
|          |   if (i < 5)                                            |
|          |     j -= i + 2;                                         |
|          |   else if (i % 2 == 0)                                  |
|          |     break;                                              |
|          |   else                                                  |
|          |     break[2i + 3];                                      |
|          | }                                                       |
+----------+---------------------------------------------------------+
| continue | for (var i := 0; i < 10; i += 1)                        |
|          | {                                                       |
|          |   if (i < 5)                                            |
|          |     continue;                                           |
|          |   j -= i + 2;                                           |
|          | }                                                       |
+----------+---------------------------------------------------------+
| return   | 1. return [1];                                          |
|          | 2. return [x, 'abx'];                                   |
|          | 3. return [x, x + y,'abx'];                             |
|          | 4. return [];                                           |
|          | 5. if (x < y)                                           |
|          |     return [x, x - y, 'result-set1', 123.456];          |
|          |    else                                                 |
|          |     return [y, x + y, 'result-set2'];                   |
+----------+---------------------------------------------------------+
| ?:       | 1. x ? y : z                                            |
|          | 2. x + 1 > 2y ? z + 1 : (w / v)                         |
|          | 3. min(x,y) > z ? (x < y + 1) ? x : y : (w * v)         |
+----------+---------------------------------------------------------+
| ~        | ~(i := x + 1, j := y / z, k := sin(w/u)) == (sin(w/u))) |
|          | ~{i := x + 1; j := y / z; k := sin(w/u)} == (sin(w/u))) |
+----------+---------------------------------------------------------+
| [*]      | [*]                                                     |
|          | {                                                       |
|          |   case (x + 1) > (y - 2)    : x := z / 2 + sin(y / pi); |
|          |   case (x + 2) < abs(y + 3) : w / 4 + min(5y,9);        |
|          |   case (x + 3) == (y * 4)   : y := abs(z / 6) + 7y;     |
|          | }                                                       |
+----------+---------------------------------------------------------+
| []       | 1. v[]                                                  |
|          | 2. max_size := max(v0[],v1[],v2[],v3[])                 |
+----------+---------------------------------------------------------+

变量&多语句
=============================================

变量定义用关键字 var，当有多个表达式时，每个表达式以分号“;” 结尾。如：

var x := 1;
var y := 2;
x := x + y; // 1 + 2 = 3

注释
=============================================
表达式中注释文本用双斜杠，可以是单独一行或表达式尾部





