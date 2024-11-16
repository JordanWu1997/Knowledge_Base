# FTP

- https://www.fosslinux.com/58783/install-ftp-and-tftp-server-fedora.htm
- https://www.server-world.info/en/note?os=Fedora_33&p=ftp&f=1
- https://www.youtube.com/watch?v=imQ3eyljjQw

## FTP Server

### Start FTP Server

1. Install `vsftpd` as ftp server

   - Very Secure FTP (`vsftpd`)

     ```bash
     sudo dnf install vsftpd
     ```

2. Modify `vsftpd` setup

   ```bash
   vi /etc/vsftpd/vsftpd.conf
   ```

3. Enable `vsftpd`

   ```bash
   systemctl enable vsftpd
   systemctl start vsftpd
   ```

4. If firewall is running

   ```bash
   firewall-cmd --add-service=ftp --permanent
   firewall-cmd --reload
   ```

5. If SELinux is enabled

   ```bash
   setsebool -P ftpd_full_access on
   ```

## FTP Client

### FTP Client Command

- `ls`: List all files
- `cd`: Change directory
- `put`: Put local file to remote ftp server
- `get`: Get file on remote ftp server
- `mput` Put multiple local files to remove ftp server
- `mget`: Get multiple files on remote ftp server
