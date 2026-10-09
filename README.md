# RSA / EC Key & CSR Generator

ブラウザだけで RSA / EC の秘密鍵と CSR (PKCS#10) を生成する、単一 HTML のツールです。
A single-file, browser-only generator for RSA / EC private keys and PKCS#10 CSRs.

## 特長 / Features
- RSA 2048 / 4096 bit、EC P-256 / P-384 / P-521
- 秘密鍵は PKCS#8 (PEM)、CSR は PKCS#10 (PEM)
- Subject Alternative Name (SAN) 対応: DNS名(ワイルドカード・IDN は punycode 変換)、IPv4 / IPv6、メール。CN の自動追加も可
- Web Crypto API を使用。サーバーへの送信はありません(CSP で外部通信も禁止)
- 外部ライブラリ・外部フォント不使用。`index.html` 1枚で動作

## 使い方 / Usage
1. `index.html` をブラウザで開く(HTTPS または `localhost` / `file://` で動作)
2. 鍵タイプと Subject 情報を入力し、生成ボタンを押す
3. 秘密鍵と CSR をコピーまたはダウンロード

## 検証 / Verify
```bash
openssl req -in request.csr -noout -verify -subject
```

## 注意 / Disclaimer
- 秘密鍵は安全に保管し、他人と共有しないでください。ページを閉じると鍵は失われます。
- 本ソフトウェアは無保証 (AS IS) で提供されます。重要な用途では OpenSSL 等の実績ある手段の利用を推奨します。
- 利用前に `index.html` の内容を確認し、信頼できる配布元から入手してください。

## License
MIT
