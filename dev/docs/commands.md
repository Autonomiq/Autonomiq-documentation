# AutonomIQ Supported NLP commands

NLP supports human understandable english, here is a general primer:

## Action Field

* *[open/launch/go to/navigate] website [url]*

```
  open website       https://www.google.com
  launch website     https://www.yahoo.com
  go to website      https://www.linkedin.com
  navigate website   https://www.github.com
```

Those commands are exist for access given `website` address only
*note that* above Instruction could be separated into 2 part which indicating `Action field` and `Data field` each

* *wait for {number} seconds*

```
  wait for 1 secs
  wait for 5 seconds
  wait 5 secs
```

`wait for` command can be used when you want to control the waiting time manually

* *Wait until element is [visible/exists/not visible]*

```
  Wait until _xpath{"//p[@class='productNumbers']"} is visible
  Wait until _xpath{"//p[@class='productNumbers']"} is not visible
  Wait until _xpath{"//p[@class='productNumbers']"} is exists
```

Our engine will wait until given element is coming up within DOM

* *Wait until element is [disabled/enabled]*

```
  Wait until _xpath{"//p[@class='productNumbers'"} is disabled
  Wait until _xpath{"//p[@class='productNumbers'"} is enabled
```

Our engine can check the status of element which could be switched like `Switch` HTML tag

* *Verify element is element*

```
  Verify _css{"body:nth-child(6) div:nth-child(2) > div.App"} is _xpath{"//div[@class='App']"}
  Verify _xpath{"//div[@class='App']"} is _css{"body:nth-child(6) div:nth-child(2) > div.App"}
```

Our engine is able to compare the 2 given element by using above `Verify` command

* *Verify element [contains/begins with/ends with] [text]*

```
  Verify _xpath{"//div[@class='App']"} contains 'sample'
  Verify _xpath{"//div[@class='App']"} begins with 'sample'
  Verify _xpath{"//div[@class='App']"} ends with 'sample'
```

Our engine is able to check whether given element has specific text if the a given element has text

* *Verify element [contains/begins with/ends with] [text] [or] [contains/begins with/ends with]*

```
  Verify _xpath{"//div[@class='App']"} begins with 'auto' or ends with 'nomiq'
```

Text include verification syntax like previous command could be implemented continuously with `or` syntax

* *Verify the current url is [url]*

```
  Verify the current url is 'https://www.test.com/'
```

Check the url which currently in with browser whether is same with given url

* *Verify new [window/tab/alert/pop up/pop-up] exists*

```
  Verify new window exists
  Verify new tab exists
  Verify new alert exists
  Verify new pop up exists
  Verify new pop-up exists
```

Check if new `window` or `alert` or `tab` or `pop up` is coming up upon existing window

* *Verify element [exist/exists]*

```
  Verify _xpath{"//div[@class='App']"} exist
  Verify _xpath{"//div[@class='App']"} exists
```

Check whether given element is exist on current DOM or not

* *Verify element [does not/doesnt/doesn't] [exists/exist]*

```
  Verify _xpath{"//div[@class='App']"} does not exists
  Verify _xpath{"//div[@class='App']"} `doesn't` exists
  Verify _xpath{"//div[@class='App']"} doesnt exists
```

Check whether given element is exist on current DOM or not

* *Switch to [first/second/1/1st/2/2nd/3/3rd/original/new] [tab/window]*

```
  Switch to first tab
  Switch to second tab
  Switch to 1 tab
  Switch to 1st tab
  Switch to 2 tab
  Switch to 2nd tab
  Switch to 3 tab
  Switch to 3rd tab
  Switch to original tab
  Switch to new tab
```

Our engine can switch the context of window if the new `tab` or `window` is coming up

* *Switch to [alert/prompt/confirm] and click on [ok/accept/leave/cancel/stay]*

```
  Switch to alert and click on ok
  Switch to prompt and click on cancel
  Switch to confirm and click on accept
```

Our engine can switch the context of window and also do an Actions that `prompt` has

* *Switch to [alert/prompt] box and enter [text] and click on [ok/accept/leave/cancel/stay]*

```
  Switch to alert box and enter 'first name' and click on cancel
```

Our engine can do continuous Action regarding what procedure the prompt window has

* *Use custom code from [FileName]*

```
  Use custom code from MyCustomCode
```

 FileName field is going to filled with file name without extension name like `.java`
 *note that the file should be stored into AutonomiQ minio server prior to use in Test case*

* *REST API calls*


 Curl syntax is support for REST api calls and results can be saved to variables


```
  _api{-X "PUT"/"GET"/"POST"  -d ${data} -H "{"Content-Type": "application/json"}"  "https://google.com"}
  save _api{-X "PUT"  -d ${data} -H "{"Content-Type": "application/json"}"  "https://google.com"} as "result" will store the result as variable result (accessible as $result)
```

Our engine is able to do Action with not only `element text` but also `element _xpath` or `element _css`

* *[click/press] [on/at] [element]*

```
  Click on 'Submit'
  Press on 'Cancel'
  Click at 'Submit'
  Press at 'Cancel'
```

Our engine is able to do Action with not only `element text` but also `element _xpath` or `element _css`

* *[click/press] [on/at] [radio/checkbox] next to [element text]*

```
  Click on radio next to      'Montana'
  Click at checkout next to   'California'
  Press on radio next to      'California'
  Press at checkout next to   'California'
```

Our engine can verify the `radio` or `checkbox` which located beside text element like Below

* *Select/choose [element text]*

```
  Select  'California'
  Choose  'California'
```

This command could be implemented when the DOM has `Select` tag for select one element from various option

* *Upload file to [field]*

```
  Upload file to 'Upload xlsx file'
```

This command could be implemented when the website require file uploading step in order to testing functionality
*note that this command require artifact file which supposed to be uploaded as file by this command*

* *Hover [over/on] element*

```
  Hover over 'user name'
  Hover on   'user name'
```

This command is needed when user need to check the elements when we hover over the cursor on given element not by `Click`

* *[Enter/type in/fill in/set] text in [field]*

```
  Enter 'John Doe' in user name
  Type in 'John Doe' in user name
  Fill in 'John Doe' in user name
  Set 'John Doe' in user name
```

Our engine is able to find the element by text in order to do `Action` on that element

* *Set screen/window size - <width> * <height>*

```
  Set screen size - 1024 * 768
```

This command can change the size of window, especially useful when user's website has different element variation when change the resolution

* **
* *Create random variable [var_name]*

```
  Create random variable password
```

This command is going to generate random alphanumeric string for checking field's restriction like `password` field

* *Save element as [variable_name]*

```
  Save _xpath{"//div[@class='App']"} as first_value
```

This command is going to store the given element's data if given element has value on it
*note that this command can store multiple value which separated with comma in one variable from table element*

* *Save [element text] as [variable_name]*

```
  Save user name as user_id
```

`Save` command also able to store the value from text based element

* *[action] and save it as [variable_name]*

```
  Enter username and save it as user_id
```

This command is going to enable to reuse the same value as data into another step by storing as variable

* **
* *begin block [block_name]*
* *[some instructions]*
* *end block*

```
  begin block create_value
  Create random variable password
  end block
```

Saved block could be used with calling the name of block as same as saved variable in this case `${create_value}`

* **
* *using for loop*
* *run ${block name} for [number] times*
* *run ${block name} for all rows*

```
  using for loop
  run ${click_button} for 5 times
```

```
  using for loop
  run ${save_value} for all rows
```

This command is useful when user should check same action but multiple time at one time
*This will shorten the length of test step obviously*

* **

## Data Field

* *${variable_name} to reference a previously saved variable*
* *{Today, <format>}*

```
  {Today, dd/mm/yy}
  {Today, mm/dd/yy}
  {Today, yy/mm/dd}
```

This format is enable to get today's date in the specified format
*note that you can use yyyy format rather than yy like below*
*{Today, MM/dd/yyyy}*

* *{Today + 2{dd}, MM/dd/yyyy}*

```
  {Today + 2{dd}, MM/dd/yyyy}
```

As of today `(11/24/2018)`, expected result is `(11/26/2018)`

* *{Today - 2{dd}, MM/dd/yyyy}*

```
  {Today - 2{dd}, MM/dd/yyyy}
```

As of today `(11/24/2018)`, expected result is `(11/22/2018)`

* *{Today - 1{mm}, MM/dd/yyyy}*

```
  {Today - 1{mm}, MM/dd/yyyy}
```

As of today `(11/24/2018)`, expected result is `(10/24/2018)`

* *{Today - 1{yy}, MM/dd/yyyy}*

```
  {Today - 1{yy}, MM/dd/yyyy}
```

As of today `(11/24/2018)`, expected result is `(11/24/2017)`

* *{Today + 1{yy}, MM/dd/yyyy}*

```
  {Today + 1{yy}, MM/dd/yyyy}
```

As of today `(11/24/2018)`, expected result is `(11/24/2019)`
