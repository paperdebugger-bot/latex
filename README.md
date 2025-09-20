# latex

1. **添加子模块**

    使用 `git submodule add` 命令，把目标仓库的地址添加到指定目录：

    ```bash
    git submodule add <repo-url> <path>
    ```

1. **初始化和更新子模块**
   添加完之后需要执行：

   ```bash
   git submodule init
   git submodule update
   ```

   或者一步到位：

   ```bash
   git submodule update --init --recursive
   ```

2. **提交变更**
   子模块信息会写入 `.gitmodules` 文件，还需要一起提交：

   ```bash
   git add .gitmodules third_party/other-repo
   git commit -m "Add submodule other-repo"
   ```

3. **以后克隆仓库**
   如果别人（或者你自己换了环境）克隆主仓库，记得用：

   ```bash
   git clone --recursive <main-repo-url>
   ```

   或者在克隆后执行：

   ```bash
   git submodule update --init --recursive
   ```
