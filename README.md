<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>LMIER - Laboratoire des Matériaux Innovants et Énergies Renouvelables</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Comfortaa:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --blue:#1e9aed;
      --blue2:#58b1f5;
      --blue3:#8fc5f7;
      --bg:#ffffff;
      --text:#155f96;
      --muted:#6b8aa3;
      --card:#f7fbff;
      --line:#d8ebfb;
      --shadow:0 12px 30px rgba(30,154,237,.10);
      --radius:22px;
    }
    *{box-sizing:border-box}
    html,body{margin:0;padding:0;background:#fff;color:var(--text);font-family:'Comfortaa',sans-serif}
    body{overflow-x:hidden}
    .container{width:min(1220px,calc(100% - 32px));margin:0 auto}
    header{
      padding:28px 0 24px;
      background:
        radial-gradient(circle at 10% 10%, rgba(30,154,237,.04), transparent 24%),
        radial-gradient(circle at 90% 15%, rgba(30,154,237,.05), transparent 22%),
        linear-gradient(180deg,#fff 0%,#fbfdff 100%);
      border-bottom:1px solid #eef6fd;
    }
    .brand{
      display:grid;
      grid-template-columns: 380px 1fr;
      gap:24px;
      align-items:center;
      justify-items:center;
    }
    .logo-wrap{display:flex;align-items:center;justify-content:center;width:100%}
    .wordmark{font-size:5.6rem;line-height:1;color:var(--blue);font-weight:400;letter-spacing:-.06em}
    .tagline{
      text-align:center;
      color:var(--blue);
      font-size:1.55rem;
      line-height:1.25;
      margin-top:24px;
      font-weight:400;
    }
    .hero-note{
      margin-top:18px;
      text-align:center;
      color:var(--muted);
      font-size:.96rem;
    }
    nav{
      position:sticky;top:0;z-index:20;
      backdrop-filter:saturate(150%) blur(12px);
      background:rgba(255,255,255,.9);
      border-bottom:1px solid #edf6fd;
    }
    .nav-inner{
      display:flex;align-items:center;justify-content:space-between;gap:16px;
      min-height:64px;
    }
    .nav-title{font-weight:700;color:var(--blue);letter-spacing:.02em}
    .nav-links{display:flex;gap:10px;flex-wrap:wrap}
    .nav-links a,.nav-links button{
      border:none;text-decoration:none;background:#fff;color:var(--text);
      border:1px solid var(--line);padding:10px 14px;border-radius:999px;
      font-family:inherit;cursor:pointer;font-size:.9rem;transition:.2s ease;
    }
    .nav-links a:hover,.nav-links button:hover{background:var(--blue);color:#fff;border-color:var(--blue)}
    main{padding:28px 0 60px}
    .intro{
      display:grid;grid-template-columns:1.2fr .8fr;gap:20px;margin-bottom:26px;
    }
    .panel{
      background:var(--card);border:1px solid var(--line);border-radius:var(--radius);
      box-shadow:var(--shadow);padding:22px;
    }
    .panel h2{margin:0 0 10px;color:var(--blue);font-size:1.35rem}
    .panel p{margin:0;color:var(--muted);line-height:1.7;font-size:.96rem}
    .stats{display:grid;grid-template-columns:repeat(3,1fr);gap:12px}
    .stat{
      background:#fff;border:1px solid var(--line);border-radius:18px;padding:16px;text-align:center
    }
    .stat b{display:block;color:var(--blue);font-size:1.8rem;margin-bottom:6px}
    .stat span{color:var(--muted);font-size:.88rem}
    .section-title{
      display:flex;align-items:center;justify-content:space-between;gap:10px;
      margin:34px 0 16px;
    }
    .section-title h3{margin:0;font-size:1.5rem;color:var(--blue)}
    .section-title .mini{color:var(--muted);font-size:.92rem}
    .teams{display:grid;grid-template-columns:1fr;gap:18px}
    .team-card{
      background:#fff;border:1px solid var(--line);border-radius:26px;box-shadow:var(--shadow);
      overflow:hidden;
    }
    .team-head{
      padding:18px 20px;
      background:linear-gradient(135deg, rgba(30,154,237,.12), rgba(143,197,247,.18));
      border-bottom:1px solid var(--line);
    }
    .team-head h4{margin:0;color:var(--blue);font-size:1.18rem}
    .team-head p{margin:8px 0 0;color:var(--muted);font-size:.93rem}
    .members{
      display:grid;
      grid-template-columns:repeat(3,1fr);
      gap:16px;
      padding:18px;
    }
    .member{
      background:var(--card);
      border:1px solid var(--line);
      border-radius:20px;
      padding:16px;
      display:flex;gap:14px;align-items:flex-start;
      transition:transform .2s ease, box-shadow .2s ease, border-color .2s ease;
    }
    .member:hover{transform:translateY(-2px);box-shadow:0 10px 24px rgba(30,154,237,.12);border-color:#bfe0fb}
    .avatar{
      width:78px;height:78px;border-radius:18px;flex:0 0 auto;
      background:linear-gradient(135deg,#cce7fd,#edf7ff);
      border:1px solid var(--line);
      display:grid;place-items:center;overflow:hidden;position:relative;
    }
    .avatar img{width:100%;height:100%;object-fit:cover;display:none}
    .avatar svg{width:40px;height:40px;opacity:.8}
    .member-body{min-width:0;flex:1}
    .name{font-weight:700;color:#1c6fa8;font-size:.98rem;line-height:1.35}
    .meta{margin-top:8px;display:grid;gap:6px}
    .badge{
      display:inline-block;width:max-content;padding:6px 10px;border-radius:999px;
      font-size:.78rem;background:#eaf5fe;color:var(--blue);border:1px solid #cde7fb
    }
    .uni{font-size:.85rem;color:var(--muted)}
    .actions{display:flex;gap:8px;flex-wrap:wrap;margin-top:10px}
    .btn{
      text-decoration:none;border:none;cursor:pointer;font-family:inherit;
      padding:8px 11px;border-radius:12px;font-size:.82rem;transition:.2s ease;
      background:#fff;border:1px solid var(--line);color:var(--text);
    }
    .btn:hover{background:var(--blue);color:#fff;border-color:var(--blue)}
    .btn.primary{background:var(--blue);border-color:var(--blue);color:#fff}
    .btn.primary:hover{filter:brightness(.95)}
    .admin-banner{
      margin-top:26px;padding:16px 18px;border-radius:18px;
      background:linear-gradient(135deg,#f3faff,#ffffff);
      border:1px dashed #b9dbfa;color:var(--muted);font-size:.92rem
    }
    .admin-banner b{color:var(--blue)}
    .modal{
      position:fixed;inset:0;background:rgba(9,40,64,.38);display:none;
      align-items:center;justify-content:center;padding:18px;z-index:100;
    }
    .modal.show{display:flex}
    .modal-card{
      width:min(760px,100%);max-height:92vh;overflow:auto;
      background:#fff;border-radius:24px;border:1px solid var(--line);box-shadow:0 24px 50px rgba(0,0,0,.16);
      padding:22px;
    }
    .modal-head{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-bottom:14px}
    .modal-head h4{margin:0;color:var(--blue)}
    .close{border:none;background:#eef7ff;color:var(--blue);width:40px;height:40px;border-radius:50%;cursor:pointer;font-size:1.2rem}
    .grid{display:grid;grid-template-columns:1fr 1fr;gap:14px}
    .field{display:grid;gap:6px}
    .field.full{grid-column:1/-1}
    label{font-size:.85rem;color:var(--text);font-weight:600}
    input,select{
      width:100%;padding:12px 14px;border:1px solid var(--line);border-radius:14px;
      font-family:inherit;font-size:.92rem;outline:none
    }
    input:focus,select:focus{border-color:var(--blue);box-shadow:0 0 0 4px rgba(30,154,237,.1)}
    .hint{font-size:.78rem;color:var(--muted)}
    .footer{padding:26px 0 40px;color:var(--muted);text-align:center;font-size:.88rem}
    .empty-link{opacity:.75}
    @media (max-width: 1100px){
      .members{grid-template-columns:repeat(2,1fr)}
      .brand{grid-template-columns:1fr;gap:10px}
      .wordmark{font-size:4.6rem}
      .intro{grid-template-columns:1fr}
    }
    @media (max-width: 720px){
      .members{grid-template-columns:1fr}
      .stats{grid-template-columns:1fr}
      .wordmark{font-size:3.3rem}
      .tagline{font-size:1.1rem}
      .grid{grid-template-columns:1fr}
      .nav-inner{padding:8px 0}
    }
  </style>
</head>
<body>
  <header>
    <div class="container">
      <div class="brand">
        <div class="logo-wrap">
          <svg width="360" height="220" viewBox="0 0 360 220" aria-label="LMIER logo">
            <rect width="360" height="220" fill="transparent"/>
            <g transform="translate(20,8)">
              <circle cx="110" cy="102" r="18" fill="#7cb4f0"/>
              <g fill="#1e9aed">
                <circle cx="110" cy="22" r="18"/>
                <circle cx="194" cy="82" r="18"/>
                <circle cx="120" cy="182" r="18"/>
                <circle cx="36" cy="146" r="18"/>
                <circle cx="26" cy="82" r="18"/>
                <circle cx="195" cy="126" r="18"/>
                <circle cx="190" cy="172" r="16"/>
                <circle cx="76" cy="166" r="15"/>
                <circle cx="60" cy="48" r="17"/>
                <circle cx="80" cy="20" r="18"/>
                <circle cx="188" cy="60" r="15"/>
                <circle cx="52" cy="100" r="14"/>
                <circle cx="128" cy="146" r="14"/>
                <circle cx="148" cy="92" r="12"/>
                <circle cx="88" cy="66" r="12"/>
                <circle cx="74" cy="126" r="11"/>
                <circle cx="162" cy="134" r="10"/>
                <circle cx="150" cy="58" r="11"/>
                <circle cx="98" cy="132" r="8"/>
                <circle cx="136" cy="76" r="9"/>
                <circle cx="170" cy="98" r="10"/>
                <circle cx="98" cy="38" r="8"/>
                <circle cx="112" cy="58" r="8"/>
                <circle cx="58" cy="108" r="8"/>
                <circle cx="126" cy="104" r="5"/>
                <circle cx="156" cy="110" r="5"/>
                <circle cx="112" cy="126" r="5"/>
                <circle cx="86" cy="92" r="4"/>
                <circle cx="140" cy="118" r="4"/>
              </g>
              <g fill="#8fc5f7">
                <circle cx="146" cy="42" r="7"/>
                <circle cx="104" cy="70" r="8"/>
                <circle cx="52" cy="132" r="7"/>
                <circle cx="88" cy="158" r="7"/>
                <circle cx="130" cy="154" r="8"/>
                <circle cx="160" cy="118" r="7"/>
                <circle cx="96" cy="84" r="6"/>
                <circle cx="180" cy="116" r="4"/>
                <circle cx="176" cy="92" r="6"/>
                <circle cx="80" cy="82" r="7"/>
                <circle cx="70" cy="68" r="4"/>
                <circle cx="128" cy="90" r="4"/>
                <circle cx="44" cy="52" r="4"/>
                <circle cx="44" cy="196" r="3"/>
                <circle cx="62" cy="196" r="4"/>
                <circle cx="192" cy="96" r="3"/>
                <circle cx="172" cy="198" r="3"/>
                <circle cx="154" cy="30" r="4"/>
                <circle cx="98" cy="196" r="3"/>
                <circle cx="164" cy="34" r="2.5"/>
                <circle cx="120" cy="24" r="3"/>
                <circle cx="92" cy="52" r="2.5"/>
                <circle cx="110" cy="168" r="3.5"/>
                <circle cx="140" cy="146" r="3.5"/>
                <circle cx="28" cy="114" r="2.5"/>
                <circle cx="180" cy="158" r="3"/>
              </g>
            </g>
          </svg>
        </div>
        <div class="wordmark">LMIER</div>
      </div>
      <div class="tagline">Laboratoire des Matériaux Innovants et<br>Énergies Renouvelables</div>
      <div class="hero-note">Présentation publique de la composition humaine du laboratoire et de ses 5 équipes de recherche.</div>
    </div>
  </header>

  <nav>
    <div class="container nav-inner">
      <div class="nav-title">LMIER</div>
      <div class="nav-links">
        <a href="#equipes">Équipes</a>
        <a href="#administration">Administration</a>
        <button id="adminAccessBtn">Accès modification</button>
      </div>
    </div>
  </nav>

  <main class="container">
    <section class="intro">
      <div class="panel">
        <h2>À propos du laboratoire</h2>
        <p>
          Le LMIER rassemble des enseignants-chercheurs et doctorants autour des matériaux innovants,
          du génie civil, de la durabilité, des composites, des sols reconstitués et des structures.
          Ce site permet de consulter les membres de chaque équipe, leurs grades, leurs universités,
          leurs photos et leurs CV.
        </p>
      </div>
      <div class="panel">
        <div class="stats">
          <div class="stat"><b>5</b><span>Équipes de recherche</span></div>
          <div class="stat"><b>38</b><span>Membres</span></div>
          <div class="stat"><b>1</b><span>Directeur du laboratoire</span></div>
        </div>
      </div>
    </section>

    <section id="equipes">
      <div class="section-title">
        <h3>Composition humaine du laboratoire</h3>
        <div class="mini">Consultation libre • Modification réservée à l’administrateur</div>
      </div>
      <div id="teams" class="teams"></div>
    </section>

    <section id="administration" class="admin-banner">
      <b>Administration :</b> le contenu est visible par tous. Les modifications (photo, CV, informations)
      sont protégées par un mot de passe administrateur créé localement sur cet appareil. Le mot de passe n’est jamais affiché sur la page.
      Pour un envoi automatique par email, il faut connecter ultérieurement un service serveur sécurisé.
    </section>
  </main>

  <div class="footer">
    LMIER — Laboratoire des Matériaux Innovants et Énergies Renouvelables
  </div>

  <div class="modal" id="authModal">
    <div class="modal-card">
      <div class="modal-head">
        <h4>Accès administrateur</h4>
        <button class="close" data-close="authModal">&times;</button>
      </div>
      <div class="grid">
        <div class="field full">
          <label>Mot de passe administrateur</label>
          <input type="password" id="adminPasswordInput" placeholder="Saisir le mot de passe">
          <div class="hint">Si aucun mot de passe n’existe encore sur cet appareil, vous pourrez en créer un.</div>
        </div>
      </div>
      <div class="actions" style="margin-top:14px">
        <button class="btn primary" id="loginBtn">Se connecter</button>
        <button class="btn" id="showSetupBtn">Créer / définir le mot de passe</button>
      </div>

      <div id="setupBox" style="display:none;margin-top:16px;padding-top:16px;border-top:1px solid var(--line)">
        <div class="grid">
          <div class="field full">
            <label>Email administrateur</label>
            <input type="email" id="adminEmail" value="berrabahhamzamadjid@gmail.com" readonly>
            <div class="hint">Référence affichée pour l’administrateur autorisé.</div>
          </div>
          <div class="field">
            <label>Nouveau mot de passe</label>
            <input type="password" id="newPassword" placeholder="Créer un mot de passe">
          </div>
          <div class="field">
            <label>Confirmer le mot de passe</label>
            <input type="password" id="confirmPassword" placeholder="Confirmer le mot de passe">
          </div>
        </div>
        <div class="actions" style="margin-top:14px">
          <button class="btn primary" id="savePasswordBtn">Enregistrer</button>
        </div>
      </div>
    </div>
  </div>

  <div class="modal" id="editModal">
    <div class="modal-card">
      <div class="modal-head">
        <h4>Modifier le membre</h4>
        <button class="close" data-close="editModal">&times;</button>
      </div>
      <div class="grid">
        <div class="field">
          <label>Nom et prénom</label>
          <input id="editName" type="text">
        </div>
        <div class="field">
          <label>Grade académique</label>
          <select id="editGrade">
            <option>Pr</option>
            <option>MCA</option>
            <option>MCB</option>
            <option>MA (MCB)</option>
            <option>Pr (associé)</option>
            <option>Doctorant</option>
            <option>Doctorante</option>
            <option>Doctorante (science)</option>
            <option>Doctorant (science)</option>
          </select>
        </div>
        <div class="field full">
          <label>Université de rattachement</label>
          <input id="editUni" type="text">
        </div>
        <div class="field">
          <label>Photo</label>
          <input id="editPhoto" type="file" accept="image/*">
          <div class="hint">Importer une photo du membre.</div>
        </div>
        <div class="field">
          <label>CV (PDF)</label>
          <input id="editCv" type="file" accept="application/pdf">
          <div class="hint">Importer le CV en format PDF.</div>
        </div>
      </div>
      <div class="actions" style="margin-top:16px">
        <button class="btn primary" id="saveMemberBtn">Enregistrer les modifications</button>
      </div>
    </div>
  </div>

  <script>
    const adminEmailAllowed = "berrabahhamzamadjid@gmail.com";

    const teamsData = [
      {
        id: 1,
        title: "Equipe N°1 : Valorisation des Matériaux en Génie civil",
        desc: "Chef d'équipe et directeur du laboratoire : SALHI Mohamed",
        members: [
          { name:"SALHI Mohamed", grade:"Pr", university:"U Relizane", role:"chef d'équipe et directeur du laboratoire" },
          { name:"SAFER Omar", grade:"MCA", university:"U Relizane" },
          { name:"CHAIB Ouaddah", grade:"MCA", university:"U Relizane" },
          { name:"BOUBEKEUR Toufik", grade:"Pr", university:"U Tissemsilt" },
          { name:"BENYAHIA Amar", grade:"MCA", university:"U Blida 2" },
          { name:"ALI KOUADRI Fadhila", grade:"Doctorante", university:"U Relizane" },
          { name:"AMEUR MESSAFAH Ahmed", grade:"Doctorant", university:"U Relizane" },
          { name:"EZZIANE Sara Malak", grade:"Doctorante", university:"U Relizane" }
        ]
      },
      {
        id: 2,
        title: "Equipe N°2 : Durabilité des matériaux de construction",
        desc: "Chef d'équipe : LAOUFI Imene",
        members: [
          { name:"LAOUFI Imene", grade:"MCA", university:"U Relizane", role:"chef d'équipe" },
          { name:"MENAD Kamel", grade:"MCA", university:"U Relizane" },
          { name:"TABTI Afaf", grade:"MCA", university:"U Relizane" },
          { name:"BENSLAMA Khadidja", grade:"MCB", university:"U Relizane" },
          { name:"HAMMADACHE Miloud", grade:"MCA", university:"U Relizane" },
          { name:"BENABEDALLAH Mohamed", grade:"Doctorant", university:"U Relizane" },
          { name:"GUENDEZ Fatma Zohra", grade:"Doctorante", university:"U Relizane" },
          { name:"GHEFIR Meriem", grade:"Doctorante (science)", university:"U Relizane" }
        ]
      },
      {
        id: 3,
        title: "Equipe N°3 : Matériaux composite",
        desc: "Chef d'équipe : HADJ Mostefa ADDA",
        members: [
          { name:"HADJ Mostefa ADDA", grade:"Pr", university:"U Relizane", role:"Chef d'équipe" },
          { name:"ABDELHAK Zahra", grade:"MCA", university:"U Relizane" },
          { name:"BALEGH Benamer", grade:"Pr", university:"U Adrar" },
          { name:"TOUNSI Abdeldjebar", grade:"MA (MCB)", university:"U Relizane" },
          { name:"MERDACI Slimane", grade:"Pr", university:"U Sidi Belabes" },
          { name:"ZEROUKI Otmane", grade:"MCB", university:"U Relizane" },
          { name:"TOUNSI Abdelouahed", grade:"Pr (associé)", university:"U Sidi Belabes" },
          { name:"HOUCINE Said", grade:"Doctorant (science)", university:"U Relizane" },
          { name:"BACHIR BOUIADJRA Ahmed", grade:"Doctorant (science)", university:"U Relizane" }
        ]
      },
      {
        id: 4,
        title: "Equipe N°4 : Comportement mécanique des sols reconstitués en laboratoire vis à vis la résistance au cisaillement",
        desc: "Chef d'équipe : AIT MOHAMED AMER Adem",
        members: [
          { name:"AIT MOHAMED AMER Adem", grade:"MCA", university:"U Relizane", role:"Chef d'équipe" },
          { name:"CHEMMAM Mohammed", grade:"MCA", university:"U Relizane" },
          { name:"ZEMRI Amine", grade:"MCA", university:"U Relizane" },
          { name:"NEHARI Abderrahim", grade:"Doctorant", university:"U Relizane" },
          { name:"KASSOUL Mohamed ABDENOUR", grade:"Doctorant", university:"U Relizane" },
          { name:"MERZOUG Fatiha", grade:"Doctorante (science)", university:"U Relizane" }
        ]
      },
      {
        id: 5,
        title: "Equipe N°5 : Structure et matériaux",
        desc: "Chef d'équipe : BERRABAH Hamza Madjid",
        members: [
          { name:"BERRABAH Hamza Madjid", grade:"Pr", university:"U Relizane", role:"Chef d'équipe" },
          { name:"LATROUCHE Noureddine", grade:"MCA", university:"U Relizane" },
          { name:"ZINE Abdallah", grade:"MCA", university:"U Relizane" },
          { name:"SEKKAL Mohamed", grade:"MCA", university:"U Relizane" },
          { name:"SAFA Abdelkader", grade:"MCB", university:"U Relizane" },
          { name:"AMEUR Bachir", grade:"Doctorant", university:"U Relizane" },
          { name:"MECHLOUF Halima", grade:"Doctorante", university:"U Relizane" }
        ]
      }
    ];

    const STORAGE_KEY = "lmier_members_data_v1";
    const PASS_KEY = "lmier_admin_password_v1";
    let isAdmin = false;
    let editRef = {teamIndex:null, memberIndex:null};

    function loadData(){
      const saved = localStorage.getItem(STORAGE_KEY);
      if(saved){
        try { return JSON.parse(saved); } catch(e){}
      }
      return teamsData;
    }
    let data = loadData();

    function saveData(){
      localStorage.setItem(STORAGE_KEY, JSON.stringify(data));
      renderTeams();
    }

    function getInitials(name){
      return name.split(" ").filter(Boolean).slice(0,2).map(n=>n[0]).join("").toUpperCase();
    }

    function personIcon(){
      return `
      <svg viewBox="0 0 24 24" fill="none" stroke="#4da7ef" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
        <path d="M20 21a8 8 0 0 0-16 0"></path>
        <circle cx="12" cy="7" r="4"></circle>
      </svg>`;
    }

    function renderTeams(){
      const root = document.getElementById("teams");
      root.innerHTML = data.map((team, ti)=>`
        <article class="team-card">
          <div class="team-head">
            <h4>${team.title}</h4>
            <p>${team.desc}</p>
          </div>
          <div class="members">
            ${team.members.map((m, mi)=>`
              <div class="member">
                <div class="avatar">
                  ${m.photo ? `<img src="${m.photo}" alt="${m.name}" style="display:block">` : personIcon()}
                </div>
                <div class="member-body">
                  <div class="name">${m.name}</div>
                  <div class="meta">
                    <span class="badge">${m.grade}${m.role ? " • " + m.role : ""}</span>
                    <div class="uni">${m.university}</div>
                  </div>
                  <div class="actions">
                    ${m.cv ? `<a class="btn primary" href="${m.cv}" download="${m.name.replace(/\s+/g,'_')}_CV.pdf">Télécharger CV</a>` : `<span class="btn empty-link" title="Aucun CV importé">CV indisponible</span>`}
                    ${isAdmin ? `<button class="btn" onclick="openEdit(${ti},${mi})">Modifier</button>` : ``}
                  </div>
                </div>
              </div>
            `).join("")}
          </div>
        </article>
      `).join("");
    }

    function openModal(id){ document.getElementById(id).classList.add("show"); }
    function closeModal(id){ document.getElementById(id).classList.remove("show"); }

    document.querySelectorAll("[data-close]").forEach(btn=>{
      btn.addEventListener("click", ()=>closeModal(btn.dataset.close));
    });
    document.querySelectorAll(".modal").forEach(m=>{
      m.addEventListener("click", e=>{ if(e.target===m) m.classList.remove("show"); });
    });

    document.getElementById("adminAccessBtn").addEventListener("click", ()=>openModal("authModal"));
    document.getElementById("showSetupBtn").addEventListener("click", ()=>{
      document.getElementById("setupBox").style.display = "block";
    });

    document.getElementById("savePasswordBtn").addEventListener("click", ()=>{
      const p1 = document.getElementById("newPassword").value.trim();
      const p2 = document.getElementById("confirmPassword").value.trim();
      if(!p1 || p1.length < 6) return alert("Le mot de passe doit contenir au moins 6 caractères.");
      if(p1 !== p2) return alert("Les mots de passe ne correspondent pas.");
      localStorage.setItem(PASS_KEY, p1);
      alert("Mot de passe administrateur enregistré localement avec succès.");
      document.getElementById("newPassword").value = "";
      document.getElementById("confirmPassword").value = "";
      document.getElementById("setupBox").style.display = "none";
    });

    document.getElementById("loginBtn").addEventListener("click", ()=>{
      const entered = document.getElementById("adminPasswordInput").value;
      const saved = localStorage.getItem(PASS_KEY);
      if(!saved){
        alert("Aucun mot de passe n’est encore défini sur cet appareil. Veuillez d’abord en créer un.");
        return;
      }
      if(entered === saved){
        isAdmin = true;
        closeModal("authModal");
        renderTeams();
        alert("Connexion administrateur réussie.");
      } else {
        alert("Mot de passe incorrect.");
      }
    });

    window.openEdit = function(teamIndex, memberIndex){
      if(!isAdmin) return;
      editRef = {teamIndex, memberIndex};
      const m = data[teamIndex].members[memberIndex];
      document.getElementById("editName").value = m.name || "";
      document.getElementById("editGrade").value = m.grade || "MCA";
      document.getElementById("editUni").value = m.university || "";
      document.getElementById("editPhoto").value = "";
      document.getElementById("editCv").value = "";
      openModal("editModal");
    }

    document.getElementById("saveMemberBtn").addEventListener("click", async ()=>{
      const {teamIndex, memberIndex} = editRef;
      const member = data[teamIndex].members[memberIndex];
      member.name = document.getElementById("editName").value.trim();
      member.grade = document.getElementById("editGrade").value;
      member.university = document.getElementById("editUni").value.trim();

      const photoFile = document.getElementById("editPhoto").files[0];
      const cvFile = document.getElementById("editCv").files[0];

      if(photoFile){
        member.photo = await fileToDataURL(photoFile);
      }
      if(cvFile){
        member.cv = await fileToDataURL(cvFile);
      }
      saveData();
      closeModal("editModal");
    });

    function fileToDataURL(file){
      return new Promise((resolve,reject)=>{
        const reader = new FileReader();
        reader.onload = ()=>resolve(reader.result);
        reader.onerror = reject;
        reader.readAsDataURL(file);
      });
    }

    renderTeams();
  </script>
</body>
</html>
