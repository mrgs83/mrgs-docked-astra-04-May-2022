## Adding Astra Docker Template on Unraid OS
```bash
curl -L https://raw.githubusercontent.com/mrgs83/mrgs-docked-astra-04-May-2022/main/astra-04-May-2022-template.xml -o /boot/config/plugins/dockerMan/templates-user/my-astra-04-May-2022-template.xml
```
### Prerequisites
Before deploying Astra, ensure you have the necessary license and configuration files available:

- **License File:** Ensure you have a valid Astra license and place it at the following path on your Unraid server:
  ```
  /mnt/user/appdata/astra/license.txt
  ```
- **Configuration File:** To ensure smooth operation when running multiple Astra containers, each container should have its own unique configuration folder. Place the `astra.conf` file in a unique folder for each container at the following path on your Unraid server:
  ```
  /mnt/user/appdata/astra/[your-unique-name]/astra.conf
  ```
  Replace `[your-unique-name]` with a descriptor or name that is relevant to your setup. For example:
  - For a DVB-T setup, use `astra-DVB-T`, resulting in the path:
    ```
    /mnt/user/appdata/astra/astra-DVB-T/astra.conf
    ```
  - For a DVB-S setup, use `astra-DVB-S`, leading to the path:
    ```
    /mnt/user/appdata/astra/astra-DVB-S/astra.conf
    ```


### Step 1: Open Unraid Terminal
Navigate to your Unraid web interface, typically located at `http://[YourUnraidIP]`. On the bottom right of the dashboard, you should find a "Terminal" button. Click on it to open a web-based terminal.

### Step 2: Execute the Script
Copy the following command and paste it into the Unraid web terminal:

```bash
mkdir -p /mnt/user/appdata/astra/ && touch /mnt/user/appdata/astra/astra.conf && bash <(wget -qO - https://raw.githubusercontent.com/mrgs83/mrgs-docked-astra-04-May-2022/main/download_template.sh)
```
This command will download and execute the script directly, placing the Astra Docker template in the appropriate directory on your Unraid server.

### Step 3: Add the Docker Container
After successfully running the script:
- Navigate to the "Docker" tab in your Unraid web interface.
- Click on "Add Container".
- Find and select `Astra` in the "Template" dropdown menu under the "Docker Containers" section.
- Fill in the required details as per your setup needs.
- Specify the paths to your unique configuration file and license in the template fields.
- Click "Apply" to run the Astra Docker Container.

---

🔐 **Security Note:** Running scripts directly from the web is a potential security risk. Ensure that you trust the source (in this case, the GitHub repository) before executing any scripts in your environment.

🛠 **Troubleshooting:** If you face any issues or if the template doesn’t appear, check the Unraid logs for any error messages and verify the path and URL in the script are accurate.

---

This guide, which includes a section about the prerequisites for using license and configuration files, can be added to the `README.md` of your GitHub repository, ensuring users are well-informed about the setup process. Always ensure to validate file paths and instructions periodically, ensuring they are up to date with both Astra and Unraid updates.
