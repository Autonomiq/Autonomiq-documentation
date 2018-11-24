# AutonomIQ Supported NLP commands

NLP supports human understandable english, here is a general primer:

## Action Field

* *open/launch/go to/navigate website [url]*

```
  `open website`     https://www.google.com
  `launch website`   https://www.yahoo.com
  `go to website`    https://www.linkedin.com
  `navigate website` https://www.github.com
```

Those commands are exist for access given `website` address only
*note that* above Instruction could be separated into 2 part which indicating `Action field` and `Data field` each

* *wait for {number} seconds*

```
  'wait for 1 secs'
  'wait for 5 seconds'
  'wait 5 secs'
```

`wait for` command can be used when you want to control the waiting time manually

* *Wait until element is visible/exists*

```
  'Wait until _xpath{"//p[@class='productNumbers']"} is visible'
  'Wait until _xpath{"//p[@class='productNumbers']"} is exists'
```

* *Wait until {xpath: "xpath"} is disabled/not visible*
* *verify {xpath: "xpath"} is [xpath]*
* *verify {xpath: "xpath"} [contains/begins with/ends with] [text]*
* *verify {xpath: "xpath"} [contains/begins with/ends with] [text] [or] [contains/begins with/ends with] (eg verify {xpath: "xpath" begins with [text] or ends with [text])*
* *verify {xpath: "xpath"} is [disabled/enabled/visible/not visible]*
* *verify the current url is [url] (eg verify the current url is https://www.test.com/)*
* *verify new window/tab/alert/pop up/pop-up exists*
* *verify {xpath: "xpath"} exist/exists*
* *verify {xpath: "xpath"} does not/doesnt/doesn't exists/exist*
* *switch to first/second/1/1st/2/2nd/3/3rd/original/new tab/window*
* *switch to alert/prompt/confirm and click on ok/accept/leave/cancel/stay*
* *switch to alert/prompt box and enter text and click on ok/accept/leave/cancel/stay*
* *use custom code from [location]*
* *click/press on/at [element text]*
* *click/press on/at [radio/checkbox] next to [element text]*
* *select/choose [element text]*
* *Upload file to [field]*
* *hover over/on [field]*
* *enter/type in/fill in/set text in [field]*
* *set screen/window size - <width> * <height>*
* **
* *"Create random variable <var_name>" for a random alphanumeric string*
* *save {xpath: "xpath"} as <variable_name>*
* *save [element text] as <variable_name>*
* *<action> and save it as <variable_name>*
* *${variable_name} to reference a previously saved variable*
* **
* *{today, <format>} to get today's date in the specified format*
* *{today, dd/mm/yy} to get today's date in the specified format*
* *{today, mm/dd/yy} to get today's date in the specified format*
* *{today, yy/mm/dd} to get today's date in the specified format*
* **
* *begin block [block_name]*
* *[some instructions]*
* *end block*
* **
* *using for loop*
* *run ${block name} for [number] times*
* *run ${block name} for all rows*
* **
* **
* **

## Data Field

* *{Today, MM/dd/yyyy}*
* *{Today + 2{dd}, MM/dd/yyyy}*
* *{Today - 2{dd}, MM/dd/yyyy}*
* *{Today - 1{mm}, MM/dd/yyyy}*
* *{Today - 1{yy}, MM/dd/yyyy}*
* *{Today + 1{yy}, MM/dd/yyyy}*
