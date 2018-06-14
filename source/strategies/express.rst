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

  "\+", "加 (eg: x + y)"
  "\-", "减 (eg: x - y)"
  "\*", "乘 (eg: x * y)"
  "/", "除 (eg: x / y)"
  "%", "取模 (eg: x % y)"
  "^", "幂 (eg: x ^ y)"
  ":=", "赋值 (eg: y := x)"
  "+=", "加法赋值 (eg: x += abs(y - z))"
  "-=", "减法赋值 (eg: x[i] -= abs(y + z))"
  "*=", "乘法赋值 (eg: x *= abs(y / z))"
  "/=", "除法赋值 (eg: x[i + j] /= abs(y * z))"
  "%=", "取模赋值 (eg: x[2] %= y ^ 2)"

等于&不等式
-------------------------------

.. csv-table::
  :header: "运算符", "示例"
  :widths: 20, 60

  "== or =", "相等 (eg: x == y)"
  "<> or !=", "不相等 (eg: x <> y or x != y)"
  "<", "小于 (eg: x < y)"
  "<=", "小于等于 (eg: x <= y)"
  ">", "大于 (eg: x > y)"
  ">=", "大于等于 (eg: x >= y)"

布尔运算符
-------------------------------

.. csv-table::
  :header: "运算符", "示例"
  :widths: 20, 60

  "true ", "真，任何不为零的值 (如： 1)."
  "false", "假，任何为零的值"
  "and  ", "与 (eg: x and y)"
  "mand ", "多个与 (eg: mand(x > y, z < w, u or v, w and x))"
  "mor  ", "多个或 (eg: mor(x > y, z < w, u or v, w and x))"
  "nand ", "与非 (eg: x nand y)"
  "nor  ", "或非 (eg: x nor y)"
  "not  ", "否 (eg: not(x and y) == x nand y)"
  "or   ", "逻辑或 (eg: x or y)"
  "xor  ", "异或 (eg: x xor y)"
  "xnor ", "异或非 (eg: x xnor y)"
  "&    ", "与，同and (eg: (x & y) == (y and x))"
  "\|   ", "或，同or (eg: (x | y) == (y or x))"

通用函数
-------------------------------

.. csv-table::
  :header: "函数", "示例"
  :widths: 20, 60

  "abs    ", "绝对值 (eg: abs(x))"
  "avg    ", "平均值 (eg: avg(x,y,z,w,u,v) == (x + y + z + w + u + v) / 6)"
  "ceil   ", "返回大于或者等于指定表达式的最小整数."
  "clamp  ", "最小数值和最大数值指定返回值的范围。 (eg: clamp(r0,x,r1))"
  "equal  ", "相等"
  "erf    ", "误差函数 (eg: erf(x))"
  "erfc   ", "互补误差函数 (eg: erfc(x))"
  "exp    ", "以自然常数e为底的指数函数 (eg: exp(x))"
  "floor  ", "向下取整，即取不大于x的最大整数 (eg: floor(x))"
  "frac   ", "返回实数的小数部分  (eg: frac(x))"
  "hypot  ", "计算直角三角形的斜边长 (eg: hypot(x,y) = sqrt(x*x + y*y))"
  "inrange", "范围内 (eg: inrange(r0,x,r1)"
  "log    ", "自然对数 (eg: log(x)) "
  "log10  ", "底为10的对数 (eg: log10(x))"
  "log1p  ", "1加自然对数 (eg: log1p(x))"
  "log2   ", "底为2的对数  (eg: log2(x))"
  "logn   ", "底为n的对数 (eg: logn(x,8))"
  "max    ", "最大值 (eg: max(x,y,z,w,u,v))"
  "min    ", "最小值 (eg: min(x,y,z,w,u))"
  "mul    ", "求积 (eg: mul(x,y,z,w,u,v,t) == (x * y * z * w * u * v * t))"
  "pow    ", "求 x 的 y 次幂（次方） (eg: pow(x,y) == x ^ y)"
  "round  ", "x最近整数  (eg: round(x))"
  "roundn ", "(eg: roundn(1.2345678,4) == 1.2346)"
  "sgn    ", "符号, -1 小于零 x < 0, +1 大于零, 否则为零. (eg: sgn(x))"
  "sqrt   ", "平方 (eg: sqrt(x))"
  "sum    ", "求和 (eg: sum(x,y,z,w,u,v,t) == (x + y + z + w + u + v + t))"
  "swap   ", "值交换"
  "<=>    ", "值交换，同swap (eg: swap(x,y) or x <=> y)"
  "trunc  ", "取整 (eg: trunc(x))"

三角函数
-------------------------------

.. csv-table::
  :header: "函数", "示例"
  :widths: 20, 60

  "acos    ", "反余弦函数 (eg: acos(x))"
  "acosh   ", "反双曲余弦值 (eg: acosh(x))"
  "asin    ", "反正弦函数 (eg: asin(x))"
  "asinh   ", "反双曲正弦值 (eg: asinh(x))"
  "atan    ", "反正切值 (eg: atan(x))"
  "atan2   ", "指方位角，也可以理解为计算复数 x+yi 的辐角 eg: atan2(x,y)"
  "atanh   ", "反双曲正切值 (eg: atanh(x))"
  "cos     ", "余弦 (eg: cos(x))"
  "cosh    ", "双曲余弦值 (eg: cosh(x))"
  "cot     ", "余切  (eg: cot(x))"
  "csc     ", "余割  (eg: csc(x))"
  "sec     ", "正割  (eg: sec(x))"
  "sin     ", "正弦  (eg: sin(x))"
  "sinc    ", "sinc函数 (eg: sinc(x))"
  "sinh    ", "双曲正弦函数 (eg: sinh(x))"
  "tan     ", "正切 (eg: tan(x))"
  "tanh    ", "双曲正切 (eg: tanh(x))"
  "deg2rad ", "角度转换为弧度  (eg: deg2rad(x))"
  "deg2grad", "角度转换为梯度  (eg: deg2grad(x))"
  "rad2deg ", "弧度转换为角度  (eg: rad2deg(x))"
  "grad2deg", "梯度转换为角度  (eg: grad2deg(x))"

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
表达式中注释文本用双斜杠（//），可以是单独一行或表达式尾部





