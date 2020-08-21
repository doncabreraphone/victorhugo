# Hugo Seo Snippets
This is a quick reference document of best practices for SEO with Hugo. Compiled from <a href="https://github.com/praveenjuge/hugo-SEO-meta-tags">Praveen Juge's SEO meta tags project.</a>

### Internal Templates
Hugo supports <a href="https://gohugo.io/templates/internal/">internal boilerplate templates</a> that will cover the most common use cases for static websites. Among those, these two stand out.

**Open Graph :** https://gohugo.io/templates/internal/#open-graph

**Twitter Cards with Hugo :** https://gohugo.io/templates/internal/#twitter-cards

We recommend you to always configure these two in all your instlalations.

Victor Hugo will analize your post, regardless of you having configured those, though.


### ``Config.toml``
```
baseURL = "https://www.example.org/"
title = "Example Site"

languageCode = "en-us"
DefaultContentLanguage = "en"

[params]
  author = "Praveen Juge"
  github = "https://github.com/praveenjuge"
  facebook = "https://facebook.com/praveenjuge"
  og_image = "/images/og.png"
  sitename = "Example Site Name"
  twitter = "@praveenjuge"
```

### ``baseof.html``
A default <a href="https://gohugo.io/templates/base/">baseof.html</a> file with best SEO practices.
```
<!DOCTYPE html>
<html prefix="og: http://ogp.me/ns#" lang="{{ .Language }}">
  <head itemscope itemtype="{{ .Site.BaseURL }}">
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />

    <!-- All the meta tags below will come under this meta partial -->
    {{ partial "meta" . }}
    {{ partial "links" . }}
  </head>

  <body>
    {{ partial "header" . }}
    <main id="main">
      {{ block "main" . }}
      {{ end }}
    </main>
    {{ partial "footer" . }}
    {{ partial "js" . }}
  </body>
</html>
```


### Title Tags
```
<title itemprop="name">{{ .Title }} | {{ .Site.Title }}</title>
<meta property="og:title" content="{{ .Title }} | {{ .Site.Title }}" />
<meta name="twitter:title" content="{{ .Title }} | {{ .Site.Title }}" />
<meta itemprop="name" content="{{ .Title }} | {{ .Site.Title }}" />
<meta name="application-name" content="{{ .Title }} | {{ .Site.Title }}" />
<meta property="og:site_name" content="{{ .Site.Params.sitename }}" />
```


### Description Tags
```
<meta name="description" content="{{ .Params.description }}" />
<meta itemprop="description" content="{{ .Params.description }}" />
<meta property="og:description" content="{{ .Params.description }}" />
<meta name="twitter:description" content="{{ .Params.description }}" />
```


### Image Tags

```
{{ with .Params.image }} 
  <meta itemprop="image" content="{{ . | absURL }}" />
  <meta property="og:image" content="{{ . | absURL }}" /> 
  <meta name="twitter:image" content="{{ . | absURL }}" />
  <meta name="twitter:image:src" content="{{ . | absURL }}" /> 
{{ else }}
  <meta itemprop="image" content="{{ .Site.Params.ogimage | absURL }}" />
  <meta property="og:image" content="{{ .Site.Params.ogimage | absURL }}" />
  <meta name="twitter:image" content="{{ .Site.Params.ogimage | absURL }}" />
  <meta name="twitter:image:src" content="{{ .Site.Params.ogimage | absURL }}" /> 
{{ end }}
```

### Search Engine Crawler Tags 
```
<meta name="robots" content="index,follow" />
<meta name="googlebot" content="index,follow" />
```

### Sitemap & RSS Feed Tags
```
<link rel="sitemap" type="application/xml" title="Sitemap" href='{{ "sitemap.xml" | absURL }}' />

{{ with .OutputFormats.Get "RSS" }}
  <link href="{{ .Permalink }}" rel="alternate" type="application/rss+xml" title="{{ $.Site.Title }}" />
  <link href="{{ .Permalink }}" rel="feed" type="application/rss+xml" title="{{ $.Site.Title }}" />
{{ end }}
```