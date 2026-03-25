# Medical IT Strategy & Architecture Lab

このOrganizationは、日本における医療DXの推進と、次世代の医療ITガバナンスの構築を目指した垂直統合型プロジェクトの拠点です。

## 🏥 医療IT全体構想図 (The 4 Pillars)

```mermaid
graph TD
    subgraph Governance ["🛡️ IT Governance (L4)"]
        Infra["medical-it-infrastructure<br/>(3省2ガイドライン / AWS / Docker)"]
    end

    subgraph Business ["💼 Management & ERP (L3)"]
        ERP["medical-erp-system<br/>(Spring Boot / Angular / 物品・会計管理)"]
    end

    subgraph Interface ["🌐 Interoperability (L1)"]
        GW["medical-interop-gateway<br/>(HL7 FHIR / API連携 / 地域連携)"]
    end

    subgraph Value ["📈 Clinical Analytics (L2)"]
        Anly["medical-clinical-analytics<br/>(Python / 診療データ利活用 / 意思決定支援)"]
    end

    Infra --> ERP
    ERP <--> GW
    GW <--> Anly
    Anly -.-> ERP
