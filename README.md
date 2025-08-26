# SIEM-Log-Analysis-Case-Study
A hands-on SIEM log analysis and incident response mini-case study. Investigates a compromised Windows system using DeepBlueCLI, documenting suspicious activity, malicious executables, persistence accounts, and SOC-style findings with screenshots and commands.

# SIEM-Log-Analysis-Case-Study

## Project Objectives
Perform a SIEM log analysis and incident response mini-case study on a Windows system compromised with a Meterpreter reverse shell. Investigate logs, identify malicious activity, and document the process like a SOC report.

---

## Implemented Solutions / Investigation Steps
- Opened terminal in the lab environment.
- Ran DeepBlueCLI:
```bash
./DeepBlue.ps1 ../security.evtx
```
- Analyzed recovered Security logs (Security.evtx).
- Tracked suspicious services, executables, and account activity.
- Recorded timestamps of malicious activity.

---

## SOC Report Workflow
```mermaid
flowchart TD
    A[Start: Launch DeepBlueCLI] --> B[Analyze Security.evtx Logs]
    B --> C[Identify Suspicious Executables]
    C --> D[Detect Meterpreter Activity & Timestamps]
    D --> E[Check Suspicious Services & Accounts]
    E --> F[Track Persistence Account Creation]
    F --> G[Correlate Findings]
    G --> H[Document Results & Screenshots]
    H --> I[End: Incident Report / GitHub Case Study]
```
## Commands and Queries
| Step | Command / Query | Purpose |
|------|-----------------|---------|
| 1 | `./DeepBlue.ps1 ../security.evtx` | Open Security.evtx and list executed processes |
| 2 | Search for ‚ÄúMetasploit‚Äù in output | Identify Meterpreter activity timestamp |
| 3 | Examine service creation events | Detect suspicious service (rztbzn) |
| 4 | Filter process creation events between 10:30‚Äì10:50 | Identify malicious executable (serviceupdate.exe) |
| 5 | Look at user creation events between 11:25‚Äì11:40 | Find command used to create persistent account (`net user ServiceAct /add`) |
| 6 | Check group membership for new account | Identify local groups: Administrators, Remote Desktop Users |

## Questions and Answers

