# Hostloc checkin

## [Hostloc刷分脚本](/hostloc/README.md)

目前支持四种部署方式：

本地或者服务器运行
部署到travis
部署到GithubActions
部署到腾讯云无服务器云函数


Github actions是github的新功能，需要排队申请，通过后即可使用，访问https://github.com/features/actions, 申请开通 
运行方式跟travis大致相同

fork此项目

访问项目settings页面左侧Secrets项，添加secrets，Name填hostloc_username_1和hostloc_password_1，value填帐号和密码，有代理添加代理，Name填代理方式hostloc_http_1或hostloc_https_1，Value填上述提到的代理，多账号以此类推

修改https://github.com/fakedon/checkin/blob/master/.github/workflows/hostloc.yml
把上一步添加的secrets添加到env: 后，如
env:
     hostloc_username_1: ${{ secrets.hostloc_username_1 }}
     hostloc_password_1: ${{ secrets.hostloc_password_1 }}
复制代码


保存就ok了
