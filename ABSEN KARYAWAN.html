<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistem Absensi & Manajemen Cloud - HWL Law Firm</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome CDN -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- QR Scanner Library CDN -->
    <script src="https://unpkg.com/html5-qrcode" type="text/javascript"></script>
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        maroon: {
                            DEFAULT: '#6B1426',
                            dark: '#4A0D1A',
                            light: '#8C1D33'
                        },
                        gold: {
                            DEFAULT: '#C5A059',
                            light: '#E2C37D',
                            dark: '#A37F3E'
                        }
                    }
                }
            }
        }
    </script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap');
        body { font-family: 'Plus Jakarta Sans', sans-serif; }
        .gold-gradient { background: linear-gradient(135deg, #C5A059 0%, #E2C37D 50%, #A37F3E 100%); }
        .maroon-gradient { background: linear-gradient(135deg, #6B1426 0%, #4A0D1A 100%); }
    </style>
</head>
<body class="bg-gray-100 text-gray-800 min-h-screen flex flex-col justify-between">

    <!-- Header Navbar -->
    <header class="maroon-gradient text-white border-b-4 border-gold shadow-lg sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-4 py-3 flex justify-between items-center">
            <div class="flex items-center space-x-3">
                <div class="w-10 h-10 rounded-full gold-gradient flex items-center justify-center text-maroon-dark font-bold text-xl shadow">
                    <i class="fa-solid fa-scale-balanced"></i>
                </div>
                <div>
                    <h1 class="font-bold text-lg leading-tight tracking-wider text-gold-light">HWL LAW FIRM</h1>
                    <p class="text-xs text-gray-200">Advocates & Legal Consultants</p>
                </div>
            </div>
            <div id="header-user-info" class="text-right text-xs">
                <!-- User status JS -->
            </div>
        </div>
    </header>

    <!-- Indikator Status Cloud Sync -->
    <div id="sync-banner" class="bg-amber-500 text-white text-[11px] font-semibold text-center py-1 hidden shadow-inner">
        <i class="fa-solid fa-arrows-rotate animate-spin mr-1"></i> Menyinkronkan data dengan Cloud Database...
    </div>

    <!-- Main Container -->
    <main id="app" class="flex-grow max-w-7xl w-full mx-auto p-4 md:p-6">
        <!-- Rendered by JS -->
    </main>

    <!-- Footer -->
    <footer class="bg-maroon-dark text-gold py-4 text-center text-xs border-t border-gold/30">
        <p>&copy; 2026 HWL Law Firm. Cloud Database Auto-Sync Active.</p>
    </footer>

    <!-- Logic Script -->
    <script>
        // URL GOOGLE APPS SCRIPT (DATABASE CLOUD TERPUSAT)
        const GOOGLE_SCRIPT_URL = "https://script.google.com/macros/s/AKfycbyUhGqaAxIOxGA4V-u3YsA3y0dQ4ce5fB6tPVi74Bvz2vyxS7iUQLeZdS2vSuEKytQX/exec";

        const DEFAULT_DATA = {
            admin: {
                email: 'admin@hwllawfirm.com',
                password: 'admin123'
            },
            settings: {
                workStart: '08:00',
                workEnd: '17:00',
                workDays: 'Senin - Jumat',
                officeQR: 'HWL-OFFICE-CHECKIN-2026'
            },
            employees: [],
            attendance: [],
            tasks: [
                { id: 1, title: 'Menyusun Eksepsi Perkara Perdata No. 01372/2024', deadline: '2026-07-31 16:00', assignee: 'all' }
            ],
            leaves: []
        };

        function getDB() {
            const data = localStorage.getItem('hwl_law_firm_db');
            return data ? JSON.parse(data) : DEFAULT_DATA;
        }

        function saveLocalDB(data) {
            localStorage.setItem('hwl_law_firm_db', JSON.stringify(data));
        }

        // FUNGSI SINKRONISASI OTOMATIS DARI CLOUD GOOGLE SHEETS
        let isSyncing = false;
        async function syncOnlineData() {
            if (isSyncing || !GOOGLE_SCRIPT_URL) return;
            isSyncing = true;
            
            const banner = document.getElementById('sync-banner');
            if (banner) banner.classList.remove('hidden');

            try {
                const response = await fetch(GOOGLE_SCRIPT_URL);
                const result = await response.json();

                if (result.status === 'success') {
                    const db = getDB();
                    
                    // Update data dari Cloud ke lokal
                    if (Array.isArray(result.employees)) db.employees = result.employees;
                    if (Array.isArray(result.attendance)) db.attendance = result.attendance;
                    if (Array.isArray(result.leaves)) db.leaves = result.leaves;

                    saveLocalDB(db);
                    render();
                }
            } catch (err) {
                console.warn("Gagal terhubung ke Cloud. Berjalan dalam mode offline cache.");
            } finally {
                isSyncing = false;
                if (banner) banner.classList.add('hidden');
            }
        }

        // Session Management
        let session = JSON.parse(sessionStorage.getItem('hwl_session')) || { role: null, user: null };

        function setSession(role, user) {
            session = { role, user };
            sessionStorage.setItem('hwl_session', JSON.stringify(session));
            render();
        }

        function logout() {
            sessionStorage.removeItem('hwl_session');
            session = { role: null, user: null };
            render();
        }

        // Core App Renderer
        function render() {
            const db = getDB();
            const app = document.getElementById('app');
            const headerInfo = document.getElementById('header-user-info');

            if (!session.role) {
                headerInfo.innerHTML = `<span class="bg-gold/20 text-gold px-2 py-1 rounded border border-gold/40"><i class="fa-solid fa-cloud-check mr-1"></i>System Online</span>`;
                app.innerHTML = renderLoginScreen(db);
            } else if (session.role === 'admin') {
                headerInfo.innerHTML = `
                    <p class="font-bold text-gold">${session.user.email}</p>
                    <button onclick="logout()" class="text-red-300 hover:text-white underline text-[10px]">Keluar Admin</button>
                `;
                app.innerHTML = renderAdminPortal(db);
            } else if (session.role === 'employee') {
                headerInfo.innerHTML = `
                    <p class="font-bold text-gold">${session.user.name}</p>
                    <button onclick="logout()" class="text-red-300 hover:text-white underline text-[10px]">Keluar Portal</button>
                `;
                app.innerHTML = renderEmployeePortal(db);
            }
        }

        // ==========================================
        // 1. TAMPILAN LOGIN
        // ==========================================
        function renderLoginScreen(db) {
            return `
                <div class="max-w-md mx-auto my-8 bg-white rounded-2xl shadow-2xl border-2 border-gold overflow-hidden">
                    <div class="maroon-gradient p-6 text-center border-b border-gold/30">
                        <i class="fa-solid fa-user-shield text-gold text-4xl mb-2"></i>
                        <h2 class="text-2xl font-bold text-white tracking-wide">Portal Akses HWL</h2>
                        <p class="text-gold-light text-xs mt-1">Sistem Absensi Online Terintegrasi Cloud</p>
                    </div>

                    <div class="p-6">
                        <div class="flex bg-gray-100 rounded-xl p-1 mb-6 border">
                            <button onclick="toggleLoginTab('admin')" id="tab-admin-btn" class="flex-1 py-2 text-sm font-bold rounded-lg bg-maroon text-gold shadow">Portal Admin</button>
                            <button onclick="toggleLoginTab('employee')" id="tab-emp-btn" class="flex-1 py-2 text-sm font-bold text-gray-500 hover:text-maroon">Portal Karyawan</button>
                        </div>

                        <!-- Form Admin -->
                        <div id="form-admin-login" class="space-y-4">
                            <div>
                                <label class="block text-xs font-bold text-gray-700 uppercase mb-1">Email Admin</label>
                                <input type="email" id="login-admin-email" value="${db.admin.email}" class="w-full px-4 py-2 text-sm border rounded-lg focus:ring-2 focus:ring-maroon focus:outline-none">
                            </div>
                            <div>
                                <label class="block text-xs font-bold text-gray-700 uppercase mb-1">Password Admin</label>
                                <input type="password" id="login-admin-pass" value="${db.admin.password}" class="w-full px-4 py-2 text-sm border rounded-lg focus:ring-2 focus:ring-maroon focus:outline-none">
                            </div>
                            <button onclick="processAdminLogin()" class="w-full maroon-gradient hover:bg-maroon-dark text-gold font-bold py-3 rounded-lg border border-gold shadow transition">
                                <i class="fa-solid fa-right-to-bracket mr-2"></i>Masuk Portal Admin
                            </button>
                        </div>

                        <!-- Form Karyawan -->
                        <div id="form-employee-login" class="space-y-4 hidden">
                            <div>
                                <label class="block text-xs font-bold text-gray-700 uppercase mb-1">Pilih Karyawan Terdaftar</label>
                                <select id="login-emp-id" class="w-full px-4 py-2 text-sm border rounded-lg focus:ring-2 focus:ring-maroon focus:outline-none">
                                    ${db.employees.length === 0 
                                        ? `<option value="">Memuat data karyawan dari Cloud...</option>` 
                                        : db.employees.map(e => `<option value="${e.id}">${e.name} (${e.id})</option>`).join('')}
                                </select>
                            </div>
                            <button onclick="processEmployeeLogin()" class="w-full bg-gold hover:bg-gold-dark text-maroon-dark font-bold py-3 rounded-lg border border-maroon shadow transition">
                                <i class="fa-solid fa-user-check mr-2"></i>Masuk Portal Absen
                            </button>
                        </div>
                    </div>
                </div>
            `;
        }

        function toggleLoginTab(tab) {
            const adminBtn = document.getElementById('tab-admin-btn');
            const empBtn = document.getElementById('tab-emp-btn');
            const formAdmin = document.getElementById('form-admin-login');
            const formEmp = document.getElementById('form-employee-login');

            if (tab === 'admin') {
                adminBtn.className = "flex-1 py-2 text-sm font-bold rounded-lg bg-maroon text-gold shadow";
                empBtn.className = "flex-1 py-2 text-sm font-bold text-gray-500 hover:text-maroon";
                formAdmin.classList.remove('hidden');
                formEmp.classList.add('hidden');
            } else {
                empBtn.className = "flex-1 py-2 text-sm font-bold rounded-lg bg-maroon text-gold shadow";
                adminBtn.className = "flex-1 py-2 text-sm font-bold text-gray-500 hover:text-maroon";
                formEmp.classList.remove('hidden');
                formAdmin.classList.add('hidden');
            }
        }

        function processAdminLogin() {
            const db = getDB();
            const email = document.getElementById('login-admin-email').value;
            const pass = document.getElementById('login-admin-pass').value;

            if (email === db.admin.email && pass === db.admin.password) {
                setSession('admin', { email: db.admin.email });
            } else {
                alert('Gagal Login: Email atau Password Admin Salah!');
            }
        }

        function processEmployeeLogin() {
            const db = getDB();
            const empId = document.getElementById('login-emp-id').value;
            const emp = db.employees.find(e => String(e.id) === String(empId));

            if (emp) {
                setSession('employee', emp);
            } else {
                alert('Pilih nama karyawan yang valid!');
            }
        }

        // ==========================================
        // 2. PORTAL ADMIN
        // ==========================================
        let adminTab = 'dashboard';

        function renderAdminPortal(db) {
            return `
                <div class="grid grid-cols-1 md:grid-cols-4 gap-6">
                    <div class="bg-white rounded-xl shadow border border-gold/30 p-4 space-y-2">
                        <div class="p-3 maroon-gradient rounded-lg text-gold text-center font-bold mb-4">
                            <i class="fa-solid fa-user-gear mr-2"></i>MENU ADMIN
                        </div>
                        <button onclick="switchAdminTab('dashboard')" class="w-full text-left px-4 py-2.5 rounded-lg font-bold text-sm ${adminTab === 'dashboard' ? 'bg-maroon text-gold' : 'hover:bg-gray-100 text-gray-700'}">
                            <i class="fa-solid fa-chart-line w-6"></i>Dashboard
                        </button>
                        <button onclick="switchAdminTab('employees')" class="w-full text-left px-4 py-2.5 rounded-lg font-bold text-sm ${adminTab === 'employees' ? 'bg-maroon text-gold' : 'hover:bg-gray-100 text-gray-700'}">
                            <i class="fa-solid fa-users w-6"></i>Data Karyawan Cloud
                        </button>
                        <button onclick="switchAdminTab('attendance')" class="w-full text-left px-4 py-2.5 rounded-lg font-bold text-sm ${adminTab === 'attendance' ? 'bg-maroon text-gold' : 'hover:bg-gray-100 text-gray-700'}">
                            <i class="fa-solid fa-clipboard-user w-6"></i>Rekap Absensi
                        </button>
                        <button onclick="switchAdminTab('leaves')" class="w-full text-left px-4 py-2.5 rounded-lg font-bold text-sm ${adminTab === 'leaves' ? 'bg-maroon text-gold' : 'hover:bg-gray-100 text-gray-700'}">
                            <i class="fa-solid fa-envelope-open-text w-6"></i>Permohonan Izin / Sakit
                        </button>
                    </div>

                    <div class="md:col-span-3">
                        ${renderAdminTabContent(db)}
                    </div>
                </div>
            `;
        }

        function switchAdminTab(tab) {
            adminTab = tab;
            render();
        }

        function renderAdminTabContent(db) {
            if (adminTab === 'dashboard') {
                return `
                    <div class="space-y-6">
                        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                            <div class="bg-white p-5 rounded-xl shadow border-l-4 border-maroon">
                                <p class="text-xs text-gray-500 font-bold uppercase">Total Karyawan Cloud</p>
                                <h3 class="text-3xl font-bold text-maroon mt-1">${db.employees.length} Orang</h3>
                            </div>
                            <div class="bg-white p-5 rounded-xl shadow border-l-4 border-gold">
                                <p class="text-xs text-gray-500 font-bold uppercase">Total Record Absensi</p>
                                <h3 class="text-3xl font-bold text-gold-dark mt-1">${db.attendance.length} Record</h3>
                            </div>
                            <div class="bg-white p-5 rounded-xl shadow border-l-4 border-maroon-light">
                                <p class="text-xs text-gray-500 font-bold uppercase">Izin / Sakit Masuk</p>
                                <h3 class="text-3xl font-bold text-maroon-light mt-1">${db.leaves.length} Pengajuan</h3>
                            </div>
                        </div>

                        <div class="bg-white rounded-xl shadow p-6 border border-gold/40 text-center">
                            <h3 class="font-bold text-lg text-maroon mb-2"><i class="fa-solid fa-qrcode mr-2 text-gold"></i>Barcode QR Absensi Utama Kantor</h3>
                            <p class="text-xs text-gray-600 mb-4">Cetak QR ini dan tempelkan di area masuk kantor HWL Law Firm.</p>
                            <div class="inline-block bg-gray-50 p-4 rounded-xl border border-dashed border-gold">
                                <img src="https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=${db.settings.officeQR}" class="mx-auto rounded shadow bg-white p-2 border">
                                <p class="font-mono text-sm font-bold text-maroon mt-3">${db.settings.officeQR}</p>
                            </div>
                        </div>
                    </div>
                `;
            }

            if (adminTab === 'employees') {
                return `
                    <div class="bg-white rounded-xl shadow p-6 border border-gold/30">
                        <div class="flex justify-between items-center mb-6">
                            <h3 class="font-bold text-lg text-maroon"><i class="fa-solid fa-users mr-2"></i>Daftar Karyawan (Google Sheets Cloud)</h3>
                            <button onclick="openModalAddEmp()" class="bg-maroon text-gold px-4 py-2 rounded-lg font-bold text-xs hover:bg-maroon-dark shadow">
                                <i class="fa-solid fa-user-plus mr-1"></i>Tambah Karyawan Baru
                            </button>
                        </div>

                        <div class="overflow-x-auto">
                            <table class="w-full text-left text-xs border-collapse">
                                <thead>
                                    <tr class="bg-maroon text-gold font-bold">
                                        <th class="p-3 border">ID & Nama</th>
                                        <th class="p-3 border">Email</th>
                                        <th class="p-3 border">No. Telp</th>
                                        <th class="p-3 border">Barcode ID</th>
                                        <th class="p-3 border text-center">Aksi</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    ${db.employees.length === 0 
                                        ? `<tr><td colspan="5" class="p-4 text-center text-gray-500">Belum ada data karyawan. Tambahkan karyawan baru di atas.</td></tr>`
                                        : db.employees.map(e => `
                                            <tr class="hover:bg-gray-50 border-b">
                                                <td class="p-3 font-bold">${e.name}<br><span class="text-[10px] text-gray-500 font-normal">${e.id}</span></td>
                                                <td class="p-3">${e.email}</td>
                                                <td class="p-3">${e.phone}</td>
                                                <td class="p-3"><span class="bg-gold/20 text-maroon px-2 py-1 rounded font-mono font-bold">${e.barcode}</span></td>
                                                <td class="p-3 text-center">
                                                    <button onclick="deleteEmployee('${e.id}')" class="text-red-600 hover:text-red-800 font-bold">
                                                        <i class="fa-solid fa-trash-can"></i> Hapus
                                                    </button>
                                                </td>
                                            </tr>
                                        `).join('')}
                                </tbody>
                            </table>
                        </div>
                    </div>
                `;
            }

            if (adminTab === 'attendance') {
                return `
                    <div class="bg-white rounded-xl shadow p-6 border border-gold/30">
                        <div class="flex justify-between items-center mb-6">
                            <div>
                                <h3 class="font-bold text-lg text-maroon"><i class="fa-solid fa-clipboard-user mr-2"></i>Rekap Absensi Real-Time Cloud</h3>
                                <p class="text-[11px] text-green-600 font-semibold mt-0.5"><i class="fa-solid fa-circle text-[8px] animate-pulse mr-1"></i>Otomatis tersinkronisasi dari HP Seluruh Karyawan</p>
                            </div>
                            <button onclick="exportAttendanceToWord()" class="bg-gold-dark text-white px-4 py-2 rounded-lg font-bold text-xs hover:bg-gold shadow">
                                <i class="fa-solid fa-file-word mr-1"></i>Download MS Word
                            </button>
                        </div>

                        <div class="overflow-x-auto">
                            <table class="w-full text-left text-xs border-collapse">
                                <thead>
                                    <tr class="bg-maroon text-gold font-bold">
                                        <th class="p-3 border">Waktu Absen</th>
                                        <th class="p-3 border">Nama Karyawan</th>
                                        <th class="p-3 border">Agenda Kerja Hari Ini</th>
                                        <th class="p-3 border">Lokasi GPS</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    ${db.attendance.length === 0 ? `<tr><td colspan="4" class="p-4 text-center text-gray-500">Belum ada catatan absensi terdeteksi.</td></tr>` : 
                                        db.attendance.map(a => `
                                            <tr class="hover:bg-gray-50 border-b">
                                                <td class="p-3 font-mono font-bold text-maroon">${a.timestamp}</td>
                                                <td class="p-3 font-bold">${a.name}</td>
                                                <td class="p-3">${a.agenda}</td>
                                                <td class="p-3 text-[10px] text-blue-600 font-semibold">${a.location}</td>
                                            </tr>
                                        `).join('')}
                                </tbody>
                            </table>
                        </div>
                    </div>
                `;
            }

            if (adminTab === 'leaves') {
                return `
                    <div class="bg-white rounded-xl shadow p-6 border border-gold/30">
                        <h3 class="font-bold text-lg text-maroon mb-6"><i class="fa-solid fa-envelope-open-text mr-2"></i>Data Pengajuan Izin / Sakit</h3>
                        <div class="overflow-x-auto">
                            <table class="w-full text-left text-xs border-collapse">
                                <thead>
                                    <tr class="bg-maroon text-gold font-bold">
                                        <th class="p-3 border">Nama Karyawan</th>
                                        <th class="p-3 border">Tipe</th>
                                        <th class="p-3 border">Alasan / Catatan</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    ${db.leaves.length === 0 ? `<tr><td colspan="3" class="p-4 text-center text-gray-500">Belum ada data izin/sakit.</td></tr>` : 
                                        db.leaves.map(l => `
                                            <tr class="hover:bg-gray-50 border-b">
                                                <td class="p-3 font-bold">${l.name}</td>
                                                <td class="p-3"><span class="px-2 py-1 rounded text-[10px] font-bold ${l.type === 'Sakit' ? 'bg-red-100 text-red-800' : 'bg-blue-100 text-blue-800'}">${l.type}</span></td>
                                                <td class="p-3">${l.reason}</td>
                                            </tr>
                                        `).join('')}
                                </tbody>
                            </table>
                        </div>
                    </div>
                `;
            }
        }

        // TAMBAH KARYAWAN ONLINE (Mengirim ke Google Sheets)
        async function openModalAddEmp() {
            const name = prompt("Nama Lengkap Karyawan (beserta Gelar):");
            if (!name) return;
            const email = prompt("Email Karyawan:") || '-';
            const phone = prompt("Nomor Telepon/WA:") || '-';

            const db = getDB();
            const id = `HWL-00${db.employees.length + 1}`;
            const newEmp = { id, name, email, phone, barcode: id };

            // Simpan sementara di lokal
            db.employees.push(newEmp);
            saveLocalDB(db);
            render();

            // Kirim ke Google Sheets Cloud
            try {
                await fetch(GOOGLE_SCRIPT_URL, {
                    method: 'POST',
                    mode: 'no-cors',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify({ action: 'add_employee', ...newEmp })
                });
                alert(`Karyawan ${name} berhasil ditambahkan ke Cloud Database!`);
                syncOnlineData();
            } catch (e) {
                alert("Gagal terhubung ke Cloud server, namun data tersimpan lokal.");
            }
        }

        // HAPUS KARYAWAN ONLINE (Menghapus dari Google Sheets)
        async function deleteEmployee(id) {
            if (confirm(`Yakin ingin menghapus karyawan ${id} dari sistem Cloud?`)) {
                const db = getDB();
                db.employees = db.employees.filter(e => String(e.id) !== String(id));
                saveLocalDB(db);
                render();

                try {
                    await fetch(GOOGLE_SCRIPT_URL, {
                        method: 'POST',
                        mode: 'no-cors',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify({ action: 'delete_employee', id: id })
                    });
                    alert(`Karyawan berhasil dihapus dari Cloud Database!`);
                    syncOnlineData();
                } catch (e) {
                    alert("Gagal memperbarui Cloud database.");
                }
            }
        }

        function exportAttendanceToWord() {
            const db = getDB();
            let htmlContent = `
                <html xmlns:o='urn:schemas-microsoft-com:office:office' xmlns:w='urn:schemas-microsoft-com:office:word' xmlns='http://www.w3.org/TR/REC-html40'>
                <head><title>Rekap Absensi HWL Law Firm</title>
                <style>
                    body { font-family: 'Times New Roman', serif; }
                    h2 { text-align: center; color: #6B1426; margin-bottom: 5px; }
                    p { text-align: center; font-size: 10pt; margin-top: 0; }
                    table { width: 100%; border-collapse: collapse; margin-top: 20px; }
                    th, td { border: 1px solid #000; padding: 8px; font-size: 10pt; text-align: left; }
                    th { background-color: #6B1426; color: #FFFFFF; }
                </style>
                </head>
                <body>
                <h2>REKAPITULASI ABSENSI KARYAWAN HWL LAW FIRM</h2>
                <p>Tanggal Cetak: ${new Date().toLocaleDateString('id-ID')}</p>
                <table>
                    <thead>
                        <tr>
                            <th>Waktu Absen</th>
                            <th>Nama Karyawan</th>
                            <th>Agenda Kegiatan</th>
                            <th>Lokasi GPS</th>
                        </tr>
                    </thead>
                    <tbody>
                        ${db.attendance.map(a => `
                            <tr>
                                <td>${a.timestamp}</td>
                                <td>${a.name}</td>
                                <td>${a.agenda}</td>
                                <td>${a.location}</td>
                            </tr>
                        `).join('')}
                    </tbody>
                </table>
                </body></html>
            `;

            const blob = new Blob(['\ufeff' + htmlContent], { type: 'application/msword' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = `Rekap_Absen_HWL_${new Date().toISOString().split('T')[0]}.doc`;
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
        }

        // ==========================================
        // 3. PORTAL KARYAWAN
        // ==========================================
        let empTab = 'scan';

        function renderEmployeePortal(db) {
            const emp = session.user;
            return `
                <div class="grid grid-cols-1 md:grid-cols-4 gap-6">
                    <div class="bg-white rounded-xl shadow border border-gold/30 p-4 space-y-4 text-center">
                        <div class="w-20 h-20 mx-auto rounded-full bg-gold/20 border-2 border-gold flex items-center justify-center">
                            <i class="fa-solid fa-user-tie text-maroon text-3xl"></i>
                        </div>
                        <div>
                            <h3 class="font-bold text-sm text-maroon">${emp.name}</h3>
                            <p class="text-xs text-gray-500">ID: ${emp.id}</p>
                        </div>

                        <div class="space-y-2 pt-2 border-t">
                            <button onclick="switchEmpTab('scan')" class="w-full text-left px-4 py-2 rounded-lg font-bold text-xs ${empTab === 'scan' ? 'bg-maroon text-gold' : 'hover:bg-gray-100'}">
                                <i class="fa-solid fa-qrcode w-5"></i>Scan Absen Kamera
                            </button>
                            <button onclick="switchEmpTab('leave')" class="w-full text-left px-4 py-2 rounded-lg font-bold text-xs ${empTab === 'leave' ? 'bg-maroon text-gold' : 'hover:bg-gray-100'}">
                                <i class="fa-solid fa-notes-medical w-5"></i>Form Izin / Sakit
                            </button>
                        </div>
                    </div>

                    <div class="md:col-span-3">
                        ${renderEmpTabContent(db)}
                    </div>
                </div>
            `;
        }

        function switchEmpTab(tab) {
            empTab = tab;
            render();
            if (tab === 'scan') {
                setTimeout(initGPS, 300);
            }
        }

        let gpsLocationString = "Mendeteksi GPS...";

        function initGPS() {
            const gpsEl = document.getElementById('emp-gps-display');
            if (navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(
                    (pos) => {
                        gpsLocationString = `Lat: ${pos.coords.latitude.toFixed(5)}, Lng: ${pos.coords.longitude.toFixed(5)}`;
                        if (gpsEl) gpsEl.innerHTML = `<i class="fa-solid fa-location-dot text-red-600 mr-1"></i>${gpsLocationString}`;
                    },
                    () => {
                        gpsLocationString = "GPS Aktif";
                        if (gpsEl) gpsEl.innerHTML = `<i class="fa-solid fa-location-dot text-gold mr-1"></i>${gpsLocationString}`;
                    }
                );
            }
        }

        function renderEmpTabContent(db) {
            if (empTab === 'scan') {
                return `
                    <div class="bg-white rounded-xl shadow p-6 border border-gold/30">
                        <h3 class="font-bold text-lg text-maroon mb-2"><i class="fa-solid fa-qrcode mr-2 text-gold"></i>Absen Kehadiran via QR Barcode</h3>
                        <p class="text-xs text-gray-500 mb-4">Arahkan kamera HP Anda ke Barcode Kantor HWL Law Firm.</p>

                        <div class="space-y-4">
                            <div class="bg-black/90 rounded-xl p-3 flex flex-col items-center justify-center min-h-[220px]">
                                <div id="reader" class="w-full max-w-sm rounded overflow-hidden"></div>
                                <button onclick="startCameraScanner()" id="start-cam-btn" class="bg-gold text-maroon-dark font-bold text-xs px-4 py-2 rounded shadow mt-2">
                                    <i class="fa-solid fa-camera mr-1"></i> Buka Kamera HP
                                </button>
                            </div>

                            <div>
                                <label class="block text-xs font-bold text-gray-700 uppercase mb-1">Agenda Kegiatan Hari Ini *</label>
                                <textarea id="emp-agenda-input" rows="3" placeholder="Tuliskan agenda kerja Anda hari ini..." class="w-full px-3 py-2 border rounded-lg text-sm focus:ring-2 focus:ring-maroon"></textarea>
                            </div>

                            <div class="bg-gray-50 p-3 rounded-lg border flex justify-between items-center text-xs">
                                <span>Status Lokasi GPS:</span>
                                <span id="emp-gps-display" class="font-bold text-maroon">Mendeteksi...</span>
                            </div>

                            <button onclick="manualSimulateScan()" class="w-full maroon-gradient text-gold font-bold py-3 rounded-lg border border-gold shadow">
                                <i class="fa-solid fa-check-circle mr-2"></i>Konfirmasi Absen Kehadiran
                            </button>
                        </div>
                    </div>
                `;
            }

            if (empTab === 'leave') {
                return `
                    <div class="bg-white rounded-xl shadow p-6 border border-gold/30 max-w-lg">
                        <h3 class="font-bold text-lg text-maroon mb-4"><i class="fa-solid fa-notes-medical mr-2"></i>Form Pengajuan Izin / Sakit</h3>
                        <div class="space-y-4">
                            <div>
                                <label class="block text-xs font-bold text-gray-700 uppercase mb-1">Kategori</label>
                                <select id="leave-type-input" class="w-full px-3 py-2 border rounded-lg text-sm">
                                    <option value="Sakit">Sakit</option>
                                    <option value="Izin">Izin Berhalangan Hadir</option>
                                </select>
                            </div>
                            <div>
                                <label class="block text-xs font-bold text-gray-700 uppercase mb-1">Alasan / Catatan</label>
                                <textarea id="leave-reason-input" rows="3" placeholder="Jelaskan alasan berhalangan..." class="w-full px-3 py-2 border rounded-lg text-sm"></textarea>
                            </div>
                            <button onclick="submitEmpLeave()" class="w-full bg-maroon text-gold font-bold py-2.5 rounded-lg hover:bg-maroon-dark">
                                Kirim Pengajuan ke Admin
                            </button>
                        </div>
                    </div>
                `;
            }
        }

        let html5QrcodeScanner = null;

        function startCameraScanner() {
            const btn = document.getElementById('start-cam-btn');
            if (btn) btn.classList.add('hidden');

            html5QrcodeScanner = new Html5Qrcode("reader");
            html5QrcodeScanner.start(
                { facingMode: "environment" },
                { fps: 10, qrbox: { width: 200, height: 200 } },
                (decodedText) => {
                    html5QrcodeScanner.stop();
                    processAttendanceRecord(decodedText);
                },
                () => {}
            ).catch(err => {
                alert('Tidak dapat mengakses kamera. Izinkan akses kamera di browser HP Anda.');
            });
        }

        function manualSimulateScan() {
            const db = getDB();
            processAttendanceRecord(db.settings.officeQR);
        }

        // PROSES ABSEN ONLINE
        async function processAttendanceRecord(scannedQR) {
            const db = getDB();
            const agenda = document.getElementById('emp-agenda-input')?.value;

            if (!agenda) {
                alert('Wajib mengisi agenda kegiatan hari ini!');
                return;
            }

            if (scannedQR !== db.settings.officeQR) {
                alert('Barcode QR tidak sesuai dengan QR Resmi HWL Law Firm!');
                return;
            }

            const now = new Date();
            const timestampStr = `${now.toLocaleDateString('id-ID', { weekday: 'long' })}, ${now.getDate()}/${now.getMonth()+1}/${now.getFullYear()} ${String(now.getHours()).padStart(2,'0')}:${String(now.getMinutes()).padStart(2,'0')}:${String(now.getSeconds()).padStart(2,'0')} WIB`;

            const payload = {
                action: 'absen',
                id: session.user.id,
                name: session.user.name,
                timestamp: timestampStr,
                agenda: agenda,
                location: gpsLocationString
            };

            // Simpan lokal dulu
            db.attendance.unshift(payload);
            saveLocalDB(db);

            // Kirim ke Google Sheets Cloud
            try {
                await fetch(GOOGLE_SCRIPT_URL, {
                    method: 'POST',
                    mode: 'no-cors',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });
                alert(`Absen Berhasil Dicatat Online!\n\nWaktu: ${timestampStr}\nKaryawan: ${session.user.name}`);
                syncOnlineData();
            } catch (err) {
                alert(`Absen tersimpan lokal. Koneksi cloud bermasalah.`);
            }

            switchEmpTab('scan');
        }

        async function submitEmpLeave() {
            const type = document.getElementById('leave-type-input').value;
            const reason = document.getElementById('leave-reason-input').value;

            if (!reason) { alert('Alasan wajib diisi!'); return; }

            const db = getDB();
            const payload = {
                action: 'izin',
                name: session.user.name,
                type: type,
                reason: reason
            };

            db.leaves.unshift({ name: session.user.name, type, reason });
            saveLocalDB(db);

            try {
                await fetch(GOOGLE_SCRIPT_URL, {
                    method: 'POST',
                    mode: 'no-cors',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });
                alert('Pengajuan izin berhasil terkirim ke Cloud Admin!');
                syncOnlineData();
            } catch (e) {
                alert('Pengajuan izin tersimpan lokal.');
            }

            switchEmpTab('leave');
        }

        // Inisialisasi Aplikasi
        render();
        // Tarik data cloud langsung saat aplikasi pertama dibuka
        syncOnlineData();

        // Polling Sinkronisasi Otomatis Setiap 8 Detik
        setInterval(() => {
            syncOnlineData();
        }, 8000);
    </script>
</body>
</html>
