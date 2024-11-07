### Installation:
1. **Install `chkrootkit` (Debian/Ubuntu):**
   ```bash
   sudo apt-get install chkrootkit
   ```

2. **Install `chkrootkit` (CentOS/Fedora):**
   ```bash
   sudo yum install chkrootkit
   ```

### Basic Commands:

1. **Run a Full System Check:**
   ```bash
   sudo chkrootkit
   ```

2. **Check Specific Rootkits (e.g., `suckit`):**
   ```bash
   sudo chkrootkit suckit
   ```

3. **Run in Quiet Mode (suppress clean messages):**
   ```bash
   sudo chkrootkit -q
   ```

4. **Save Results to a File:**
   ```bash
   sudo chkrootkit > /path/to/output.txt
   ```

5. **Run in Expert Mode (detailed output):**
   ```bash
   sudo chkrootkit -x
   ```

### Additional Options:

1. **List All Tests:**
   ```bash
   sudo chkrootkit -l
   ```

2. **Update chkrootkit:**
   - Download and compile the latest version:
     ```bash
     wget ftp://ftp.pangeia.com.br/pub/seg/pac/chkrootkit.tar.gz
     tar -xzf chkrootkit.tar.gz
     cd chkrootkit-*
     make sense
     ```
