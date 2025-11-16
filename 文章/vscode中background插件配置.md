在settings中找到Background: Editor，点击下面的Edit in settings.json
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
用浏览器打开图片即可

