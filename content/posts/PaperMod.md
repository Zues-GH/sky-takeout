+++
title = 'PaperMod'
weight = 2
categories = ["博客"]
+++
## 参数配置
### 隐藏摘要和内容
```toml{title="hugo.toml"}
[params]  
hideSummary = true
```

### 关闭首页特色文章
```toml{title="hugo.toml"}
[params.homeInfoParams]
disableFeatured = true
```

## 博客美化

### 字体字号
```css{title="assets\css\extended\custom.css"}
body 
{
    font-family: '新宋体';
    font-size: 24px;
}
```

### logo
```toml{title="hugo.toml"}
[params.assets]  
favicon = "/images/logo.jpg" # 浏览器标签栏的 logo  
[params.label]  
text = "博客" # 网站名称  
icon = "/images/logo.jpg" # 导航栏中的 logo  
iconHeight = 35 # logo 的高度
```

### 代码块
```css{title="assets\css\extended\code.css"}
    /* === 主题变量 === */
    :root {
        --pe-primary-hover-color: #777777;
        --pe-code-block-header-color: #333333;
        /* 标题文字颜色 */
        --pe-code-block-header-bg-color: #dbdbdbbc;
        /* 标题背景色 */
        --pe-code-block-color: #979797;
        --pe-code-block-bg-color: #f5f5f5;
        /* 代码背景色 */
        --pe-copy-code-color: #fff;
        --pe-copy-code-bg-color: #979797;
        --pe-scrollbar-bg-color: #a3a3a5;
        /* 滚动条颜色 */
        --pe-scrollbar-hover-bg-color: #717175;
        --copy-btn-hover-color: #4489f9;
        --code-color: #ff8a8a;
        --pe-code-block-border-color: #b9b1b1;
        /* 新增边框颜色变量 */
    }

    .dark {
        --pe-code-block-header-color: rgba(255, 255, 255, 0.9);
        --pe-code-block-header-bg-color: #20252B;
        --pe-code-block-color: rgba(255, 255, 255, 0.7);
        --pe-code-block-bg-color: #272C34;
        --pe-copy-code-color: rgba(255, 255, 255, 0.7);
        --pe-copy-code-bg-color: #414244;
        --pe-scrollbar-bg-color: #717175;
        --pe-scrollbar-hover-bg-color: #a3a3a5;
        --copy-btn-hover-color: #b3d0ff;
        --pe-code-block-border-color: #656262;
        /* 暗色模式边框颜色 */
    }

    /* === 基础样式 === */
    .post-content a:hover {
        color: var(--copy-btn-hover-color);
    }

    .post-content code {
        margin: unset;
        padding: .3rem .4rem;
        line-height: 1.5;
        background: var(--code-bg);
        border-radius: .5rem;
        font-size: 0.875em;
        font-family: "新宋体", sans-serif;
        color: var(--code-color);
    }

    /* === 代码块容器 === */
    .pe-code-block-wrap {
        position: relative;
        border-radius: var(--radius);
        margin: var(--content-gap) auto;
        background-color: var(--pe-code-block-header-bg-color);
        border: 1px solid transparent;
        border-color: var(--pe-code-block-border-color);
        font-family: "新宋体", sans-serif;
        overflow: hidden;
    }

    /* === 标题栏 === */
    .pe-code-block-header {
        display: flex;
        width: 100%;
        align-items: center;
        color: var(--pe-code-block-header-color);
        justify-content: space-between;
        padding: .4rem 1rem;
        font-size: 0.875rem;
    }

    .pe-code-block-header-left {
        text-align: left;
        display: flex;
        align-items: baseline;
        gap: .2rem;
    }

    .pe-code-block-header-center {
        text-align: center;
    }

    .pe-code-block-header-right {
        display: flex;
        align-items: center;
        gap: 0.5rem;
        padding-top: 2px;
    }

    /* === 代码内容区 === */
    .post-content .highlight:not(table) {
        margin: 0;
        background: var(--pe-code-block-bg-color) !important;
        border-radius: unset;
        border-top: none;
    }

    .post-content pre code {
        background-color: var(--pe-code-block-bg-color) !important;
        font-size: 0.875rem;
        color: var(--pe-code-block-color);
        border-radius: unset;
    }

    /* === 复制按钮 === */
    .pe-icon {
        width: 1.2rem;
        height: 1.2rem;
        transition: transform 0.2s ease;
    }

    .pe-code-copy-button {
        padding: 0;
        background: transparent;
        border: none;
        cursor: pointer;
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100%;
    }

    .pe-code-copy-button:hover .pe-icon {
        transform: scale(1.1);
        color: var(--copy-btn-hover-color);
    }

    /* === 滚动条 === */
    .pe-code-details-content {
        overflow-y: auto !important;
        scrollbar-width: thin;
        scrollbar-color: var(--pe-scrollbar-bg-color) var(--pe-code-block-bg-color);
    }

    .pe-code-details-content::-webkit-scrollbar {
        width: 12px;
        height: 12px;
        background: transparent;
    }

    .pe-code-details-content::-webkit-scrollbar-track {
        background: var(--pe-code-block-bg-color);
        border-radius: unset;
    }

    .pe-code-details-content::-webkit-scrollbar-thumb {
        border: 3px solid transparent;
        background: var(--pe-scrollbar-bg-color);
        background-clip: content-box;
        border-radius: 6px;
    }

    .pe-code-details-content::-webkit-scrollbar-thumb:hover {
        background: var(--pe-scrollbar-hover-bg-color);
    }

    .pe-code-details-content::-webkit-scrollbar-corner {
        background: transparent;
    }

    /* === 折叠功能 === */
    .pe-code-details .pe-code-details-summary:hover {
        cursor: pointer;
    }

    .pe-code-details i.pe-code-details-icon {
        color: var(--pe-code-block-header-color);
        transform: rotate(0deg);
        transition: transform 0.2s ease;
        background: transparent;
    }

    .pe-code-details.open i.pe-code-details-icon {
        transform: rotate(180deg);
    }

    .pe-code-details .pe-code-details-content {
        max-height: calc(6 * 1.5em);
        overflow-y: auto;
        transition: max-height 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .pe-code-details.open .pe-code-details-content {
        max-height: 80vh;
    }

    /* === 短代码处理 === */
    .pe-code-block-wrap.short-code .pe-code-details-icon {
        display: none !important;
    }

    .pe-code-block-wrap.short-code .pe-code-details-summary {
        cursor: default !important;
    }

    .pe-code-block-wrap.short-code .pe-code-details-content {
        max-height: none !important;
        overflow: visible !important;
    }
```

```html{title="layouts\_default\_markup\render-codeblock.html"}
<!-- 
  代码块组件
  参数说明：
  - fold: 控制折叠行为（true/false/"disable"）
  - title: 代码块标题
  - lang: 覆盖自动检测的语言
  - hide: 隐藏语言显示
  - force: 强制使用指定语言
-->

<!-- 获取默认折叠模式（默认为true即折叠） -->
{{ $defaultFoldMod := .Page.Param "codeBlockFoldMode" | default true }}

<!-- 获取代码语言和标题 -->
{{- $lang := .Type | default "text" }}
{{- $title := .Attributes.title | default "" }}
{{- $u_lang := .Attributes.lang | default "" }}
{{- $hideLang := .Attributes.hide | default false }}
{{ $foldMode := .Attributes.fold | default $defaultFoldMod }}

<!-- 处理强制语言设置 -->
{{- if and (.Attributes.force) (ne $u_lang "") }}
{{- $lang = $u_lang }}
{{- end }}

<!-- 计算代码行数并判断是否为短代码（6行及以下） -->
{{ $lineCount := len (split .Inner "\n") }}
{{ $isShortCode := le $lineCount 6 }}

<!-- 主容器 
  class说明：
  - pe-code-details: 可折叠代码块
  - open: 展开状态
  - short-code: 短代码（不折叠）
  - scrollable: 可滚动
-->
<div class="pe-code-block-wrap 
    {{ if and (ne $foldMode "disable") (not $isShortCode) }} pe-code-details {{ end }}
    {{ if not $foldMode }} open {{ end }}
    {{ if $isShortCode }} short-code {{ end }}
    scrollable">
    
    <!-- 代码块头部 -->
    <div class="pe-code-block-header pe-code-details-summary">
        <!-- 左侧：语言显示 -->
        <div class="pe-code-block-header-left">
            {{ if not $hideLang }}
            <span>
                {{- if ne $u_lang "" }}
                {{- $u_lang -}}
                {{- else }}{{- $lang -}}{{- end }}
            </span>
            {{ end }}
        </div>
        
        <!-- 中间：标题显示 -->
        <div class="pe-code-block-header-center">
            <span>
                {{- if ne $title "" }}
                {{- $title }}
                {{ end }}
            </span>
        </div>
        
        <!-- 右侧：操作按钮 -->
        <div class="pe-code-block-header-right">
            <!-- 折叠按钮（仅当不是短代码且未禁用折叠时显示） -->
            {{ if and (ne $foldMode "disable") (not $isShortCode) }}
            <i class="arrow fas fa-chevron-down fa-fw pe-code-details-icon" aria-hidden="true"></i>
            {{ end }}
            
            <!-- 复制按钮 -->
            <button class="pe-code-copy-button" aria-label="复制代码">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24" class="pe-icon">
                    <path fill="currentColor" fill-rule="evenodd" d="M7 5a3 3 0 0 1 3-3h9a3 3 0 0 1 3 3v9a3 3 0 0 1-3 3h-2v2a3 3 0 0 1-3 3H5a3 3 0 0 1-3-3v-9a3 3 0 0 1 3-3h2zm2 2h5a3 3 0 0 1 3 3v5h2a1 1 0 0 0 1-1V5a1 1 0 0 0-1-1h-9a1 1 0 0 0-1 1zM5 9a1 1 0 0 0-1 1v9a1 1 0 0 0 1 1h9a1 1 0 0 0 1-1v-9a1 1 0 0 0-1-1z" clip-rule="evenodd"></path>
                </svg>
            </button>
        </div>
    </div>
    
    <!-- 代码内容区域 -->
    <div class="pe-code-details-content scrollable">
        {{ highlight .Inner $lang .Options }}
    </div>
</div>
```

```html{title="layouts\_default\_markup\render-codeblock-mermaid.html"}

<pre class="mermaid">
    {{- .Inner | safeHTML }}
  </pre>
  {{ .Page.Store.Set "hasMermaid" true }}
```

```html{title="layouts\partials\extend_head.html"}
<!-- layouts/partials/head.html -->
<head>
    <!-- 其他 meta 标签 -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />
</head>
```

```html{title="layouts\partials\extend_footer.html"}
<script>
document.querySelectorAll('pre > code').forEach((codeBlock) => {
    const codeBlockWrap = codeBlock.closest('.pe-code-block-wrap')
    const copyButton = codeBlockWrap.querySelector('button')

    function copyingDone() {
        copyButton.innerHTML = '<svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="pe-icon"><path fill-rule="evenodd" clip-rule="evenodd" d="M18.0633 5.67375C18.5196 5.98487 18.6374 6.607 18.3262 7.06331L10.8262 18.0633C10.6585 18.3093 10.3898 18.4678 10.0934 18.4956C9.79688 18.5234 9.50345 18.4176 9.29289 18.2071L4.79289 13.7071C4.40237 13.3166 4.40237 12.6834 4.79289 12.2929C5.18342 11.9023 5.81658 11.9023 6.20711 12.2929L9.85368 15.9394L16.6738 5.93664C16.9849 5.48033 17.607 5.36263 18.0633 5.67375Z" fill="currentColor"></path></svg>'
        setTimeout(() => {
            copyButton.innerHTML = '<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24" class="pe-icon"><path fill="currentColor" fill-rule="evenodd" d="M7 5a3 3 0 0 1 3-3h9a3 3 0 0 1 3 3v9a3 3 0 0 1-3 3h-2v2a3 3 0 0 1-3 3H5a3 3 0 0 1-3-3v-9a3 3 0 0 1 3-3h2zm2 2h5a3 3 0 0 1 3 3v5h2a1 1 0 0 0 1-1V5a1 1 0 0 0-1-1h-9a1 1 0 0 0-1 1zM5 9a1 1 0 0 0-1 1v9a1 1 0 0 0 1 1h9a1 1 0 0 0 1-1v-9a1 1 0 0 0-1-1z" clip-rule="evenodd"></path></svg>'
        }, 2000);
    }

    copyButton.addEventListener('click', (cb) => {
        // 防止触发 details-summary 点击事件
        cb.stopPropagation();
        if ('clipboard' in navigator) {
            navigator.clipboard.writeText(codeBlock.textContent).then(() => {
                copyingDone();
            })
            return;
        }
        const range = document.createRange();
        range.selectNodeContents(codeBlock);
        const selection = window.getSelection();
        selection.removeAllRanges();
        selection.addRange(range);
        try {
            document.execCommand('copy');
            copyingDone();
        } catch (e) {
        }
        selection.removeRange(range);
    });
});

let peCodeDetails = document.getElementsByClassName('pe-code-details')
for (let element of peCodeDetails) {
    const peCodeSummary = element.getElementsByClassName('pe-code-details-summary')[0];
    if (peCodeSummary) {
        peCodeSummary.addEventListener('click', () => {
            if (element.classList.contains('open')) {
                element.classList.remove('open');
                element.classList.remove('scrollable');
            } else {
                element.classList.add('open');
                setTimeout(() => {
                    element.classList.add('scrollable');
                }, 800);
            }
        }, false);
    }
}
</script>
```

### 目录
```css{title="assets\css\extended\\toc.css"}
:root {
    --nav-width: 1380px;
    --article-width: 650px;
    --toc-width: 330px;
}

/* 目录容器基础样式 */
.toc {
    margin: 0 2.2px 44px 0;
    border: 1.1px solid var(--border);
    background: var(--entry);
    border-radius: calc(var(--radius) * 1.1);
    padding: 0.44em 0.44em 0.44em 0.3em;
}

/* 宽屏固定定位样式 */
.toc-container.wide {
    position: fixed;
    right: 22px;
    top: 110px;
    width: var(--toc-width);
    height: auto;
    max-height: 88vh;
    border-left: 1.1px solid var(--border);
    background: var(--entry);
    border-radius: calc(var(--radius) * 1.1);
    padding: 0.88em 0.88em 0.88em 0.6em;
    box-shadow: 0 2.2px 11px rgba(0,0,0,0.1);
    z-index: 100;
    overflow-y: auto;
}

.wide .toc {
    position: static;
    border: 1.1px solid var(--border);
    background: var(--entry);
    border-radius: calc(var(--radius) * 1.1);
    width: 100%;
    margin: 0;
}

/* 目录标题样式 */
.toc details summary {
    cursor: zoom-in;
    margin-inline-start: 25px;
    padding: 13.2px 0;
    font-size: 1.21em;
}

.toc details[open] summary {
    font-weight: 500;
    font-size: 1.32em;
}

.toc-container.wide .toc .inner {
    margin: 0;
}

/* 目录内容区域 */
.toc .inner {
    margin: 0 0 0 25px;
    padding: 0px 16.5px 16.5px 25px;
    font-size: 17.6px;
    max-height: 91.3vh;
    overflow-y: auto;
}

/* 滚动条样式 */
.toc .inner::-webkit-scrollbar-thumb {
    background: var(--border);
    border: 7.7px solid var(--theme);
    border-radius: calc(var(--radius) * 1.1);
}

/* 列表项样式 */
.toc li ul {
    margin-inline-start: calc(var(--gap) * 0.88);
    list-style-type: none;
}

.toc li {
    list-style: none;
    font-size: 1.045rem;
    padding-bottom: 5.5px;
    padding-left: 8px;
}

/* 激活状态样式 */
.active {
    font-size: 121%;
    font-weight: 600;
}

.toc li a:hover {
    color: var(--secondary);
}

/* 响应式设计 */
@media (max-width: 1320px) {
    .toc-container.wide {
        position: static;
        width: 100%;
        max-height: none;
        margin: 1.1rem 0;
        right: auto;
        border-left: none;
    }
    
    .toc details summary {
        margin-inline-start: 18px;
    }
    
    .toc .inner {
        margin: 0 0 0 18px;
        padding: 0px 12px 12px 18px;
        font-size: 16px;
    }
}
```

```html{title="layouts\partials\\toc.html"}
{{- $headers := findRE "<h[1-6].*?>(.|\n])+?</h[1-6]>" .Content -}}
{{- $has_headers := ge (len $headers) 1 -}}
{{- if $has_headers -}}
<aside id="toc-container" class="toc-container wide">
    <div class="toc">
        <details {{if (.Param "TocOpen") }} open{{ end }}>
            <summary accesskey="c" title="(Alt + C)">
                <span class="details">{{- i18n "toc" | default "Table of Contents" }}</span>
            </summary>

            <div class="inner">
                {{- $largest := 6 -}}
                {{- range $headers -}}
                {{- $headerLevel := index (findRE "[1-6]" . 1) 0 -}}
                {{- $headerLevel := len (seq $headerLevel) -}}
                {{- if lt $headerLevel $largest -}}
                {{- $largest = $headerLevel -}}
                {{- end -}}
                {{- end -}}

                {{- $firstHeaderLevel := len (seq (index (findRE "[1-6]" (index $headers 0) 1) 0)) -}}

                {{- $.Scratch.Set "bareul" slice -}}
                <ul>
                    {{- range seq (sub $firstHeaderLevel $largest) -}}
                    <ul>
                        {{- $.Scratch.Add "bareul" (sub (add $largest .) 1) -}}
                        {{- end -}}
                        {{- range $i, $header := $headers -}}
                        {{- $headerLevel := index (findRE "[1-6]" . 1) 0 -}}
                        {{- $headerLevel := len (seq $headerLevel) -}}

                        {{/* get id="xyz" */}}
                        {{- $id := index (findRE "(id=\"(.*?)\")" $header 9) 0 }}

                        {{- /* strip id="" to leave xyz, no way to get regex capturing groups in hugo */ -}}
                        {{- $cleanedID := replace (replace $id "id=\"" "") "\"" "" }}
                        {{- $header := replaceRE "<h[1-6].*?>((.|\n])+?)</h[1-6]>" "$1" $header -}}

                        {{- if ne $i 0 -}}
                        {{- $prevHeaderLevel := index (findRE "[1-6]" (index $headers (sub $i 1)) 1) 0 -}}
                        {{- $prevHeaderLevel := len (seq $prevHeaderLevel) -}}
                        {{- if gt $headerLevel $prevHeaderLevel -}}
                        {{- range seq $prevHeaderLevel (sub $headerLevel 1) -}}
                        <ul>
                            {{/* the first should not be recorded */}}
                            {{- if ne $prevHeaderLevel . -}}
                            {{- $.Scratch.Add "bareul" . -}}
                            {{- end -}}
                            {{- end -}}
                            {{- else -}}
                            </li>
                            {{- if lt $headerLevel $prevHeaderLevel -}}
                            {{- range seq (sub $prevHeaderLevel 1) -1 $headerLevel -}}
                            {{- if in ($.Scratch.Get "bareul") . -}}
                        </ul>
                        {{/* manually do pop item */}}
                        {{- $tmp := $.Scratch.Get "bareul" -}}
                        {{- $.Scratch.Delete "bareul" -}}
                        {{- $.Scratch.Set "bareul" slice}}
                        {{- range seq (sub (len $tmp) 1) -}}
                        {{- $.Scratch.Add "bareul" (index $tmp (sub . 1)) -}}
                        {{- end -}}
                        {{- else -}}
                    </ul>
                    </li>
                    {{- end -}}
                    {{- end -}}
                    {{- end -}}
                    {{- end }}
                    <li>
                        <a href="#{{- $cleanedID -}}" aria-label="{{- $header | plainify -}}">{{- $header | safeHTML -}}</a>
                        {{- else }}
                    <li>
                        <a href="#{{- $cleanedID -}}" aria-label="{{- $header | plainify -}}">{{- $header | safeHTML -}}</a>
                        {{- end -}}
                        {{- end -}}
                        <!-- {{- $firstHeaderLevel := len (seq (index (findRE "[1-6]" (index $headers 0) 1) 0)) -}} -->
                        {{- $firstHeaderLevel := $largest }}
                        {{- $lastHeaderLevel := len (seq (index (findRE "[1-6]" (index $headers (sub (len $headers) 1)) 1) 0)) }}
                    </li>
                    {{- range seq (sub $lastHeaderLevel $firstHeaderLevel) -}}
                    {{- if in ($.Scratch.Get "bareul") (add . $firstHeaderLevel) }}
                </ul>
                {{- else }}
                </ul>
                </li>
                {{- end -}}
                {{- end }}
                </ul>
            </div>
        </details>
    </div>
</aside>
<script>
    let activeElement;
    let elements;
    
    document.addEventListener('DOMContentLoaded', function (event) {
        checkTocPosition();
    
        elements = document.querySelectorAll('h1[id],h2[id],h3[id],h4[id],h5[id],h6[id]');
        if (elements.length > 0) {
            // Make the first header active
            activeElement = elements[0];
            const id = encodeURI(activeElement.getAttribute('id')).toLowerCase();
            document.querySelector(`.inner ul li a[href="#${id}"]`).classList.add('active');
        }
    
        // Add event listener for the "back to top" link
        const topLink = document.getElementById('top-link');
        if (topLink) {
            topLink.addEventListener('click', (event) => {
                // Prevent the default action
                event.preventDefault();
    
                // Smooth scroll to the top
                window.scrollTo({ top: 0, behavior: 'smooth' });
            });
        }
    }, false);
    
    window.addEventListener('resize', function(event) {
        checkTocPosition();
    }, false);
    
    window.addEventListener('scroll', () => {
        // Get the current scroll position
        const scrollPosition = window.pageYOffset || document.documentElement.scrollTop;
    
        // Check if the scroll position is at the top of the page
        if (scrollPosition === 0) {
            return;
        }
    
        // Ensure elements is a valid NodeList
        if (elements && elements.length > 0) {
            // Check if there is an object in the top half of the screen or keep the last item active
            activeElement = Array.from(elements).find((element) => {
                if ((getOffsetTop(element) - scrollPosition) > 0 && 
                    (getOffsetTop(element) - scrollPosition) < window.innerHeight / 2) {
                    return element;
                }
            }) || activeElement;
    
            elements.forEach(element => {
                const id = encodeURI(element.getAttribute('id')).toLowerCase();
                const tocLink = document.querySelector(`.inner ul li a[href="#${id}"]`);
                if (element === activeElement){
                    tocLink.classList.add('active');
    
                    // Ensure the active element is in view within the .inner container
                    const tocContainer = document.querySelector('.toc .inner');
                    const linkOffsetTop = tocLink.offsetTop;
                    const containerHeight = tocContainer.clientHeight;
                    const linkHeight = tocLink.clientHeight;
    
                    // Calculate the scroll position to center the active link
                    const scrollPosition = linkOffsetTop - (containerHeight / 2) + (linkHeight / 2);
                    tocContainer.scrollTo({ top: scrollPosition, behavior: 'smooth' });
                } else {
                    tocLink.classList.remove('active');
                }
            });
        }
    }, false);
    
    const main = parseInt(getComputedStyle(document.body).getPropertyValue('--article-width'), 10);
    const toc = parseInt(getComputedStyle(document.body).getPropertyValue('--toc-width'), 10);
    const gap = parseInt(getComputedStyle(document.body).getPropertyValue('--gap'), 10);
    
    function checkTocPosition() {
        const width = document.body.scrollWidth;
    
        if (width - main - (toc * 2) - (gap * 4) > 0) {
            document.getElementById("toc-container").classList.add("wide");
        } else {
            document.getElementById("toc-container").classList.remove("wide");
        }
    }
    
    function getOffsetTop(element) {
        if (!element.getClientRects().length) {
            return 0;
        }
        let rect = element.getBoundingClientRect();
        let win = element.ownerDocument.defaultView;
        return rect.top + win.pageYOffset;   
    }
    
</script>
{{- end }}
```

```toml{title="archetypes\default.toml"}
showToc = true # 显示目录
TocOpen = true # 打开目录

```
