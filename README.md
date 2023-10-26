# Github Actions

## The difference between single quotes ('') and double quotes ("") in YAML files.

1. **Single Quotes ('')**:
   - In YAML, single quotes are used for scalar values. When you enclose a string in single quotes, it is treated as a plain string without any special interpretation.
   - Special characters, escape sequences, and variables within single quotes are treated as literal characters. For example, `'$100'` would be treated as the string "$100," and escape sequences like `'\n'` are not interpreted but are treated as the actual characters '\n'.

   Example:
   ```yaml
   key: 'This is a string with special characters: $100 and \n newline.'
   ```

2. **Double Quotes ("")**:
   - Double quotes are used for string values as well but with some differences. Strings enclosed in double quotes allow for escape sequences to be interpreted and variable substitution (if supported by the YAML parser). For example, `"$100"` might be interpreted as a string with the value of the variable `$100`, and `"\n"` would be interpreted as a newline character.

   Example:
   ```yaml
   key: "This is a string with variable interpolation: $100 and a newline: \n"
   ```

In summary, the choice between single and double quotes in YAML depends on how you want the string to be treated. If you want to preserve special characters as literals and avoid variable interpolation, you can use single quotes. If you want to allow for variable substitution and interpretation of escape sequences, you can use double quotes. The specific behavior may also depend on the YAML parser being used, as some parsers may have slight variations in how they handle quotes.