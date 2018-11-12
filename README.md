# iOS-企业包服务

- 企业版分发的plist、icon、ipa下载url必须是https协议。

- 下载配置文件 ： manifest.plist

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>items</key>
    <array>
        <dict>
            <key>assets</key>
            <array>
                <dict>
                    <key>kind</key>
                    <string>software-package</string>
                    <key>url</key>
                    <string>https://www.spark.com/iOS-enterprise/demo.ipa</string>
                </dict>
                <dict>
                    <key>kind</key>
                    <string>display-image</string>
                    <key>url</key>
                    <string>https://www.spark.com/iOS-enterprise/image-512x512.png</string>
                </dict>
                <dict>
                    <key>kind</key>
                    <string>full-size-image</string>
                    <key>url</key>
                    <string>https://www.spark.com/iOS-enterprise/image-57x57.png</string>
                </dict>
            </array>
            <key>metadata</key>
            <dict>
                <key>bundle-identifier</key>
                <string>com.demo.enterprise</string>
                <key>bundle-version</key>
                <string>1.0.0</string>
                <key>kind</key>
                <string>software</string>
                <key>title</key>
                <string>Demo</string>
            </dict>
        </dict>
    </array>
</dict>
</plist>  

```


- 安装协议

itms-services://?action=download-manifest&amp;url=https://www.example.com/apps/download/mainifest.plist

直接将此链接复制到Safari或者在App内直接openURL:是可以直接安装的。

做一个html下载页面。

注：客户端对这个文件会有缓存，如安装不成功。可以将.plist文件改个名字试试！！！

注意：

mime

在服务器的配置中需在MIME下添加类型：

l  .ipa application/octet-stream

l  .plist text/xml

下载路径不能超三级
