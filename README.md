## ⚠️ Deprecation Notice

As of May 2025, the [RiskIQ Community site](https://community.riskiq.com) has been discontinued and replaced by Microsoft Defender Threat Intelligence. Since the original source for subdomain data is no longer available, this tool is now deprecated and no longer functional.

**Note:**  
RiskIQ's PassiveTotal Community product has been retired, and there is no longer public access to its subdomain enumeration features. Please consider alternative sources or tools for subdomain discovery.

---

## Whats use of this tool?
To get subdomains from 'https://community.riskiq.com'. As there is no api endpoint, it uses valid credentials to login and then get subdomains.

## Why riskiqsub?
Actually I found [RiskIQ](https://community.riskiq.com) a fair source of getting subdomains and it is not included in [amass](https://github.com/OWASP/Amass) enum list (I think because of `no api support` for riskiq's subdomains functionality). Thats how this tool idea came.

## Requirement?
* python 3.x
* [RiskIQ](https://community.riskiq.com) Credentials `email`&`password`.

## Installation
```bash
git clone https://github.com/MAAYTHM/riskiqsub.git
cd riskiqsub
```
* EITHER
```bash
pip3 install -r requirements.txt
python3 riskiq_subfinder.py -h
```
* OR
```bash
pip install -r requirements.txt
python riskiq_subfinder.py -h
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
    * -v  --verbose   Verbose mode for detailed error messages.
    * -q  --quiet     Silent mode (Only print subdomains/error messages).
    * --conf          Path to file which contains credentials for 'https://community.riskiq.com/' (.json) (default - './riskiq_subfinder.json').
    * --verify        Verify the credentials for 'https://community.riskiq.com/'

Examples :-
    * python3 riskiq_subfinder.py -h
    * python3 riskiq_subfinder.py -f anyfile.txt
    * echo 'anyting' | python3 riskiq_subfinder.py -

Note :-
    * If you want to give input from stdin then checkout example number 3 (above).
    * Export / Save email address and password of RiskIQ website (https://community.riskiq.com/login) in 'riskiq_subfinder.json'.
    * If stacktrace is not shown while using '-v', then it means the error is explained only with the single line printed with '[-] Error'.
```

## Saving Credentials
* For using this tool, **Valid credentials** are needed which you can get by creating an account on [riskiq](https://community.riskiq.com/login).
* Then enter your credentials in `riskiq_subfinder.json` or create your own `custom_name.json`.
* The config JSON file should follow this format :
```python
{
    "email":"youremail@yahoo.com",
    "pass":"yourPassw0rd"
}
```
* **After saving** your credentials in proper `config file`, You can use this tool with only `--verify` flag to check that **creds are valid**.
```bash
python3 riskiq_subfinder.py --verify
```

## Few Examples
> **Simple Input**
```bash
python3 riskiq_subfinder.py example.com
```
![1.png](https://github.com/MAAYTHM/riskiqsub/raw/main/images/1.png)

> **File Input**
```bash
python3 riskiq_subfinder.py -f target.txt
```
![3.png](https://github.com/MAAYTHM/riskiqsub/raw/main/images/3.png)

> **Pipe Input**
```bash
echo example.com | python3 riskiq_subfinder.py -
```
![2.png](https://github.com/MAAYTHM/riskiqsub/raw/main/images/2.png)

## Last Note
* Ignore any error like :
```diff
- safeurl 0.0.7 requires requests==2.7.0, but you have requests 2.28.1 which is incompatible.
```
* All issues / updates suggestion are welcomed.

## Disclaimer
The developer assumes no liability and is not responsible for any misuse or damage caused by this program. Please use responsibly.
