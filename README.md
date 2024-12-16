# nwa-email
NWA was never that easy! 😎

Don't forget to change the data with your S-Number ;)

*Just make sure to review my commands, just in case of...*

# Step 1
Encode your username and password in base64 and store it in a notepad.

## Encode your email
```
echo -n "S2410239...@sin-lab.at" | base64 # Replace with your S-Number
```

## Encode your password
```
echo -n "l0ngpasswordsaremuchb3tters1b24" | base64
```

# Step 2
The worst part feared by everyone: send the email!

## Using openssl

```
openssl s_client -connect smtps.sin-lab.at:587 -starttls smtp -ign_eof

STARTTLS

AUTH LOGIN
[USER_BASE64_VALUE]
[PASSWORD_BASE64_VALUE]

MAIL FROM:<S2410239...@sin-lab.at> # Replace with your S-Number

RCPT TO:<tutor_nwa1@sin-lab.at>

DATA
Subject: S2410239... Authentication + secure SMTP # Replace with your S-Number
Date: Mon, 16 Dec 2024 HH:MM:SS +0000 # Just change this date to the current
Message-ID: <YYYYMMDD-HHMMSS@sin-lab.at> # Also change this date to the current

Hello dear tutor :)


. # Don't forget this ".", without it you'll be stuck forever...
```

# Step 3
Enjoy your good grade and give me a Baguette. 🥖💫
