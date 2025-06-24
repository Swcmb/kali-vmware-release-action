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

