# Answers to Part 3

Add your answers to the questions in Part 3, Step 2 below. 

## Vulernability Remediation:
### Vulnerability 1: 
1. Which package or library are you addressing?
Pillow (Python Imaging Library fork) v9.4.0
2. Which CVE is linked to this vulnerability?
CVE-2023-50447. Pillow through 10.1.0 allows arbitrary code execution through `PIL.ImageMath.eval` via the `environment` parameter.
3. What remediation steps do you suggest?
Users should upgrade Pillow to 10.2.0 ir higher, rebuild the container image and re-run the scans.
### Vulnerability 2:
1. Which vulnerability are you addressing?
PyJWT v2.4.0
2. Which CVE is linked to this vulnerability?
CVE-2026-102268. In PyJWT versions before 2.14.0, `is_pem_format` in `jwt/utils.py` does not recognize every PEM representation the `cryptography` loader accepts. An attacker can use the public key to forge validly signed HMAC tokens, allowing for authentication bypass.
3. What remediation steps do you suggest? 
Users should upgrade to 2.14.0 or later, rotate signing keys, and restrict the accepted algorithms in the jwt call.