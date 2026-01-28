## Storage & Security

This section describes how secure storage, access control, and event-based automation were implemented
for the Azure Fabric NYC Taxi Medallion Pipeline.

The design follows cloud security best practices, including least-privilege access, RBAC,
and secure data ingestion from Azure Data Lake into Microsoft Fabric.

---

## Storage Architecture

- **Azure Data Lake Storage Gen2 (ADLS Gen2)** is used as the raw landing zone.
- A dedicated container (`raw-landing`) stores incoming NYC Taxi data files.
- Hierarchical namespace is enabled to support analytics workloads.
- Storage is configured as **private**, with no anonymous public access.

**Purpose:**
- Acts as the system-of-record for raw data ingestion
- Decouples storage from compute
- Supports scalable and event-driven ingestion into Microsoft Fabric

---

## Access Control & RBAC

Role-Based Access Control (RBAC) is implemented to secure the storage account and event-based workflows.

### Assigned Roles:
- **Owner** – Subscription-level ownership for administration
- **Storage Blob Data Contributor** – Read/write access to blob containers
- **Storage Blob Data Owner** – Full control over blob data
- **EventGrid Contributor** – Allows creation and management of Event Grid topics
- **Fabric Event Grid Creator** – Enables integration between Azure Event Grid and Microsoft Fabric
- **Logic App Contributor** – Supports automation workflows

**Security Principles Applied:**
- Least privilege access
- Role separation between storage, automation, and analytics
- No shared keys or hard-coded credentials

---

## Event-Based Automation

- Azure **Event Grid** is configured to listen for `BlobCreated` events.
- Events are filtered to trigger only when new files arrive in the `raw-landing` container.
- These events are linked to Microsoft Fabric to support automated pipeline execution.

**Benefit:**
- Enables near–real-time ingestion
- Eliminates manual pipeline execution
- Improves operational efficiency and reliability

---

## Security Best Practices Applied

- Secure transfer required (HTTPS only)
- Blob anonymous access disabled
- RBAC used instead of access keys
- Centralized identity management via **Microsoft Entra ID**
- Separation of raw, curated, and analytics layers (Bronze / Silver / Gold)

---

## Summary

The storage and security design ensures that:
- Data ingestion is secure and automated
- Access is tightly controlled using Azure RBAC
- The pipeline aligns with enterprise cloud governance standards
- The solution is production-ready and scalable
