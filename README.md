# glueops-loki-log-exporter-to-s3

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![AppVersion: v0.0.1](https://img.shields.io/badge/AppVersion-v0.0.1-informational?style=flat-square)

GlueOps Helm Chart for exporting logs from loki to AWS S3

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| aws_accessKey | string | `"nil"` | Part of `loki_log_exporter` output from terraform-module-cloud-multy-prerequisites: https://github.com/GlueOps/terraform-module-cloud-multy-prerequisites |
| aws_region | string | `"nil"` | Should be the same `primary_region` you used in: https://github.com/GlueOps/terraform-module-cloud-multy-prerequisites |
| aws_secretKey | string | `"nil"` | Part of `loki_log_exporter` output from terraform-module-cloud-multy-prerequisites: https://github.com/GlueOps/terraform-module-cloud-multy-prerequisites |
| captain_domain | string | `"nil"` | The Route53 subdomain for the services on your cluster. It will be used as the suffix url for argocd, grafana, vault, and any other services that come out of the box in the glueops platform. Note: you need to create this before using this repo as this repo does not provision DNS Zones for you. This is the domain you created through: https://github.com/GlueOps/terraform-module-cloud-multy-prerequisites |
| company_key | string | `"nil"` | The company or tenant key |
| cron_expression | string | `"0 */6 * * *"` | The cron expression for the log exporter to s3. Default is every 6 hours. |
| loki_addr | string | `"nil"` | The loki address. This is the same as the loki-gateway service in the glueops-core-loki namespace. You can find this by running: `kubectl get svc -n glueops-core-loki` |
