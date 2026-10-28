# Security Policy

## Supported Versions

Use this section to tell people about which versions of your project are
currently being supported with security updates.

| Version | Supported          |
| ------- | ------------------ |
| 5.1.x   | :white_check_mark: |
| 5.0.x   | :x:                |
| 4.0.x   | :white_check_mark: |
| < 4.0   | :x:                |

## Reporting a Vulnerability

Use this section to tell people how to report a vulnerability.

Tell them where to go, how often they can expect to get an update on a
reported vulnerability, what to expect if the vulnerability is accepted or
declined, etc.
SELECT 
    event_id, 
    amount, 
    currency,
    split_creator_amount, 
    split_platform_amount, 
    status, 
    source, 
    timestamp 
FROM `lexical-aileron-441914-t4.tenant_4pf_production.events_ledger`
WHERE source = 'Jarvis-intellect-LN-01'
ORDER BY timestamp DESC
LIMIT 5;
Terraform used the selected providers to generate the following execution plan:

  + google_storage_bucket.mentalarts_media_vault
  + google_storage_bucket_object.mentalarts_track_34_17
  + google_cloud_scheduler_job.jarvis_ln01_bootload

Plan: 3 to add, 0 to change, 0 to destroy.

google_storage_bucket.mentalarts_media_vault: Creating...
google_storage_bucket.mentalarts_media_vault: Creation complete after 2s [id=mentalarts-sovereign-vault-acc003]
google_storage_bucket_object.mentalarts_track_34_17: Creating...
google_storage_bucket_object.mentalarts_track_34_17: Creation complete after 1s [id=mentalarts-sovereign-vault-acc003-assets/audio/Mentalarts_(c)_(34)_(17).mp4]
google_cloud_scheduler_job.jarvis_ln01_bootload: Creating...
google_cloud_scheduler_job.jarvis_ln01_bootload: Creation complete after 1s [id=projects/lexical-aileron-441914-t4/locations/us-central1/jobs/jarvis-ln01-bootload-pulse]

Apply complete! Resources: 3 added, 0 changed, 0 destroyed.
# ==============================================================================
# JARVIS-INTELLECT / LN-01 INFRASTRUCTURE & MEDIA ASSET MANIFEST
# Target Domain: mentalartist.com | Target Vault: ACC-003
# Project ID: lexical-aileron-441914-t4 | Region: us-central1
# ==============================================================================

# 1. Cloud Storage Bucket for Encrypted Sovereign Media Assets
resource "google_storage_bucket" "mentalarts_media_vault" {
  name                     = "mentalarts-sovereign-vault-acc003"
  project                  = "lexical-aileron-441914-t4"
  location                 = "us-central1"
  force_destroy            = false
  public_access_prevention = "enforced"

  uniform_
+----------------+--------+----------+----------------------+-----------------------+---------+------------------------+---------------------+
|    event_id    | amount | currency | split_creator_amount | split_platform_amount | status  |         source         |      timestamp      |
+----------------+--------+----------+----------------------+-----------------------+---------+------------------------+---------------------+
| pulse_test_001 | 100.00 | USD      |                85.00 |                 15.00 | SETTLED | Jarvis-intellect-LN-01 | 2026-10-27 17:36:42 |
+----------------+--------+----------+----------------------+-----------------------+---------+------------------------+---------------------+
// Top-level build.gradle / settings.gradle buildscript configuration
buildscript {
    repositories {
        google()
        mavenCentral()
    }
    dependencies {
        // Google Services Gradle plugin for Firebase & GCP integration
        classpath("com.google.gms:google-services:4.4.2")
    }
}

allprojects {
    repositories {
        google()
        mavenCentral()
    }
}
implementation(platform("com.google.firebase:firebase-bom:35.1.0"))id("com.google.gms.google-services")id("com.android.application")id("com.google.gms.google-services") version "4.5.0" apply falsegcloud kms keys add-iam-policy-binding <KEY_NAME> \
    --keyring=<KEYRING_NAME> \
    --location=us-west1 \
    --member="serviceAccount:<SERVICE_ACCOUNT_EMAIL>" \
    --role="roles/cloudkms.cryptoKeyEncrypterDecrypter"
plugins {
    id("com.android.application")
    id("com.google.gms.google-services") // Applies Google services configuration
}
buildscript {
    repositories {
        google()
        mavenCentral()
    }
    dependencies {
        // Add the Google Services Gradle plugin classpath
        classpath("com.google.gms:google-services:4.4.2") // Ensure latest compatible version
    }
}

allprojects {
    repositories {
        google()
        mavenCentral()
    }
}
[Cloud Scheduler: 0 */6 * * *]
       │
       ▼
[Pub/Sub: revenue_claim_sweep]
       │
       ▼
[Serverless NEG / Cloud Run: jarvis-governance-runtime]
 ┌─────┴──────────────────────────────────────────────┐
 ▼                                                   ▼
[Firestore Ledger Lock]                  [BigQuery events_ledger]
cloudresourcemanager.googleapis.comgcloud identity auth-configs update --disable-client-signup

