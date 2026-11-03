# assets

README 头图。版式与配色沿用 `gongwen-dna-xhs-rain` 的 rain-note 模板（红头文件正红
`#e2000f` + 中性纸底 + 雨丝纹理），横版重排。

| 文件 | 用途 |
|---|---|
| `gongwen-dna-hero-zh.jpg` | README 顶部头图，1200×560 |
| `hero.html` | 头图的版式源文件 |
| `rain.js` | 雨丝动画，取自 rain-note 模板 |
| `shoot.mjs` | 截图脚本 |

## 重新生成

```bash
node shoot.mjs --width 1400 --height 760
```

`--width/--height` 是浏览器窗口，要比画布本身大一圈，画布尺寸由 `hero.html`
里 `.scene` 的 width/height 决定。

依赖 Playwright（`/opt/homebrew/lib/node_modules/playwright`）。脚本会报告
`scroll/client` 两个数字，相等即表示内容没有溢出画布。头图不依赖外部图片。

## 为什么是 JPEG 而不是 PNG

纸纹是满版噪点，PNG 在这个尺寸下约有 1MB。这张头图使用 JPEG q92，
保留纸面纹理，同时减小 README 的加载体积。
