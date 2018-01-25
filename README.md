Cloud Torrent特点

    支持 BT下载
    支持 磁力链接下载
    支持 搜索磁力链接
    支持 离线下载
    支持 边下边播( 格式限制：mp4/wbem/ogg，同时需要手动输入链接)
    可视化界面 Web UI

# 安装步骤

    wget -N --no-check-certificate https://softs.fun/Bash/cloudt.sh && chmod +x cloudt.sh && bash cloudt.sh

备用下载地址（上面的链接无法下载，就用这个）：

    wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/cloudt.sh && chmod +x cloudt.sh && bash cloudt.sh

下载运行完毕脚本，会出现脚本菜单，选择并输入 1，就会直接开始安装 Cloud Torrent。

安装完成之后，就会提醒你，输入要开放的端口（默认 8000）可选：用户名（默认 user）和密码（默认 doub.io）。

    # 域名为示例域名，请不要照者写。
     
    请输入 Cloud Torrent 监听域名或IP（当你要绑定域名前，记得先做好域名解析，目前只支持http://访问，不要写http://，只写域名！）
    (默认回车自动获取外网IP绑定):toyoo.ml
     
    ========================
    	端口 :  toyoo.ml 
    ========================
     
    请输入 Cloud Torrent 监听端口 [1-65535]（如果是绑定的域名，那么建议80端口）
    (默认端口: 80):
     
    ========================
    	端口 :  80
    ========================
    是否设置 用户名和密码 ? [y/N] :Y
    请输入用户名
    (默认用户名: user):
    ========================
    	用户名 :  user 
    ========================
     
    请输入用户名的密码
    (默认密码: doub.io):
    ========================
    	密码 :  doub.io
    ========================
    ————————————————
     你的 Cloud Torrent 信息 :
     
     地址 : http://toyoo.ml
     用户 : user
     密码 : doub.io
    ————————————————

启动后，访问 http://toyoo.ml 即可看到Web UI界面了。

# 使用说明
脚本使用说明

    bash cloudt.sh

然后就会看到菜单，输入对应选项的数字即可。

    请输入一个数字来选择选项
     
     1. 安装 Cloud Torrent
     2. 升级 Cloud Torrent
     3. 卸载 Cloud Torrent
    ————————————
     4. 启动 Cloud Torrent
     5. 停止 Cloud Torrent
     6. 重启 Cloud Torrent
    ————————————
     7. 设置 Cloud Torrent 账号
     8. 查看 Cloud Torrent 账号
     9. 查看 Cloud Torrent 日志
    ————————————
     
     当前状态: 已安装 并 已启动

同时脚本设置了 系统服务，所以可以这样控制：

启动：/etc/init.d/cloudt start

停止：/etc/init.d/cloudt stop

重启：/etc/init.d/cloudt restart

查看状态：/etc/init.d/cloudt status

并且支持开机启动了。

# BT 和 磁力链接

Cloud Torrent可以直接在输入中输入 磁力链接 或者 在线的BT种子（不支持本地上传），点击下面的 蓝色的按钮，就会开始解析资源。
<img src="https://user-images.githubusercontent.com/633843/32198822-e59a0fc4-be1d-11e7-9b92-03ce17ba05ba.png" alt="screenshot"/>

# 按钮说明

成功解析后，就会显示如下的界面，开始下载。

Files 是查看正在下载的文件列表， Start 是启动下载（默认解析后直接启动下载）， Stop 是停止下载。

还有，如果你下载完毕或者点了 Stop 停止下载，那么 Stop 就会变成 Remove 删除任务的按钮了。

# 搜索磁力链接

Cloud Torrent支持搜索磁力链接，在输入栏中直接输入你要搜索的文件名称，同时点击 绿色的按钮 选择一个搜索源，然后点击 蓝色的Search 按钮就可以搜索了。

注意：Cloud Torrent是国外人写的，所以这些搜索源均是国外的磁力链接网站，搜索到的资源基本没有中文的，所以非特殊需求的这个功能就没什么卵用了。

# 设置Cloud Torrent

点击右上角的第一个按钮，就会出现下面这个界面。

功能依次是：

    自动启动
    禁用加密
    下载目录
    启用种子
    启用上传
    输入端口

这里的配置存在：/usr/local/cloudtorrent/cloud-torrent.json

# 删除文件

如果你想要删除刚才下载的文件，那么你可以点击你 下载的文件的名称 右边的垃圾箱图标，点击之后会变成一个 对号 图标，代表确认按钮，所以再点击一下就会出现转圈圈删除了。

# 下载/在线播放

当BT中的某个文件下载完毕之后，文件名 就会变成可以点击的蓝色，点击后就会开始下载。

如果是 MP4 Webm Ogg 这三个格式的视频，那只要浏览器支持HTML5视频 就能在线播放，其他的格式需要额外的解码器，所以浏览器无法直接播放。

# 边下边播

这个软件其实也可以边下载边播放的，只是软件的机制是：只有当BT中的某个文件下载完成后，才会显示下载连接，所以文件正在下载的时候，显示文件名是无法点击的，但是不代表链接不存在，所以你可以手动拼接链接，这样就能实现边下边播了！下面是示例。

比如：你的网站是 1.1.1.1:8000 ，你下载的是下图中的 mp4 视频，那么你访问

    http://1.1.1.1:8000/download/文件夹（一定要注意这个，不要忽略了文件夹！！！！）/文件名.mp4

    http://1.1.1.1:8000/download/圆梦巨人.The.BFG.2016.BD720P.超清中英字幕-迅影网/圆梦巨人.The.BFG.2016.BD720P.超清中英字幕-迅影网.mp4

下载的BT文件都是在 download 文件夹下面新建立一个单独的文件夹，里面包含了下载的文件。

所以即使是在下载中，你也可以直接播放，当然，最好BT下载一部分再开始观看，否则可能不流畅。

# 文件位置

安装目录：/usr/local/cloudtorrent

下载目录：/usr/local/cloudtorrent/downloads

配置文件：/usr/local/cloudtorrent/cloud-torrent.json

配置文件：/usr/local/cloudtorrent/cloud-torrent.conf (这个为脚本所用的配置文件)

日志文件：/tmp/ct.log (日志存放在系统临时文件夹，重启VPS后自动清理)
