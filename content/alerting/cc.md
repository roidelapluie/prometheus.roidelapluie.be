---
title: "Sending emails with cc:"
date: 2018-05-03T09:44:53+02:00
---

To send an email with a CC: in alertmanager, it is not sufficient to add a CC: header.

```
receivers:
- name: my-receiver
  email_configs:
  - to: 'one@foo.com'
    headers:
      subject: 'my subject'
      CC: 'two@bar.com'
```

You also need to add the CC: address to the to: field and explicitely add a to:
field.

```
receivers:
- name: my-receiver
  email_configs:
  - to: 'one@foo.com,two@bar.com'
    headers:
      subject: 'my subject'
      To: 'one@foo.com'
      CC: 'two@bar.com'
```

To send a mail in `BCC:`, overwrite the To: header and add the BCC addresses to
the to: field:

```
receivers:
- name: my-receiver
  email_configs:
  - to: 'one@foo.com,three@foo.com'
    headers:
      subject: 'my subject'
      To: 'one@foo.com'
```
