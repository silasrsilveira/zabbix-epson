<img src="[URL_da_Imagem]([https://github.com/silasrsilveira/zabbix-epson/blob/main/see%20info.png](https://github.com/silasrsilveira/zabbix-epson/blob/b85be2cc56a6d13980864f76ffbc01bc62a4f6c7/see%20info.png))" alt="Exemplo">
---

To obtain the exact OIDs for your EPSON WorkForce Pro WF-C878R printer, I recommend using an SNMP management tool, such as `snmpwalk`, to explore the printer's MIB and identify the available OIDs. Here is an example of how you can do this:

1. **Install `snmpwalk`**:
   ```bash
   sudo yum install net-snmp-utils
   ```

2. **Run `snmpwalk` to explore the MIB**:
   ```bash
   snmpwalk -v 2c -c public  .1.3.6.1.2.1.43.11.1.1.9
   ```

Replace `` with the IP address of your printer. This should list all OIDs related to toner levels.

If you need more help using `snmpwalk` or anything else, I'm here to help!

---

Let me know if there's anything else you need!
