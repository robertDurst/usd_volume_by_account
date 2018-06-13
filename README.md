# Buzz
A Simple CLI tool to calculate an account's payment volume (USD) over time and output results.

![Buzz Lightyear](https://i.pinimg.com/originals/92/d5/71/92d571103d621e62a053ac4f799e9225.jpg)

## Output
Currently, there are two output options availible.
### Print to Screen
Quick and easy... see the magic right before your eyes.
![terminal output](https://imgur.com/crks1Nu.png)

### Save to CSV
Export as CSV and let your excel sheet wizards do their magic.
![imported to sheets](https://imgur.com/WpqQV6C.png)

## Setup
We will assume no previous setup.
1. Install Brew: <br> `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
2. Setup Go. I reccomend following [this tutorial]( http://sourabhbajaj.com/mac-setup/Go/README.html).
3. Obtain a [Currencylayer](https://currencylayer.com/) API key. Fun fact, they don't actually validate any of your credentials so you can obtain as many keys as you want. *Note:* you only get 1000 request per month. 
4. Move to go working directory. Example:  <br>`cd ~/go-workspace/src/github.com/`
5. Make a *robertdurst* directory:  <br>`mkdir robertdurst && cd robertdurst`
6. Clone this repo:  <br>`git clone https://github.com/robertDurst/buzz.git`
7. Move to repo directory  <br>`cd buzz`
8. Install [dep](https://github.com/golang/dep). This can be done via:  <br> `brew install dep`.
9. Install dependencies:  <br>`dep ensure`
10. Install Buzz: <br> `go install`
11. Query some account payment history!

## How to use
This is a command line interace (CLI), so it is run via typing commands, arguments, and flags to the terminal.

Currently there is only one command `query`. It is followed by two commands and then a set of optional flags:
```
buzz query [stellar_address] [currencylayer_api_key] [flags]
```

**Flags**
```
--aggregate [day | month | none] // Time interval aggregating of data [DEFAULT: none]
--output [csv | terminal] // Print to screen or save to csv [DEFAULT: terminal]
--filename [ ANYTHING ] // Filename of csv to be saved [DEFAULT: results]
```

## Current State
* Only supports XLM and fiat based tokens

## Future Work
* Use an alternative currency, such as EUR, instead of USD (**requires paid subscription**)
* Differentiating between sent and received payments
* Automated bash script to run act as a *dashboard*
* Output *unmatched assets* to let user know what assets were not included in volume calculation
* Make a release for easier installation and use

## Wish List
* Fully functional web app
* Programmatically generate graphs
* Advanaced statistical analysis
