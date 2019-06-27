一、你为什么需要这个？
如果您要为React Native创建本机模块，则需要为要支持的每个平台提供一些本机代码，然后将一些JavaScript代码绑定在一起。自己设置可能非常耗时。

这就是这个工具的用武之地。它创建了一个包含所有当前最佳实践的样板。为什么不用react-native new-library？不幸的是，该命令不会创建一个最新的库，需要一个已经初始化的React Native项目，并且只设置iOS方面的东西。

警告：这仅创建没有视图组件的本机模块。

二、安装
要求：节点6.0+

$ npm install -g react-native-create-library-evs

三、命令行用法
导航到空目录以执行该命令。

$ react-native-create-library-evs MyFancyLibrary
这将创建将MyFancyLibrary在其中创建库的文件夹。

Usage: react-native-create-library [options] <name>

Options:

-h, --help                                output usage information
-V, --version                             output the version number
-p, --prefix <prefix>                     The prefix for the library (Default: `RN`)
--module-prefix <modulePrefix>            The module prefix for the library (Default: `react-native`)
--package-identifier <packageIdentifier>  (Android only!) The package name for the Android module (Default: `com.reactlibrary`)
--namespace <namespace>                   (Windows only!) The namespace for the Windows module
(Default: The name as PascalCase)
--platforms <platforms>                   Platforms the library will be created for. (comma separated; default: `ios,android,windows`)

四、程序化使用
const createLibrary = require('react-native-create-library');

createLibrary({
name: 'MyFancyLibrary'
}).then(() => {
console.log('Oh yay! My library has been created!');
})
Options
{
name: String, /* The name of the library (Default: Library) */
prefix: String, /* The prefix for the library (Default: RN) */
modulePrefix: String, /* The module prefix for the library (Default: react-native) */
platforms: Array, /* Platforms the library will be created for. (Default: ['ios', 'android', 'windows']) */
packageIdentifier: String, /* (Android only!) The package name for the Android module (Default: com.reactlibrary) */
namespace: String, /* (Windows only!) The namespace for the Windows module (Default: The package identifier as PascalCase, which is `Com.Reactlibrary`) */
}
