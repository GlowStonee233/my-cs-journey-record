在settings中找到Background: Editor，点击下面的Edit in settings.json，文件大致如下所示：
```
{

    "editor.experimental.treeSitterTelemetry": true,

    "editor.minimap.enabled": false,

    "editor.unicodeHighlight.nonBasicASCII": false,

    "code-runner.runInTerminal": true,

    "github.copilot.nextEditSuggestions.enabled": true,

    "workbench.iconTheme": "vscode-icons",

    "background.editor": {

  

        "useFront": true,

        "style": {

            "background-position": "100% 100%",

            "background-size": "auto",

            "opacity": 0.6

        },

        "styles": [

            {},

            {},

            {}

        ],

        "images":[],    

        "interval": 0,

        "random": false

    }

}
```
在文件里找到"images":\[],  在里面填入图片的文件URL路径，中间以","隔开，即可设置Edit区域背景。
**如何获得图片的URL路径**
对于网页上的图片直接使用它的网页链接即可。
对于本地图片，可以将其上传到图床网站，转换成网页。
如果一定要用本地照片，请自行搜索如何将文件路径转换为URL路径
关于转换，有一个比较好用的小技巧：
用浏览器打开本地图片，地址栏显示的即为URL路径

