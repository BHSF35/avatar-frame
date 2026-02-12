# 套框头像生成器

![](https://p.pstatp.com/origin/fec00001f85976c6dcc5)

总有一些屑营销号为了搞营销，经常在<abbr title="微信">某个功能残缺的辣鸡 APP</abbr> 里面用这种套框头像生成器做活动，并且打上“H5 互动”之类的~~一般人看着就会觉得很厉害实际上却令人不明所以的~~名头。

这东西做起来并不难，所以我也自己做了一个。你可以直接下载源码，修改网页的标题和文本，配置好 `config.json` 后自行部署使用。也可以在[这里](https://transparentlc.github.io/avatar-frame/)查看使用效果。

```json
{
    // 生成的头像边长
    "avatarSize": 800,
    // 初始时可以编辑的头像图片
    // webp和legacy分别对应webp格式和传统格式（jpg、png）的图片URL，根据浏览器支持情况自动选择
    // 如果不设置webp则直接加载legacy
    "initialImage": {
        "webp": "https://ae01.alicdn.com/kf/Ha99b7df48097484b90d7420566942d5bx.jpg",
        "legacy": "https://ae01.alicdn.com/kf/Hed78e27fcc7b49319e7ad7ff00972a3dU.png"
    },
    // 头像模板
    "templates": [
        {
            // 用于生成头像的高清模板图
            "src": {
                "webp": "https://ae01.alicdn.com/kf/Hbefc66e2ef6f4966a0b8ddc67e736708G.jpg",
                "legacy": "https://ae01.alicdn.com/kf/Hce5ac16efdf0408b964a0237b016ac42s.png"
            },
            // 生成的预览中使用的低清模板图
            "preview": {
                "webp": "https://ae01.alicdn.com/kf/Hf276d26dd084434eb28e30c7c49207a8V.jpg",
                "legacy": "https://ae01.alicdn.com/kf/H1b0914f1316c46da8be7acd2461410dc7.png"
            },
            // 在选择头像处显示的预览图
            "example": {
                "webp": "https://ae01.alicdn.com/kf/H98157ee7a7214cdea88232cd3bdcacbcj.jpg",
                "legacy": "https://ae01.alicdn.com/kf/Hbcb1978b0c384a36b32215d091c8950bw.jpg"
            }
        },
        ...
    ]
}
```

## 部署到 GitHub Pages

本仓库已配置 GitHub Actions 自动部署工作流。要启用 GitHub Pages：

1. 进入仓库的 Settings（设置）页面
2. 在左侧菜单中找到 Pages（页面）选项
3. 在 "Build and deployment" 部分：
   - Source（源）选择 "GitHub Actions"
4. 将此分支合并到 `master` 分支后，工作流会自动运行并部署网站
5. 部署完成后，你的网站将在 `https://<你的用户名>.github.io/<仓库名>/` 可访问

工作流会在每次推送到 `master` 分支时自动运行，也可以在 Actions 标签页手动触发。
