# 个人网站导航页

## 功能简介

demo： [demo 页面](https://www.salve.cf)

- 个人网站导航页，标题 / 图片 
- 使用 Vue 和 Vuetify 构建的静态网页
- 自明的配置文件，直接修改即可使用
- 没有其它功能了

## 配置文件说明

请自行修改配置文件 config.json 和 img/ 下的图片，配置文件是自明的。

修改配置文件后刷新即可看到网页的变化。

## 使用说明

### 推荐方法（Action 自动部署推送）

1. Fork 仓库

2. 配置 Repository secrets

   | 环境变量名      | 内容            |
   | --------------- | --------------- |
   | REMOTE_HOST     | 服务器域名 / IP |
   | REMOTE_PORT     | SSH 端口        |
   | REMOTE_USER     | SSH 登录用户    |
   | SSH_PRIVATE_KEY | SSH 私钥        |
   | TARGET          | 网站根目录      |

3. 克隆仓库并修改配置

4. 推送仓库至 Github，Github Action 会自动部署至服务器

### 备用方法（手动修改配置文件）

#### A. 编译

1. 克隆仓库

   ```
   git clone https://github.com/hasbai/navipage.git
   ```

2. 修改配置

3. 编译

    ```
    npm install
    npm run build
    ```
4. 将 dist 文件夹中所有文件上传至网站根目录
#### B. 下载 releases 里面编译好的文件
将 dist 文件夹中所有文件上传至网站根目录
