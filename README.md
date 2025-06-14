# OPENCTI & Connectors

Most of this is out of the box opencti from their github repository. All credit to Filigran.

Where I deverge here is with some of the connector setup for my own deployment which includes

- Mitre Att&ck
- Malware Bazaar
- URLHaus
- ThreatFox
- AlienVault OTX
- AbuseIPDB

Deployment will require extending the .env file (sample also in this repo) with some of the required configuration and api keys.

```
#abuseipdb
ABUSEIPDB_API_KEY=
CONNECTOR_ABUSEIPDB_IPBLACKLIST=
CONNECTOR_ABUSEIPDB_ID=


# AlienVault OTX Connector
CONNECTOR_OTX_ID=
ALIENVAULT_API_KEY=
ALIENVAULT_UPDATE_EXISTING_DATA=True
ALIENVAULT_BASE_URL=https://otx.alienvault.com
ALIENVAULT_INTERVAL=1
ALIENVAULT_PULSE_START_TIMESTAMP=2020-01-01T00:00:00
ALIENVAULT_REPORT_STATUS=New
ALIENVAULT_REPORT_TYPE=Internal Report
ALIENVAULT_GUESS_MALWARE=False
ALIENVAULT_GUESS_CVE=False
ALIENVAULT_EXCLUDED_PULSE_INDICATOR_TYPES=
ALIENVAULT_ENABLE_RELATIONSHIPS=True
ALIENVAULT_ENABLE_ATTACK_PATTERNS_INDICATES=True
ALIENVAULT_FILTER_INDICATORS=True
ALIENVAULT_FILTER_INDICATORS_VALID_FROM=3

# Mitre Setup
CONNECTOR_MITRE_ID=

# AbuseCH API key
ABUSECH_AUTH_KEY=

# Malware Bazar Setup
CONNECTOR_MALWAREBAZAAR_ID=

# URLHaus Setup
CONNECTOR_URLHAUS_ID=

# ThreatFox Setup
CONNECTOR_THREATFOX_ID=
```

Each connector needs to be a unique GUID value. You can generate this with

```bash
uuidgen
```

To run the instance

```
sudo docker compose up -d
```

To run or restart a specific connector

```
sudo docker compose down connector-abuseipdb-ipblacklist
sudo docker compose restart connector-abuseipdb-ipblacklist

```

To invetigate logs for connectors

```
sudo docker compose logs --since=5m connector-mitre
```

To bring the instance down

```
sudo docker compose down
```


## Documentation

You can find the detailed documentation about the Docker installation in the [OpenCTI documentation space](https://docs.opencti.io/latest/deployment/installation/#using-docker).

## Community

### Status & bugs

Currently OpenCTI is under heavy development, if you wish to report bugs or ask for new features, you can directly use the [Github issues module](https://github.com/OpenCTI-Platform/opencti/issues).

### Discussion

If you need support or you wish to engage a discussion about the OpenCTI platform, feel free to join us on our [Slack channel](https://community.filigran.io). You can also send us an email to contact@opencti.io.

## About

OpenCTI is a product designed and developed by the company [Filigran](https://filigran.io).

<a href="https://filigran.io" alt="Filigran"><img src="https://github.com/OpenCTI-Platform/opencti/raw/master/.github/img/logo_filigran.png" width="300" /></a>
