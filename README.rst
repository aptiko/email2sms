================================
email2sms - email to sms gateway
================================

This Python 3 program is an smtp server that can send sms's. In order to
send an SMS, the recipient address must be ``+1234567890@sms.sms``,
where the local part is a telephone number and the host is literally
``sms.sms``.  For other recipient addresses, a smarthost is used to
forward the email as is.  The body text of any email towards
``number@sms.sms`` is sent with SMS to the number (the first 159
characters only; the subject is also ignored). The email must be encoded
in plain text; no base64 or other weirdness, or the SMS will be
unreadable.

It currently only supports sending SMS's through diamondcard.us.

Uses configuration file ``/etc/email2sms.cfg``, like this::

    [main]
    syslog_facility = local0
    listen_host = localhost
    listen_port = 2025
    smarthost_host = localhost
    smarthost_port = 25
    log_level = debug

    [diamondcard]
    acc = your_diamondcard_id
    pin = your_diamondcard_pin

© 2012-2016 Antonis Christofides

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.
