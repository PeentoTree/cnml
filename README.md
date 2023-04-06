## 前端

### 本地启动
```
pnpm install
pnpm build:packages
pnpm dev
```

## 后端

### 环境安装
1. 先安装jdk17
    ```
    brew install openjdk@17
    sudo ln -sfn $(brew --prefix)/opt/openjdk@17/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-17.jdk 
    ```
    添加JAVA_HOME, 编辑~/.bash_profile
    ```
    JAVA_HOME="/Library/Java/JavaVirtualMachines/openjdk-17.jdk/Contents/Home"
    export JAVA_HOME
    CLASS_PATH="$JAVA_HOME/lib"
    PATH=".$PATH:$JAVA_HOME/bin"
    ```
2. 安装gradle
    执行项目下的gradlew文件会自动下载对应版本gradle
    ```
    ./gradlew
    ```

### vscode本地启动
1. 安装扩展Extension Pack for Java，如果安装失败，可以尝试下载扩展文件安装
2. 等待gradle安装依赖之后，创建luanch.json
    ```
    {
    // 使用 IntelliSense 了解相关属性。 
    // 悬停以查看现有属性的描述。
    // 欲了解更多信息，请访问: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "type": "java",
            "name": "Current File",
            "request": "launch",
            "mainClass": "${file}"
        },
        {
            "type": "java",
            "name": "Application",
            "request": "launch",
            "mainClass": "run.halo.app.Application",
            // 指定配置文件
            "args": "--spring.profiles.active=dev",
            "preLaunchTask": "gradle: compileJava",
            "projectName": "halo-application"
        }
    ]
    }
    ```

3. 启动项目，访问`http://localhost:8090/console/#/theme`，账号密码在配置文件里
   
4. 如果`/`访问报500错误，代表没有安装主题，在上面的路由页面里启用默认主题
5. 

    
