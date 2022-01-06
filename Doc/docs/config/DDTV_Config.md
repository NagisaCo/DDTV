# DDTV Core通用配置文件
## Core配置文件说明
配置文件`DDTV_Config.ini`为DDTV核心初始化配置文件，在DDTV_GUI和DDTV_WEB_Server中都存在  

## 完整的配置文件示例
:::tip
如没特殊需要，请勿手动修改，请使用GUI或者API接口进行程序化修改
:::
```ini
[Core]
RoomListConfig=./RoomListConfig.json
ClientAID=cad1c1a170144da2ae60b739f60b2066
[WEB_API]
WEB_API_SSL=false
WEB_API_SSL=false
WebUserName=ami
WebPassword=ddtv
ServerAID=895fff67-149a-447f-bc7b-129379b4e4f8
ServerName=DDTV_Server
[Download]
DownloadPath=./Rec/
DownloadDirectoryName={ROOMID}_{NAME}
DownloadFileName={DATE}_{TIME}_{TITLE}
TmpPath=./tmp/
RecQuality=10000
IsRecDanmu=true
IsRecGift=true
IsRecGuard=true
IsRecSC=true
IsFlvSplit=False
FlvSplitSize=0
```
### 配置说明
```csharp
        /// <summary>
        /// 配置分组(每个值对应的组是固定的，请勿随意填写)
        /// </summary>
        public enum Group
        {
            /// <summary>
            /// 缺省配置组(按道理应该给每个配置都设置组，不应该在缺省组里)
            /// </summary>
            Default,
            /// <summary>
            /// DDTV_Core运行相关的配置
            /// </summary>
            Core,
            /// <summary>
            /// 下载系统运行相关的配置
            /// </summary>
            Download,
            /// <summary>
            /// WEBAPI相关的配置
            /// </summary>
            WEB_API,
            /// <summary>
            /// 播放器相关设置
            /// </summary>
            Play,
        }
        public enum Key
        {
            /// <summary>
            /// 房间配置文件(应该是一个绝对\相对路径文件地址)
            /// </summary>
            RoomListConfig,
            /// <summary>
            /// 默认下载总文件夹(应该是一个绝对\相对路径目录)
            /// </summary>
            DownloadPath,
            /// <summary>
            /// 临时文件存放文件夹
            /// </summary>
            TmpPath,
            /// <summary>
            /// 默认下载文件夹名字格式(应该为关键字组合，如:{ROOMID}_{NAME})
            /// </summary>
            DownloadDirectoryName,
            /// <summary>
            /// 默认下载文件名格式(应该为关键字组合，如:{DATE}_{TIME}_{TITLE})
            /// </summary>
            DownloadFileName,
            /// <summary>
            /// 转码默认参数(应该是带A\B关键字的参数字符串，如:-i {Before} -vcodec copy -acodec copy {After})
            /// </summary>
            TranscodParmetrs,
            /// <summary>
            /// 自动转码(自动转码的使能配置，为布尔值false或ture)
            /// </summary>
            IsAutoTranscod,
            /// <summary>
            /// 是否启用WEB_API加密证书(应该为布尔值)
            /// </summary>
            WEB_API_SSL,
            /// <summary>
            /// WEB_API启用HTTPS后调用的pfx证书文件路径(应该是一个绝对\相对路径文件地址)
            /// </summary>
            pfxFileName,
            /// <summary>
            /// WEB_API启用后HTTPS调用的pfx证书秘钥文件(应该是一个绝对\相对路径文件地址)
            /// </summary>
            pfxPasswordFileName,
            /// <summary>
            /// 播放器默认音量(应该是一个uint值，取值0-100)
            /// </summary>
            DefaultVolume,
            /// <summary>
            /// 首次启动标志位(应该是一个布尔值第一次启动为真)
            /// </summary>
            FirstStart,
            /// <summary>
            /// 录制分辨率(应该为有限的int值，可选值为 80:流畅  150:高清  250:超清  400:蓝光  10000:原画)
            /// </summary>
            RecQuality,
            /// <summary>
            /// 默认在线观看的分辨率(应该为有限的int值，可选值为 80:流畅  150:高清  250:超清  400:蓝光  10000:原画)
            /// </summary>
            PlayQuality,
            /// <summary>
            /// 全局弹幕录制开关(布尔值，每个房间自己在房间配置列表单独设置，这个是是否启用弹幕录制功能的总共开关)
            /// </summary>
            IsRecDanmu,
            /// <summary>
            /// 全局礼物录制开关(布尔值)
            /// </summary>
            IsRecGift,
            /// <summary>
            /// 全局上舰录制开关(布尔值)
            /// </summary>
            IsRecGuard,
            /// <summary>
            /// 全局SC录制开关(布尔值)
            /// </summary>
            IsRecSC,
            /// <summary>
            /// 全局FLV文件按大小切分开关(布尔值)
            /// </summary>
            IsFlvSplit,
            /// <summary>
            /// 当IsFlvSplit为真时使能，FLV文件切分的大小(应该为long值，切割值应该以byte计算)
            /// </summary>
            FlvSplitSize,
            /// <summary>
            /// WEB登陆使用的用户名(string)
            /// </summary>
            WebUserName,
            /// <summary>
            /// WEB登陆使用的密码(string)
            /// </summary>
            WebPassword,
            /// <summary>
            /// WEBAPI使用的KeyId(string)
            /// </summary>
            AccessKeyId,
            /// <summary>
            /// WEBAPI使用的KeySecret(string)
            /// </summary>
            AccessKeySecret,
            /// <summary>
            /// 用于标记服务器资源ID编号(string)
            /// </summary>
            ServerAID,
            /// <summary>
            /// 用于标记服务器名称(string)
            /// </summary>
            ServerName,
            /// <summary>
            /// 客户端唯一标识(string)
            /// </summary>
            ClientAID,
        }
```