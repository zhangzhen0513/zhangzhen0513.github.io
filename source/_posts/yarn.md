---
title: Yarn
toc: true
date: 2019-09-25 11:09:34
tags:
  - Yarn
  - 包管理
categories:
  - Yarn
---
## 全局安装yarn

原因：vue-cli初始化项目无法使用cnpm，速度太慢，yarn也是一个包管理器

### 全局安装yarn

```bash
npm install -g yarn
#cnpm i -g yarn
```

此时无法使用yarn全局安装，因为yarn还未添加到全局path中
<!-- more -->
### yarn添加到全局环境变量

1. cmd中输入

   ```bash
   yarn global bin
   ```

2. 找到相关路径`C:\Users\10903\AppData\Local\Yarn\bin`

3. 右键我的电脑

4. 属性

5. 高级系统设置

6. 环境变量

7. 选中Path编辑

8. 新建

9. 将yarn的bin文件路径添加进去

之后就能使用

```bash
yarn global add @vue/cli
```

即进行yarn进行本地和全局的模块安装了

## yarn的常用命令

1. 安装模块

```bash
# 全局
yarn global add bootstrap@3.4.1
# 本地
yarn add bootstrap@3.4.1
```

2. 移除模块

```bash
# 全局
yarn global remove bootstrap@3.4.1
# 本地
yarn remove bootstrap@3.4.1
```

3. 运行脚本

```bash
#yarn 脚本名
yarn serve
```

4. 恢复安装，即重装`package.json`中模块

```bash
yarn
# 对应npm/cnpm中的
npm install
```
