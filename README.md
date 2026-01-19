<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# osTicket Service Availability Issue

## 1. Scenario (Problem Statement)
Users unable to access the osTicket web interface hosted on a cloud-based server.

---

## 2. Investigation Steps (High Level)
- Verified web service status on the server
- Checked whether required services were listening on expected ports
- Reviewed application and web server logs
- Inspected firewall and network security rules
- Tested connectivity from external client

---

## 3. Key Commands Used
- `systemctl status apache2`  
  Verified web server service status.
- `ss -tuln`  
  Confirmed listening ports for web services.
- `journalctl -xe`  
  Reviewed system logs for service startup or runtime errors.
- `curl localhost`  
  Tested local web service response.

---

## 4. Root Cause
Required service port was not permitted through network security rules.

---

## 5. Resolution
Updated firewall and cloud network rules to allow inbound traffic to the web service.

---

## 6. Verification
Web interface became accessible and osTicket loaded successfully.
