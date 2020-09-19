# How_to_enable_repository_for_rhel
rhel,oracle linuxでepelレポジトリを有効にするための設定です。


```
# 例えばgolangの場合。
#レポジトリの公開鍵をダウンロードして、サーバーに登録する。
wget https://ftp.jaist.ac.jp/pub/Linux/Fedora/epel/RPM-GPG-KEY-EPEL-7Server
rpm --import RPM-GPG-KEY-EPEL-7Server
# 登録したので削除
rm RPM-GPG-KEY-EPEL-7Server
# レポジトリの登録を行う。
yum-config-manager --add-repo https://ftp.jaist.ac.jp/pub/Linux/Fedora/epel/7Server/x86_64
yum install -y golang
# 競合するため、golangインストール後は無効化
yum-config-manager --disable ftp.jaist.ac.jp_pub_Linux_Fedora_epel_7Server_x86_64 > /dev/null
```
