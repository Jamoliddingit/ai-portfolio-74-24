𝐈𝐬𝐦𝐨𝐢𝐥𝐨𝐟𝐟, [14.10.2025 15:49]
<!DOCTYPE html>
<html lang="uz">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>AI Portfolio 74-24</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: "Poppins", sans-serif;
      background: #f3f4f6;
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
    }

    header {
      text-align: center;
      padding: 2rem 1rem;
    }

    h1 {
      font-size: 2rem;
      color: #1e3a8a;
    }

    input {
      padding: 0.7rem 1rem;
      width: 80%;
      max-width: 500px;
      border-radius: 8px;
      border: 1px solid #cbd5e1;
      margin-bottom: 1rem;
      outline: none;
    }

    .list {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
      gap: 1rem;
      width: 90%;
      max-width: 900px;
    }

    .student {
      background: white;
      border-radius: 12px;
      padding: 1rem;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
      cursor: pointer;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }

    .student:hover {
      transform: translateY(-5px);
      box-shadow: 0 4px 14px rgba(0, 0, 0, 0.15);
    }

    .portfolio {
      display: none;
      max-width: 700px;
      background: white;
      border-radius: 16px;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
      padding: 2rem;
      margin: 1rem;
      animation: fadeIn 0.4s ease;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.98); }
      to { opacity: 1; transform: scale(1); }
    }

    .back-btn {
      display: inline-block;
      margin-top: 1rem;
      background: #2563eb;
      color: white;
      padding: 0.6rem 1.4rem;
      border-radius: 8px;
      text-decoration: none;
      transition: background 0.2s ease;
    }

    .back-btn:hover {
      background: #1e40af;
    }

    footer {
      text-align: center;
      padding: 1rem;
      margin-top: auto;
    }

    .button {
      background-color: #2563eb;
      color: #fff;
      padding: 0.8rem 1.6rem;
      border-radius: 10px;
      text-decoration: none;
    }
  </style>
</head>
<body>
  <header>
    <h1>🧠 AI Portfolio 74-24</h1>
    <input type="text" id="search" placeholder="Ism bo‘yicha qidirish..." />
  </header>

  <div class="list" id="list"></div>

  <div class="portfolio" id="portfolio"></div>

  <footer>
    <a class="button" href="https://t.me/Portfolio7424Bot" target="_blank">🤖 Bot orqali ko‘rish</a>
  </footer>

𝐈𝐬𝐦𝐨𝐢𝐥𝐨𝐟𝐟, [14.10.2025 15:49]
<script>
    const students = [
  { id: 1, name: "Abdullayev Ulug‘bek O‘tkir o‘g‘li" },
  { id: 2, name: "Abdurasulov Xondamir Nozimjon o‘g‘li" },
  { id: 3, name: "Abdusalamov Suxrob Tulqin o‘g‘li" },
  { 
    id: 4, 
    name: "Absalamova Zilolaxon Ergashxo‘ja qizi", 
    db: "https://e-commerce-one-omega-68.vercel.app/", 
    tech: ["HTML", "CSS", "Sass", "JavaScript", "React", "Bootstrap", "Tailwind", "Python"]
  },
  { id: 5, name: "Ahmadaliyev Muhammadjon Abduxalil o‘g‘li" },
  { id: 6, name: "Allayev Yoqubjon Rayimjon o‘g‘li" },
  { id: 7, name: "Boxodirov Nazarbek Qobuljon o‘g‘li" },
  { id: 8, name: "Davlatboyev Bunyod Rashid o‘g‘li" },
  { id: 9, name: "Davlatova Sevinch Faxriddin qizi" },
  { id: 10, name: "Doniyorbekov Rashidbek Xurshidbek o‘g‘li" },
  { id: 11, name: "Hakimov Oybek Obid o‘g‘li" },
  { id: 12, name: "Ismoilov Jamoliddin Kamoliddin o‘g‘li" },
  { id: 13, name: "Jabborqulov Otabek Ulug‘bek o‘g‘li" },
  { id: 14, name: "Maxmudova Zulayho Jumanazar qizi" },
  { id: 15, name: "Murodullayev Javohir Akmal o‘g‘li" },
  { id: 16, name: "Ongarbaev Quralbay Baxadírovich" },
  { id: 17, name: "Ozodova Malikaxon Ravshan qizi" },
  { id: 18, name: "Pulatov Dilshod Dilmurod o‘g‘li" },
  { id: 19, name: "Qayumjonov Mahmudjon Mahkamjon o‘g‘li" },
  { id: 20, name: "Saatbayev Sherzod Farxadovich" },
  { id: 21, name: "Sheraliyev O‘tkirbek Alisher o‘g‘li" },
  { id: 22, name: "Sobirqulov Baxodir Zoir o‘g‘li" },
  { id: 23, name: "Sodiqov Xudoyberdi Ato o‘g‘li" },
  { id: 24, name: "Suyundiqov Abdulazizjon Alisher o‘g‘li" },
  { id: 25, name: "Vaxobov Ismoil Vaxob o‘g‘li" }
];


    const list = document.getElementById("list");
    const portfolio = document.getElementById("portfolio");
    const search = document.getElementById("search");

    function renderList(filtered = students) {
      list.innerHTML = filtered.map(s => `
        <div class="student" onclick="openPortfolio(${s.id})">
          ${s.name}
        </div>
      `).join("");
    }

    function openPortfolio(id) {
      const s = students.find(st => st.id === id);
      list.style.display = "none";
      portfolio.style.display = "block";
      portfolio.innerHTML = `
        <h2>${s.name}</h2>
        ${s.tech ? <p><b>Texnologiyalar:</b> ${s.tech.join(", ")}</p> : ""}
        ${s.db ? <p><a href="${s.db}" target="_blank"> Ma'lumotar bazasini ko'rish</a></p> : ""}
        <a href="#" class="back-btn" onclick="goBack()">⬅️ Orqaga</a>
      `;
    }

    function goBack() {
      portfolio.style.display = "none";
      list.style.display = "grid";
    }

    search.addEventListener("input", e => {
      const val = e.target.value.toLowerCase();
      const filtered = students.filter(s => s.name.toLowerCase().includes(val));
      renderList(filtered);
    });

    renderList();
  </script>
</body>
</html>
