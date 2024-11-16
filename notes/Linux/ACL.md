# Account Management and ACL

- https://linux.vbird.org/linux_basic/centos7/0410accountmanager.php
- https://www.youtube.com/watch?v=A_hymh5diqA&list=WL&index=73

## Access Control List (ACL)

Provides more specific file/directory authentication for user/group/other

### Get file access control lists

- Get ACL list of file FILE
  - `getfacl FILE`

### Set file access control lists

- Add user/group/other USER/GROUP/OTHER with `rwx` to ACL list of file FILE
  - `setfacl -m u:USER:rwx FILE`
  - `setfacl -m g:GROUP:rwx FILE`
  - `setfacl -m o:OTHER:rwx FILE`
- Remove user/group/other USER/GROUP/OTHER from ACL list of file FILE
  - `setfacl -x u:USER FILE`
  - `setfacl -x g:GROUP FILE`
  - `setfacl -x o:OTHER FILE`
- Remove all ACL list of file FILE
  - `setfacl -b FILE`
- Remove all ACL list within directory DIR recursively
  - `setfacl -bR DIR`
- Set default ACL list for user USER within directory DIR
  - `setfacl -m d:u:USER:rx DIR`
- Set maximal authentication to `x` for ACL list of file FILE
  - `setfactl -m m:x FILE`

## Pluggable Authentication Modules (PAM)
