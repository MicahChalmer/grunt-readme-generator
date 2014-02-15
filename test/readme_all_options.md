                                  _                
                                 (_)               
      __ _ _ __   ___  _ __ __  ___                
     / _` | '_ \ / _ \| '_ \\ \/ / |               
    | (_| | |_) | (_) | | | |>  <| |               
     \__,_| .__/ \___/|_| |_/_/\_\_|               
          | |                                      
          |_|                                      
        ______               ____  ___                 
        | ___ \             | |  \/  |                 
        | |_/ /___  __ _  __| | .  . | ___             
        |    // _ \/ _` |/ _` | |\/| |/ _ \            
        | |\ \  __/ (_| | (_| | |  | |  __/            
        \_| \_\___|\__,_|\__,_\_|  |_/\___|            
                                                       
                                                       
             _____                           _             
            |  __ \                         | |            
            | |  \/ ___ _ __   ___ _ __ __ _| |_ ___  _ __ 
            | | __ / _ \ '_ \ / _ \ '__/ _` | __/ _ \| '__|
            | |_\ \  __/ | | |  __/ | | (_| | || (_) | |   
             \____/\___|_| |_|\___|_|  \__,_|\__\___/|_|   
                                                           
                                                   
# grunt-readme-generator 
[![Build Status](https://secure.travis-ci.org/aponxi/grunt-readme-generator.png?branch=master)](http://travis-ci.org/aponxi/grunt-readme-generator)

> A grunt task to generate a dynamic readme.md from partial markdown files in readme folder. Specifically designed for GitHub projects!

## Jump to Section

* [Options used to generate this readme file](#options-used-to-generate-this-readme-file)
* [Installation](#installation)
* [Usage](#usage)
* [Options](#options)
* [Example](#example)
* [Example Output](#example-output)
* [Building and Testing](#building-and-testing)
* [Legal Mambo Jambo](#legal-mambo-jambo)
* [Release History](#release-history)
* [Tip Me ![](http://i.imgur.com/C0P9DIx.gif?1)](https://www.gittip.com/aponxi/)
* [Donate Me! ![](http://i.imgur.com/2tqfhMO.png?1)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=VBUW4M9LKTR62)

## Options used to generate this readme file
[[Back To Top]](#jump-to-section)

```js
readme_generator: {
  all_options: {
    options: {
      generate_changelog: true,
      has_travis: true,
      output: "test/readme_all_options.md",
      table_of_contents: true,
      readme_folder: "test/readme",
      changelog_folder: "test/changelogs",
      changelog_version_prefix: "v",
      toc_extra_links: ["[Tip Me ![](http://i.imgur.com/C0P9DIx.gif?1)](https://www.gittip.com/aponxi/)", "[Donate Me! ![](http://i.imgur.com/2tqfhMO.png?1)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=VBUW4M9LKTR62)"],
      banner: "banner.md"
    },
    order: {
      "installation.md": "Installation",
      "usage.md": "Usage",
      "options.md": "Options",
      "example.md": "Example",
      "output.md": "Example Output",
      "building-and-testing.md": "Building and Testing",
      "legal.md": "Legal Mambo Jambo"
    }
  },
}
```

## Installation
[[Back To Top]](#jump-to-section)

- via npm

```shell
npm install coffee-init
```

- Manually

```shell
git clone git://github.com/nox/coffee-init.git
```

## Usage
[[Back To Top]](#jump-to-section)

```javascript
var coffee_init = require('coffee-init');
coffee_init.awesome(); // "awesome"
```

If the output's line is more than the maximum bytes, then the rest of the characters will be treated as if it's in the next line. Meaning that you can find a very long line split into two in the `output` array key. Right now the max char limit is `16384` bytes.


## Options
[[Back To Top]](#jump-to-section)

- `chained`: `bool`

  `chained`, which is `true` by default, is an option that can stop running commands after one of them failed. To see if it failed, it checks the exit code of the command that is run.

- `returnOutput`: `bool`

  `returnOutput` is also `true` by default. This is what returns the output in an array, parsing them line by line. I supply with this option because sometimes you might run a command that only returns server's IP address or sometimes you can run a command that just outputs very long lines and a very long text. I added the ability to opt out so that when unnecessary you might set it to false.

## Example
[[Back To Top]](#jump-to-section)

```js
//require the extension/module/wtv
var execxi = require("execxi");

// I just defined some commands here
// These will run for a long time. So you can see that outputs are occurring in real-time.
var long_commands = ["find ~/"];
// These are just some shell scripts that exit with different exit codes
// one exits with 0, other exists with 1, and lastly 2.
var exit_codes = ["./tests/exit_0.sh","./tests/exit_1.sh","./tests/exit_2.sh"];
// this is non existent command to see what happens when it doesn't find the command to run.
// returns 127 exit code.
var non_existent = ["./tests/sadf.sh"];
// this is just a command that echoes one line, 5000 bytes.
var long_text = ["./tests/echo_bytes_5000.sh"];
// some regular commands that run successfully
var regular = Array("ls","echo \"Works\"", "ls -lart");


```

## Example Output
[[Back To Top]](#jump-to-section)

That example outputs something long like this:

```
Some Output
Coming Soon
```


## Building and Testing
[[Back To Top]](#jump-to-section)

I have packaged a `Makefile`, `Gruntfile` for building and testing, and `npm` scripts point to those.

Available commands are:

- `make` (Aliases: `npm run-script preinstall`) : 
  Compiles the C++ code into node extension.

- `make clean` (Aliases: `npm run-script preuninstall`):
  Removes the `build` directory.

- `node test` (Aliases: `make test`) : 
  This is for visual testing rather than unit testing. 

- `grunt test`  (Aliases: `grunt`; `npm test`): 
  This is for unit testing. 

## Legal Mambo Jambo
[[Back To Top]](#jump-to-section)

Copyright © 2013 aponxi <aponxi@weaponxi.com>

This software is licensed under [MIT License](http://aponxi.mit-license.org/).

## Release History
[[Back To Top]](#jump-to-section)

You can find [all the changelogs here](/test/changelogs).

### Latest changelog is from v0.10.0.md:

#### v0.10.0 11/Feb/2014
- V prefix. A more recent version than v0.1.0.

#### v0.1.01 05/Jun/2013
- Added utf-8 encode/decode to prevent unicode decode errors, fixed #17
- Corrected years in 0.6 changelog... Should get used to it by now.
- Added error output in panel which fixes #16





--------
<small>_This readme has been automatically generated by [readme generator](https://github.com/aponxi/grunt-readme-generator) on Fri Feb 14 2014 23:49:08 GMT-0500 (EST)._</small>