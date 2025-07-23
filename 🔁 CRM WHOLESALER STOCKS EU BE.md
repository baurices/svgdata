# 🔁 Transfert de Fichier : stocks.be@ceva.com 

## 🟦 Source
- **Mail** : `stocks.be@ceva.com`


## 🟩 Destination
- **Name** : `Talend v7`
- **Directory** :  /project_resources/dev/CVALUE/data/in/be/STOCKS/

## Miscellanous
- **Rules** :CRM_WHOLESALER_STOCKS_EU_GB_DEV // CRM_WHOLESALER_STOCKS_EU_GB
- **Talend plan** : CRM_WHOLESALER_STOCKS_EU_BE

## 🔐 Protocole
- **Protocoles utilisé** : `sftp and r66`

## ➡️ Flow

```mermaid
stateDiagram-v2
direction LR
Powerautomate --> Waarp_Gateway: sftp
Waarp_Gateway --> Azure_PROD: r66
Azure_PROD --> corsrvtrfp01: r66
corsrvtrfp01 --> corsrvappbip01: r66
corsrvtrfp01 --> corsrvappbid01: r66

note left of Powerautomate
Mail sent to stocks.be\@ceva.com with an attachment (xlsx file mandatory)
end note
```