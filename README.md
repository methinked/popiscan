# PopiScan — Client-Side POPIA Compliance Scanner

> **Domain:** [popiscan.co.za](https://popiscan.co.za)  
> **Architecture:** 100% Client-Side Browser-First Execution. Zero biometrics, photos, or consent metadata ever leave the user's browser or touch a remote server.

---

## 🛡️ Executive Summary & Legal Grounding

Under South Africa's **Protection of Personal Information Act (Act 4 of 2013)**, processing biometric information and photographs of individuals—especially minors (**Section 35: General Prohibition on Processing Personal Information of Children**)—carries strict legal consent obligations and severe non-compliance penalties.

Traditional photo management and facial recognition platforms require uploading event albums to remote cloud servers. This introduces:
1. **Third-Party Data Breach Risk** (Section 19 Security Measures).
2. **Unlawful Cross-Border Data Transfers** (Section 72).
3. **Biometric Vault Liability** for schools, churches, sports clubs, and event organizers.

**PopiScan** completely inverts this paradigm:
- **Zero Cloud Ingestion:** The browser sandbox executes face detection, subject matching, and privacy redaction in real time using client-side JavaScript and HTML5 Canvas.
- **Offline & Private:** Photos loaded via drag-and-drop or local folder selection are processed entirely in browser memory (`RAM`).
- **Instant Compliance Redaction:** Any detected non-consenting individual can be immediately sanitized (blurred, pixelated, or censored with a black privacy bar) on canvas prior to public distribution.
- **Verifiable Audit Trail:** Generates a Section 19 POPIA Compliance Verification Certificate and exportable JSON audit log without retaining raw biometrics.

---

## 🔑 Core Features

1. **POPIA Consent Registry (Roster)**:
   - Maintains records of subjects (students, staff, event attendees).
   - Configurable status: `CONSENTED` (Full media release), `RESTRICTED` (Opted-out / Do Not Photograph), or `INTERNAL_ONLY`.
   - Local persistence via browser `localStorage`.

2. **Batch Photo Scanner**:
   - Drag-and-drop batch audit of event photos.
   - Real-time client-side face detection via Haar-cascade computer vision.
   - Categorizes photos as `✅ Compliant`, `🚨 POPIA Violation`, or `⚠️ Needs Review`.

3. **Interactive Photo Inspector & Redactor**:
   - High-resolution canvas inspection with bounding boxes.
   - One-click privacy redaction: **Blur**, **Pixelate**, or **Black Bar**.
   - Download sanitized, compliant images directly from canvas.

4. **POPIA Audit Certificate & Legal Disclaimers**:
   - Printable verification certificate proving photos were audited against registered consent forms.
   - Built-in legal disclaimer and limitation of liability documentation.

---

## 🚀 Deployment & Containerization

Lightweight Alpine Nginx container:

```bash
# Start container
docker compose up -d

# Check status
docker compose ps

# View access logs
docker compose logs -f
```

---

## 📄 License & Privacy Notice

Distributed under the MIT License. PopiScan is an open-source privacy compliance aid and does not provide formal legal counsel. All verification processing occurs strictly on the client device.
