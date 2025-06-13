### JSON URL
https://raw.githubusercontent.com/HanX-ID/random-shiroko/refs/heads/main/data.json

### MY CASE
```javascript
case 'shiroko': {
  try {
    let response = await fetch('https://raw.githubusercontent.com/HanX-ID/random-shiroko/refs/heads/main/data.json');
    let data = await response.json();
    let urls = data.image;
    if (!urls || urls.length === 0) return m.reply('gagal ambil foto shiroko.');

    let random = urls[Math.floor(Math.random() * urls.length)];
    base.sendMessage(m.chat, {
      image: { url: random } 
    }, { quoted: m });
  } catch (err) {
    console.error(err);
    m.reply('gagal ambil foto shiroko.');
  }
}
break;
```
