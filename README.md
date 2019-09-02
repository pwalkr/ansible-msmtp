# Ansible role for msmtp mail utility

This will allow any user on a system to send mail through an external SMTP
server using `msmtp`. Common setup is to use an app password with gmail.

https://www.ansible.com/

## Usage

Clone to a role directory like `roles/msmtp` and include:

    tasks:
      - include_role:
          name: msmtp
        vars:
          # Required variables. Password is stored in plain text msmtprc, so try
          # to use an app password or other revokable token.
          msmtp_user: foo
          msmtp_password: secret_password
