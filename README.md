# 📦 Kali VMware 自动发布仓库

本仓库用于通过 GitHub Actions 自动下载 Kali Linux VMware 镜像，并将其拆分后上传至 GitHub Release。

## 🔧 功能说明

- 自动下载 Kali Linux VMware 镜像（3GB+）
- 自动拆分为 < 2GB 分卷（满足 GitHub 限制）
- 自动上传所有分卷到 Release

## 🚀 如何使用

1. Fork 本仓库或自行创建仓库并复制 `.github/workflows/release-kali.yml`
2. 打开 GitHub 页面 → Actions → 选择 `Download Kali and Upload Release` → 点击 **Run workflow**
3. 等待任务执行完成
4. 前往 [Releases](../../releases) 页面下载分卷文件

## 🔄 文件合并说明

Release 中会生成若干文件：

```

kali.7z.part\_aa
kali.7z.part\_ab
kali.7z.part\_ac
...

````

**下载所有分卷后，在本地运行以下命令进行合并和解压：**

### 🔧 合并分卷文件

#### Windows（CMD 或 PowerShell）：

```cmd
copy /b kali.7z.part_* kali.7z
```

#### macOS / Linux（终端）：

```bash
cat kali.7z.part_* > kali.7z
```

---

### 📦 解压 `.7z` 文件

需要先安装 `7-Zip` 或 `p7zip`：

* **Windows**：请安装 [7-Zip](https://www.7-zip.org/)
* **macOS**：使用 Homebrew 安装：

  ```bash
  brew install p7zip
  ```
* **Linux**：使用包管理器安装（以 Debian/Ubuntu 为例）：

  ```bash
  sudo apt install p7zip-full
  ```

#### 解压命令（所有平台）：

```bash
7z x kali.7z
```

---

💡 **注意**：解压时请确保磁盘空间充足，文件路径中不要包含中文或特殊字符以避免出错。
