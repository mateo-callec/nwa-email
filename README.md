# NWA Emails
NWA was never that easy! 😎

⚠️ **Don't forget to change the following data with your S-Number ;)**

*Make sure to review my commands, just in case of...*

# First part, send an email (SMTP)

## Step 1
Encode your username and password in base64 and store it in a notepad.

### Encode your email
```
echo -n "S2410239...@sin-lab.at" | base64 # Replace with your S-Number
```

### Encode your password
```
echo -n "l0ngpasswordsaremuchb3tters1b24" | base64
```

## Step 2
The worst part feared by everyone: send the email!

### Using openssl

```
openssl s_client -connect smtps.sin-lab.at:587 -starttls smtp -ign_eof

STARTTLS

AUTH LOGIN
[USER_BASE64_VALUE]
[PASSWORD_BASE64_VALUE]

MAIL FROM: <S2410239...@sin-lab.at> # Replace with your S-Number

RCPT TO: <tutor_nwa1@sin-lab.at>

DATA
From: <S2410239...@sin-lab.at> # Replace with your S-Number
To: <tutor_nwa1@sin-lab.at>
Subject: S2410239... Authentication + secure SMTP # Replace with your S-Number
Date: Mon, 16 Dec 2024 HH:MM:SS +0000 # Just change this date to the current
Message-ID: <YYYYMMDD-HHMMSS@sin-lab.at> # Also change this date to the current

Hello dear tutor :)


. # Don't forget this ".", without it you'll be stuck forever...
```

# Second part, receive emails (IMAP)

## Step 1

Connect to the IMAP server:
```
openssl s_client -connect imaps.sin-lab.at:993 -ign_eof
```

## Step 2

You then need to authenticate yourself to your account:
```
a1 LOGIN "S2410239...@sin-lab.at" "l0ngpasswordsaremuchb3tters1b24" # Replace with your S-Number
```

## Step 3

Read the first email:
```
a3 FETCH 1 (BODY[HEADER] BODY[TEXT])
```

# Final part
Enjoy your good grade and give me a Baguette! 🥖💫
