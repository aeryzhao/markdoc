| 注解                     | 用途                                                         |
| ------------------------ | :----------------------------------------------------------- |
| AssertFalse              | 用于boolean字段，该字段的值只能为false                       |
| AssertTrue               | 用于boolean字段，该字段只能为true                            |
| DecimalMax(value)        | 被注释的元素必须是一个数字，只能大于或等于该值               |
| DecimalMin(value)        | 被注释的元素必须是一个数字，只能小于或等于该值               |
| Digits(integer,fraction) | 检查是否是一种数字的(整数,小数)的位数                        |
| Email                    | 被注释的元素必须是电子邮箱地址                               |
| Future                   | 检查该字段的日期是否是属于将来的日期                         |
| FutureOrPresent          | 判断日期是否是将来或现在日期                                 |
| Max(value)               | 该字段的值只能小于或等于该值                                 |
| Min(value)               | 该字段的值只能大于或等于该值                                 |
| Negative                 | 判断负数                                                     |
| NegativeOrZero           | 判断负数或0                                                  |
| NotBlank                 | 只能用于字符串不为null，并且字符串trim()以后length要大于0    |
| NotEmpty                 | 集合对象的元素不为0，即集合不为空，也可以用于字符串不为null  |
| NotNull                  | 不能为null                                                   |
| Null                     | 必须为 null                                                  |
| Past                     | 检查该字段的日期是在过去                                     |
| PastOrPresent            | 判断日期是否是过去或现在日期                                 |
| Pattern(value)           | 被注释的元素必须符合指定的正则表达式                         |
| Positive                 | 判断正数                                                     |
| PositiveOrZero           | 判断正数或0                                                  |
| Size(max, min)           | 检查该字段的size是否在min和max之间，可以是字符串、数组、集合、Map等 |
| Length(max, min)         | 判断字符串长度                                               |
| CreditCardNumber         | 被注释的字符串必须通过Luhn校验算法，银行卡，信用卡等号码一般都用Luhn计算合法性 |