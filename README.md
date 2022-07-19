## Whats use of this tool?
To get subdomains from 'https://community.riskiq.com'. As there is no api endpoint, it uses valid credentials to login and then get subdomains.

## Why riskiqsub?
Actually I found [RiskIQ](https://community.riskiq.com) a fair source of getting subdomains and it is not included in [amass](https://github.com/OWASP/Amass) enum list (I think because of `no api support` for riskiq's subdomains functionality). Thats how this tool idea came.

## Requirement?
* python 3.x

## Installation
```bash
git clone https://github.com/MAAYTHM/riskiqsub.git
cd riskiqsub
```
* EITHER
```bash
pip3 install -r requirements.txt
```
* OR
```bash
pip install -r requirements.txt
```

## Help Banner
```bash
$ python .\riskiq_subfinder.py -h

d8888b. d888888b .d8888. db   dD d888888b  .d88b.  .d8888. db    db d8888b. 
88  `8D   `88'   88'  YP 88 ,8P'   `88'   .8P  Y8. 88'  YP 88    88 88  `8D
88oobY'    88    `8bo.   88,8P      88    88    88 `8bo.   88    88 88oooY'
88`8b      88      `Y8b. 88`8b      88    88    88   `Y8b. 88    88 88~~~b.
88 `88.   .88.   db   8D 88 `88.   .88.   `8P  d8' db   8D 88b  d88 88   8D
88   YD Y888888P `8888Y' YP   YD Y888888P  `Y88'Y8 `8888Y' ~Y8888P' Y8888P'
                            By MAAYTHM 🥷 (https://github.com/MAAYTHM)

a small python3 wrapper tool around 'https://community.riskiq.com' website to find subdomains
- By MAAYTHM (https://github.com/MAAYTHM)

Flags :-
    * -h  --help      Print this help message.
    * -f  --file      Take input from file (.txt).
    * -t  --timeout   Timeout for requests (in seconds) (default: 10 seconds).
    * --conf          Path to file which contains credentials for 'https://community.riskiq.com/' (.json) (default - './riskiq_subfinder.json').
    * -v  --verbose   Verbose mode for detailed error messages.
    * -q  --quiet     Silent mode (Only print subdomains/error messages).

Examples :-
    * python3 riskiq_subfinder.py -h
    * python3 riskiq_subfinder.py -f anyfile.txt
    * echo 'anyting' | python3 riskiq_subfinder.py -

Note :-
    * If you want to give input from stdin then checkout example number 3 (above).
    * Export / Save email address and password of RiskIQ website (https://community.riskiq.com/login) in 'riskiq_subfinder.json'.
    * If stacktrace is not shown while using '-v', then it means the error is explained only with the single line printed with '[-] Error'.
```

## Few Examples
> **Simple Input**
![1.png](https://github.com/MAAYTHM/riskiqsub/raw/main/images/1.png)

> **File Input**
![3.png](https://github.com/MAAYTHM/riskiqsub/raw/main/images/3.png)

> **Pipe Input**
![2.png](https://github.com/MAAYTHM/riskiqsub/raw/main/images/2.png)

## Last Note
All issues / updates suggestion are welcomed.

## Disclaimer
The developer assumes no liability and is not responsible for any misuse or damage caused by this program. Please use responsibly.
