
## Brute force username and Password


```bash
ffuf -request tmp.txt -request-proto http -mode clusterbomb -w /usr/share/seclists/Passwords/pass5.txt:FUZZPASSWORD -w /usr/share/seclists/Usernames/top-usernames-shortlist.txt:FUZZUSERNAME -fs 3256
```

Learn more here: [[Jun 19, 2024]]
