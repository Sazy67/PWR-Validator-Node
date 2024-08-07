
### **PWR Chain Validator Node & RPC Node Kurulum Rehberi**

### **Validator Node Guide**


#### **Minimum Gereksinim..**:
- **CPU**: 1 vCPU
- **Memory**: 1 GB RAM
- **Disk**: 25 GB HDD or higher
- **Open TCP Ports**: 8231, 8085
- **Open UDP Port**: 7621

#### **Başlangıç**:

1. **Server Güncelleştirme**: 
   ```bash
   sudo apt update
   ```

2. **Java Yükleme**: 
   ```bash
   apt install openjdk-19-jre-headless
   ```

3. **Node yazılım ve konfig yükleme**:
   ```bash
   wget https://github.com/pwrlabs/PWR-Validator-Node/raw/main/validator.jar
   wget https://github.com/pwrlabs/PWR-Validator-Node/raw/main/config.json
   ```

4. **Şifre Belirleme**:
   ```bash
   sudo nano password
   ```
   - Şifre Gir.
   - `Ctrl + x`  ile Kapat.
   - Press `Y`   ile Kaydet
  
5.  **Node key girme**:
   chorome kurduğunuz pwr wallet  key lerini  içeriya aktarmamız gerekiyor.
    <private key here> yazan yere  keyiniz  password yazan yere  bi önceki adımda belirlediğimiz şifremiz. 
[PWR Browser Wallet](https://chromewebstore.google.com/u/3/detail/pwr-wallet/kennjipeijpeengjlogfdjkiiadhbmjl)
   ```bash
   sudo java -jar validator.jar --import-key <private key here> password
   ```

7. **Node Başlatma**:

    `<YOUR_SERVER_IP>`  yazan yeri kendi server ip adresi ile değiştirin.
   ```bash
   sudo java -jar validator.jar password <YOUR_SERVER_IP> --compression-level 0
   ```

8. **Adres Bulma  Yöntemlerden biri.**:
     ```
     curl localhost:8085/address/
     ```

9. **Testnet coin**:

   - Başlangıçta düğümünüz blockchain ile senkronize olacak ancak stake edilmiş PWR Coin'lere sahip olana kadar doğrulayıcı sorumluluklarını üstlenmeyecektir.
   
   - Staking için yeterli PWR Coin elde etmek için [Discord sunucumuzda test ağı doğrulayıcısı olmak için başvurun](https://discord.gg/DJkcuy9SAg). Onaylandıktan sonra, 100.000 PWR stake etmek için discord botumuzu kullanabilirsiniz.
   
   - Coinlerinizi talep ettikten sonra, düğümünüz doğrulayıcı olarak kaydolmak için bir işlem başlatacaktır.
   - 
10. **Arka planda çalıştırmak için**:
 'Screen -S  PWR   komutuda kullanabilirsiniz.

    ```bash
    sudo java -jar validator.jar password <YOUR_SERVER_IP> --compression-level 0
    ```

Tebrikler  PWR Chain validator node Kurulumu Gerçekleştirdiniz.
