# Troubleshooting

Tech is complicated, tech can break.

As always, Google is your best friend here.

## CERTIFICATE_VERIFY_FAILED

One user (on a Mac, pip install of Lute) reported an error on doing image or dictionary lookups:

```
Mac OSX python ssl.SSLError: [SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed (_ssl.c:749)
```

Likely solutions are outlined in [this StackOverflow post](https://stackoverflow.com/questions/42098126/mac-osx-python-ssl-sslerror-ssl-certificate-verify-failed-certificate-verify).