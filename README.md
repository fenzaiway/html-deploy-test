# Demo Hub

静态演示例子导航，通过 GitHub Pages 部署。

## 访问地址

- **首页导航**: https://fenzaiway.github.io/html-deploy-test/
- **Hello World**: https://fenzaiway.github.io/html-deploy-test/examples/hello-world/
- **Pretext 演示**: https://fenzaiway.github.io/html-deploy-test/examples/pretext/
- **性能对比测试**: https://fenzaiway.github.io/html-deploy-test/examples/performance-test/

## 目录结构

```
├── index.html                    # 首页导航 (Demo Hub)
├── README.md
└── examples/
    ├── hello-world/index.html    # 基础部署验证
    ├── pretext/index.html        # Pretext 纯算术文本布局
    └── performance-test/         # DOM vs Canvas 性能对比
        └── index.html
```

## 如何提交

### 1. 本地修改后提交

```bash
git add .
git commit -m "描述改动"
git push origin main
```

### 2. 添加新例子

1. 在 `examples/` 下创建新目录，放入 `index.html`
2. 修改根目录 `index.html`，在 `<div class="grid">` 内新增一个卡片：

```html
<a class="card" href="examples/新目录名/index.html">
    <span class="card-icon">🆕</span>
    <div class="card-title">新例子名称</div>
    <div class="card-desc">描述</div>
    <span class="card-tag">标签</span>
</a>
```

3. 提交并推送：

```bash
git add .
git commit -m "add: 新例子名称"
git push origin main
```

### 3. 网络受限 (DNS 解析不了 github.com)

如果 push 失败，切换到手机热点或可访问 GitHub 的网络：

```bash
# 检查连通性
curl -I https://github.com

# 如果 DNS 不通，临时修改 DNS
sudo networksetup -setdnsservers Wi-Fi 8.8.8.8 8.8.4.4

# 推送
git push origin main

# 完成后恢复自动 DNS
sudo networksetup -setdnsservers Wi-Fi empty
```

### 4. 遇到远端历史不一致

如果远端被重写导致 push 被拒绝，确认本地是正确版本后：

```bash
git push --force origin main
```

> ⚠️ 慎用，会覆盖远端历史。
