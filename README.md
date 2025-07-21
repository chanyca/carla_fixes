# carla_fixes
Fixes for installing and compiling Carla 0.9.13  
---
If you don't want to read the articles, here's a tl;dr for easy installation and fixes.

**Step 0: Install Unreal Engine 4.26**  
You MUST install [Unreal Engine 4.26 (CARLA fork)](https://github.com/CarlaUnreal/UnrealEngine) before installing and compiling Carla  
Installation guide: You can read my [article](https://medium.com/@ailene.chan/the-struggle-is-real-installing-dreyevr-carla-0-9-13-d68d0d1cd625), or refer to official documentation.  

**Install Carla**
1. After cloning Carla 0.9.13, download files from this repo and replace accordingly.
2. Download content file using this [link](http://carla-assets.s3.us-east-005.backblazeb2.com/20211112_d5cfa12.tar.gz)
3. Extract content with the following command  
   ```
   mkdir <path-to-carla>\Unreal\CarlaUE4\Content\Carla
   tar -xvzf 20211112_d5cfa12.tar.gz -C <path-to-carla>\Unreal\CarlaUE4\Content\Carla
   ```
   *** This is what `Update.bat` does (Steps 2 and 3).  

4. Download backup boost zip file (‘boost_1_72_0.zip’) with this [link](https://carla-releases.s3.us-east-005.backblazeb2.com/Backup/boost_1_72_0.zip) to `<path-to-carla>\Build`
5. Download xerces-c-3.2.3.zip (in this repo), extract content to `<path-to-carla>\Build\xerces-c-3.2.3-source`
6. Run `make PythonAPI` in carla root
7. Key checkpoints
   ```
   # Successful build of LibCarla
   -[BuildLibCarla]: LibCarla server has been successfully installed "<path-to-carla>\Unreal\CarlaUE4\Plugins\Carla\CarlaDependencies\"!
   -[BuildLibCarla]: LibCarla client has been successfully installed in "<path-to-carla>\PythonAPI\carla\dependencies\"!

    # Successful build of
   -[BuildPythonAPI]: Carla lib for python has been successfully installed in "<path-to-carla>\PythonAPI\carla\dist"!
   ```
8. You should be able to see `carla-0.9.13-cp37-cp37m-win_amd64.whl` and `carla-0.9.13-py3.7-win-amd64.egg` in `<path-to-carla>\PythonAPI\carla\dist`





```
# Steps here
git clone https://github.com/CarlaUnreal/UnrealEngine 
# set this location to your $UE4_ROOT environment variable

# in $UE4_ROOT
git checkout d40ec35474e8793b4eea60dba6c4f051186e458e
# or git reset --hard d40ec35474e8793b4eea60dba6c4f051186e458e

```
Note: In order to successfully run `Setup.bat`, you will need to download and replace the `Commit.gitdeps.xml` file within `<path-to-UnrealEngin>\Engine\Build`. [Download here](https://github.com/EpicGames/UnrealEngine/blob/4.26/Engine/Build/Commit.gitdeps.xml)
```
# In x64 Native Tools Command Prompt for VS 2019
Setup.bat
GenerateProjectFiles.bat
```


---
Installation Guide ([Link](https://medium.com/@ailene.chan/the-struggle-is-real-installing-dreyevr-carla-0-9-13-d68d0d1cd625))
- Platform/OS: Windows 11
- Visual Studio Installer 2019
- Python version 3.8.10
  
Previous (failed attempt) using Visual Studio Installer 2022 ([Link](https://medium.com/@ailene.chan/the-struggle-is-real-installing-dreyevr-carla-0-9-13-simulator-unrealengine-4-26-on-windows-11-eb5bee1353e7))

---
Contact: Ailene Chan <chanyca@caltech.edu>
