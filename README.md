# Appstore
> distribute application by github

通过 `Github` 的 `https` 证书来完成在线安装 `ipa`

- 可以完成流程，但是速度太慢无法使用，建议使用自有的证书来实现该功能
- 需要自行去设置**信任证书**



#### 流程

1. 创建一个**公开的仓库**用于管理 `ipa` 文件 & `plist` 文件

2. 更新 `plist` 文件的信息

   ```html
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
                       <string>https://raw.githubusercontent.com/iLifexiao/appstore/master/test/test.ipa</string>
                   </dict>
               </array>
               <key>metadata</key>
               <dict>
                   <key>bundle-identifier</key>
                   <string>com.nd.sdp.component.debug4.ele-l_beeArq</string>
                   <key>bundle-version</key>
                   <string>version_name_2019-11-25T13:52:59+0800</string>
                   <key>kind</key>
                   <string>software</string>
                   <key>title</key>
                   <string>ele-l_beeArq</string>
               </dict>
           </dict>
       </array>
   </dict>
   </plist>
   ```

3. 上传的 GitHub 上

4. 通过 Safari 打开如下链接 -> `itms-services://?action=download-manifest&url=${plistPath}`

   **链接地址配置如下**

   - `ipaPath` 表示 `GitHub` 上面的配置的 `plist` 地址，如：（https://raw.githubusercontent.com/iLifexiao/appstore/master/test/test.plist）





#### 目前支持下载的 ipa 软件

- [Test](itms-services://?action=download-manifest&url=https://raw.githubusercontent.com/iLifexiao/appstore/master/test/test.plist)







#### 参考资料

- [ipa在线下载安装（itms-services）](https://blog.csdn.net/xlyrh/article/details/79078271)