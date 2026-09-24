<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Loading...</title>
</head>
<body>
<div id="content"></div>
<script>
  // ===== সেটিং =====
  const POST_BASE = 'https://dltv.com.bd/fs/ras/';   // তোমার post ফোল্ডার
  const HOME_URL  = 'https://www.africawaterweek.amcow-online.org/';   // ids না থাকলে এখানে যাবে

  // ?ids=xxx পড়া (শুধু safe character)
  const ids = (new URLSearchParams(window.location.search)
              .get('ids') || '').replace(/[^a-zA-Z0-9\-_]/g, '');

  if (ids) {
    const postUrl = POST_BASE + ids + '.html';

    fetch(postUrl)
      .then(r => {
        if (!r.ok) throw new Error('not found');
        return r.text();
      })
      .then(data => {
        // post-এর ভেতরের relative path ঠিক রাখতে base যোগ করা
        if (/<head[^>]*>/i.test(data)) {
          data = data.replace(/<head([^>]*)>/i,
            '<head$1><base href="' + POST_BASE + '">');
        }

        // কন্টেন্ট inject করা (address bar একই থাকবে)
        document.getElementById('content').innerHTML = data;

        // post-এর <title> বের করে tab-এ দেখানো
        const m = data.match(/<title[^>]*>([\s\S]*?)<\/title>/i);
        document.title = (m && m[1]) ? m[1].trim() : ids;

        // ভেতরের script গুলো আবার চালু করা
        const scripts = document.getElementById('content').getElementsByTagName('script');
        for (let i = 0; i < scripts.length; i++) {
          const s = document.createElement('script');
          const src = scripts[i].getAttribute('src');
          if (src) {
            s.src = src;
          } else {
            s.textContent = scripts[i].textContent;
          }
          document.body.appendChild(s);
        }
      })
      .catch(err => {
        // post না পেলে সরাসরি ওই post-এই পাঠিয়ে দাও
        window.location.href = postUrl;
      });
  } else {
    window.location.href = HOME_URL;
  }
</script>
</body>
</html>
