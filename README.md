# Front-End Checklist 前端开发清单

[源文](https://github.com/thedaviddias/Front-End-Checklist)

---

[![Join the chat at https://gitter.im/Front-End-Checklist/Lobby](https://badges.gitter.im/Front-End-Checklist/Lobby.svg)](https://gitter.im/Front-End-Checklist/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
[![Contributors](https://img.shields.io/github/contributors/thedaviddias/Front-End-Checklist.svg)](https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors)
[![StackShare](https://img.shields.io/badge/tech-stack-0690fa.svg?style=flat)](https://stackshare.io/thedaviddias/front-end-checklist)
[![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

**Front-End Checklist** 是一份在网站 / HTML 页面发布到生产环境前，提供所有需要测试元素的详细清单

这份清单基于前端开发人员多年经验的累积，以及其他开源清单而成。

## 目录

1. **[Head](#head)**
2. **[HTML](#html)**
3. **[Webfonts](#webfonts)**
4. **[CSS](#css)**
5. **[Images](#images)**
6. **[JavaScript](#javascript)**
7. **[Security](#security)**
8. **[Performance](#performance-1)**
9. **[Accessibility](#accessibility)**
10. **[SEO](#seo)**

## How to use?

**Front-End Checklist** 中的所有项目都是大部分专桉所必需的，但某些元素可以省略或者不是那么重要（在管理 Web APP 的情况下，你可能不需要 RSS 订阅）。我们将元素区分成 3 种等级：

* ![Low][low_img] 表示该项目是**推荐**使用的，但在某些特定情况下可以省略。

* ![Medium][medium_img] 表示该项目是**强烈推荐**的，但可能在某些特殊情况下被省略。某些元素如果省略可能会降低性能或 SEO。

* ![High][high_img] 表示项目**不能省略**，否则可能导致页面有访问性的功能障碍或 SEO 的问题。应该优先测试这些元素。

某些资源有特定的图示，帮助你理解清单上不同类型的内容：

* 📖: 文件或文章
* 🛠: 线上工具 / 测试工具
* 📹: 媒体或视频内容

---

## Head

> **Notes:** 你可以从 [a list of everything](https://github.com/joshbuchea/HEAD) 找到`<head>`标签内可操作的内容

### Meta tag

* [ ] **Doctype:** ![High][high_img] Doctype 是 HTML5 的标准宣告，写在 HTML 网页的开头

```html
<!-- Doctype HTML5 -->
<!doctype html>
```

> 📖 [Determining the character encoding - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

*下方 3 个 meta tags (Charset, X-UA Compatible and Viewport) 需要写于`<head>`标签内的起始处*

* [ ] **Charset:** ![High][high_img] 正确宣告网页字符集 ( UTF-8 )

```html
<!-- 设置文档的字符编码 -->
<meta charset=\"utf-8\">
```

* [ ] **X-UA-Compatible:** ![Medium][medium_img] 设置 IE 兼容模式

```html
<!-- 指示 Internet Explorer 使用最新的渲染引擎 -->
<meta http-equiv=\"x-ua-compatible\" content=\"ie=edge\">
```

> 📖 [Specifying legacy document modes (Internet Explorer)](https://msdn.microsoft.com/en-us/library/jj676915(v=vs.85).aspx)

* [ ] **Viewport:** ![High][high_img] 正确宣告浏览器窗口设置

```html
<!-- 窗口用于响应式网页设计 -->
<meta name=\"viewport\" content=\"width=device-width, initial-scale=1\">
```

* [ ] **Title:** ![High][high_img] 所有网页都使用 title ( SEO : Google 计算 title 的 总字符宽度为 472 ~ 482 px 之间， 平均可容纳 55 个字符 )

```html
<!-- 文件标题 -->
<title>Page Title less than 65 characters</title>
```

> 📖 [Title - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)

* [ ] **Description:** ![High][high_img] 提供网页的描述，它是唯一的且限制于150个字符内

```html
<!-- Meta 描述 -->
<meta name=\"description\" content=\"Description of the page less than 150 characters\">
```

* [ ] **Favicons:** ![Medium][medium_img] 设置网页的favicon，确保每个 favicon 被创建且显示正常，如果只有`favicon.ico`，把它放在网站的根目录下，通常你不需要使用任何标记即可显示，但最佳做法是以下方范例的方式来连结。现在推荐使用 **PNG** 格式来取代`.ico`格式。( 尺寸 : 32 x 32像素 )

```html
<!-- 标准 favicon -->
<link rel=\"icon\" type=\"image/x-icon\" href=\"https://example.com/favicon.ico\">
<!-- 推荐 favicon 格式 -->
<link rel=\"icon\" type=\"image/png\" href=\"https://example.com/favicon.png\">
```

> * 🛠 [Favicon Generator](https://www.favicon-generator.org/)
> * 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
> * 📖 [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet)
> * 📖 [Favicons, Touch Icons, Tile Icons, etc. Which Do You Need? - CSS Tricks](https://css-tricks.com/favicon-quiz/)
> * 📖 [PNG favicons - caniuse](https://caniuse.com/#feat=link-icon-png)

* [ ] **Apple Touch Icon:** ![Low][low_img] 供 Apple 设备呈现的 favicon。( 图标至少 200 x 200 像素尺寸以支持可能需要的所有尺寸)

```html
<!-- Apple Touch Icon -->
<link rel=\"apple-touch-icon\" href=\"/custom-icon.png\">
```

> 📖 [Configuring Web Applications](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

- [ ] **Windows Tiles:**![Low][low_img] windows 的动态砖设置

```html
<!-- Microsoft Tiles -->
<meta name=\"msapplication-config\" content=\"browserconfig.xml\" />
```

browserconfig.xml 文件至少需含以下 xml 标记:

```xml
<?xml version=\"1.0\" encoding=\"utf-8\"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src=\"small.png\"/>
        <square150x150logo src=\"medium.png\"/>
        <wide310x150logo src=\"wide.png\"/>
        <square310x310logo src=\"large.png\"/>
     </tile>
   </msapplication>
</browserconfig>
```

> 📖 [Browser configuration schema reference](https://msdn.microsoft.com/en-us/library/dn320426(v=vs.85).aspx)

* [ ] **Canonical:** ![Medium][medium_img] 使用 `rel=\"canonical\"` 来避免重复的内容。( 目的是让搜寻引擎不要索引放置该宣告的页面，而去索引指向的页面 )

```html
<!-- 有助于防止重复内容的问题 -->
<link rel=\"canonical\" href=\"http://example.com/2017/09/a-new-article-to-red.html\">
```

### HTML tags

* [ ] **Language tag:** ![High][high_img] 设置当前页面使用的语系

```html
<html lang=\"en\">
```

* [ ] **Direction tag:** ![Medium][medium_img] 设置网页的文章流向 ( 可被设定在其他 HTML 标签上 )

```html
<html dir=\"rtl\">
```

> 📖 [dir - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

* [ ] **Alternate language:** ![Low][low_img] 设置当前页面的替代语系

```html
<link rel=\"alternate\" href=\"https://es.example.com/\" hreflang=\"es\">
```

* [ ] **Conditional comments:** ![Low][low_img] for IE 使用的条件式注解

> 📖 [About conditional comments (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx)

* [ ] **RSS feed:** ![Low][low_img] 供专桉类型为部落格或含有文章的网页提供 RSS 连结

* [ ] **CSS Critical:** ![Medium][medium_img] CSS critical 集合并渲染页面中可见部分的 CSS。在主要的 CSS 调用前以单行 ( 最小化 ) 的方式嵌入`<style></style>`中

> 🛠 [Critical by Addy Osmani on Github](https://github.com/addyosmani/critical)

* [ ] **CSS order:** ![High][high_img] `<head>`中的 CSS 文件需于 JavaScript 文件前载入 ( 除了特定情况时 JS 文件会异步加载到页面上 )

### Social meta

强烈推荐 ***Facebook OG*** 和 ***Twitter Cards*** ，如有特定需求也可使用其他社交媒体标签以确保功能显示正常

* [ ] **Facebook Open Graph:** ![Low][low_img] 确保所有 Facebook Open Graph（OG）都经过测试，没有错误或漏掉信息。图片至少需要 600 x 315 像素，建议使用 1200 x 630 像素。

```html
<meta property=\"og:type\" content=\"website\">
<meta property=\"og:url\" content=\"https://example.com/page.html\">
<meta property=\"og:title\" content=\"Content Title\">
<meta property=\"og:image\" content=\"https://example.com/image.jpg\">
<meta property=\"og:description\" content=\"Description Here\">
<meta property=\"og:site_name\" content=\"Site Name\">
<meta property=\"og:locale\" content=\"en_US\">
```

> * 📖 [A Guide to Sharing for Webmasters](https://developers.facebook.com/docs/sharing/webmasters/)
> * 🛠 Test your page with the [Facebook OG testing](https://developers.facebook.com/tools/debug/)

* [ ] **Twitter Card:** ![Low][low_img]

```html
<meta name=\"twitter:card\" content=\"summary\">
<meta name=\"twitter:site\" content=\"@site_account\">
<meta name=\"twitter:creator\" content=\"@individual_account\">
<meta name=\"twitter:url\" content=\"https://example.com/page.html\">
<meta name=\"twitter:title\" content=\"Content Title\">
<meta name=\"twitter:description\" content=\"Content description less than 200 characters\">
<meta name=\"twitter:image\" content=\"https://example.com/image.jpg\">
```

> * 📖 [Getting started with cards — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
> * 🛠 Test your page with the [Twitter card validator](https://cards-dev.twitter.com/validator)

**[⬆ back to top](#table-of-contents)**

---

## HTML

### 最佳做法 ( Best practices )

* [ ] **HTML5 Semantic Elements:** ![High][high_img] 适当的使用 HTML5 语意化元素 (header, section, footer, main...)

> 📖 [HTML Reference](http://htmlreference.io/)

* [ ] **Error pages:** ![High][high_img] 存在 404 和 5xx 错误页面。 5xx 错误页面需要集成其 CSS（当前服务器上无法外部调用）

* [ ] **Noopener:** ![Medium][medium_img] 如果你使用`target=\"_blank\"`外部连结，你的连结应包含属性`rel=\"noopener\"`来避免钓鱼攻击。如果你需要支援旧版 firefox ，使用`rel=\"noopener noreferrer\"`

> 📖 [About rel=noopener](https://mathiasbynens.github.io/rel-noopener/)

* [ ] **Clean up comments:** ![Low][low_img] 非必要的程式码应于网页上线前被清除

### HTML 测试 ( HTML testing )

* [ ] **W3C compliant:** ![High][high_img] 所有页面都需要通过 W3C 验证器进行测试，以检测HTML代码中可能有的问题。

> 🛠 [W3C validator](https://validator.w3.org/)

* [ ] **HTML Lint:** ![High][high_img] 使用工具帮助分析 HTML 代码中可能有的问题

> 🛠 [Dirty markup](https://dirtymarkup.com/)

* [ ] **Desktop Browsers:** ![High][high_img] 所有页面于桌机浏览器作测试 ( Safari, Firefox, Chrome, Internet Explorer, EDGE... )

* [ ] **Mobile Browsers:**  ![High][high_img] 所有页面于行动装置浏览器作测试 ( Native browser, Chrome, Safari... )

* [ ] **Link checker:** ![High][high_img] 确保没有坏掉的连结以及 404 错误页面的出现

> 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

* [ ] **Adblockers test:** ![Medium][medium_img] 你的网站在启用广告拦截器的情况下可正确显示内容 ( 可以提供一则讯息鼓励使用者停用广告拦截器 )

- [ ] **Pixel perfect:** ![High][high_img] 页面接近完美像素。根据素材的质量，可能不会100％准确，但应尽可能与模板质量接近。

> [Pixel Perfect - Chrome Extension](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

**[⬆ back to top](#table-of-contents)**

---

## Webfonts

* [ ] **Webfont format:** ![High][high_img] WOFF, WOFF2 和 TTF 是当代浏览器通用的格式

> * 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff).
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType and OpenType font support](https://caniuse.com/#feat=ttf)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Webfont size:** ![High][high_img] Webfont 档桉大小不要超过 2 MB (含所有版本).

**[⬆ back to top](#table-of-contents)**

---

## CSS

> **Notes:** 大部分前端开发人员都会参考 [CSS guidelines](https://cssguidelin.es/) 和 [Sass Guidelines](https://sass-guidelin.es/) 。如果你对 CSS 属性有疑问，可以访问 [CSS Reference](http://cssreference.io/)。

* [ ] **Responsive Web Design:** ![High][high_img] 网站使用响应式设计
* [ ] **CSS Print:** ![Medium][medium_img] 提供打印模式下的 CSS 样式呈现，确保每个页面都显示正常
* [ ] **Preprocessors:** ![Medium][medium_img] 你的页面有使用 CSS 预处理器 ( 推荐使用 [Sass](http://sass-lang.com/) )
* [ ] **Unique ID:** ![High][high_img] 确保每个页面中的 ID 都是唯一的
* [ ] **Reset CSS:** ![High][high_img] 使用最新的 CSS reset ( reset, normalize 或者 reboot )，如使用 Bootstrap 或 Foundation 等的 CSS 框架，框架本身已包含 reset 设置

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

* [ ] **JS prefix:** ![Low][low_img] 有前缀 **js-** 的 class、id 不要作为 CSS 样式套用

```html
<div id=\"js-slider\" class=\"my-slider\">
<!-- Or -->
<div id=\"id-used-by-cms\" class=\"js-slider my-slider\">
```

* [ ] **CSS embed or line:** ![High][high_img] 避免使用内嵌或行内 CSS : 仅用于有必要的时候 ( 例 : slider 的 background-image， CSS critical 等 )
* [ ] **Vendor prefixes:** ![High][high_img] 使用供应商的 CSS 前缀，让浏览器支援兼容性。

> 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### 性能 ( Performance )

- [ ] **Concatenation:** ![High][high_img] CSS 文件合并成一个文件 ( 不适用于 HTTP/2 )
- [ ] **Minification:** ![High][high_img] 所有 CSS 文件作最小化压缩
- [ ] **Non-blocking:** ![Medium][medium_img] 避免因 CSS 文件阻塞导致花更多时间载入 DOM

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
> * 📖 [Example of preload CSS using loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **Unused CSS:** ![Low][low_img] 移除未使用的 CSS

> * 🛠 [UnCSS Online](https://uncss-online.com/) 🛠
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
> * 🛠 [Chrome DevTools Coverage](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage)


### CSS 测试 ( CSS testing )

* [ ] **Stylelint:** ![High][high_img] 所有 CSS 或 SCSS 文件没有任何错误

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)

* [ ] **Responsive web design:** ![High][high_img] 所有页面经过以下断点测试 : 320px, 768px, 1024px ( 根据不同需求可以设定更多断点 )

* [ ] **CSS Validator:** ![Medium][medium_img] CSS 经过测试，并排除相关的错误。

> 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

* [ ] **Reading direction:** ![High][high_img] 如果有文章流向的需求，应测试所有页面的 LTR 和 RTL languages 显示

> * 📖 [Building RTL-Aware Web Apps & Websites: Part 1 - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
> * 📖 [Building RTL-Aware Web Apps & Websites: Part 2 - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ back to top](#table-of-contents)**

---

## Images

> **Notes:** 想了解更完整的图片优化内容，请查看 Addy Osmani 的 **[Essential Image Optimization](https://images.guide/)**

### 最佳做法 ( Best practices )

* [ ] **Optimization:** ![High][high_img] 所有图像都经过优化且可在浏览器中呈现。 WebP 格式可用于关键页面（如首页）

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 Use [ImageOptim](https://imageoptim.com/) to optimise your images for free.

* [ ] **Retina:** ![Low][low_img] 提供x2 或 3x 的图像以支持视网膜显示
* [ ] **Sprite:** ![Medium][medium_img] 小图片统一存成一个 sprite 档 ( icons 可统一存成一个 SVG sprite )
* [ ] **Width and Height:** ![High][high_img] 所有`<img>`标签有设定 width 和 height ( 不含单位 px 或 % )

> ***Note:*** 许多开发人员认为设定图片宽高会与响应式设计不兼容，但实际上不是这样。

* [ ] **Alternative text:** ![High][high_img] 所有`<img>`应有替代文字 ( alt ) 来描述图片内容
* [ ] **Lazy loading:** ![Medium][medium_img] 图片使用 lazyloaded ( 也应提供 noscript 当作备桉 )

**[⬆ back to top](#table-of-contents)**

---

## JavaScript

### 最佳做法 ( Best practices )

* [ ] **JavaScript Inline:** ![High][high_img] 避免使用行内 JavaScript ( 与 HTML 写在一起 )
* [ ] **Concatenation:** ![High][high_img] 合并 JavaScript 文件
* [ ] **Minification:** ![High][high_img] JavaScript 文件最小化压缩 ( 可于档名加入后缀 `.min` )

> [Minify Resources (HTML, CSS, and JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **JavaScript security:**

> [Guidelines for Developing Secure Applications Utilizing JavaScript](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)*

* [ ] **Non-blocking:** ![Medium][medium_img] 使用`async`或是`defer`属性来异步载入 JavaScript 文件

> 📖 [Remove Render-Blocking JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Modernizr:** ![Low][low_img] 如果你需要某些特定功能，可以使用自定义 Modernizr 在`<html>`标签中添加 classes。

> 🛠 [Customize your Modernizr](https://modernizr.com/download?setclasses)

### JavaScript 测试 ( JavaScript testing )

* [ ] **ESLint:** ![High][high_img] 没有被 ESLint 标记错误（ 根据你的配置或标准规则 ）

> * 📖 [ESLint - The pluggable linting utility for JavaScript and JSX](https://eslint.org/)

**[⬆ back to top](#table-of-contents)**

---

## Security

### 扫瞄并检查网站 ( Scan and check your web site )

> * [securityheaders.io](https://securityheaders.io/)
> * [Observatory by Mozilla](https://observatory.mozilla.org/)
> * [ASafaWeb - Automated Security Analyser for ASP.NET Websites](https://asafaweb.com/)

### 最佳做法 ( Best practices )

* [ ] **HTTPS:** ![Medium][medium_img] 使用 HTTPS 于每个页面和所有外部内容 ( 插件，图像... )

> * 🛠 [Let\'s Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/)
> * 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html)
> * 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity)

* [ ] **HTTP Strict Transport Security (HSTS):** ![Medium][medium_img] HTTP header 设置为 “强制安全传输”。

> * 🛠 [Check HSTS preload status and eligibility](https://hstspreload.org/)
> * 📖 [HTTP Strict Transport Security Cheat Sheet - OWASP](https://www.owasp.org/index.php/HTTP_Strict_Transport_Security_Cheat_Sheet)
> * 📖 [Transport Layer Protection Cheat Sheet - OWASP](https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet)

* [ ] **Cross Site Request Forgery (CSRF):** ![High][high_img] 确保向你的服务器端发出的请求是合法且来自你的网站/应用程序，以防止发生CSRF攻击。

> 📖 [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet)

* [ ] **Cross Site Scripting (XSS):** ![High][high_img] 你的网页或网站没有跨网站指令码的问题。

> * 📖 [XSS (Cross Site Scripting) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet)
> * 📖 [DOM based XSS Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet)

* [ ] **Content Type Options** ![Medium][medium_img] 阻止 Google Chrome 和 Internet Explorer 尝试将响应的内容类型与服务器声明的内容类型进行比较

> * 📖 [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

* [ ] **X-Frame-Options (XFO)** ![Medium][medium_img] 保护你的访客免受骇客攻击

> * 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
> * 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034)

**[⬆ back to top](#table-of-contents)**

---

## Performance

### 最佳做法 ( Best practices )

- [ ] **Weight page:** ![High][high_img] 每个页面大小于 0 ~ 500KB 之间

> * 🛠 [Website Page Analysis](https://tools.pingdom.com)
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Minified:** ![Medium][medium_img] 你的 HTML 有最小化压缩
> 🛠 [W3C Validator](https://validator.w3.org/)

* [ ] **Lazy loading:** ![Medium][medium_img] 图片，脚本和 CSS 需要 lazy loaded 以改善当前页面的响应时间 ( 请见各部分的详细说明 )

* [ ] **Cookie size:** 如果使用 Cookie，请确保每个 Cookie 不超过 4096 个字节，且域名下不超过 20 个 cookie

> * 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)
> * 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
> * 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/)

### 准备即将到来的请求 ( Preparing upcoming requests )

> 📖 [Explanation of the following techniques](https://css-tricks.com/prefetching-preloading-prebrowsing/)

* [ ] **DNS resolution:** ![Low][low_img] 使用`dns-prefetch`于空闲时间提前载入第三方服务器的 DNS

```html
<link rel=\"dns-prefetch\" href=\"https://example.com\">
```

* [ ] **Preconnection:** ![Low][low_img] 使用`preconnect`提前在空闲时间完成服务器的 DNS 查询，TCP 三向交握以及 TLS 协商。

```html
<link rel=\"preconnect\" href=\"https://example.com\">
```

* [ ] **Prefetching:** ![Low][low_img] 使用`prefetch`提前在空闲时间请求即将需要的资源 ( 例 : lazy lorded 的图像 )

```html
<link rel=\"prefetch\" href=\"image.png\">
```

* [ ] **Preloading:** ![Low][low_img] 使用`preload`提前加载当前页面需要的资源 ( 例 : 放在`<body>`结尾处的 script )

```html
<link rel=\"preload\" href=\"app.js\">
```

> 📖 [Difference between prefetch and preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### 效能测试 ( Performance testing )

* [ ] **Google PageSpeed:** ![High][high_img] 所有的网页都经过测试 ( 不仅是首页 )，且至少达到 90/100 的评分

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)

**[⬆ back to top](#table-of-contents)**

---

## Accessibility

> **Notes:** 你可以参考播放清单 [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### 最佳做法 ( Best practices )

- [ ] **Progressive enhancement:** ![Medium][medium_img] 主要功能如主导航和搜寻应该在没有启用 JavaScript 的情况下工作

> 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Color contrast:** ![Medium][medium_img] 颜色对比应至少通过 WCAG AA 标准 ( AAA for 行动装置 )

> 🛠 [Contrast ratio](https://leaverou.github.io/contrast-ratio/)

#### Headings

* [ ] **H1:** ![High][high_img] 所有页面都有非网站 title 的 H1 标签
* [ ] **Headings:** ![High][high_img] 标题应使用正确的顺序 ( H1 至 H6 )

> 📹 [Why headings and landmarks are so important -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

#### Landmarks

- [ ] **Role banner:** ![High][high_img] `<header>`有`role=\"banner\"`属性
- [ ] **Role navigation:** ![High][high_img] `<nav>`有`role=\"navigation\"`属性
- [ ] **Role main:** ![High][high_img] `<main>`有`role=\"main\"`属性

> 📖 [Using ARIA landmarks to identify regions of a page](https://www.w3.org/WAI/GL/wiki/Using_ARIA_landmarks_to_identify_regions_of_a_page)

### 语意化 ( Semantics )

- [ ] **Specific HTML5 input types are used:** ![Medium][medium_img] 对于显示自定义键盘和不同类型小工具的行动装置尤其重要。

> 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### 表单 ( Form )

* [ ] **Label:** ![High][high_img] 标签与每个输入表单元素相关联。如果无法显示标签，请改用`aria-label`

> 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute)

### 无障碍测试 ( Accessibility testing )

* [ ] **Accessibility standards testing:** ![High][high_img] 使用 WAVE 工具测试页面是否符合辅助功能标准

> 🛠 [Wave testing](http://wave.webaim.org/)

* [ ] **Keyboard navigation:** ![High][high_img] 仅用键盘以可能出现的操作顺序测试你的网站，确保所有互动元素都可访问及使用
* [ ] **Screen-reader:** ![Medium][medium_img] 所有页面经过萤幕阅读器的测试 ( VoiceOver, ChromeVox, NVDA or Lynx )
* [ ] **Focus style:** ![High][high_img] 如果 focus 被禁用，使用 CSS 的可见状态替代

> 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ back to top](#table-of-contents)**

---

## SEO

* [ ] **Google Analytics:** ![High][high_img] 安装 Google Analytics 且正确配置
* [ ] **Headings logic:** ![Medium][medium_img] 标题文字有助于了解当前页面中的内容
* [ ] **sitemap.xml:** ![High][high_img] 有 sitemap.xml 档，并提交给 Google Search Console ( 以前的 Google 网站管理员工具 )
* [ ] **robots.txt:** ![High][high_img] The robots.txt 没有阻挡网页被搜索

> * 🛠 Test your robots.txt with [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool)

* [ ] **Structured Data:** ![High][high_img] 使用结构化数据的页面经过测试且没有错误。结构化数据有助于爬虫工具了解当前页面的内容

> * 📖 [Introduction to Structured Data - Search - Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
> * 🛠 Test your page with the [Structured Data Testing Tool](https://developers.google.com/structured-data/testing-tool/)

* [ ] **Sitemap HTML:** ![Medium][medium_img] 提供 HTML 网站地图，可通过网站页尾中的链接进行访问

> * 📖 [Sitemap guidelines - Google Support](https://support.google.com/webmasters/answer/183668?hl=en)
> * 🛠 [Sitemap generator](https://websiteseochecker.com/html-sitemap-generator/)


**[⬆ back to top](#table-of-contents)**

---

## Translation

The Front-End Checklist 也提供其他语言版本，感谢所有的翻译者!


* 🇯🇵 Japanese: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)
* 🇪🇸 Spanish: [eoasakura/Front-End-Checklist-ES](https://github.com/eoasakura/Front-End-Checklist-ES)
* 🇨🇳 Chinese: [JohnsenZhou/Front-End-Checklist](https://github.com/JohnsenZhou/Front-End-Checklist)
* 🇰🇷 Korean: [kesuskim/Front-End-Checklist](https://github.com/kesuskim/Front-End-Checklist)
* 🇧🇷 Portuguese: [jcezarms/Front-End-Checklist](https://github.com/jcezarms/Front-End-Checklist)

---

## Front-End Checklist Badge

如果想显示你有遵循前端清单的规定，请将此徽章放在 README 文件上！

➔ [![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)

```md
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
```

**[⬆ back to top](#table-of-contents)**

---

## Contributing

**透过 issue 或 pull request 来建议更改或添加内容**

### Guide

**Front-End Checklist** 由两个分支组成 :

#### 1. `master`

该分支包含自动反映在 [Front-End Checklist](http://frontendchecklist.com/) 网站上的`README.md`文件

#### 2. `develop`

这个分支用于对结构及内容进行一些重大更改。最好使用主分支来修复小错误或添加新项目

### Contributors

查看所有 [contributors](https://github.com/thedaviddias/frontendchecklist/graphs/contributors)

## Support

如果你有任何疑问或建议，可透过 Gitter or Twitter 与我联系 :

* [Chat on Gitter](https://gitter.im/Front-End-Checklist/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)
* [Twitter](https://twitter.com/thedaviddias)

## Authors

**[David Dias](https://github.com/thedaviddias/Front-End-Checklist)**

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ back to top](#table-of-contents)**

[low_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png
[medium_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png
[high_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png
