il2cppdumper## IL2CPPDumper
Dump Lib libil2cpp.so from Memory of Game Process and Generate structure dump.cs

## Features
- No need of Ptrace
- Support Only arm-v7a 32bit Games
- Dumping of Lib from Memory of Game
- Fix and Regenerate Elf File
- Support Only IL2CPP Metadata v24 for Dumping Structure
- Dumping of Internal Game Structure as .cs file(Need to Find Pointers Manually)
- Support Both Fast & Slow Dumping
 
## How to use
- You can Use latest precompiled Binaries from [HERE](https://github.com/kp7742/IL2CPPDumper/tree/master/libs/) or You Can build your Own.
- Needs Root Access or Virtual Space
- Get Root Shell through Adb or Terminal Apps(type: 'su') or Normal Shell into Virtual Space via Terminal Apps
- For Usage Help: il2cppdumper -h
- For General Usage: il2cppdumper <option(s)>
	```
	 ./il2cppdumper -h
	 
	 IL2CPPDumper v0.4 <==> Made By KMODs(kp7742)
	 Usage: il2cppdumper <option(s)>
	 Dump Lib libil2cpp.so from Memory of Game Process and Generate structure dump.cs
	 @@Unity il2cpp v24 Supported Only@@
	  Options:
	 --Lib Args--------------------------------------------------------------
	   -l --lib                              Dump libil2cpp.so from Memory
	   -p --package <packageName>            Package Name of Game
	   -r --raw(Optional)                    Output Raw Lib and Not Rebuild It
	   -f --fast(Optional)                   Enable Fast Dumping
	 										(May Miss Some Bytes in Dump)
	 --Script Args-----------------------------------------------------------
	   -s --script                           Generate structure dump.cs
	   -p --package <packageName>            Package Name of Game
	   -g --global  <address>                GlobalMetaData Address
	   -m --meta    <address>                MetadataRegistration Address
	   -c --code    <address>                CodeRegistration Address
	 --Other Args------------------------------------------------------------
	   -o --output <outputPath>              File Output path
	   -h --help                             Display this information
	```
	```
	$ adb root # might be required
	$ adb push IL2CPPDumper /data/local/tmp/
	adb push F:\git\IL2CPPSODumper\libs\armeabi-v7a\il2cppdumper /data/local/tmp/
	adb push F:\git\IL2CPPSODumper\libs\arm64-v8a\il2cppdumper /data/local/tmp/
	adb -s 127.0.0.1:5555 push F:\git\IL2CPPSODumper\libs\armeabi-v7a\il2cppdumper /data/local/tmp/
	$ adb shell "chmod 755 /data/local/tmp/IL2CPPDumper"
	adb shell
	su
	chmod 755 /data/local/tmp/il2cppdumper
	/data/local/tmp/il2cppdumper -l -p com.hypergryph.arknights.forminor -o /storage/emulated/0/
	/data/local/tmp/il2cppdumper -l -r -p com.bfire.da.nuj -o /storage/emulated/0/
	/data/local/tmp/IL2CPPDumper -l -r -p com.sunborn.neuralcloud.cn.bilibili -o /sdcard
	/data/local/tmp/il2cppdumper -l -r -p com.komoe.kmumamusumegp
	/data/local/tmp/il2cppdumper -l -r -p com.bilibili.priconne2
	/data/local/tmp/il2cppdumper -l -r -p com.sunborn.neuralcloud.cn
	/data/local/tmp/il2cppdumper -l -r -p com.komoe.kmumamusumegp 赛马娘,台服
	/data/local/tmp/il2cppdumper -l -r -p com.kurogame.haru.hero 战双
	adb  pull /sdcard/libil2cpp.so
	adb -s 127.0.0.1:5555  pull /sdcard/libil2cpp.so
	 L:\leidian\LDPlayer64\adb.exe -s 127.0.0.1:5555 push libunityLive2d /data/local/tmp/
	 L:\leidian\LDPlayer64\adb.exe -s 127.0.0.1:5555 push F:\git\tecFramework\TecFramework\newHook\libs\armeabi-v7a\libunityLive2d.so /data/local/tmp/
	chmod 755 /data/local/tmp/libunityLive2d.so
	
	
	/data/local/tmp/IL2CPPDumper  -l -p com.bilibili.zzzj.bili  -r -o /sdcard
	/data/local/tmp/IL2CPPDumper  -l -p com.sunborn.neuralcloud.cn.bilibili  -o /sdcard
	```
	frida
	```
	adb push F:\git\IL2CPPSODumper\libs\armeabi-v7a\frida-server-15.1.3-android-arm /data/local/tmp/
	
		adb shell
	su
	chmod 755 /data/local/tmp/frida-server-15.1.3-android-arm
	
	
	adb push F:\git\IL2CPPSODumper\libs\armeabi-v7a\frida-server-15.1.3-android-arm /data/local/tmp/
	adb shell
	su
	chmod 755 /data/local/tmp/frida-server-15.1.3-android-arm
	/data/local/tmp/frida-server-15.1.3-android-arm &
	```
## How to Build
- Clone this repo
- Install Android NDK, if not already.
- Open Shell/CMD in Project Folder
- Drag ndk-build of NDK in Shell or CMD an then Execute
- Output will be in libs Folder.

## Credits
- [SoFixer](https://github.com/F8LEFT/SoFixer): So(Elf) Rebuilding
- [Il2CppDumper-Perfare](https://github.com/Perfare/Il2CppDumper): CS Dumping Code

## Technlogy Communication
> Email: patel.kuldip91@gmail.com
