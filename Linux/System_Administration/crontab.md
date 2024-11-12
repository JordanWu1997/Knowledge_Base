# CRON

## User

- Modify crontab jobs
  - `crontab -e`
    - `Format`: MINUTE HOUR DAY MONTH WEEK COMMAND
      - `*`: Any
      - `-`: From A to B
      - `,`: A and B
      - `/n`: Every n units
- List all crontab job
  - `crontab -l`

## System

- `/etc/crontab`
  - MINUTE HOUR DAY MONTH WEEK USERNAME COMMAND
- `/etc/cron.d/*`
- `/var/spool/cron/*`
  - Cron table for users

## anacron
