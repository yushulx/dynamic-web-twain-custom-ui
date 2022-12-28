# Dynamic Web TWAIN API Samples
The samples demonstrate how to use [Dynamic Web TWAIN](https://www.dynamsoft.com/web-twain/docs/info/api/Dynamsoft_WebTwainEnv.html) UI API, UI-less API and remote scan API to build web document scanning applications.

![Dynamic Web TWAIN without UI Binding](https://www.dynamsoft.com/codepool/img/2022/12/dynamic-web-twain-without-ui.png)


## Installation
```bash
npm install dwt
```

## Basic Usage
1. Get a license from [Dynamsoft Licensing Portal](https://www.dynamsoft.com/customer/license/trialLicense?product=dwt).
2. Update the license key in `index.html`.

    ```js
    Dynamsoft.DWT.ProductKey = "LICENSE-KEY";
    ```

3. Run the sample.

    ```bash
    python -m http.server
    ```


    ![Dynamic Web TWAIN UI-less API sample](https://www.dynamsoft.com/codepool/img/2022/12/dynamic-web-twain-custom-ui.gif)

## How to Deploy the Remote Scan Example
The remote scan example allows you to scan documents from any web browsers on **iOS**, **iPadOS**, **Android**, **ChomeOS**, **Raspberri Pi OS**, **Windows**, **Linux** and **macOS**.
![Dynamic Web TWAIN remote scan](https://www.dynamsoft.com/remote-scan/docs/assets/imgs/image1.png)

To make `dwt-remote.html` work:
1. Download Dynamic Web TWAIN 18.0 installer and proxy service from [Dynamsoft customer portal](https://www.dynamsoft.com/customer/download).
    
    ![Dynamsoft proxy](https://www.dynamsoft.com/codepool/img/2022/12/dynamsoft-proxy-download.png)

     - Install Dynamsoft service on Windows, Linux or macOS, and then visit `http://127.0.0.1:18625/` in your web browser to specify the host, port (E.g. `18622`) and SSL port (E.g. `18623`). You also need to check the bonjour service option to make the service discoverable on the network. 
              
     - Run `Install.cmd` as administrator to install the proxy, and then visit `http://127.0.0.1:18625/admin/proxy.html` in your web browser to specify the host, port (E.g. `80`), and SSL port (E.g. `443`). An SSL certificate is required for the proxy to work. If you don't have one, you can download a certificate provided by Dynamsoft from the [customer portal](https://www.dynamsoft.com/customer/account/certificate). One more step is to bind your IP address to a custom domain name. 
         
        ![Dynamsoft domain certificate](https://www.dynamsoft.com/codepool/img/2022/12/dynamsoft-domain-certificate.png)
    
2. Update the license key and the server URL in `dwt-remote.html`.

    ```js
    Dynamsoft.DWT.ProductKey = "LICENSE-KEY";
    var url = 'https://<YOUR-DOMAIN-GENERATED-IN-CUSTOMER-PORTAL>';
    ```
3. Run Python HTTP server and bind it to your IP address.

    ```bash
    python -m http.server 8000 --bind YOUR-IP-ADDRESS
    ```
4. Visit `http://<YOUR-IP-ADDRESS>:8000/dwt-remote.html` from any devices, such as **iPad**:

    ![Dynamic Web TWAIN UI-less API sample](https://www.dynamsoft.com/codepool/img/2022/12/remote-scan-document-network-scanner.jpg)
