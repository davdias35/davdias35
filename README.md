<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Curso de Sedação Consciente com Óxido Nitroso</title>
    <style>
        :root {
            --primary-color: #2c3e50;
            --secondary-color: #3498db;
            --admin-color: #8e44ad;
            --success-color: #27ae60;
            --background-color: #f8f9fa;
            --card-color: #ffffff;
            --text-color: #333333;
            --gold-color: #f1c40f;
            --alert-color: #e67e22;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--background-color);
            color: var(--text-color);
            margin: 0;
            padding: 0;
            user-select: none;
            -webkit-user-select: none;
        }

        header {
            background-color: var(--primary-color);
            color: white;
            padding: 20px;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            position: relative;
        }

        .btn-logout {
            position: absolute;
            top: 20px;
            right: 20px;
            background-color: #e74c3c;
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 4px;
            cursor: pointer;
            width: auto;
        }

        .btn-logout:hover {
            background-color: #c0392b;
        }

        .container {
            max-width: 1100px;
            margin: 30px auto;
            padding: 0 20px;
        }

        /* Barra de Progresso */
        .progress-container {
            background: var(--card-color);
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
            margin-bottom: 25px;
        }

        .progress-bar-bg {
            background: #e0e0e0;
            border-radius: 10px;
            height: 20px;
            width: 100%;
            overflow: hidden;
            margin-top: 10px;
        }

        .progress-bar-fill {
            background: linear-gradient(90deg, var(--secondary-color), var(--success-color));
            height: 100%;
            width: 0%;
            transition: width 0.5s ease;
        }

        .progress-text {
            display: flex;
            justify-content: space-between;
            font-weight: bold;
            font-size: 16px;
        }

        /* Container do Certificado */
        .certificate-box {
            background: #fff;
            border: 2px dashed #bdc3c7;
            padding: 25px;
            border-radius: 8px;
            text-align: center;
            margin-top: 40px;
            margin-bottom: 40px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
        }

        .certificate-box.unlocked {
            border: 2px solid var(--gold-color);
            background: #fffdf3;
        }

        .btn-certificate {
            background-color: #95a5a6;
            color: white;
            font-size: 18px;
            font-weight: bold;
            padding: 15px 30px;
            border: none;
            border-radius: 6px;
            cursor: not-allowed;
            display: inline-block;
            margin-top: 15px;
            width: auto;
            transition: all 0.3s;
        }

        .btn-certificate.active {
            background-color: var(--gold-color);
            color: #2c3e50;
            cursor: pointer;
            box-shadow: 0 4px 10px rgba(241, 196, 15, 0.4);
        }

        .btn-certificate.active:hover {
            background-color: #f39c12;
            transform: scale(1.02);
        }

        /* Telas de Login */
        .auth-card {
            background-color: var(--card-color);
            padding: 40px;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            text-align: center;
            max-width: 400px;
            margin: 80px auto;
        }

        input[type="text"], input[type="password"], select {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
            font-size: 16px;
        }

        button {
            background-color: var(--secondary-color);
            color: white;
            border: none;
            padding: 12px 24px;
            font-size: 16px;
            border-radius: 4px;
            cursor: pointer;
            width: 100%;
            transition: background 0.3s;
            margin-top: 10px;
        }

        button:hover {
            background-color: #2980b9;
        }

        .error-message {
            color: #e74c3c;
            margin-top: 10px;
            display: none;
            font-weight: bold;
        }

        /* Áreas de Conteúdo */
        #course-area, #admin-area {
            display: none;
        }

        .admin-header {
            background-color: var(--admin-color) !important;
        }
        
        .admin-box {
            background: white;
            padding: 25px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
            margin-bottom: 30px;
        }

        .admin-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        .full-width {
            grid-column: 1 / -1;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 15px;
        }

        table, th, td {
            border: 1px solid #ddd;
        }

        th, td {
            padding: 12px;
            text-align: left;
        }

        th {
            background-color: #f2f2f2;
        }

        .btn-delete {
            background-color: #e74c3c;
            padding: 6px 10px;
            font-size: 14px;
            width: auto;
            margin: 0;
        }

        .btn-action-success {
            background-color: var(--success-color);
            padding: 6px 10px;
            font-size: 14px;
            width: auto;
            margin: 0;
        }

        .module-title {
            color: var(--primary-color);
            border-bottom: 2px solid var(--secondary-color);
            padding-bottom: 8px;
            margin-top: 20px;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .card {
            background: var(--card-color);
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
            padding: 20px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .video-container {
            width: 100%;
            background-color: #000;
            border-radius: 6px;
            margin-bottom: 15px;
            overflow: hidden;
            aspect-ratio: 16 / 9;
            position: relative;
        }

        .video-container iframe, .video-container video {
            width: 100%;
            height: 100%;
            display: block;
            border: none;
        }

        .video-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 12%;
            z-index: 10;
            background: transparent;
        }

        .no-video {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            color: #7f8c8d;
            text-align: center;
            font-size: 14px;
            width: 90%;
        }

        .btn-download {
            background-color: var(--success-color);
            text-align: center;
            color: white;
            text-decoration: none;
            padding: 10px;
            border-radius: 4px;
            display: block;
            margin-top: 10px;
            transition: background 0.3s;
        }

        .btn-download:hover {
            background-color: #219653;
        }
        
        .disabled-link {
            background-color: #95a5a6 !important;
            cursor: not-allowed;
            pointer-events: none;
        }

        .btn-status-video {
            background-color: #7f8c8d;
            margin-top: 10px;
            font-size: 14px;
            padding: 8px;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            width: 100%;
        }
        .btn-status-video.watched {
            background-color: var(--success-color);
        }
    </style>
</head>
<body oncontextmenu="return false;">

    <div id="auth-screen" class="auth-card">
        <h2>Área de Acesso</h2>
        <p>Insira suas credenciais para acessar o painel.</p>
        <input type="text" id="login-user" placeholder="Usuário">
        <input type="password" id="login-pass" placeholder="Senha">
        <button id="btn-login">Entrar</button>
        <p class="error-message" id="error-msg">Usuário ou senha incorretos.</p>
    </div>

    <div id="admin-area">
        <header class="admin-header">
            <h1>Painel do Administrador</h1>
            <p>Gerenciamento de Alunos e Conteúdo das Aulas</p>
            <button class="btn-logout" id="btn-logout-admin">Sair</button>
        </header>
        
        <div class="container">
            <div class="admin-grid">

                <div class="admin-box full-width" style="border: 2px solid var(--alert-color);">
                    <h3 style="color: var(--alert-color); margin-top: 0;">⚠️ Solicitações de Certificado Pendentes</h3>
                    <p style="font-size: 14px; color: #555; margin-top: -10px;">Os alunos listados abaixo concluíram 100% do curso e solicitaram a emissão do certificado.</p>
                    <div style="overflow-x:auto;">
                        <table>
                            <thead>
                                <tr>
                                    <th>Nome do Aluno</th>
                                    <th>Usuário</th>
                                    <th>Data da Solicitação</th>
                                    <th>Ações</th>
                                </tr>
                            </thead>
                            <tbody id="cert-requests-table-body">
                            </tbody>
                        </table>
                    </div>
                </div>
                
                <div class="admin-box full-width">
                    <h3>Gerenciar Conteúdo das Aulas (Limite: 5 Aulas)</h3>
                    <p style="font-size: 14px; color: #666; margin-top: -10px;">Selecione qual das 5 aulas deseja atualizar, insira os dados e salve.</p>
                    
                    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px;">
                        <div>
                            <label style="font-weight: bold;">Selecione a Aula:</label>
                            <select id="upload-lesson-select">
                                <option value="1">Aula 1</option>
                                <option value="2">Aula 2</option>
                                <option value="3">Aula 3</option>
                                <option value="4">Aula 4</option>
                                <option value="5">Aula 5</option>
                            </select>
                        </div>
                        <div>
                            <label style="font-weight: bold;">Título da Aula:</label>
                            <input type="text" id="upload-title" placeholder="Ex: Histórico e Aspectos Legais">
                        </div>
                    </div>

                    <div style="margin-top: 10px;">
                        <label style="font-weight: bold;">Link do Arquivo de Vídeo (Google Drive ou .mp4 direto):</label>
                        <input type="text" id="upload-video" placeholder="Ex: https://drive.google.com/file/d/.../view?usp=sharing">
                    </div>

                    <div style="margin-top: 10px;">
                        <label style="font-weight: bold;">Link do Material de Apoio (PDF / Drive):</label>
                        <input type="text" id="upload-pdf" placeholder="Ex: https://drive.google.com/file/d/... (Deixe em branco se não houver)">
                    </div>

                    <button id="btn-save-lesson" style="background-color: var(--success-color); margin-top: 15px; width: auto; padding: 12px 30px;">Atualizar Conteúdo desta Aula</button>
                </div>

                <div class="admin-box">
                    <h3>Cadastrar Novo Aluno</h3>
                    <input type="text" id="reg-name" placeholder="Nome Completo do Aluno">
                    <input type="text" id="reg-user" placeholder="Definir Usuário (Ex: davi.silva)">
                    <input type="password" id="reg-pass" placeholder="Definir Senha">
                    <button id="btn-register-student" style="background-color: var(--admin-color);">Cadastrar Aluno</button>
                </div>

                <div class="admin-box">
                    <h3>Alunos Cadastrados</h3>
                    <div style="overflow-x:auto;">
                        <table>
                            <thead>
                                <tr>
                                    <th>Nome</th>
                                    <th>Usuário</th>
                                    <th>Ações</th>
                                </tr>
                            </thead>
                            <tbody id="students-table-body">
                            </tbody>
                        </table>
                    </div>
                </div>

            </div>
        </div>
    </div>

    <div id="course-area">
        <header>
            <h1>Imersão em Sedação Consciente</h1>
            <p>Conceitos, Legislação e Prática Clínica com Óxido Nitroso</p>
            <button class="btn-logout" id="btn-logout-course">Sair</button>
        </header>

        <div class="container">
            <div class="progress-container">
                <div class="progress-text">
                    <span>Seu Progresso no Curso</span>
                    <span id="progress-percentage">0%</span>
                </div>
                <div class="progress-bar-bg">
                    <div id="progress-bar" class="progress-bar-fill"></div>
                </div>
            </div>

            <h2 class="module-title">Cronograma de Aulas Disponíveis</h2>
            <div class="grid" id="course-lessons-grid">
            </div>

            <div id="certificate-section" class="certificate-box">
                <h3 id="cert-title">📜 Certificado de Conclusão</h3>
                <p id="cert-desc">Você precisa concluir todas as aulas (assistir aos vídeos e abrir os materiais de apoio) para liberar seu certificado.</p>
                <button id="btn-cert" class="btn-certificate">Solicitar Meu Certificado</button>
            </div>
        </div>
    </div>

    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/10.8.1/firebase-app.js";
        import { 
            getFirestore, doc, setDoc, getDoc, getDocs, deleteDoc, collection 
        } from "https://www.gstatic.com/firebasejs/10.8.1/firebase-firestore.js";

        // Configuração capturada do seu projeto do Firebase
        const firebaseConfig = {
            apiKey: "AIzaSyA2bpuVRD_wZcMNJ_c3C9q7NXzdpG80mj4",
            authDomain: "curso-oxido-nitroso.firebaseapp.com",
            projectId: "curso-oxido-nitroso",
            storageBucket: "curso-oxido-nitroso.firebasestorage.app",
            messagingSenderId: "267103826277",
            appId: "1:267103826277:web:c0f83209d4d38bb2e1b18c",
            measurementId: "G-0HNM6P3HNE"
        };

        const app = initializeApp(firebaseConfig);
        const db = getFirestore(app);

        const ADMIN_USER = "drarobertaadmin";
        const ADMIN_PASS = "sedacao2026";

        function setupListeners() {
            document.getElementById('btn-login').onclick = handleLogin;
            document.getElementById('btn-logout-admin').onclick = logout;
            document.getElementById('btn-logout-course').onclick = logout;
            document.getElementById('btn-register-student').onclick = registerStudent;
            document.getElementById('btn-save-lesson').onclick = saveLessonContent;
            document.getElementById('upload-lesson-select').onchange = loadLessonToForm;
            document.getElementById('btn-cert').onclick = requestCertificate;
        }

        async function checkAndInitializeLessons() {
            const defaultLessons = [
                { id: 1, title: "Aula 1: Histórico e Aspectos Legais", video: "", pdf: "" },
                { id: 2, title: "Aula 2: Anatomia dos Equipamentos e Cilindros", video: "", pdf: "" },
                { id: 3, title: "Aula 3: Titulação e Protocolo Clínico", video: "", pdf: "" },
                { id: 4, title: "Aula 4: Farmacologia e Seleção de Pacientes", video: "", pdf: "" },
                { id: 5, title: "Aula 5: Atendimento de Emergência e Suporte", video: "", pdf: "" }
            ];

            for (const lesson of defaultLessons) {
                const lessonRef = doc(db, "lessons", lesson.id.toString());
                const snap = await getDoc(lessonRef);
                if (!snap.exists()) {
                    await setDoc(lessonRef, lesson);
                }
            }
        }

        async function handleLogin() {
            const user = document.getElementById('login-user').value.trim();
            const pass = document.getElementById('login-pass').value.trim();
            const errorMsg = document.getElementById('error-msg');

            if (user === ADMIN_USER && pass === ADMIN_PASS) {
                showScreen('admin-area');
                sessionStorage.setItem('loggedUser', 'admin_session');
                await updateStudentsTable();
                await updateCertRequestsTable();
                await loadLessonToForm();
                clearLoginInputs();
                return;
            }

            try {
                const studentRef = doc(db, "students", user.toLowerCase());
                const studentSnap = await getDoc(studentRef);

                if (studentSnap.exists() && studentSnap.data().password === pass) {
                    showScreen('course-area');
                    sessionStorage.setItem('loggedUser', user.toLowerCase());
                    await renderCourseLessons();
                    clearLoginInputs();
                } else {
                    errorMsg.style.display = 'block';
                }
            } catch (e) {
                console.error("Erro no login: ", e);
                errorMsg.style.display = 'block';
            }
        }

        async function loadLessonToForm() {
            const selectedId = document.getElementById('upload-lesson-select').value;
            try {
                const lessonRef = doc(db, "lessons", selectedId);
                const lessonSnap = await getDoc(lessonRef);

                if (lessonSnap.exists()) {
                    const lesson = lessonSnap.data();
                    document.getElementById('upload-title').value = lesson.title || '';
                    document.getElementById('upload-video').value = lesson.video || '';
                    document.getElementById('upload-pdf').value = lesson.pdf || '';
                }
            } catch (e) {
                console.error("Erro ao buscar aula: ", e);
            }
        }

        async function saveLessonContent() {
            const selectedId = document.getElementById('upload-lesson-select').value;
            const title = document.getElementById('upload-title').value.trim();
            const videoInput = document.getElementById('upload-video').value.trim();
            const pdf = document.getElementById('upload-pdf').value.trim();

            if (!title) {
                alert("Insira um título para a aula.");
                return;
            }

            try {
                const lessonRef = doc(db, "lessons", selectedId);
                await setDoc(lessonRef, {
                    id: parseInt(selectedId),
                    title: title,
                    video: videoInput,
                    pdf: pdf
                });
                alert(`Conteúdo da Aula ${selectedId} salvo no Firebase!`);
            } catch (e) {
                alert("Erro ao salvar no banco.");
                console.error(e);
            }
        }

        async function registerStudent() {
            const name = document.getElementById('reg-name').value.trim();
            const user = document.getElementById('reg-user').value.trim().toLowerCase();
            const pass = document.getElementById('reg-pass').value.trim();

            if (!name || !user || !pass) {
                alert("Por favor, preencha todos os campos do cadastro.");
                return;
            }

            if (user === ADMIN_USER) {
                alert("Este nome de usuário é restrito.");
                return;
            }

            try {
                const studentRef = doc(db, "students", user);
                const checkSnap = await getDoc(studentRef);

                if (checkSnap.exists()) {
                    alert("Este nome de usuário já está cadastrado.");
                    return;
                }

                await setDoc(studentRef, { 
                    name: name, 
                    username: user, 
                    password: pass
                });

                document.getElementById('reg-name').value = '';
                document.getElementById('reg-user').value = '';
                document.getElementById('reg-pass').value = '';
                
                alert(`Aluno "${name}" cadastrado com sucesso!`);
                await updateStudentsTable();
            } catch (e) {
                alert("Ocorreu um erro técnico ao cadastrar novo aluno no Firebase. Certifique-se de liberar as regras de gravação (Rules) no painel do Cloud Firestore.");
                console.error(e);
            }
        }

        async function updateStudentsTable() {
            const tbody = document.getElementById('students-table-body');
            tbody.innerHTML = '';

            try {
                const querySnapshot = await getDocs(collection(db, "students"));
                if (querySnapshot.empty) {
                    tbody.innerHTML = `<tr><td colspan="3" style="text-align:center; color:#7f8c8d;">Nenhum aluno cadastrado.</td></tr>`;
                    return;
                }

                querySnapshot.forEach((docSnap) => {
                    const student = docSnap.data();
                    const row = document.createElement('tr');
                    row.innerHTML = `
                        <td>${student.name}</td>
                        <td><code>${student.username}</code></td>
                        <td><button class="btn-delete" data-user="${student.username}">Excluir</button></td>
                    `;
                    tbody.appendChild(row);
                });

                document.querySelectorAll('.btn-delete').forEach(btn => {
                    btn.onclick = async (e) => {
                        const userToDelete = e.target.getAttribute('data-user');
                        if (confirm(`Remover o acesso do aluno ${userToDelete}?`)) {
                            await deleteDoc(doc(db, "students", userToDelete));
                            await updateStudentsTable();
                        }
                    };
                });
            } catch (e) {
                console.error(e);
            }
        }

        async function updateCertRequestsTable() {
            const tbody = document.getElementById('cert-requests-table-body');
            tbody.innerHTML = '';

            try {
                const querySnapshot = await getDocs(collection(db, "certRequests"));
                if (querySnapshot.empty) {
                    tbody.innerHTML = `<tr><td colspan="4" style="text-align:center; color:#7f8c8d;">Nenhuma solicitação pendente.</td></tr>`;
                    return;
                }

                querySnapshot.forEach((docSnap) => {
                    const req = docSnap.data();
                    const row = document.createElement('tr');
                    row.innerHTML = `
                        <td><strong>${req.name}</strong></td>
                        <td><code>${req.username}</code></td>
                        <td>${req.date}</td>
                        <td><button class="btn-action-success" data-id="${docSnap.id}">Marcar como Emitido</button></td>
                    `;
                    tbody.appendChild(row);
                });

                document.querySelectorAll('.btn-action-success').forEach(btn => {
                    btn.onclick = async (e) => {
                        const idToArchive = e.target.getAttribute('data-id');
                        await deleteDoc(doc(db, "certRequests", idToArchive));
                        await updateCertRequestsTable();
                        alert("Solicitação concluída.");
                    };
                });
            } catch (e) {
                console.error(e);
            }
        }

        async function toggleVideoWatched(lessonId) {
            const user = sessionStorage.getItem('loggedUser');
            const progressRef = doc(db, "progress", user);
            
            try {
                const snap = await getDoc(progressRef);
                let progress = snap.exists() ? snap.data() : { videos: [], pdfs: [] };
                
                if (!progress.videos) progress.videos = [];
                if (!progress.pdfs) progress.pdfs = [];

                const index = progress.videos.indexOf(lessonId);
                if (index === -1) {
                    progress.videos.push(lessonId);
                } else {
                    progress.videos.splice(index, 1);
                }
                
                await setDoc(progressRef, progress);
                await renderCourseLessons();
            } catch (e) {
                console.error(e);
            }
        }

        async function markPdfOpened(lessonId) {
            const user = sessionStorage.getItem('loggedUser');
            const progressRef = doc(db, "progress", user);
            
            try {
                const snap = await getDoc(progressRef);
                let progress = snap.exists() ? snap.data() : { videos: [], pdfs: [] };

                if (!progress.videos) progress.videos = [];
                if (!progress.pdfs) progress.pdfs = [];
                
                if (!progress.pdfs.includes(lessonId)) {
                    progress.pdfs.push(lessonId);
                    await setDoc(progressRef, progress);
                    await calculateProgress();
                }
            } catch (e) {
                console.error(e);
            }
        }

        async function calculateProgress() {
            try {
                const user = sessionStorage.getItem('loggedUser');
                
                const lessonsSnap = await getDocs(collection(db, "lessons"));
                const progressSnap = await getDoc(doc(db, "progress", user));
                
                const progress = progressSnap.exists() ? progressSnap.data() : { videos: [], pdfs: [] };
                const videosWatched = progress.videos || [];
                const pdfsOpened = progress.pdfs || [];

                let totalTasks = 0;
                let completedTasks = 0;

                lessonsSnap.forEach(docSnap => {
                    const lesson = docSnap.data();
                    if (lesson.video) {
                        totalTasks++;
                        if (videosWatched.includes(lesson.id)) completedTasks++;
                    }
                    if (lesson.pdf) {
                        totalTasks++;
                        if (pdfsOpened.includes(lesson.id)) completedTasks++;
                    }
                });

                const percent = totalTasks > 0 ? Math.round((completedTasks / totalTasks) * 100) : 0;
                
                document.getElementById('progress-bar').style.width = `${percent}%`;
                document.getElementById('progress-percentage').innerText = `${percent}%`;

                const certBox = document.getElementById('certificate-section');
                const certBtn = document.getElementById('btn-cert');
                const certDesc = document.getElementById('cert-desc');

                if (percent === 100 && totalTasks > 0) {
                    certBox.classList.add('unlocked');
                    certBtn.classList.add('active');
                    certBtn.style.cursor = 'pointer';
                    certDesc.innerHTML = "<strong>Parabéns!</strong> Você concluiu 100% do conteúdo. Clique abaixo para emitir seu documento.";
                } else {
                    certBox.classList.remove('unlocked');
                    certBtn.classList.remove('active');
                    certBtn.style.cursor = 'not-allowed';
                    certDesc.innerText = "Você precisa concluir todas as aulas (assistir aos vídeos e abrir os materiais de apoio) para liberar seu certificado.";
                }
            } catch (e) {
                console.error(e);
            }
        }

        async function requestCertificate() {
            const certBtn = document.getElementById('btn-cert');
            if (!certBtn.classList.contains('active')) {
                alert("Acesso Bloqueado: Conclua todo o conteúdo antes de solicitar.");
                return;
            }

            const currentUsername = sessionStorage.getItem('loggedUser');
            
            try {
                const studentSnap = await getDoc(doc(db, "students", currentUsername));
                const studentName = studentSnap.exists() ? studentSnap.data().name : "Aluno";

                const requestRef = doc(db, "certRequests", currentUsername);
                const reqSnap = await getDoc(requestRef);
                
                if (reqSnap.exists()) {
                    alert("Você já enviou uma solicitação! A administração já está trabalhando na emissão.");
                    return;
                }

                const now = new Date();
                const dateStr = now.toLocaleDateString('pt-BR') + ' às ' + now.toLocaleTimeString('pt-BR', {hour: '2-digit', minute:'2-digit'});

                await setDoc(requestRef, {
                    name: studentName,
                    username: currentUsername,
                    date: dateStr
                });

                alert(`Parabéns, ${studentName}!\n\nSua solicitação foi enviada para o painel da coordenação.`);
            } catch (e) {
                console.error(e);
            }
        }

        async function renderCourseLessons() {
            try {
                const user = sessionStorage.getItem('loggedUser');
                const querySnapshot = await getDocs(collection(db, "lessons"));
                const progressSnap = await getDoc(doc(db, "progress", user));
                
                const progress = progressSnap.exists() ? progressSnap.data() : { videos: [], pdfs: [] };
                const videosWatched = progress.videos || [];
                
                const lessons = [];
                querySnapshot.forEach(d => lessons.push(d.data()));
                lessons.sort((a, b) => a.id - b.id);

                const grid = document.getElementById('course-lessons-grid');
                grid.innerHTML = '';

                lessons.forEach(lesson => {
                    const card = document.createElement('div');
                    card.className = 'card';

                    let videoHTML = '';
                    let statusVideoBtn = '';
                    
                    if (lesson.video) {
                        let finalVideoUrl = lesson.video;
                        
                        if (lesson.video.includes('drive.google.com')) {
                            const matches = lesson.video.match(/\/d\/([^/]+)/);
                            if (matches && matches[1]) {
                                finalVideoUrl = `https://drive.google.com/file/d/${matches[1]}/preview`;
                            }
                        }

                        if (finalVideoUrl.includes('drive.google.com')) {
                            videoHTML = `
                                <div class="video-container">
                                    <div class="video-overlay"></div>
                                    <iframe src="${finalVideoUrl}" allow="autoplay"></iframe>
                                </div>`;
                        } else {
                            videoHTML = `
                                <div class="video-container">
                                    <video controls controlsList="nodownload" oncontextmenu="return false;" preload="metadata">
                                        <source src="${finalVideoUrl}" type="video/mp4">
                                    </video>
                                </div>`;
                        }

                        const isWatched = videosWatched.includes(lesson.id);
                        
                        statusVideoBtn = `
                            <button class="btn-status-video ${isWatched ? 'watched' : ''}" data-lesson-id="${lesson.id}">
                                ${isWatched ? '✓ Aula Assistida' : 'Marcar Aula como Assistida'}
                            </button>
                        `;
                    } else {
                        videoHTML = `
                        <div class="video-container">
                            <div class="no-video">O vídeo desta aula será disponibilizado em breve.</div>
                        </div>`;
                    }

                    let pdfHTML = `<a href="${lesson.pdf}" target="_blank" data-pdf-id="${lesson.id}" class="btn-download btn-pdf-link">Baixar Material de Apoio</a>`;
                    if (!lesson.pdf) {
                        pdfHTML = `<a href="#" class="btn-download disabled-link">Material Indisponível</a>`;
                    }

                    card.innerHTML = `
                        <h3>${lesson.title}</h3>
                        ${videoHTML}
                        ${statusVideoBtn}
                        <p style="margin-top: 15px; font-size:14px; color:#555;">Assista à aula e abra o material de apoio para computar seu progresso.</p>
                        ${pdfHTML}
                    `;
                    grid.appendChild(card);
                });

                document.querySelectorAll('.btn-status-video').forEach(btn => {
                    btn.onclick = async (e) => {
                        const lId = parseInt(e.target.getAttribute('data-lesson-id'));
                        await toggleVideoWatched(lId);
                    };
                });

                document.querySelectorAll('.btn-pdf-link').forEach(link => {
                    link.onclick = async (e) => {
                        const pId = parseInt(e.target.getAttribute('data-pdf-id'));
                        await markPdfOpened(pId);
                    };
                });

                await calculateProgress();
            } catch (e) {
                console.error(e);
            }
        }

        function showScreen(screenId) {
            document.getElementById('auth-screen').style.display = 'none';
            document.getElementById('admin-area').style.display = 'none';
            document.getElementById('course-area').style.display = 'none';
            document.getElementById(screenId).style.display = 'block';
        }

        function logout() {
            sessionStorage.removeItem('loggedUser');
            document.getElementById('error-msg').style.display = 'none';
            showScreen('auth-screen');
        }

        function clearLoginInputs() {
            document.getElementById('login-user').value = '';
            document.getElementById('login-pass').value = '';
        }

        async function initApp() {
            setupListeners();
            await checkAndInitializeLessons();
            const loggedUser = sessionStorage.getItem('loggedUser');
            if (loggedUser === 'admin_session') {
                showScreen('admin-area');
                await updateStudentsTable();
                await updateCertRequestsTable();
                await loadLessonToForm();
            } else if (loggedUser) {
                showScreen('course-area');
                await renderCourseLessons();
            } else {
                showScreen('auth-screen');
            }
        }

        initApp();
    </script>
</body>
</html>
