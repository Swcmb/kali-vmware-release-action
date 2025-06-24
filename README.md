# 📦 Kali VMware 自动发布仓库

本仓库用于通过 GitHub Actions 加速下载 Kali Linux VMware 镜像。

## 🔄 文件合并与解压说明

Release 中会生成多个分卷压缩文件：

```
kali.7z.part_aa  
kali.7z.part_ab  
kali.7z.part_ac  
...
```

请 **下载所有分卷后**，根据你的操作系统在本地执行以下步骤进行合并与解压。


### 🔧 第一步：合并分卷文件

#### 🪟 Windows（CMD 或 PowerShell）：

```cmd
copy /b kali.7z.part_* kali.7z
```

#### 🍎 macOS / 🐧 Linux（终端）：

```bash
cat kali.7z.part_* > kali.7z
```


### 📦 第二步：解压 `.7z` 文件

解压前请先安装解压工具：

* **Windows**：安装 [7-Zip 官方版](https://www.7-zip.org/)
* **macOS**（使用 Homebrew）：

  ```bash
  brew install p7zip
  ```
* **Linux**（Debian/Ubuntu）：

  ```bash
  sudo apt install p7zip-full
  ```

#### 通用解压命令（所有平台）：

```bash
7z x kali.7z
```


💡 **提示**：

* 解压前请确保磁盘空间充足。
* 路径中避免使用中文或特殊符号，以防止出错。
* 若文件损坏或解压失败，请重新校验分卷是否完整下载。

---
