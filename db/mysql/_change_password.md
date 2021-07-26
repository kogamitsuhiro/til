# rootのパスワード変更

## mysql@8.0
xxxxを置換する。
```
mysql> FLUSH PRIVILEGES;
mysql> ALTER USER 'root'@'localhost' IDENTIFIED BY 'xxxx';
```
