1. **Default Script Scan:**
   - Run the default Nmap:
     ```bash
     nmap <target-ip>
     ```

2. **Scan UDP Ports:**
   - Use the `-sU` option to scan UDP ports:
     ```bash
     nmap -sU <target-ip>
     ```

3. **Scan using Stealth mode:**
   - Use the `-sS` with a TCP SYN scan:
     ```bash
     nmap -sS <target-ip>
     ```

5. **Operating System Detection:**
   - Use the `-O` option to detect the OS of the target:
     ```bash
     nmap -O <target-ip>
```

6. **Run Specific NSE Scripts:**
   - Example for HTTP vulnerabilities:
     ```bash
     nmap --script=http-vuln* <target-ip>
     ```

6. **Service Version Detection with NSE:**
   - Detect service versions using NSE:
     ```bash
     nmap -sV --script=version <target-ip>
     ```

7. **Run Vulnerability Scripts:**
   - Run vulnerability checks with a TCP SYN scan:
     ```bash
     nmap --script=vuln <target-ip>
     ```


