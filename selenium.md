# Selenium

For now, this assumes you're going to use Selenium with Python3.

## Install and setup

### Windows

`pip install selenium`

I then tried the basic selenium test to startup firefox and chrome, however I was only able to get Chrome to work.

#### Chrome

Download the latest chromedriver.exe and place it in the test folder, then you can run this test script for chrome (make sure you set the correct user):

```
from selenium import webdriver


browser = webdriver.Chrome("C:\\Users\\<user>\\Projects\\Programming\\tdd\\tdd\\tests\\chromedriver.exe")
browser.get('http://localhost:8000')
assert 'Django' in browser.title

browser.quit()

```

#### Firefox

As I mentioned, I couldn't get this to work the best I could get to work was this:

`set PATH=%PATH%;"C:\Program Files (x86)\Mozilla Firefox;"`

I then ran the chrome script but with Firefox with no args and with the path to the `firefox.exe`.