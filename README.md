# Whell-Of-Fortune-Discord-Bot
Repository ini berisi kode sumber untuk Game Whell Of Fortune di Discord .Game ini memungkinkan pengguna untuk memainkan  game dengan cara memilih peserta secara acak dan mengumumkan peserta yang terpilih 

Berikut adalah contoh kode game Wheel of Fortune

Kode Game Wheel of Fortune
```
const Discord = require('discord.js');
const client = new Discord.Client();

// Daftar nama-nama peserta
const peserta = ['John Doe', 'Jane Doe', 'Bob Smith', 'Alice Johnson', 'Mike Brown'];

// Daftar hadiah
const hadiah = ['1000 poin', '500 poin', '300 poin', '200 poin', '100 poin'];

// Fungsi untuk memilih peserta secara acak
function pilihPeserta() {
  const index = Math.floor(Math.random() * peserta.length);
  return peserta[index];
}

// Fungsi untuk memilih hadiah secara acak
function pilihHadiah() {
  const index = Math.floor(Math.random() * hadiah.length);
  return hadiah[index];
}

client.on('ready', () => {
  console.log('Bot siap!');
});

client.on('message', (message) => {
  if (message.content === '!wheel') {
    // Memilih peserta secara acak
    const pesertaTerpilih = pilihPeserta();
    
    // Memilih hadiah secara acak
    const hadiahTerpilih = pilihHadiah();
    
    // Mengatur waktu antara putaran wheel
    const waktu = 5000; // 5 detik
    
    // Mengumumkan nama peserta yang terpilih
    message.reply(`Selamat, ${pesertaTerpilih}! Kamu terpilih!`);
    
    // Mengumumkan hadiah yang terpilih
    setTimeout(() => {
      message.reply(`Hadiahmu adalah: ${hadiahTerpilih}!`);
    }, waktu);
  }
});

client.login('TOKEN_BOT_ANDA');
```

Cara Bermain
1. Ketik `!wheel` di channel Discord untuk memulai permainan.
2. Bot akan memilih secara acak salah satu peserta dari daftar nama-nama peserta.
3. Bot akan mengumumkan nama peserta yang terpilih.
4. Setelah 5 detik, bot akan mengumumkan hadiah yang terpilih bagi pemenang.

Menambahkan Fitur
Anda dapat menambahkan fitur-fitur lainnya, seperti:

- Mengatur jumlah putaran wheel
- Mengatur waktu antara putaran wheel
- Mengatur sistem poin untuk peserta yang terpilih
- Mengatur hadiah tambahan untuk pemenang

Dengan demikian, Anda telah berhasil membuat game Wheel of Fortune yang berisi nama-nama peserta dan hadiah bagi pemenang di bot Discord.