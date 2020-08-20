### 集成
个人仓库地址
```
allprojects {
    repositories {
      ...
      maven { url 'https://raw.github.com/forJrking/maven/master/' }
    }
}
```

### 发布
```
module中添加
apply from: "https://raw.githubusercontent.com/forJrking/maven/master/upload_maven.gradle"
```
新建文件
````
gradle.propreties

添加如下内容

# 以下信息非常重要 禁止上传到个人外部仓库和其他公共存储空间
username=xxx
password=xxx
releaseRepositoryUrl    =xxx
snapshotsRepositoryUrl  =xxx
# 禁止上传到个人外部仓库和其他公共存储空间

android.packageBuildConfig = false
# 项目名称一般取 ARTIFACT_ID
POM_NAME = Tools
#版本号 (测试版本使用0.0.1-SNAPSHOT)
POM_VERSION = 0.0.2
#组名
POM_GROUP_ID = com.xx.android.components
#组件名称 (例如 tools
POM_ARTIFACT_ID = tools
#包类型 jar aar
POM_PACKAGING = aar
#描述信息
POM_DESCRIPTION = components
#是否打包自动创建tag
POM_GIT_TAG = false
```
