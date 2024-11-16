### Markdown Document for Monitoring Toner Levels of EPSON WF-C878R Printer in Zabbix

```markdown
# Monitoring Toner Levels of EPSON WF-C878R Printer in Zabbix

## OIDs for Toner Levels

- **Black toner level**:
  ```plaintext
  iso.3.6.1.2.1.43.11.1.1.9.1.1
  ```

- **Cyan toner level**:
  ```plaintext
  iso.3.6.1.2.1.43.11.1.1.9.1.2
  ```

- **Magenta toner level**:
  ```plaintext
  iso.3.6.1.2.1.43.11.1.1.9.1.3
  ```

- **Yellow toner level**:
  ```plaintext
  iso.3.6.1.2.1.43.11.1.1.9.1.4
  ```

## Creating a Template in Zabbix

1. **Create a New Template**:
   - Go to **Configuration** > **Templates**.
   - Click on **Create template**.
   - Fill in the necessary fields, such as the template name (e.g., "EPSON WF-C878R Toner Levels").

2. **Add Items to the Template**:
   - In the newly created template, go to the **Items** tab and click on **Create item**.
   - Add items for each toner level using the OIDs you obtained:

     - **Black toner level**:
       ```plaintext
       Name: Black Toner Level
       Type: SNMPv2 agent
       Key: toner.black
       OID: iso.3.6.1.2.1.43.11.1.1.9.1.1
       Type of Information: Numeric (integer)
       Units: %
       ```

     - **Cyan toner level**:
       ```plaintext
       Name: Cyan Toner Level
       Type: SNMPv2 agent
       Key: toner.cyan
       OID: iso.3.6.1.2.1.43.11.1.1.9.1.2
       Type of Information: Numeric (integer)
       Units: %
       ```

     - **Magenta toner level**:
       ```plaintext
       Name: Magenta Toner Level
       Type: SNMPv2 agent
       Key: toner.magenta
       OID: iso.3.6.1.2.1.43.11.1.1.9.1.3
       Type of Information: Numeric (integer)
       Units: %
       ```

     - **Yellow toner level**:
       ```plaintext
       Name: Yellow Toner Level
       Type: SNMPv2 agent
       Key: toner.yellow
       OID: iso.3.6.1.2.1.43.11.1.1.9.1.4
       Type of Information: Numeric (integer)
       Units: %
       ```

3. **Add Triggers (Optional)**:
   - You can add triggers to alert when toner levels are low. Go to the **Triggers** tab in the template and click on **Create trigger**.
   - Example trigger for black toner:
     ```plaintext
     Name: Low Black Toner
     Expression: {EPSON WF-C878R Toner Levels:toner.black.last()}<20
     Severity: Warning
     ```

4. **Link the Template to a Host**:
   - Go to **Configuration** > **Hosts**.
   - Select the host for the EPSON WF-C878R printer and go to the **Templates** tab.
   - Click on **Select** and add the template you created.

5. **Check the Data**:
   - After linking the template, Zabbix will start collecting data on toner levels. You can check the data in **Monitoring** > **Latest data**.

## Additional Resources

For more details on creating templates and items in Zabbix, you can refer to the official Zabbix documentation.

```

You can copy and paste this content into a Markdown file (`README.md`, for example) and add it to your GitHub repository. If you need anything else, feel free to ask!
