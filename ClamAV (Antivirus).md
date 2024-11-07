### Installation:
1. **Install `ClamAV` (Debian/Ubuntu):**
   ```bash
   sudo apt-get install clamav clamav-daemon
   ```

2. **Install `ClamAV` (CentOS/Fedora):**
   ```bash
   sudo yum install clamav clamav-update
   ```

### Basic Commands:

1. **Update Virus Definitions:**
   ```bash
   sudo freshclam
   ```

2. **Scan a Directory:**
   - Scan `/home/user` directory:
     ```bash
     sudo clamscan -r /home/user
     ```

3. **Scan and Remove Infected Files:**
   - Scan `/home/user` and automatically delete infected files:
     ```bash
     sudo clamscan -r --remove /home/user
     ```

4. **Log Scan Results to a File:**
   - Save results to `scan_log.txt`:
     ```bash
     sudo clamscan -r /home/user > /path/to/scan_log.txt
     ```

5. **Run in Quiet Mode (Suppress Clean Messages):**
   ```bash
   sudo clamscan -r -i /home/user
   ```

### Additional Options:

1. **Scan Entire System:**
   ```bash
   sudo clamscan -r /
   ```

2. **Check Only for Infected Files:**
   ```bash
   sudo clamscan -r -i /home/user
   ```

3. **Schedule Daily Scans (using `cron`):**
   - Edit crontab to schedule a daily scan:
     ```bash
     sudo crontab -e
     ```
   - Add this line for a daily scan at midnight:
     ```bash
     0 0 * * * /usr/bin/clamscan -r /home/user --quiet --log=/path/to/scan_log.txt
     ```
