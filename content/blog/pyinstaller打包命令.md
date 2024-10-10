---
title: pyinstaller打包命令
date: 2024-10-10T03:18:05.412Z
---

--add-data SOURCE:DEST 要添加到应用程序中的附加数据文件或包含数据文件的目录。参数值的形式应为 "source:dest_dir"，其中 source 是要收集的文件（或目录）的路径，dest_dir 是相对于应用程序顶层目录的目标目录，两个路径之间用冒号（:）分隔。要将文件放入应用程序顶层目录，使用 . 作为 dest_dir。该选项可多次使用。

--add-binary SOURCE:DEST 要添加到可执行文件中的其他二进制文件。格式参考 --add-data 选项。该选项可多次使用。

-p DIR, --paths DIR 搜索导入的路径（如使用 PYTHONPATH）。允许使用多个路径，以 : 分隔，或多次使用该选项。相当于在 spec 文件中提供 pathex 参数。

--hidden-import MODULENAME, --hiddenimport MODULENAME 指明脚本中不可见的导入关系。该选项可多次使用。

--collect-submodules MODULENAME 收集指定软件包或模块的所有子模块。该选项可多次使用。

--collect-data MODULENAME, --collect-datas MODULENAME 收集指定软件包或模块的所有数据。该选项可多次使用。

--collect-binaries MODULENAME 收集指定软件包或模块的所有二进制文件。该选项可多次使用。

--collect-all MODULENAME 收集指定软件包或模块的所有子模块、数据文件和二进制文件。该选项可多次使用。

--copy-metadata PACKAGENAME 复制指定包的元数据。该选项可多次使用。

--recursive-copy-metadata PACKAGENAME 复制指定包及其所有依赖项的元数据。该选项可多次使用。

--additional-hooks-dir HOOKSPATH 用于搜索钩子的附加路径。该选项可多次使用。

--runtime-hook RUNTIME_HOOKS 自定义运行时钩子文件的路径。运行时钩子是与可执行文件捆绑在一起的代码，在其他代码或模块之前执行，以设置运行时环境的特殊功能。该选项可多次使用。

--exclude-module EXCLUDES 将被忽略（就像没有被找到一样）的可选模块或软件包（Python 名称，不是路径名）。该选项可多次使用。

--splash IMAGE_FILE （实验性功能）为应用程序添加一个带有 IMAGE_FILE 图像的闪屏。闪屏可以在解压缩时显示进度更新。

-c, --console, --nowindowed 为标准 i/o 打开一个控制台窗口（默认选项）。在 Windows 中，如果第一个脚本是 ‘.pyw’ 文件，则此选项无效。

-w, --windowed, --noconsole 不提供用于标准 i/o 的控制台窗口。在 macOS 上，这也会触发构建一个 .app 捆绑程序。在 Windows 系统中，如果第一个脚本是 ‘.pyw’ 文件，则会自动设置该选项。在 *NIX 系统上，该选项将被忽略。

-i <FILE.ico or FILE.exe,ID or FILE.icns or Image or "NONE">, --icon <FILE.ico or FILE.exe,ID or FILE.icns or Image or "NONE"> FILE.ico：将图标应用于 Windows 可执行文件。FILE.exe,ID：从一个 exe 文件中提取带有 ID 的图标。FILE.icns：将图标应用到 macOS 的 .app 捆绑程序中。如果输入的图像文件不是对应平台的格式（Windows 为 ico，Mac 为 icns），PyInstaller 会尝试使用 Pillow 将图标翻译成正确的格式（如果安装了 Pillow）。使用 “NONE” 不应用任何图标，从而使操作系统显示默认图标（默认值：使用 PyInstaller 的图标）。该选项可多次使用。

--disable-windowed-traceback 禁用窗口（noconsole）模式下未处理异常的回溯转储，并显示禁用此功能的信息。

-w：不会出现命令窗口

-i：给 exe 文件添加一个图标（.ico格式）

-F, –onefile 打包一个单个文件，如果你的代码都写在一个.py文件的话，可以用这个，如果是多个.py文件就别用

-D, –onedir 生成一个文件夹，里面有一堆依赖，便于维护