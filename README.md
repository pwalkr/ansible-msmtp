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
          # Optional variables (defaults to gmail)
          msmtp_host: smtp.gmail.com
          msmtp_port: 587
          # Optional custom tls path
          tls_trust_file: /etc/ssl/certs/ca-certificates.crt
          # Specify "From" field
          msmtp_from: my name user@email
