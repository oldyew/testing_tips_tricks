# Selenium

```python
print(wd.capabilities) # list of browser capabilities

wd = webdriver.Chrome(desired_capabilities={"chromeOptions": {"args": ["--start-fullscreen"]}})
```

```ruby
caps = Selenium::WebDriver::Remote::Capabilities('chromeOptions' => {"args" => ["--start-fullscreen"]})
wd = Selenium::WebDriver.for :firefox, desired_capabilities: caps
```

## Attribute value check

``` css
"[checked]" /* attribute presence */
"[name=email]" /* attribute matching */
"[title*=Name]" /* contain text */
"[src^=http]" /* begin with text */
"[src$=.pdf]" /* end with text */
"lable:not(.error)" /* without class error */
"a:not([href^=http])" /* begin with text */
"div#main p" /* find p somewhere inside main */
"div#main > p" /* find p exectly inside main */
"div#main li:first-child" /*  */
"div#main li:last-child" /*  */
"div#main li:nth-child(1)" /*  */
"div#header > div:nth-of-type(1)" /*  */



```
