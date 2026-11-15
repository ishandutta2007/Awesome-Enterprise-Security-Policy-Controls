# Awesome-Enterprise-Security-Policy-Controls

## Top Enterprise Security Policy Controls Ecosystem

**Curated List of SaaS Platforms & Open-Source GitHub Projects**  
*Focused on Conditional Access, Identity Governance & Self-Hosted Zero Trust Control Planes*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Enterprise Security Policy Controls**. These tools help organizations enforce access policies, govern identities, and secure privileged sessions—covering everything from conditional access engines and identity governance platforms to zero-trust network access and self-hosted policy control planes.

**Examples** include Microsoft Entra Conditional Access, Okta Identity Governance, SailPoint IdentityIQ, CyberArk, BeyondTrust, HashiCorp Boundary, Cloudflare One, Zscaler Internet Access, and open-source alternatives like Apache Syncope and Octelium (the category leaders).

**Open-source emphasis**: This section highlights every major active project for self-hosted identity governance, open-source zero-trust access, and community-driven policy enforcement—ideal for organizations seeking data sovereignty and avoiding per-user or per-application licensing. The open-source landscape is genuinely functional: **Apache Syncope** provides enterprise IGA with provisioning and audit capabilities , **Octelium** delivers a zero-trust, secretless access platform with OPA policy-as-code , and **HashiCorp Boundary** brokers credentialless access with dynamic secret injection from Vault .

Contributions welcome! Open an PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

| Product | Description | Pricing (Starting) | Free Tier / Trial Limits |
|---------|-------------|-------------------|--------------------------|
| **[Microsoft Entra Conditional Access](https://www.microsoft.com/en-us/security/business/identity-access/microsoft-entra-id)** | **The identity-driven policy engine for Microsoft estates.** Evaluates user risk, device compliance, IP location, and application context to enforce if-then access decisions after authentication [citation:3]. Three-tier Zero Trust model: Basic (MFA + app protection for BYOD), Enhanced (risk-based + device compliance), High (managed devices only, password reset for risky sign-ins) [citation:3]. **Requires Entra ID P1/P2 licensing** for Conditional Access policies [citation:3]. | P1: **$6/user/month**; P2: **$9/user/month** (includes Identity Protection) | Free edition includes security defaults (no Conditional Access); P1/P2 required for granular policies |
| **[Okta Identity Governance](https://www.okta.com/)** | **Real-time, risk-triggered access certifications.** Combines Identity Threat Protection with Workflows to fire micro-campaigns the moment a user's risk score elevates—no waiting for quarterly reviews [citation:2]. **Identity Reconciliation** detects entitlement drift and rogue accounts created outside Okta; **Resource Collections** bundle baseline access per role; **Intra-app SoD for groups** blocks toxic combinations before approval [citation:14]. | Quote-only (Workforce + Governance add-on) | No free tier; developer edition available |
| **[SailPoint IdentityIQ](https://www.sailpoint.com/)** | **Industry-leading IGA for complex hybrid enterprises.** Centralizes identity governance across legacy, cloud, and on-prem systems. **Automated Joiner-Mover-Leaver workflows**, **access certifications with risk scoring**, **Separation of Duties enforcement**, and **audit-ready governance trails** [citation:5]. Connectors via REST, SCIM, JDBC, CSV, and LDAP [citation:5]. | Quote-only (enterprise contract) | No free tier; demo via sales |
| **[CyberArk](https://www.cyberark.com/)** | **Privileged access security with session isolation and threat analytics.** Phased maturity model: "go wide" (vault built-in accounts, rotate, isolate sessions) then "go deep" (manage service accounts, application IDs, remove hardcoded credentials, enforce least privilege) [citation:4]. **Privileged Session Manager** isolates and monitors privileged sessions; **Privileged Threat Analytics** detects anomalous behavior [citation:4]. | Quote-only (enterprise contract) | No free tier; demo via sales |
| **[BeyondTrust](https://www.beyondtrust.com/)** | **Unified privileged access with zero trust and credential injection.** **Total PASM+** combines Password Safe (vaulting + rotation), Privileged Remote Access (RDP/SSH/web), and Identity Security Insights (risk visibility across domains) [citation:10]. **Credential injection** ensures end users never see passwords; **session monitoring and recording** for audit [citation:10]. | Quote-only (enterprise contract) | No free tier; demo via sales |
| **[HashiCorp Boundary](https://www.hashicorp.com/)** | **Identity-based secure remote access without distributing credentials.** Users authenticate via IdP; Boundary authorizes access to specific targets and can **broker or inject dynamic credentials from Vault** [citation:6]. **Brokered credentials** are shown at session start; **injected credentials** are never visible to the user—the session uses them transparently [citation:6]. SSH certificates, LDAP secrets, and generic KV secrets supported [citation:6]. | Quote-only (HCP Boundary or Boundary Enterprise) | **Boundary Community Edition** free to self-host (Business Source License); session recording and credential injection require paid tiers |
| **[Cloudflare One](https://www.cloudflare.com/)** | **SASE platform with Zero Trust access, SWG, DLP, and RBI.** Replaces legacy perimeters with a unified control plane [citation:8]. Products include **Cloudflare Access** (identity-aware proxy), **Tunnel** (outbound-only connections), **CASB**, **DLP**, and **Remote Browser Isolation** [citation:8]. | Quote-only (enterprise contract) | Free tier available for small teams; Enterprise via sales |
| **[Zscaler Internet Access](https://www.zscaler.com/)** | **Cloud-native SWG with inline SSL inspection, AI-powered threat protection, and data protection.** 100% cloud-delivered with 99.999% availability SLA and <100ms proxy latency [citation:7]. **Data privacy**: content never written to disk; granular RBAC for logging; six-month or less retention by default [citation:7]. | Quote-only (edition-based: Essentials, Business, Transformation, Unlimited) | No free tier; demo via sales |

## Open-Source GitHub Projects

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[Apache Syncope](https://github.com/apache/syncope)** | [![Stars](https://img.shields.io/github/stars/apache/syncope?style=social&color=white)](https://github.com/apache/syncope/stargazers) | **The most complete open-source IGA platform for enterprise identity governance.** Apache-2.0. **Centralized IAM with user/group/role management, automated provisioning and deprovisioning workflows, RBAC, delegated administration, and audit logging** [citation:11]. **Supports LDAP, Active Directory, databases, SAML 2.0, OIDC, and SCIM** standards [citation:11]. **REST APIs** for integration and automation. Web-based admin console. **Best for organizations wanting open-source IGA** with provisioning and compliance reporting without per-identity licensing . |
| **[Octelium](https://github.com/octelium/octelium)** | [![Stars](https://img.shields.io/github/stars/octelium/octelium?style=social&color=white)](https://github.com/octelium/octelium/stargazers) | **Self-hosted zero-trust access platform with secretless access and policy-as-code.** **No notion of an "admin" user**—zero standing privileges by default . **Layer-7 awareness** enables access to HTTP APIs, SSH, Kubernetes, and PostgreSQL/MySQL **without exposing or distributing secrets** . **Policy-as-code with CEL and OPA** for per-request, attribute-based access control . **OpenTelemetry-native auditing**—every request logged and exported to SIEM . **FIDO2/WebAuthn, TOTP, and TPM 2.0** authentication built in . **Best for teams wanting a modern, Kubernetes-native zero-trust access plane** without commercial licensing . |
| **[HashiCorp Boundary (Community)](https://github.com/hashicorp/boundary)** | [![Stars](https://img.shields.io/github/stars/hashicorp/boundary?style=social&color=white)](https://github.com/hashicorp/boundary/stargazers) | **Identity-based secure remote access with credential brokering.** Community Edition free to self-host. Users authenticate via IdP; Boundary authorizes access to specific targets. Integrates with Vault for **dynamic, short-lived credentials**—database passwords, SSH certificates, and LDAP secrets generated per session and revoked on close [citation:6]. **Session recording and credential injection require paid tiers** (Business Source License, not OSI open source) . **Best for teams already using HashiCorp Vault** wanting just-in-time access without distributing static credentials . |
| **[Authelia](https://github.com/authelia/authelia)** | [![Stars](https://img.shields.io/github/stars/authelia/authelia?style=social&color=white)](https://github.com/authelia/authelia/stargazers) | **Open-source authentication and authorization server with 2FA and SSO for web applications.** Lightweight companion for protecting internal services behind a reverse proxy. **Best for homelabs and small teams** needing policy enforcement without a full IGA platform . |

### Additional Strong Open-Source Options

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[Ory Polis (BoxyHQ Jackson)](https://github.com/ory/polis)** | [![Stars](https://img.shields.io/github/stars/ory/polis?style=social&color=white)](https://github.com/ory/polis/stargazers) | **Enterprise SSO service bridging SAML/OIDC to OAuth 2.0 with SCIM 2.0 directory sync.** **Best for SaaS products needing to accept enterprise customer IdPs** without building SAML parsing from scratch . |
| **[Teleport (Community)](https://github.com/gravitational/teleport)** | [![Stars](https://img.shields.io/github/stars/gravitational/teleport?style=social&color=white)](https://github.com/gravitational/teleport/stargazers) | **Identity-aware access for SSH, Kubernetes, databases, and apps.** Replaces bastion hosts and shared SSH keys with certificate-based, short-lived access. **Community Edition free to self-host** (some features gated to paid tiers) . **Best for DevOps teams** wanting just-in-time infrastructure access . |

**Frameworks for building custom systems**: Choose **Apache Syncope** for enterprise IGA with provisioning, RBAC, and audit , **Octelium** for zero-trust, secretless access with OPA policy-as-code , or **HashiCorp Boundary** for credential-brokered remote access integrated with Vault —all without per-identity or per-application commercial licensing.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Security policy controls govern access to critical systems and privileged credentials; **policy misconfigurations can either block legitimate business or create security gaps**. Test policies in report-only/audit mode before enforcement.
- **Enterprise policy control platforms are quote-only and deeply gated by licensing tiers.** **Microsoft Entra Conditional Access requires P1/P2** ($6–$9/user/month)—the free tier lacks granular policies entirely [citation:3]. **Okta Identity Governance is an add-on** to Workforce with quote-only pricing . **SailPoint, CyberArk, and BeyondTrust are enterprise contracts** with no public rates. **Open-source alternatives have different trade-offs**: **Apache Syncope** provides IGA fundamentals (provisioning, RBAC, audit) but lacks the AI-driven risk scoring and peer-group analysis of SailPoint [citation:5][citation:11]. **Octelium** offers modern zero-trust with secretless access and OPA policies, but is newer and Kubernetes-centric . **HashiCorp Boundary Community is free** but session recording and credential injection require paid tiers—and the Business Source License is not OSI open source . **Validate whether you need IGA (Syncope), zero-trust access (Octelium, Boundary), or conditional access (Entra)** before committing.

---

**Made for identity architects, security engineers, and organizations building policy-driven access control.**  
Let's make enterprise security policy controls more open, least-privileged, and auditable.
