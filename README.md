# Installation
- Install Haxe : https://haxe.org/download/
- Install Hashlink : https://hashlink.haxe.org/#download
- Install Git : https://git-scm.com/downloads
- ``haxelib install heaps`` or ``haxelib git heaps https://github.com/HeapsIO/heaps.git``
- ``haxelib install hldx``
- ``haxelib install hlopenal``
- ``haxelib install hlsdl``

# Project Structure
```
.
├── .vscode/
│   └── launch.json
├── res/
├── src/
│   └── Main.hx
└── compile.hxml
```
# compile.hxml
```
-cp src
-lib heaps
-lib hlsdl #lib hldx for windows
-hl main.hl
-main Main
#-D windowSize=1366x768
```
# Main.hx
```haxe
class  Main  extends hxd.App {
  override  function  init() {
	  var  tf = new h2d.Text(hxd.res.DefaultFont.get(), s2d);
	  tf.text = "Hello World !";
  }
  static  function  main() {
	  new  Main();
  }
}
```
# .vscode/launch.json
```json
{
	"version": "0.2.0",
	"configurations": [
        {
            "name": "HashLink",
            "request": "launch",
            "type": "hl",
            "cwd": "${workspaceFolder}",
            "preLaunchTask": {
                "type": "haxe",
                "args": "active configuration"
            }
        }
	]
}
```
