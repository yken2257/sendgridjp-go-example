sendgridjp-go-example
=====================

本コードは[SendGrid公式Goライブラリ](https://github.com/sendgrid/sendgrid-go)の利用サンプルです。
現在、[smtpapi-go](https://github.com/sendgrid/smtpapi-go)がUnicodeエスケープされていないため、SubstitutionやSectionに日本語を指定した場合文字化けします。
日本語が必要な場合smtpapi-goが返すJsonStringをUnicodeエスケープするよう修正して利用してください。

## 使い方

```bash
git clone http://github.com/sendgridjp/sendgridjp-go-example.git
cd sendgridjp-go-example
cp config.json.example config.json
# config.jsonファイルを編集してください
go get github.com/sendgrid/sendgrid-go
go install main
./bin/main
```

## config.jsonファイルの編集
config.jsonファイルは以下のような内容になっています。

```json
{
  "SENDGRID_USERNAME": "your_username",
  "SENDGRID_PASSWORD": "your_password",
  "TOS": ["you@youremail.com","friend1@friendemail.com","friend2@friendemail.com"],
  "FROM": "you@youremail.com",
}
```
SENDGRID_USERNAME:SendGridのユーザ名を指定してください。  
SENDGRID_PASSWORD:SendGridのパスワードを指定してください。  
TOS:宛先をカンマ区切りで指定してください。  
FROM:送信元アドレスを指定してください。  

