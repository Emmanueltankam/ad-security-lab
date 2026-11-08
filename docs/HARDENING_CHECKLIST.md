# AD hardening checklist

Each item is checked only once it is applied **and verified** in the lab, with the evidence (screenshot, command output or audit result) added to `docs/evidence/`.

## Accounts and privileges
- [ ] Separate admin accounts from daily accounts
- [ ] Tiered administration model (tier 0 for domain controllers)
- [ ] Privileged accounts in the **Protected Users** group
- [ ] Built-in Administrator renamed and monitored
- [ ] No service account in privileged groups; long random passwords or gMSA

## Passwords and authentication
- [ ] Default domain password policy reviewed (length first, per NIST SP 800-63B)
- [ ] Fine-grained password policy for privileged accounts
- [ ] **Windows LAPS** for local administrator passwords
- [ ] NTLMv1 disabled; NTLM usage audited
- [ ] Kerberos pre-authentication required for every account
- [ ] AES encryption preferred for Kerberos service accounts

## Network protocols
- [ ] SMB signing required
- [ ] LDAP signing and channel binding enforced
- [ ] LLMNR and NetBIOS over TCP/IP disabled
- [ ] SMBv1 removed

## Logging
- [ ] Advanced audit policy (logon, Kerberos, account management, directory service access)
- [ ] Sysmon deployed with a maintained configuration
- [ ] Wazuh agents on the domain controller and the client
- [ ] Security log size increased and forwarded

## Verification
- [ ] Baseline audit score before hardening
- [ ] Audit score after hardening, with the remaining findings explained
