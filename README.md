Windows11向けの説明です

wslとUbuntuとDockerの導入

[https://github.com/microsoft/wsl/releases](https://github.com/microsoft/wsl/releases)
から「wsl.2.6.2.0.x64.msi」のようなファイル名のファイルをダウンロード、インストール

Microsoft Storeで「Ubuntu」で検索して
「Ubuntu24.04.1 LTS」をインストール

Ubuntuのターミナルで
```bash
sudo apt update
```
```bash
sudo apt upgrade
```
```bash
curl -sSL https://get.docker.com/ | sh
```
```bash
sudo usermod -aG docker $USER
```
```bash
docker -v
```
でバージョンが確認できたらOK

%UserProfile%\.wslconfig
のファイルを手動で作成し、

```ini
[wsl2]
memory=4GB
processors=4
swap=0
localhostForwarding=true
```

memoryとprocessorsはホスト側の1/4くらいにする

Windows側のターミナルで
```powershell
wsl --shutdown
```

Ubuntu側のターミナルで
```bash
free -h
```
で設定したメモリ容量になったか確認する
