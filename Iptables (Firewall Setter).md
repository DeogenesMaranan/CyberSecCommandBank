### Basic `iptables` Commands:

1. **Check Current Rules:**
   - View the current firewall rules:
     ```bash
     sudo iptables -L
     ```

2. **List All Rules with Line Numbers:**
   - View rules with line numbers (useful for removing specific rules):
     ```bash
     sudo iptables -L --line-numbers
     ```

3. **Flush All Rules:**
   - Remove all existing rules:
     ```bash
     sudo iptables -F
     ```

4. **Set Default Policy (DROP or ACCEPT):**
   - Set default policy to drop all incoming traffic:
     ```bash
     sudo iptables -P INPUT DROP
     ```
   - Set default policy to accept all incoming traffic:
     ```bash
     sudo iptables -P INPUT ACCEPT
     ```

5. **Allow All Incoming and Outgoing Traffic:**
   - Accept all incoming and outgoing traffic:
     ```bash
     sudo iptables -P INPUT ACCEPT
     sudo iptables -P OUTPUT ACCEPT
     sudo iptables -P FORWARD ACCEPT
     ```

6. **Drop All Incoming and Outgoing Traffic:**
   - Drop all incoming and outgoing traffic (not recommended unless you want to completely block all traffic):
     ```bash
     sudo iptables -P INPUT DROP
     sudo iptables -P OUTPUT DROP
     sudo iptables -P FORWARD DROP
     ```

### Adding Rules:

1. **Allow Incoming Traffic on a Specific Port:**
   - Allow incoming traffic on port 80 (HTTP):
     ```bash
     sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
     ```
   - Allow incoming traffic on port 443 (HTTPS):
     ```bash
     sudo iptables -A INPUT -p tcp --dport 443 -j ACCEPT
     ```

2. **Block Incoming Traffic on a Specific Port:**
   - Block incoming traffic on port 22 (SSH):
     ```bash
     sudo iptables -A INPUT -p tcp --dport 22 -j DROP
     ```

3. **Allow Incoming Traffic from a Specific IP:**
   - Allow incoming traffic from a specific IP address (e.g., `192.168.1.100`):
     ```bash
     sudo iptables -A INPUT -s 192.168.1.100 -j ACCEPT
     ```

4. **Allow Outgoing Traffic to a Specific IP:**
   - Allow outgoing traffic to a specific IP address:
     ```bash
     sudo iptables -A OUTPUT -d 192.168.1.100 -j ACCEPT
     ```

5. **Allow Specific Protocol (e.g., ICMP / Ping):**
   - Allow ICMP (ping) requests:
     ```bash
     sudo iptables -A INPUT -p icmp --icmp-type echo-request -j ACCEPT
     ```

### Deleting Rules:

1. **Delete a Specific Rule:**
   - To delete a rule by line number (first list the rules with `iptables -L --line-numbers`):
     ```bash
     sudo iptables -D INPUT <line-number>
     ```

2. **Delete All Rules for a Specific Chain:**
   - Delete all rules in the INPUT chain:
     ```bash
     sudo iptables -F INPUT
     ```

3. **Delete All Rules:**
   - Flush (delete) all rules in all chains:
     ```bash
     sudo iptables -F
     ```

4. **Delete a Specific Rule by Specification:**
   - Delete a rule based on the exact rule you added (e.g., block SSH):
     ```bash
     sudo iptables -D INPUT -p tcp --dport 22 -j DROP
     ```

### Saving and Restoring Rules:

1. **Save Current Rules:**
   - Save the current `iptables` rules to a file (for persistence across reboots):
     ```bash
     sudo iptables-save > /etc/iptables/rules.v4
     ```

2. **Restore Rules from a File:**
   - Restore saved rules from a file:
     ```bash
     sudo iptables-restore < /etc/iptables/rules.v4
     ```

3. **Persist iptables Rules Across Reboots (Debian/Ubuntu):**
   - Install `iptables-persistent` to ensure that rules are saved across reboots:
     ```bash
     sudo apt-get install iptables-persistent
     ```
     After installation, rules will be automatically saved and restored.

### Logging Traffic:

1. **Log Incoming Traffic (e.g., Port 80):**
   - Log incoming traffic on port 80:
     ```bash
     sudo iptables -A INPUT -p tcp --dport 80 -j LOG --log-prefix "HTTP traffic: "
     ```

2. **Log All Dropped Packets:**
   - Log all dropped packets:
     ```bash
     sudo iptables -A INPUT -j LOG --log-prefix "Dropped packet: "
     ```

### Advanced Options:

1. **Limit Incoming Connections (to prevent DoS attacks):**
   - Limit incoming SSH connections to 3 attempts per minute:
     ```bash
     sudo iptables -A INPUT -p tcp --dport 22 -m state --state NEW -m recent --set
     sudo iptables -A INPUT -p tcp --dport 22 -m state --state NEW -m recent --update --seconds 60 --hitcount 3 -j REJECT
     ```

2. **Allow a Specific IP to Access All Ports (Whitelist):**
   - Allow all incoming traffic from `192.168.1.100`:
     ```bash
     sudo iptables -A INPUT -s 192.168.1.100 -j ACCEPT
     ```

3. **Block an IP Address:**
   - Block all incoming traffic from a specific IP address:
     ```bash
     sudo iptables -A INPUT -s 192.168.1.100 -j DROP
     ```

4. **Redirect Incoming Traffic (Port Forwarding):**
   - Redirect incoming traffic on port 80 to port 8080:
     ```bash
     sudo iptables -t nat -A PREROUTING -p tcp --dport 80 -j REDIRECT --to-port 8080
     ```

### NAT (Network Address Translation) and Port Forwarding:
1. **Enable NAT for Internet Sharing (Masquerading):**
   - Enable NAT for outgoing traffic:
     ```bash
     sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
     ```

2. **Port Forwarding Example (Forward Port 80 to 8080):**
   - Forward incoming traffic on port 80 to an internal IP on port 8080:
     ```bash
     sudo iptables -t nat -A PREROUTING -p tcp --dport 80 -j DNAT --to-destination 192.168.1.100:8080
     sudo iptables -A FORWARD -p tcp -d 192.168.1.100 --dport 8080 -j ACCEPT
     ```
