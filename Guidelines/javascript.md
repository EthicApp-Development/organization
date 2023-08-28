# JavaScript guidelines

- [JavaScript guidelines](#javascript-guidelines)
  - [1. Indentation](#1-indentation)
  - [2. Naming](#2-naming)
  - [3. Comments](#3-comments)
    - [3.1. Functions](#31-functions)
    - [3.2. Classes](#32-classes)
  - [4. Strings](#4-strings)

The linter for automatically enforcing the coding style is [ESLint](https://eslint.org/). Its configuration file `.eslint.yaml` is located at the root directory of the [main project repository](https://github.com/EthicApp-Development/ethicapp-main/tree/master), where the custom rules are defined, based on ESLint's recommended configuration.

## 1. Indentation

Each indentation level must be 4 spaces (also configured for JavaScript files automatically on VScode IDE, which is defined at `.vscode/settings.json`, located in the main repository).

## 2. Naming

All member names must be in english and **meaningful** (at least 3 characters long, as self-explanatory as possible) and must follow the case standard as follows. Do not be afraid of long names, as well as they are meaningful and not excessively long.

| Member                  | Case type    |
| ----------------------- | ------------ |
| Variable name           | `camelCase`  |
| Function or method name | `camelCase`  |
| Class or name           | `PascalCase` |
| Constant name           | `MACRO_CASE` |
| Source file name        | `kebab-case` |

## 3. Comments

Code documentation must follow [`JSDoc`](https://jsdoc.app/) standard (JSDoc3), which is natively integrated in VSCode IDE and will provide intellisense when used right. A brief and simplified description of JSDoc is presented in this section. For a more detailed reference, please review [this great article from Wordpress](https://developer.wordpress.org/coding-standards/inline-documentation-standards/javascript/).

### 3.1. Functions

```js
/**
 * [Overall description.]
 *
 * @param {parameter_type} parameter_name Description.
 * [@throws {error_type} Description.]
 * @returns {return_type} Description.
 */
function myFunction(parameter_name) {
    ...
}
```

### 3.2. Classes

```js
/**
 * [Overall description.]
 *
 * @member {member_type} member_name Description.
 */
class MyClass {
    ...
}
```

Note that, for both cases, the overall description is optional and should be included wisely when needed.

## 4. Strings

Strings must be double-quoted, `"like this"`.
