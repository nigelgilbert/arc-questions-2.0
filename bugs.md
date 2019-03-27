# Arc Bug Reports

### A Bundle cannot be deployed or deleted in the DMN PageBuilder Production environment
- **Bundle name:** "Nigel's test bundle #2"
- **URL:** https://dmn.arcpublishing.com/deployments/fusion/
- **additional context:**
    - pressing `Delete` from the bundle kabob menu causes modal flash and gray overlay, but doesn't delete bundle
    - pressing `Deploy` from bundle kabob menu causes error modal
        - message: `Command failed: rm -rf /tmp/tmp.NyHBAeFJN4 rm: cannot remove ‘/tmp/tmp.NyHBAeFJN4/node_modules’: Directory not empty`
        - screenshot: