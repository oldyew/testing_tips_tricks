# JMETER

## How to save response in a variable in jmeter

### Beanshell PostProcessor

vars.put("response", new String(data));
${response}
https://blazemeter.com/blog/queen-jmeters-built-componentshow-use-beanshell

### Regular Expression Extractor

Reference Name: response
Regular Expression: (?s)(^.*)
Template: $1$
http://jmeter.apache.org/usermanual/regular_expressions.html
