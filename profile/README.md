# Medical IT Strategy & Architecture Lab

医療 DX の推進と、次世代の医療 IT ガバナンス構築を目的とした垂直統合型プロジェクトの拠点です。

## 🏥 医療 IT 垂直統合モデル (The 5 Pillars)

本 Organization は、ガバナンスから実装までを 5 つのレイヤーで構造化しています。

```mermaid
graph TD
    subgraph Control ["🛰️ Control Tower"]
        DOT[".github<br/>(全体構想・戦略管理)"]
    end

    subgraph Governance ["🛡️ IT Governance (L4)"]
        Infra["medical-it-infrastructure<br/>(3省2ガイドライン / セキュリティ基盤)"]
    end

    subgraph Business ["💼 Management & ERP (L3)"]
        ERP["medical-erp-system<br/>(Spring Boot / Angular / 業務実装)"]
    end

    subgraph Interface ["🌐 Interoperability (L1)"]
        GW["medical-interop-gateway<br/>(HL7 FHIR / API 連携標準)"]
    end

    subgraph Value ["📈 Clinical Analytics (L2)"]
        Anly["medical-clinical-analytics<br/>(Python / 診療データ利活用案)"]
    end

    DOT --> Infra
    Infra --> ERP
    ERP <--> GW
    GW <--> Anly
