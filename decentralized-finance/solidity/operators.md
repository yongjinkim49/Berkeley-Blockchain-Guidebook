---
description: From official Solidity Guide
---

# Operators

1.  #### _Ternary Operator_

    __

    The ternary operator is used in expressions of the form `<expression> ? <trueExpression> : <falseExpression>`. It evaluates one of the latter two given expressions depending upon the result of the evaluation of the main `<expression>`. If `<expression>` evaluates to `true`, then `<trueExpression>` will be evaluated, otherwise `<falseExpression>` is evaluated.\
    __
2.  #### _Compound and Increment/Decrement Operators_

    __\
    __If `a` is an LValue (i.e. a variable or something that can be assigned to), the following operators are available as shorthands:\


    `a += e` is equivalent to `a = a + e`. The operators `-=`, `*=`, `/=`, `%=`, `|=`, `&=`, `^=`, `<<=` and `>>=` are defined accordingly. `a++` and `a--` are equivalent to `a += 1` / `a -= 1` but the expression itself still has the previous value of `a`. In contrast, `--a` and `++a` have the same effect on `a` but return the value after the change.\
    __\
    __
3.  #### _delete_

    __\
    __`delete a` assigns the initial value for the type to `a`. I.e. for integers it is equivalent to `a = 0`, but it can also be used on arrays, where it assigns a dynamic array of length zero or a static array of the same length with all elements set to their initial value. `delete a[x]` deletes the item at index `x` of the array and leaves all other elements and the length of the array untouched. This especially means that it leaves a gap in the array. If you plan to remove items, a [mapping](https://docs.soliditylang.org/en/v0.8.16/types.html#mapping-types) is probably a better choice.\
    __\
    __For structs, it assigns a struct with all members reset. In other words, the value of `a` after `delete a` is the same as if `a` would be declared without assignment, with the following caveat:\


    `delete` has no effect on mappings (as the keys of mappings may be arbitrary and are generally unknown). So if you delete a struct, it will reset all members that are not mappings and also recurse into the members unless they are mappings. However, individual keys and what they map to can be deleted: If `a` is a mapping, then `delete a[x]` will delete the value stored at `x`.\

4.  _**Order of Precedence of Operators**_\
    _****_

    <figure><img src="../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>
5. _**Others**_\
   _****_\
   _****_\
   _****_

{% embed url="https://docs.soliditylang.org/en/v0.8.16/types.html#operators" %}
