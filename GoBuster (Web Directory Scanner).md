1. **Basic Directory Brute force:**
   - Perform a simple directory brute-force attack:
     ```bash
     gobuster dir -u <target-url> -w <wordlist.txt>
     ```

2. **Scan with Specific Extension:**
   - Scan a URL and look for specific file extensions (e.g., `.php`, `.html`):
     ```bash
     gobuster dir -u <target-url> -w <wordlist.txt> -x .php,.html
     ```

3. **Scan with Custom Status Codes:**
   - Scan and filter by specific status codes, e.g., filtering only 200 responses:
     ```bash
     gobuster dir -u <target-url> -w <wordlist.txt> -s 200
     ```

4. **Set a Timeout for Requests:**
   - Set a custom timeout value (in seconds):
     ```bash
     gobuster dir -u <target-url> -w <wordlist.txt> -t 50
     ```
     (`-t` specifies the number of threads to use)

5. **Scan with Multiple Threads:**
   - Increase the number of concurrent threads for faster scanning:
     ```bash
     gobuster dir -u <target-url> -w <wordlist.txt> -t 100
     ```

6. **Show Only Status Codes:**
   - Show only the status codes of the responses:
     ```bash
     gobuster dir -u <target-url> -w <wordlist.txt> -s 200,301
     ```

7. **Fuzzing Files with File Extensions:**
   - Scan for files, such as `robots.txt`, `index.php`, or `config.php`:
     ```bash
     gobuster dir -u <target-url> -w <wordlist.txt> -x .txt,.php,.config
     ```

8. **Start from Specific Directory:**
   - Start brute-forcing from a specific directory:
     ```bash
     gobuster dir -u <target-url>/path/ -w <wordlist.txt>
     ```

9. **DNS Subdomain Brute force:**
   - Perform a subdomain brute-force attack:
     ```bash
     gobuster dns -d <domain.com> -w <wordlist.txt>
     ```

10. **Use HTTPS (Secure Connection):**
    - Perform the brute-force scan over HTTPS:
      ```bash
      gobuster dir -u https://<target-url> -w <wordlist.txt>
      ```

11. **Save Output to a File:**
    - Save the results to a file:
      ```bash
      gobuster dir -u <target-url> -w <wordlist.txt> -o output.txt
      ```
