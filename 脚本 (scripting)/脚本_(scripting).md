## 脚本 (SCRIPTING)

###### 激活脚本功能 (ACTIVATING SCRIPTING)
要想激活 Sketch 当中的脚本功能，你需要进入到菜单栏中的 *Sketch > 偏好 (Preferences)*，选择 *通用 (General)* 标签，单击 *激活脚本(Enable Scripting)*。一个新的菜单项会显示在菜单栏中，名字叫 *插件 (Plugins)*，点击这个 *自定义脚本选项… (Custom Script...)* 你就可以开始便携自己的脚本了。

###### 安装脚本 (INSTALLING SCRIPTS)

脚本文件需要有一个 *.jstalk* 的扩展名，放在 *~/library/application support/sketch/plugins* 的目录下面。 如果你的 Sketch 是从 App Store 下载的，那么它将处于沙盒模式当中，所以你需要把脚本文件放在 *~/Library/Containers/com.bohemiancoding.sketch/Data/Library/Application Support/sketch/Plugins* 的路径下。

他们就会出现在 Sketch 的 *插件 (Plugins)* 菜单里。插件的文件名既是插件的名称，你甚至可以为这个插件自己设定一个快捷键。 

###### 语法 (SYNTAX)

想要了解 JSTalk 和他的语法请参考 JSTalk.org。

###### 前导 (PREAMBLE)

Sketch 会在它运行的运行的每一个脚本前加上下面这个代码片段，这样就可以访问一些常用的变量。

var doc = [[NSDocumentController sharedDocumentController] currentDocument]; 
var selection = doc.selectedLayers(); 

###### 键盘快捷键 (KEYBOARD SHORTCUTS)

你可以给菜单栏中的插件设置快捷键，按照下面的步骤：第一行应该是一段注释，用以解释这个脚本要做什么，第一行当中还应当包含用括号括起来的快捷键，比如：

// just a comment (cmd y) // (ctrl alt cmd t) 

最后一个字符会被当作快捷键，在他之前的会作为修饰键。下面的这些修饰键全部都是有效的：

control ctrl alt option cmd command shift 

需要注意的是，一旦你安装一个插件，那么你就可以在 *[Plugins](http://bohemiancoding.com/sketch/scripting/Plugins)> Custom Script* 这个菜单下运行所有自定义脚本。

###### 案例 (EXAMPLES)
我认为通过举例来说明 API 的使用方法会比发布头文件更加容易：

- [Make Selected Objects Square](http://bohemiancoding.com/sketch/scripting/make%20selected%20objects%20square.html)
- [Make a 5x5 Grid of an Object](http://bohemiancoding.com/sketch/scripting/make%20a%205x5%20grid%20of%20an%20object.html)
- [Make 5 copies of an object with varying opacity](http://bohemiancoding.com/sketch/scripting/make%205%20copies%20of%20an%20object%20with%20varying%20opacity.html)
- [User Input Examples](http://bohemiancoding.com/sketch/scripting/user%20input%20examples.html)
- [Exporting Areas](http://bohemiancoding.com/sketch/scripting/exporting%20areas.html)
- [Zoom to Fit a an Area](http://bohemiancoding.com/sketch/scripting/zoom%20to%20fit%20a%20an%20area.html)

以上所有案例文件你也都可以在 [Github](https://github.com/pieteromvlee/Sketch-Scripts)上找到。

###### 请求用户输入 (ASKING FOR USER INPUT)
一个脚本可以按照以下方式请求用户输入，返回的结果是一个字符串，它可以被轻易地转换成整数或浮点数。需要两个参数，一个是短标签，用以通知用户；另一个是输入框内的默认值。

[doc askForUserInput:"How many times?" initialValue:10]; 

通过 [User Input Examples](http://bohemiancoding.com/sketch/scripting/user%20input%20examples.html) 来查看案例。

###### API
 
- [MSDocument](http://bohemiancoding.com/sketch/scripting/msdocument.html)
- [MSContentDrawView](http://bohemiancoding.com/sketch/scripting/mscontentdrawview.html)
- [MSLayer](http://bohemiancoding.com/sketch/scripting/mslayer.html)
- [MSLayerGroup](http://bohemiancoding.com/sketch/scripting/mslayergroup.html)
- [MSRect](http://bohemiancoding.com/sketch/scripting/msrect.html)
- [MSStyle](http://bohemiancoding.com/sketch/scripting/msstyle.html)
- [MSPage](http://bohemiancoding.com/sketch/scripting/mspage.html)
- [MSDocument](http://bohemiancoding.com/sketch/scripting/msdocument.html)
- [MSArtboardGroup](http://bohemiancoding.com/sketch/scripting/msartboardgroup.html)
- [MSSliceLayer](http://bohemiancoding.com/sketch/scripting/msslicelayer.html)

以上所有脚本都可以保存为一个 .jstalk 的文件，然后把它们放在上文所提到的路径下，即可正常运行。

###### 第三方脚本 (THIRD-PARTY SCRIPT)
想要更多的 Sketch 脚本，请参见下面这个代码库:

https://github.com/bomberstudios/sketch-commands

API的所有正要变更，请参见 [chengelog](http://bohemiancoding.com/sketch/scripting/changelog.html)



下一个条目：[快捷键](http://www.bohemiancoding.com/sketch/help/manual/shortcuts/)


