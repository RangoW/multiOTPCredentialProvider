# multiOTP 部署

## 开源项目  

> [multiOTP](https://github.com/multiOTP/multiOTPCredentialProvider)

## 部署步骤

1. [下载](https://download.multiotp.net/) multiOTP 服务文件，编译 Dockerfile，运行 docker 镜像，启动 OTP 验证服务 url。

    ```shell
    % docker run --mount source=multiotp-data,target=/etc/multiotp -p 80:80 -p 443:443 -p 1812:1812/udp -p 1813:1813/udp -d multiotp/multiotp-open-source
    ```

2. 在 windows 服务端，运行 multiOTP 认证器安装程序，过程中输入 OTP 验证服务 url。

3. 打开终端，切换到安装目录，创建用户并输出身份二维码。 

    ```shell
    % cd C:\Program Files (x86)\multiOTP
    % .\multiotp.exe -fastcreate username
    % .\multiotp.exe -qrcode username qrcode.png
    ```

4. 手机上下载安装 OTP 验证器：Google Authenticator，扫描二维码图片绑定用户。

5. 每次登录该服务器时，输入验证器中的 OTP 验证码即可登录。
