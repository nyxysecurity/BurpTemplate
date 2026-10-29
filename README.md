# Burp Template

A minimal starting point for writing Burp Suite scanner extensions in Python (Jython, Burp Extender API).

## What it does
- Registers a passive scanner check (`IScannerCheck`) with Burp.
- Includes a helper that splits each response into headers and body for inspection.
- Includes a stubbed `IScanIssue` class for reporting findings, plus duplicate-issue handling.
- Ships with an example check, commented out, that flags **version 1 UUIDs** in responses. Version 1 UUIDs are time-based and predictable, which can enable IDOR and enumeration attacks against APIs.

## Usage
1. In Burp, go to **Extensions → Extensions settings → Python environment** and point it at a Jython standalone JAR.
2. Go to **Extensions → Installed → Add**, choose **Python**, and select `burptemplate.py`.
3. Copy the file, rename the extension, and put your detection logic in `doPassiveScan` (or `doActiveScan`).
