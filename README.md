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

puts driver.execute_script("return window.location.pathname")
element = driver.execute_script("return document.body")
driver.execute_script("return arguments[0].tagName", element)
wait = Selenium::WebDriver::Wait.new(timeout: 10)
wait.until { driver.find_element(id: "foo") }
driver.switch_to.frame ""
driver.switch_to.frame driver.find_element(id: 'some-frame')
driver.switch_to.default_content
driver.manage.window.move_to(300, 400)
driver.manage.window.resize_to(500, 800)
driver.manage.window.maximize

class_name = element.attribute("class")
element.displayed?
element.click
elementt.location
element.location_once_scrolled_into_view
element.size
element.send_keys :space
element.text

driver.action.key_down(:shift).
              click(element).
              double_click(second_element).
              key_up(:shift).
              drag_and_drop(element, third_element).
              perform

options = Selnium::WebDriver::Chrome::Options.new
options.add_argument('--ignore-certificate-errors')
options.add_argument('--disable-popup-blocking')
options.add_argument('--disable-translate')
driver = Selenium::WebDriver.for :chrome, options: options

prefs = {
  prompt_for_download: false,
  default_directory: "/path/to/dir"
}
options = Selenium::WebDriver::Chrome::Options.new
options.add_prefrence(:download, prefs)
driver = Selenium::WebDriver.for :chrome, options: options

driver = Selenium::WebDriver.for :remote
driver = Selenium::WebDriver.for :remote, url: "http://myserver:4444/wd/hub"
driver = Selenium::WebDriver.for :remote, desired_capabilities: :firefox

caps = Selenium::WebDriver::Remote::Capabilities.internet_explore(native_events: false)
driver = Selenium::WebDriver.for :remote, desired_capabilities: caps

caps = Selenium::WebDriver::Remote::Capabilities.internet_explorer
caps['EnablePersistentHover'] = false
driver = Selenium::WebDriver.for :remote, desired_capabilities:: caps
```

```sh
java -jar selenium-server-standalone.jar
```
