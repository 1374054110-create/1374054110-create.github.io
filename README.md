# Owen.Hu / 具身智能与触觉

一个用于展示和长期记录具身智能、触觉操作研究的个人主页。页面不依赖构建工具，直接打开 `index.html` 或通过本地静态服务器运行即可。

## 快速开始

在当前目录运行：

```powershell
python -m http.server 4173 --directory ..
```

然后打开 <http://127.0.0.1:4173/owen-hu/>。

## 最先要改的地方

- `index.html`：修改姓名、简介、项目标题、时间线、社交链接和邮箱。
- `styles.css`：修改 `:root` 中的色彩和字体变量。
- `assets/companies/`：存放公司、机器人和智能眼镜图片。替换同名文件即可更新图库，页面无需联网加载图片。

## 内容地图

用 VS Code 打开 `index.html`，按 `Ctrl + F` 搜索下面的文字，就能快速定位：

| 想修改的内容 | 搜索文字 | 位置 |
| --- | --- | --- |
| 首屏姓名、研究方向、简介 | `OWEN.HU` / `hero-lede` | 首屏 `hero` 区域 |
| 公司图片 | `company-gallery` | 经历区下方的五张图片 |
| 研究内容 | `research-prose` | `research` 区域的一段英文正文 |
| 工作笔记 | `note-row` | `notes-section` 区域 |
| 经历与教育 | `experience-item` / `education-block` | `experience-section` 区域 |
| 邮箱与站内索引 | `12333497@mail.sustech.edu.cn` / `social-links` | `contact-section` 区域 |

例如，把邮箱统一改成自己的地址时，至少改两处：

```html
<button data-copy-email="me@example.com">me@example.com</button>
<a href="mailto:me@example.com">发一封邮件</a>
```

## 替换图片

可以继续使用在线图片地址，也可以把自己的图片放进同一个目录下的 `assets` 文件夹，然后写相对路径：

```html
<img src="assets/avatar.jpg" alt="我的工作肖像" />
```

建议图片宽度至少 1200px，项目图尽量使用相近的横竖比例。线上图片需要网络，使用 `assets` 本地图片后，直接打开 `index.html` 也能显示。

## 修改颜色和字体

打开 `styles.css` 顶部的 `:root`（第 1—14 行），集中修改这些变量：

```css
--paper: #f2eee7; /* 页面底色 */
--ink: #171717;   /* 文字和深色区 */
--lime: #d3ef69;  /* 荧光绿 */
--coral: #f06d4f; /* 珊瑚色 */
--blue: #6684ff;  /* 蓝色 */
```

## 日常维护方式

1. 用 VS Code 修改 `index.html`、`styles.css` 或 `script.js`。
2. 保存后刷新 `http://127.0.0.1:4173/owen-hu/`，就能看到结果。
3. 研究内容是一段连续文本，直接修改 `<p class="research-prose">...</p>` 即可。
4. 只改文字和图片通常不需要动 `script.js`；菜单、筛选和复制邮箱等交互都在那里。

简历 PDF 仅存放在本地目录中作为个人资料，不被主页引用，也没有网页下载入口。

如果未来每周都要更新项目和文章，建议把它迁移成 Astro + Markdown，让内容和页面样式彻底分开。

页面没有使用框架，后续可以直接迁移到 Astro、Eleventy 或 Next.js。

## 可参考的开源方向

- Astro + MDX：适合把“项目”和“随笔”拆成内容文件，推荐看 Astro 官方博客模板。
- Magic Portfolio：适合参考项目卡片、暗色联系区和响应式排版的组织方式。
- Eleventy Starter Blog：适合保持极简、可长期维护的个人写作档案。

这版没有套用模板，保留了这些开源方向的可迁移思路，但视觉和页面内容是从零设计的。
