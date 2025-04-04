# Comprehensive List of Meta Tags

This list covers various types of meta tags used in HTML documents, including standard, SEO-related, social media (Open Graph, Twitter Cards), mobile/viewport configuration, and others.

---

## 1. Standard HTML Meta Tags

These are defined by HTML standards (WHATWG/W3C).

*   **Charset Declaration:**
    *   `<meta charset="UTF-8">`
    *   **Purpose:** Specifies the character encoding for the document. UTF-8 is the universal standard and highly recommended. (Technically not a `name` attribute meta tag, but placed similarly).

*   **Content Description:**
    *   `<meta name="description" content="A brief description of the page content (typically 150-160 characters).">`
    *   **Purpose:** Provides a summary of the page's content. Used by search engines for snippets in search results. Crucial for SEO.

*   **Keywords (Largely Ignored by Major Search Engines):**
    *   `<meta name="keywords" content="keyword1, keyword2, keyword3">`
    *   **Purpose:** Historically used to list relevant keywords for the page. Most major search engines (like Google) no longer use this for ranking purposes due to abuse, but some smaller engines might.

*   **Author:**
    *   `<meta name="author" content="Author Name or Company Name">`
    *   **Purpose:** Specifies the author of the document.

*   **Generator:**
    *   `<meta name="generator" content="CMS Name or Software vX.Y">`
    *   **Purpose:** Indicates the software used to generate the page (e.g., "WordPress 6.2"). Often added automatically by CMSs.

*   **Viewport Settings (Crucial for Responsive Design):**
    *   `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
    *   **Purpose:** Controls the layout on mobile browsers. `width=device-width` sets the width of the viewport to the device width, and `initial-scale=1.0` sets the initial zoom level. Other options exist (e.g., `maximum-scale`, `user-scalable=no`).

*   **Robots Control (Crucial for SEO):**
    *   `<meta name="robots" content="index, follow">` (Default, often omitted)
    *   `<meta name="robots" content="noindex, nofollow">`
    *   `<meta name="robots" content="noindex, follow">`
    *   `<meta name="robots" content="index, nofollow">`
    *   `<meta name="robots" content="noarchive">` (Don't show cached link)
    *   `<meta name="robots" content="nosnippet">` (Don't show snippet in results)
    *   `<meta name="robots" content="notranslate">` (Don't offer translation)
    *   `<meta name="robots" content="noimageindex">` (Don't index images on this page)
    *   `<meta name="robots" content="unavailable_after: [RFC 850 date/time]">` (Don't show after specific date)
    *   **Purpose:** Provides instructions to web crawlers (bots). You can combine values (e.g., `"noindex, nofollow, noarchive"`). Specific bot targeting is also possible (e.g., `<meta name="googlebot" content="...">`).

*   **Content Type (Legacy - Prefer `charset`):**
    *   `<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">`
    *   **Purpose:** Used to declare the document's MIME type and character set. The `<meta charset="UTF-8">` tag is the modern, preferred way to set the charset.

*   **Refresh/Redirect (Use with Caution):**
    *   `<meta http-equiv="refresh" content="5;url=https://example.com/">`
    *   **Purpose:** Refreshes the page after a delay or redirects to another URL. Server-side redirects (301/302) are strongly preferred for SEO and user experience.

*   **Theme Color (Browser UI Hint):**
    *   `<meta name="theme-color" content="#4285f4">`
    *   **Purpose:** Suggests a color for user agents to customize the display of the page or surrounding UI (e.g., the browser's address bar or task switcher).

*   **Referrer Policy:**
    *   `<meta name="referrer" content="origin">` (or `no-referrer`, `origin-when-cross-origin`, `strict-origin`, etc.)
    *   **Purpose:** Controls how much referrer information (the previous page URL) is sent with requests originating from the document.

---

## 2. Open Graph (OG) Tags (for Facebook, LinkedIn, Pinterest, etc.)

These tags control how your content appears when shared on social platforms that support the Open Graph protocol. They use the `property` attribute.

*   **Basic Required Tags:**
    *   `<meta property="og:title" content="The Title of Your Content Here">`
    *   `<meta property="og:type" content="website">` (Common types: `website`, `article`, `book`, `profile`, `video.movie`, `music.song`)
    *   `<meta property="og:image" content="https://example.com/image.jpg">` (URL to the representative image)
    *   `<meta property="og:url" content="https://example.com/page.html">` (The canonical URL of the page)

*   **Optional Recommended Tags:**
    *   `<meta property="og:description" content="A brief description, often longer than the meta description (aim for ~200 chars).">`
    *   `<meta property="og:site_name" content="Your Site Name">`
    *   `<meta property="og:locale" content="en_US">` (Default is `en_US`. Use `language_TERRITORY` format)
    *   `<meta property="og:locale:alternate" content="fr_FR">`
    *   `<meta property="og:locale:alternate" content="es_ES">`

*   **Image Specific Tags:**
    *   `<meta property="og:image:secure_url" content="https://example.com/secure-image.jpg">` (HTTPS URL for the image)
    *   `<meta property="og:image:type" content="image/jpeg">` (MIME type: `image/jpeg`, `image/png`, `image/gif`)
    *   `<meta property="og:image:width" content="1200">` (Pixel width)
    *   `<meta property="og:image:height" content="630">` (Pixel height - 1.91:1 ratio often recommended)
    *   `<meta property="og:image:alt" content="Alt text describing the image">` (Highly recommended for accessibility)
    *   *(You can include multiple `og:image` tags for platforms to choose from)*

*   **Video Specific Tags (when `og:type` is video related):**
    *   `<meta property="og:video" content="https://example.com/video.mp4">` (URL to the video file)
    *   `<meta property="og:video:secure_url" content="https://example.com/secure-video.mp4">`
    *   `<meta property="og:video:type" content="video/mp4">` (MIME type)
    *   `<meta property="og:video:width" content="1280">`
    *   `<meta property="og:video:height" content="720">`

*   **Audio Specific Tags (when `og:type` is audio related):**
    *   `<meta property="og:audio" content="https://example.com/audio.mp3">`
    *   `<meta property="og:audio:secure_url" content="https://example.com/secure-audio.mp3">`
    *   `<meta property="og:audio:type" content="audio/mpeg">`

*   **Article Specific Tags (when `og:type` is `article`):**
    *   `<meta property="article:published_time" content="YYYY-MM-DDTHH:MM:SSZ">` (ISO 8601 format)
    *   `<meta property="article:modified_time" content="YYYY-MM-DDTHH:MM:SSZ">`
    *   `<meta property="article:expiration_time" content="YYYY-MM-DDTHH:MM:SSZ">`
    *   `<meta property="article:author" content="Profile URL or Name">` (Can be repeated for multiple authors)
    *   `<meta property="article:section" content="Technology">` (Category)
    *   `<meta property="article:tag" content="tag1">` (Can be repeated)

*   **Book Specific Tags (when `og:type` is `book`):**
    *   `<meta property="book:author" content="Profile URL or Name">`
    *   `<meta property="book:isbn" content="ISBN Number">`
    *   `<meta property="book:release_date" content="YYYY-MM-DD">`
    *   `<meta property="book:tag" content="tag1">`

*   **Profile Specific Tags (when `og:type` is `profile`):**
    *   `<meta property="profile:first_name" content="First Name">`
    *   `<meta property="profile:last_name" content="Last Name">`
    *   `<meta property="profile:username" content="Username">`
    *   `<meta property="profile:gender" content="male | female">`

---

## 3. Twitter Card Tags

These provide richer experiences when content is shared on Twitter. They often fall back to OG tags if not present, but specific Twitter tags offer more control.

*   **Card Type:**
    *   `<meta name="twitter:card" content="summary">` (Default: Title, description, thumbnail)
    *   `<meta name="twitter:card" content="summary_large_image">` (Similar to summary, but with a larger featured image)
    *   `<meta name="twitter:card" content="app">` (Direct link to a mobile app)
    *   `<meta name="twitter:card" content="player">` (Provides inline video/audio playback)

*   **Common Tags (Often Mirroring OG):**
    *   `<meta name="twitter:site" content="@YourSiteHandle">` (The Twitter @username the website belongs to)
    *   `<meta name="twitter:creator" content="@AuthorHandle">` (The Twitter @username of the content creator/author)
    *   `<meta name="twitter:title" content="Title (falls back to og:title)">`
    *   `<meta name="twitter:description" content="Description (max 200 chars, falls back to og:description)">`
    *   `<meta name="twitter:image" content="https://example.com/twitter-image.jpg">` (URL of image, falls back to og:image. Needs to be <= 5MB. Different sizes per card type.)
    *   `<meta name="twitter:image:alt" content="Alt text for image">` (Highly recommended)

*   **Player Card Specific Tags:**
    *   `<meta name="twitter:player" content="https://example.com/player.html">` (HTTPS URL to the player iframe)
    *   `<meta name="twitter:player:width" content="480">`
    *   `<meta name="twitter:player:height" content="480">`
    *   `<meta name="twitter:player:stream" content="https://example.com/video.mp4">` (Direct video/audio stream URL)
    *   `<meta name="twitter:player:stream:content_type" content="video/mp4; codecs="avc1.42E01E, mp4a.40.2"">`

*   **App Card Specific Tags:**
    *   `<meta name="twitter:app:name:iphone" content="YourAppName">`
    *   `<meta name="twitter:app:id:iphone" content="YourAppID">`
    *   `<meta name="twitter:app:url:iphone" content="your-app-scheme://...">`
    *   `<meta name="twitter:app:name:ipad" content="YourAppName">`
    *   `<meta name="twitter:app:id:ipad" content="YourAppID">`
    *   `<meta name="twitter:app:url:ipad" content="your-app-scheme://...">`
    *   `<meta name="twitter:app:name:googleplay" content="YourAppName">`
    *   `<meta name="twitter:app:id:googleplay" content="com.example.app">`
    *   `<meta name="twitter:app:url:googleplay" content="https://play.google.com/store/apps/details?id=...">`

---

## 4. Apple iOS Specific Meta Tags

Used for web apps saved to the home screen on iOS devices.

*   `<meta name="apple-mobile-web-app-capable" content="yes">` (Allows launching in full-screen mode)
*   `<meta name="apple-mobile-web-app-status-bar-style" content="black">` (Options: `default`, `black`, `black-translucent`)
*   `<meta name="apple-mobile-web-app-title" content="App Title">` (Title shown below the icon on the home screen)
*   `<meta name="format-detection" content="telephone=no">` (Prevents automatic detection and linking of phone numbers)

---

## 5. Microsoft Specific Meta Tags

Mainly for Windows tiles and older IE compatibility.

*   `<meta http-equiv="X-UA-Compatible" content="IE=edge">` (Tells older IE versions to use the latest rendering engine available)
*   `<meta name="msapplication-TileColor" content="#ffffff">` (Color for Windows Start Screen tile)
*   `<meta name="msapplication-TileImage" content="/ms-tile-image.png">` (Image for Windows Start Screen tile)
*   `<meta name="msapplication-config" content="/browserconfig.xml">` (Points to an XML file with more tile configurations)

---

## 6. Verification Meta Tags

Used to prove ownership of a site to various webmaster tools.

*   `<meta name="google-site-verification" content="YourVerificationString">` (Google Search Console)
*   `<meta name="msvalidate.01" content="YourVerificationString">` (Bing Webmaster Tools)
*   `<meta name="p:domain_verify" content="YourVerificationString">` (Pinterest Verification - file upload is also common)
*   `<meta name="yandex-verification" content="YourVerificationString">` (Yandex Webmaster)
*   `<meta name="facebook-domain-verification" content="YourVerificationString">` (Facebook Business Manager)

---

## 7. Other Less Common / Niche / Deprecated Meta Tags

*   `<meta name="rating" content="General">` (Content rating, e.g., `General`, `Mature`, `Restricted`. Largely symbolic.)
*   `<meta name="copyright" content="Copyright © YYYY Your Name/Company">`
*   `<meta name="distribution" content="Global">` (Intended audience distribution, e.g., `Global`, `Local`, `IU` (Internal Use). Rarely used.)
*   `<meta name="resource-type" content="document">` (Legacy tag indicating the type of resource.)
*   `<meta name="revisit-after" content="7 days">` (Suggests revisit frequency to crawlers - generally ignored by major search engines.)
*   `<meta name="format-detection" content="email=no">`
*   `<meta name="format-detection" content="address=no">`
*   `<meta http-equiv="Cache-Control" content="no-cache">` (Attempts to control caching; HTTP headers are the reliable way.)
*   `<meta http-equiv="Pragma" content="no-cache">` (Similar to above, less effective; use HTTP headers.)
*   `<meta http-equiv="Expires" content="0">` or `<meta http-equiv="Expires" content="[Date]">` (Suggests expiration; use HTTP headers.)

---

## Important Considerations

*   **JSON-LD for Structured Data:** While not meta tags, using JSON-LD within a `<script>` tag in the `<head>` is the modern, preferred way (recommended by Google) to provide detailed structured data (Schema.org) to search engines for rich snippets, knowledge graph information, etc. It's more flexible and powerful than embedding microdata or RDFa directly in HTML tags.
*   **`link` Tags:** Don't confuse meta tags with `<link>` tags also found in the head, such as:
    *   `<link rel="canonical" href="https://example.com/canonical-url">` (Crucial for SEO to indicate the preferred URL)
    *   `<link rel="alternate" hreflang="es" href="https://example.com/es/page">` (For multilingual sites)
    *   `<link rel="icon" href="/favicon.ico">` (Favicon)
    *   `<link rel="stylesheet" href="styles.css">` (CSS)
*   **Validation:** Use tools like the Facebook Sharing Debugger, Twitter Card Validator, and Schema.org validators to check your implementation.
*   **Necessity:** Only include the meta tags that are necessary and relevant to your content and goals. Overloading with unnecessary tags adds bloat.

# Comprehensive List of Meta Tags (Continued)

This list continues from the previous sections, adding more specialized metadata standards like Dublin Core and relevant `<link>` tags often managed alongside meta tags.

---

## 8. Dublin Core Metadata Element Set (DC Tags)

Dublin Core is a set of standardized metadata terms for describing resources. While less common for general web pages than Open Graph or Twitter Cards, it's used in digital libraries, archives, and specific contexts. They typically use the `name` attribute prefixed with `DC.`.

*   `<meta name="DC.Title" content="Resource Title">`
*   `<meta name="DC.Creator" content="Creator Name">`
*   `<meta name="DC.Subject" content="Keywords or Subject Matter">`
*   `<meta name="DC.Description" content="Description of the resource">`
*   `<meta name="DC.Publisher" content="Publisher Name">`
*   `<meta name="DC.Contributor" content="Contributor Name">`
*   `<meta name="DC.Date" content="YYYY-MM-DD">` (Creation or publication date)
*   `<meta name="DC.Type" content="Text">` (Nature or genre, e.g., `Collection`, `Dataset`, `Image`, `InteractiveResource`, `Service`, `Software`, `Sound`, `Text`)
*   `<meta name="DC.Format" content="text/html">` (MIME type or physical medium)
*   `<meta name="DC.Identifier" content="https://example.com/resource-id">` (Unique identifier, often the URL or a DOI)
*   `<meta name="DC.Source" content="Source Resource">` (A related resource from which the described resource is derived)
*   `<meta name="DC.Language" content="en">` (Language code, e.g., ISO 639-1)
*   `<meta name="DC.Relation" content="Related Resource">` (A related resource)
*   `<meta name="DC.Coverage" content="Spatial or Temporal Topic">` (e.g., a location name or time period)
*   `<meta name="DC.Rights" content="Copyright Statement or Rights Holder">`

*(Note: Dublin Core has more qualified terms (e.g., `DCTERMS.issued`, `DCTERMS.abstract`), but the simple DC set above is more commonly seen when implemented via basic meta tags.)*

---

## 9. Relevant `<link>` Tags (Often used alongside Meta Tags)

While not technically `<meta>` tags, these `<link>` tags serve related purposes in defining relationships, resource hints, or providing metadata, and are crucial parts of the `<head>`.

*   **Canonical URL:**
    *   `<link rel="canonical" href="https://example.com/preferred-url">`
    *   **Purpose:** Specifies the preferred URL for content that might be accessible via multiple URLs. Essential for SEO to avoid duplicate content issues.

*   **Alternate Languages/Regions (hreflang):**
    *   `<link rel="alternate" hreflang="es" href="https://example.com/es/page">`
    *   `<link rel="alternate" hreflang="en-GB" href="https://example.com/uk/page">`
    *   `<link rel="alternate" hreflang="x-default" href="https://example.com/">` (Default/fallback version)
    *   **Purpose:** Tells search engines about different language or regional versions of a page. Crucial for international SEO.

*   **Alternate Formats/Feeds:**
    *   `<link rel="alternate" type="application/rss+xml" title="RSS Feed" href="/feed.xml">`
    *   `<link rel="alternate" type="application/atom+xml" title="Atom Feed" href="/atom.xml">`
    *   `<link rel="alternate" type="application/json" title="JSON Feed" href="/feed.json">`
    *   `<link rel="alternate" type="application/pdf" title="PDF Version" href="/document.pdf">`
    *   **Purpose:** Points to alternative representations or syndication feeds for the content.

*   **Favicons (Multiple Sizes/Formats Recommended):**
    *   `<link rel="icon" href="/favicon.ico" sizes="any">` (Traditional ICO format)
    *   `<link rel="icon" href="/favicon.svg" type="image/svg+xml">` (Modern SVG format)
    *   `<link rel="apple-touch-icon" href="/apple-touch-icon.png">` (For iOS home screen icons)
    *   `<link rel="manifest" href="/site.webmanifest">` (Points to the Web App Manifest file, which itself contains metadata like icons, theme color, display mode, etc.)

*   **Resource Hints (Performance Optimization):**
    *   `<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>` (Establish connection early)
    *   `<link rel="dns-prefetch" href="//example.com">` (Resolve DNS early)
    *   `<link rel="preload" href="/critical.css" as="style">` (Load critical resources sooner)
    *   `<link rel="prefetch" href="/next-page.html" as="document">` (Load resources likely needed for next navigation)

*   **Pagination:**
    *   `<link rel="prev" href="https://example.com/page/1/">`
    *   `<link rel="next" href="https://example.com/page/3/">`
    *   **Purpose:** Indicates the relationship between pages in a sequence (e.g., paginated archives). Google now primarily relies on links within the page content for discovery, but these can still provide context.

*   **License:**
    *   `<link rel="license" href="https://creativecommons.org/licenses/by/4.0/">`
    *   **Purpose:** Specifies the license under which the content is provided.

---

## 10. Considerations for HTTP Headers

It's important to remember that some metadata-like directives are more effectively or exclusively controlled via **HTTP Headers** sent by the server, rather than meta tags in the HTML. These include:

*   **Content Security Policy (CSP):** Defines allowed sources for content, mitigating XSS attacks.
    *   `Content-Security-Policy: default-src 'self'; img-src *; media-src media1.com media2.com; script-src userscripts.example.com`
*   **Caching Directives:** Precise control over how browsers and proxies cache content.
    *   `Cache-Control: no-cache, no-store, must-revalidate`
    *   `Pragma: no-cache` (Legacy)
    *   `Expires: 0` (Legacy)
*   **Strict Transport Security (HSTS):** Enforces HTTPS.
    *   `Strict-Transport-Security: max-age=31536000; includeSubDomains`
*   **X-Content-Type-Options:** Prevents MIME-sniffing.
    *   `X-Content-Type-Options: nosniff`
*   **X-Frame-Options:** Controls embedding in `<iframe>`.
    *   `X-Frame-Options: DENY` or `SAMEORIGIN`
*   **Referrer-Policy:** Controls referrer information (can also be set via meta tag, but header has wider scope).
    *   `Referrer-Policy: strict-origin-when-cross-origin`

---

This expanded list covers the vast majority of meta tags and closely related `<link>` tags you might encounter or need to use. Remember to prioritize based on your specific needs: basic HTML, SEO (robots, description, canonical), social sharing (OG, Twitter), responsive design (viewport), and structured data (JSON-LD) are typically the most critical areas.
