# bakufuの公開配布物

このリポジトリは、bakufuのインストーラとLinux向けの署名付き配布元だけを公開します。製品のソースコードや開発中の成果物は置きません。

正式版ごとのDMG、NSIS形式、MSI形式、deb、AppImageは[Releases](https://github.com/bakufu-dev/bakufu-releases/releases)から取得できます。

## Linuxへaptで入れる

最初に、bakufuの配布物だけを信頼する公開鍵と配布元を登録します。

```bash
curl -fsSL https://bakufu-dev.github.io/bakufu-releases/apt/bakufu-archive-keyring.gpg \
  | sudo tee /usr/share/keyrings/bakufu-archive-keyring.gpg >/dev/null

echo "deb [arch=amd64 signed-by=/usr/share/keyrings/bakufu-archive-keyring.gpg] https://bakufu-dev.github.io/bakufu-releases/apt stable main" \
  | sudo tee /etc/apt/sources.list.d/bakufu.list >/dev/null

sudo apt update
sudo apt install bakufu
```

以後は、通常の更新と同じ入口から新しい正式版へ更新できます。

```bash
sudo apt update
sudo apt upgrade bakufu
```

初回の正式版が発行されるまでは、Releasesとapt配布元は空です。

bakufuの公開インストーラとLinux配布元
