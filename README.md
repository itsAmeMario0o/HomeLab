# 📡 Home Lab Network Topology

```
                                +--------------------------+
                                |         INTERNET         |
                                +--------------------------+
                                             |
                                             |
                                +--------------------------+
                                |         ROUTER           |
                                +--------------------------+
                                             |
                                             |
                                +--------------------------+
                                |       ROUTER/AP          |
                                | Subnet: 192.168.86.0/24  |
                                +--------------------------+
                                             |
                                ~~~~~~~~~~~ MESH ~~~~~~~~~~~
                                             |
                                +--------------------------+
                                |          MESH AP         |
                                +--------------------------+
                                             |
                                +--------------------------+
                                |       L2 SWITCH          |
                                | Mgmt IP: 192.168.86.199  |
                                | MAC: 94:18:65:6F:C2:50   |
                                | Password: !Cre8vpw       |
                                +--------------------------+
                                             |
                                +--------------------------+
                                |         SERVER           |
                                | Mgmt IP: 192.168.86.221  |
                                | MAC: d8:9d:67:f3:4a:67   |
                                | SSH: eve / root          |
                                | Web UI: admin / eve      |
                                +--------------------------+
```

---

## 🧾 Summary of Key Addresses & Credentials

| Device      | IP Address        | MAC Address            | Credentials             |
|-------------|-------------------|-------------------------|--------------------------|
| L2 Switch   | 192.168.86.199    | 94:18:65:6F:C2:50       | Password: `!Cre8vpw`     |
| Server      | 192.168.86.221    | d8:9d:67:f3:4a:67       | SSH: `eve/root`<br>Web UI: `admin/eve` |

---

## 🧪 Usage Instructions

- **Wake Server**: Use the following command from another machine on the same LAN to wake the server:
  ```bash
  wakeonlan d8:9d:67:f3:4a:67
  ```

- **SSH into Server**: For administrative tasks, connect using:
  ```bash
  ssh eve@192.168.86.221
  ```

- **Access the Web UI**: Open **Firefox** and go to:
  ```
  http://192.168.86.221
  ```

---

## 🛠️ Troubleshooting

- **Check Total Memory**:
  ```bash
  free -h
  ```
  > You should see approximately **128G** of RAM.

- **Diagnose Faulty DIMMs** (if memory is incorrect):
  ```bash
  sudo dmidecode --type memory
  ```
  Review each module's size and status to identify any bad or missing DIMMs.
