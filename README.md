### Selenium-with-Ruby
---
https://github.com/SeleniumHQ/selenium/tree/master/rb

https://github.com/SeleniumHQ/selenium/wiki/Ruby-Bindings

https://www.browserstack.com/automate/ruby

```
gem install selenium-webdriver
http://www.apache.org/licenses/LICENSE-2.0
```

```ruby
require "selenium-webdriver"
driver = Selenium::WebDriver.for :firefox
driver.nabigate.to "http://google.com"
element = driver.find_element(name: 'q')
element.send_keys "Hello WebDriver!"
element.submit
puts driver.title
driver.quit

```



```ruby

```

