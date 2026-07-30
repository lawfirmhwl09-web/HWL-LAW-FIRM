<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aplikasi Absensi - HWL Law Firm</title>
    
    <!-- Progressive Web App (PWA) Meta Tags -->
    <meta name="theme-color" content="#6B0D18">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="apple-mobile-web-app-title" content="Absensi HWL">
    
    <!-- Dynamic Web App Manifest via Data URI -->
    <link rel="manifest" href='data:application/manifest+json,{"name":"Aplikasi Absensi HWL Law Firm","short_name":"Absensi HWL","start_url":".","display":"standalone","background_color":"#FAF8F5","theme_color":"#6B0D18","icons":[{"src":"https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/svgs/solid/scale-balanced.svg","sizes":"192x192 512x512","type":"image/svg+xml"}]}'>

    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@500;700;800&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <!-- QRCode.js Library -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <!-- JsQR Library for Camera Scanning -->
    <script src="https://cdn.jsdelivr.net/npm/jsqr@1.4.0/dist/jsQR.min.js"></script>
    
    <style>
        :root {
            --maroon-primary: #6B0D18;
            --maroon-dark: #4A0810;
            --maroon-light: #8C1C2A;
            --gold-primary: #D4AF37;
            --gold-light: #F4E5B0;
            --gold-dark: #AA820A;
            --white: #FFFFFF;
            --bg-light: #FAF8F5;
            --text-dark: #2C2C2C;
            --text-muted: #666666;
            --border-color: #E2D9CC;
            --shadow: 0 8px 24px rgba(107, 13, 24, 0.08);
            --shadow-hover: 0 12px 32px rgba(107, 13, 24, 0.15);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Plus Jakarta Sans', sans-serif;
        }

        body {
            background-color: var(--bg-light);
            color: var(--text-dark);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        .navbar {
            background: linear-gradient(135deg, var(--maroon-dark) 0%, var(--maroon-primary) 100%);
            color: var(--white);
            padding: 1rem 2rem;
            border-bottom: 4px solid var(--gold-primary);
            box-shadow: 0 4px 15px rgba(0,0,0,0.15);
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .brand-container {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .brand-logo {
            width: 48px;
            height: 48px;
            background: var(--gold-primary);
            color: var(--maroon-dark);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            box-shadow: 0 0 10px rgba(212, 175, 55, 0.4);
        }

        .brand-title {
            font-family: 'Cinzel', serif;
            font-size: 1.4rem;
            font-weight: 700;
            letter-spacing: 1px;
            color: var(--gold-light);
        }

        .brand-subtitle {
            font-size: 0.75rem;
            color: rgba(255,255,255,0.8);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .nav-controls {
            display: flex;
            gap: 0.75rem;
            align-items: center;
        }

        .btn {
            padding: 0.6rem 1.2rem;
            border-radius: 6px;
            border: none;
            font-weight: 600;
            font-size: 0.88rem;
            cursor: pointer;
            transition: all 0.25s ease;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            text-decoration: none;
        }

        .btn:disabled {
            opacity: 0.5;
            cursor: not-allowed !important;
            filter: grayscale(1);
        }

        .btn-gold {
            background: linear-gradient(135deg, var(--gold-primary) 0%, var(--gold-dark) 100%);
            color: var(--maroon-dark);
            border: 1px solid var(--gold-light);
        }

        .btn-gold:hover:not(:disabled) {
            background: var(--gold-light);
            box-shadow: 0 0 12px rgba(212, 175, 55, 0.5);
            transform: translateY(-1px);
        }

        .btn-maroon {
            background: var(--maroon-primary);
            color: var(--white);
            border: 1px solid var(--gold-primary);
        }

        .btn-maroon:hover:not(:disabled) {
            background: var(--maroon-light);
            transform: translateY(-1px);
        }

        .btn-outline {
            background: transparent;
            color: var(--white);
            border: 1px solid var(--gold-primary);
        }

        .btn-outline:hover {
            background: rgba(212, 175, 55, 0.15);
            color: var(--gold-light);
        }

        .btn-secondary {
            background: #e0e0e0;
            color: #333;
        }

        .btn-secondary:hover {
            background: #d0d0d0;
        }

        .btn-danger {
            background: #c0392b;
            color: white;
        }

        .btn-danger:hover {
            background: #a93226;
        }

        .main-container {
            max-width: 1300px;
            width: 100%;
            margin: 2rem auto;
            padding: 0 1.5rem;
            flex: 1;
        }

        .view-section {
            display: none;
        }

        .view-section.active {
            display: block;
            animation: fadeIn 0.3s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(6px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .card {
            background: var(--white);
            border-radius: 12px;
            border: 1px solid var(--border-color);
            box-shadow: var(--shadow);
            padding: 1.8rem;
            margin-bottom: 1.8rem;
        }

        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 2px solid var(--bg-light);
            padding-bottom: 1rem;
            margin-bottom: 1.5rem;
        }

        .card-title {
            font-family: 'Cinzel', serif;
            font-size: 1.25rem;
            color: var(--maroon-primary);
            display: flex;
            align-items: center;
            gap: 0.6rem;
            font-weight: 700;
        }

        .grid-2 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 1.5rem;
        }

        .grid-4 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 1.2rem;
        }

        .stat-card {
            background: linear-gradient(135deg, #FFFDF8 0%, #FAF4E8 100%);
            border: 1px solid var(--gold-primary);
            border-radius: 10px;
            padding: 1.2rem;
            display: flex;
            align-items: center;
            gap: 1.2rem;
        }

        .stat-icon {
            width: 50px;
            height: 50px;
            border-radius: 10px;
            background: var(--maroon-primary);
            color: var(--gold-primary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.4rem;
        }

        .stat-val {
            font-size: 1.6rem;
            font-weight: 700;
            color: var(--maroon-dark);
        }

        .stat-lbl {
            font-size: 0.8rem;
            color: var(--text-muted);
            text-transform: uppercase;
            font-weight: 600;
        }

        .form-group {
            margin-bottom: 1.2rem;
        }

        .form-label {
            display: block;
            font-weight: 600;
            font-size: 0.88rem;
            margin-bottom: 0.4rem;
            color: var(--maroon-dark);
        }

        .form-control {
            width: 100%;
            padding: 0.7rem 0.9rem;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            font-size: 0.9rem;
            transition: border-color 0.2s ease;
            background: #FAFAFA;
        }

        .form-control:disabled {
            background-color: #f0f0f0;
            cursor: not-allowed;
            color: #888;
        }

        .form-control:focus:not(:disabled) {
            outline: none;
            border-color: var(--gold-primary);
            background: #FFF;
            box-shadow: 0 0 0 3px rgba(212, 175, 55, 0.15);
        }

        textarea.form-control {
            min-height: 90px;
            resize: vertical;
        }

        .table-responsive {
            width: 100%;
            overflow-x: auto;
            border-radius: 8px;
            border: 1px solid var(--border-color);
        }

        .table {
            width: 100%;
            border-collapse: collapse;
            text-align: left;
            font-size: 0.88rem;
        }

        .table th {
            background: var(--maroon-primary);
            color: var(--gold-light);
            padding: 0.9rem 1rem;
            font-weight: 600;
            text-transform: uppercase;
            font-size: 0.78rem;
            letter-spacing: 0.5px;
            border-bottom: 2px solid var(--gold-primary);
        }

        .table td {
            padding: 0.8rem 1rem;
            border-bottom: 1px solid var(--border-color);
            vertical-align: middle;
        }

        .table tbody tr:nth-child(even) {
            background-color: #FAF8F5;
        }

        .table tbody tr:hover {
            background-color: #F3ECE1;
        }

        .badge {
            padding: 0.35rem 0.7rem;
            border-radius: 50px;
            font-size: 0.75rem;
            font-weight: 700;
            display: inline-block;
        }

        .badge-success { background: #27ae60; color: white; }
        .badge-warning { background: #f39c12; color: white; }
        .badge-info { background: #2980b9; color: white; }

        .status-box {
            padding: 0.8rem 1rem;
            border-radius: 8px;
            margin-bottom: 1.2rem;
            font-size: 0.85rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 0.6rem;
            transition: all 0.3s ease;
        }
        .status-box.locked {
            background: #FDEDEC;
            color: #C0392B;
            border: 1px solid #F5B7B1;
        }
        .status-box.unlocked {
            background: #E8F8F5;
            color: #117864;
            border: 1px solid #A3E4D7;
        }

        #interactive-scanner {
            width: 100%;
            max-width: 450px;
            height: 320px;
            border: 3px solid var(--gold-primary);
            border-radius: 12px;
            overflow: hidden;
            position: relative;
            background: #000;
            margin: 0 auto 1.5rem auto;
        }

        #scanner-video {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .scanner-overlay {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 220px;
            height: 220px;
            border: 2px dashed var(--gold-primary);
            box-shadow: 0 0 0 9999px rgba(0, 0, 0, 0.45);
            pointer-events: none;
            border-radius: 8px;
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.65);
            backdrop-filter: blur(4px);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }

        .modal.active { display: flex; }

        .modal-content {
            background: var(--white);
            border-radius: 12px;
            width: 90%;
            max-width: 550px;
            border: 2px solid var(--gold-primary);
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            overflow: hidden;
            animation: modalSlide 0.3s ease;
        }

        @keyframes modalSlide {
            from { transform: translateY(-20px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .modal-header {
            background: var(--maroon-primary);
            color: var(--gold-light);
            padding: 1rem 1.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-family: 'Cinzel', serif;
        }

        .modal-body {
            padding: 1.5rem;
            max-height: 80vh;
            overflow-y: auto;
        }

        .modal-footer {
            padding: 1rem 1.5rem;
            background: #F9F9F9;
            border-top: 1px solid var(--border-color);
            display: flex;
            justify-content: flex-end;
            gap: 0.8rem;
        }

        .close-btn {
            background: none;
            border: none;
            color: var(--gold-light);
            font-size: 1.2rem;
            cursor: pointer;
        }

        .profile-qr-card {
            text-align: center;
            padding: 1.5rem;
            border: 2px dashed var(--gold-primary);
            border-radius: 12px;
            background: #FFFDF8;
        }

        .profile-img-preview {
            width: 110px;
            height: 110px;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid var(--gold-primary);
            margin: 0 auto 1rem auto;
            display: block;
            background: #eee;
        }

        .table-profile-img {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            object-fit: cover;
            border: 2px solid var(--gold-primary);
            display: inline-block;
            vertical-align: middle;
            margin-right: 8px;
            background: #eee;
        }

        .live-clock {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--maroon-primary);
            font-family: monospace;
            letter-spacing: 2px;
            text-align: center;
            margin: 0.5rem 0;
        }

        .live-date {
            text-align: center;
            font-weight: 600;
            color: var(--text-muted);
            margin-bottom: 1.2rem;
        }

        footer {
            text-align: center;
            padding: 1.5rem;
            background: var(--maroon-dark);
            color: var(--gold-light);
            font-size: 0.82rem;
            border-top: 2px solid var(--gold-primary);
            margin-top: auto;
        }

        @media print {
            body * { visibility: hidden; }
            #printable-wall-qr, #printable-wall-qr * { visibility: visible; }
            #printable-wall-qr { position: absolute; left: 0; top: 0; width: 100%; }
        }

        .sync-pill {
            display: inline-flex;
            align-items: center;
            gap: 6px;
            padding: 4px 10px;
            border-radius: 20px;
            font-size: 0.75rem;
            background: rgba(255,255,255,0.15);
            color: #fff;
            border: 1px solid rgba(212,175,55,0.5);
        }
        .sync-dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: #2ecc71;
            box-shadow: 0 0 6px #2ecc71;
        }
    </style>
</head>
<body>

    <!-- NAVBAR -->
    <nav class="navbar">
        <div class="brand-container">
            <div class="brand-logo">
                <i class="fa-solid fa-scale-balanced"></i>
            </div>
            <div>
                <div class="brand-title">HWL LAW FIRM</div>
                <div class="brand-subtitle">Kantor Hukum HWL & Partners - Sistem Absensi Real-Time</div>
            </div>
        </div>

        <div class="sync-pill" id="syncStatus">
            <div class="sync-dot"></div>
            <span>Firebase RTDB Terkoneksi</span>
        </div>

        <div class="nav-controls">
            <button class="btn btn-gold" id="btnNavKaryawan" onclick="switchView('karyawanView')">
                <i class="fa-solid fa-user-check"></i> Portal Karyawan
            </button>
            <button class="btn btn-outline" id="btnNavAdmin" onclick="openAdminLoginModal()">
                <i class="fa-solid fa-user-shield"></i> Portal Admin
            </button>
            <button class="btn btn-outline" onclick="switchView('wallBarcodeView')">
                <i class="fa-solid fa-qrcode"></i> QR Dinding Kantor
            </button>
            <button class="btn btn-gold" id="btnInstallPwa" style="display:none;" onclick="installPWA()">
                <i class="fa-solid fa-download"></i> Install App
            </button>
        </div>
    </nav>

    <div class="main-container">

        <!-- PORTAL KARYAWAN VIEW -->
        <div id="karyawanView" class="view-section active">
            
            <div class="grid-2">
                <!-- Left Box: Scan Barcode Absen & Presensi -->
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">
                            <i class="fa-solid fa-camera"></i> Scan Barcode Presensi Hari Ini
                        </div>
                    </div>

                    <div class="live-clock" id="liveClockDisplay">00:00:00</div>
                    <div class="live-date" id="liveDateDisplay">Kamis, 30 Juli 2026</div>

                    <!-- Status Lock / Unlock Notice -->
                    <div class="status-box locked" id="scanLockNotice">
                        <i class="fa-solid fa-lock"></i>
                        <span id="scanNoticeText">Scan Barcode Kantor / ID Anda terlebih dahulu untuk membuka form presensi!</span>
                    </div>

                    <!-- Mode Selector for Scan -->
                    <div class="form-group" style="text-align: center; margin-bottom: 1.2rem;">
                        <button class="btn btn-maroon btn-sm" onclick="startCameraScan()"><i class="fa-solid fa-video"></i> Buka Kamera HP Scan QR Kantor</button>
                        <button class="btn btn-secondary btn-sm" onclick="stopCameraScan()"><i class="fa-solid fa-video-slash"></i> Matikan Kamera</button>
                    </div>

                    <div id="interactive-scanner" style="display: none;">
                        <video id="scanner-video" playsinline></video>
                        <div class="scanner-overlay"></div>
                    </div>

                    <!-- Form Presensi Manual / Auto after QR Scan -->
                    <form id="attendanceForm" onsubmit="handleAttendanceSubmit(event)">
                        <div class="form-group">
                            <label class="form-label">Pilih ID / Nama Karyawan</label>
                            <select class="form-control" id="employeeSelect" required disabled onchange="onEmployeeSelectChange()">
                                <option value="">-- Pilih Nama Anda --</option>
                            </select>
                        </div>

                        <div class="form-group">
                            <label class="form-label">Agenda Kegiatan Hari Ini</label>
                            <textarea class="form-control" id="agendaInput" disabled placeholder="Tuliskan detail agenda persidangan, riset hukum, pendampingan klien, atau tugas hari ini..." required></textarea>
                        </div>

                        <div class="form-group">
                            <label class="form-label">Lokasi GPS Perangkat (Real-Time)</label>
                            <div style="display: flex; gap: 0.5rem;">
                                <input type="text" class="form-control" id="gpsDisplay" readonly placeholder="Mengambil koordinat GPS HP...">
                                <button type="button" class="btn btn-gold" id="btnRefreshGps" disabled onclick="fetchGPSLocation(true)"><i class="fa-solid fa-location-crosshairs"></i></button>
                            </div>
                        </div>

                        <button type="submit" class="btn btn-gold" id="btnSubmitAttendance" disabled style="width: 100%; padding: 0.9rem; font-size: 1rem;">
                            <i class="fa-solid fa-fingerprint"></i> KIRIM PRESENSI SEKARANG
                        </button>
                    </form>
                </div>

                <!-- Right Box: Info Tugas, Profile & Request Izin -->
                <div>
                    <!-- Card Profile & QR Code ID -->
                    <div class="card">
                        <div class="card-header">
                            <div class="card-title">
                                <i class="fa-solid fa-id-card"></i> Identitas & Profil Karyawan
                            </div>
                        </div>
                        <div class="profile-qr-card" id="profileQrDisplayBox">
                            <img src="https://via.placeholder.com/110?text=Foto" id="employeeProfilePic" class="profile-img-preview">
                            <h3 id="employeeProfileName" style="color: var(--maroon-primary); font-family: 'Cinzel', serif;">Pilih Karyawan</h3>
                            <p id="employeeProfileRole" style="color: var(--text-muted); font-size: 0.9rem; margin-bottom: 1rem;">-</p>
                            
                            <div style="margin-top: 1rem;">
                                <button type="button" class="btn btn-outline btn-sm" onclick="openChangePhotoModal()" style="color: var(--maroon-dark); border-color: var(--maroon-dark);">
                                    <i class="fa-solid fa-image"></i> Ganti Foto Profil dari Galeri
                                </button>
                            </div>

                            <div style="margin-top: 1.5rem; display: inline-block;">
                                <div id="employeePersonalQR"></div>
                                <div style="font-size: 0.75rem; color: var(--text-muted); margin-top: 0.4rem;">QR Code ID Karyawan</div>
                            </div>
                        </div>
                    </div>

                    <!-- Card Portal Izin / Sakit -->
                    <div class="card">
                        <div class="card-header">
                            <div class="card-title">
                                <i class="fa-solid fa-notes-medical"></i> Portal Izin / Surat Sakit
                            </div>
                        </div>
                        <form id="leaveForm" onsubmit="handleLeaveSubmit(event)">
                            <div class="form-group">
                                <label class="form-label">Karyawan</label>
                                <select class="form-control" id="leaveEmployeeSelect" required>
                                    <option value="">-- Pilih Karyawan --</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label class="form-label">Jenis Permohonan</label>
                                <select class="form-control" id="leaveType" required>
                                    <option value="Sakit dengan Surat Dokter">Sakit dengan Surat Dokter</option>
                                    <option value="Izin Keperluan Mendesak">Izin Keperluan Mendesak</option>
                                    <option value="Cuti Resmi">Cuti Resmi</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label class="form-label">Tanggal Izin</label>
                                <input type="date" class="form-control" id="leaveDate" required>
                            </div>
                            <div class="form-group">
                                <label class="form-label">Keterangan / Alasan</label>
                                <textarea class="form-control" id="leaveReason" placeholder="Jelaskan alasan permohonan izin..." required></textarea>
                            </div>
                            <div class="form-group">
                                <label class="form-label">Unggah Foto Surat Keterangan Sakit / Bukti</label>
                                <input type="file" class="form-control" id="leaveProofFile" accept="image/*" required onchange="previewLeaveProof(event)">
                                <img id="leaveProofPreview" style="max-width: 100%; max-height: 150px; display: none; margin-top: 0.8rem; border-radius: 6px; border: 1px solid var(--gold-primary);">
                            </div>
                            <button type="submit" class="btn btn-maroon" style="width: 100%;">
                                <i class="fa-solid fa-paper-plane"></i> Kirim Permohonan Izin
                            </button>
                        </form>
                    </div>
                </div>
            </div>

            <!-- Bottom Section: Daftar Tugas & Deadline Hari Ini -->
            <div class="card">
                <div class="card-header">
                    <div class="card-title">
                        <i class="fa-solid fa-list-check"></i> Daftar Tugas & Deadline Hari Ini
                    </div>
                </div>
                <div class="table-responsive">
                    <table class="table" id="employeeTaskTable">
                        <thead>
                            <tr>
                                <th>Judul Tugas</th>
                                <th>Ditugaskan Kepada</th>
                                <th>Deskripsi Pekerjaan</th>
                                <th>Deadline</th>
                                <th>Status</th>
                            </tr>
                        </thead>
                        <tbody id="employeeTaskTableBody">
                            <tr>
                                <td colspan="5" style="text-align: center; color: var(--text-muted);">Memuat tugas...</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>

        </div>

        <!-- PORTAL ADMIN VIEW -->
        <div id="adminView" class="view-section">
            
            <div class="card" style="background: linear-gradient(135deg, var(--maroon-dark) 0%, var(--maroon-primary) 100%); color: white;">
                <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 1rem;">
                    <div>
                        <h2 style="font-family: 'Cinzel', serif; color: var(--gold-light);">Dashboard Administrasi HWL Law Firm</h2>
                        <p style="font-size: 0.88rem; opacity: 0.9;">Pengelolaan Presensi, Data Karyawan, Pengaturan Jam Kerja & Laporan</p>
                    </div>
                    <div style="display: flex; gap: 0.6rem;">
                        <button class="btn btn-gold" onclick="openAdminSettingsModal()">
                            <i class="fa-solid fa-gear"></i> Setting Jam Kerja & Akun Admin
                        </button>
                        <button class="btn btn-outline" onclick="logoutAdmin()">
                            <i class="fa-solid fa-right-from-bracket"></i> Keluar Portal
                        </button>
                    </div>
                </div>
            </div>

            <div class="grid-4" style="margin-bottom: 1.8rem;">
                <div class="stat-card">
                    <div class="stat-icon"><i class="fa-solid fa-users"></i></div>
                    <div>
                        <div class="stat-val" id="statTotalEmployees">0</div>
                        <div class="stat-lbl">Total Karyawan</div>
                    </div>
                </div>
                <div class="stat-card">
                    <div class="stat-icon" style="background: #27ae60;"><i class="fa-solid fa-user-check"></i></div>
                    <div>
                        <div class="stat-val" id="statHadirToday">0</div>
                        <div class="stat-lbl">Hadir Hari Ini</div>
                    </div>
                </div>
                <div class="stat-card">
                    <div class="stat-icon" style="background: #f39c12;"><i class="fa-solid fa-notes-medical"></i></div>
                    <div>
                        <div class="stat-val" id="statIzinToday">0</div>
                        <div class="stat-lbl">Izin / Sakit</div>
                    </div>
                </div>
                <div class="stat-card">
                    <div class="stat-icon" style="background: #2980b9;"><i class="fa-solid fa-tasks"></i></div>
                    <div>
                        <div class="stat-val" id="statPendingTasks">0</div>
                        <div class="stat-lbl">Tugas Active</div>
                    </div>
                </div>
            </div>

            <div style="display: flex; gap: 0.5rem; margin-bottom: 1.5rem; overflow-x: auto;">
                <button class="btn btn-gold admin-tab-btn active" onclick="switchAdminSubTab('rekapSubTab', this)">
                    <i class="fa-solid fa-table"></i> Rekap Laporan Absensi
                </button>
                <button class="btn btn-outline admin-tab-btn" onclick="switchAdminSubTab('karyawanSubTab', this)" style="color: var(--maroon-primary); border-color: var(--maroon-primary);">
                    <i class="fa-solid fa-user-plus"></i> Kelola Data Karyawan
                </button>
                <button class="btn btn-outline admin-tab-btn" onclick="switchAdminSubTab('tugasSubTab', this)" style="color: var(--maroon-primary); border-color: var(--maroon-primary);">
                    <i class="fa-solid fa-list-check"></i> Input Tugas & Deadline
                </button>
                <button class="btn btn-outline admin-tab-btn" onclick="switchAdminSubTab('izinSubTab', this)" style="color: var(--maroon-primary); border-color: var(--maroon-primary);">
                    <i class="fa-solid fa-envelope-open-text"></i> Verifikasi Izin & Sakit
                </button>
            </div>

            <!-- SUB TAB 1: REKAP ABSENSI -->
            <div id="rekapSubTab" class="admin-sub-tab">
                <div class="card">
                    <div class="card-header">
                        <div class="card-title">
                            <i class="fa-solid fa-clock-rotate-left"></i> Rekapitulasi Presensi Karyawan
                        </div>
                        <div style="display: flex; gap: 0.5rem;">
                            <button class="btn btn-gold btn-sm" onclick="exportToWordDoc()">
                                <i class="fa-solid fa-file-word"></i> Download Rekap (.doc / Word)
                            </button>
                        </div>
                    </div>

                    <div class="table-responsive">
                        <table class="table" id="rekapAttendanceTable">
                            <thead>
                                <tr>
                                    <th>Hari / Tanggal</th>
                                    <th>Waktu Precise</th>
                                    <th>NIP & Nama Karyawan</th>
                                    <th>Jabatan</th>
                                    <th>Agenda Kegiatan</th>
                                    <th>Lokasi GPS</th>
                                    <th>Status Shift</th>
                                    <th>Aksi</th>
                                </tr>
                            </thead>
                            <tbody id="rekapAttendanceTableBody">
                                <tr>
                                    <td colspan="8" style="text-align: center;">Memuat data absensi...</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>

            <!-- SUB TAB 2: KELOLA KARYAWAN -->
            <div id="karyawanSubTab" class="admin-sub-tab" style="display: none;">
                <div class="grid-2">
                    <div class="card">
                        <div class="card-header">
                            <div class="card-title"><i class="fa-solid fa-user-plus"></i> Tambah / Edit Karyawan</div>
                        </div>
                        <form id="addEmployeeForm" onsubmit="handleSaveEmployee(event)">
                            <input type="hidden" id="editEmpId">
                            <div class="form-group">
                                <label class="form-label">NIP / ID Karyawan</label>
                                <input type="text" class="form-control" id="empNip" placeholder="Contoh: HWL-2026-001" required>
                            </div>
                            <div class="form-group">
                                <label class="form-label">Nama Lengkap & Gelar</label>
                                <input type="text" class="form-control" id="empName" placeholder="Contoh: Budi Santoso, S.H., M.H." required>
                            </div>
                            <div class="form-group">
                                <label class="form-label">Jabatan</label>
                                <select class="form-control" id="empRole" required>
                                    <option value="Advokat Utama / Partner">Advokat Utama / Partner</option>
                                    <option value="Senior Associate">Senior Associate</option>
                                    <option value="Junior Associate">Junior Associate</option>
                                    <option value="Paralegal">Paralegal</option>
                                    <option value="Staff Administrasi & Keuangan">Staff Administrasi & Keuangan</option>
                                    <option value="IT & Operations">IT & Operations</option>
                                </select>
                            </div>
                            <button type="submit" class="btn btn-gold" style="width: 100%;">
                                <i class="fa-solid fa-floppy-disk"></i> Simpan Data Karyawan
                            </button>
                        </form>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <div class="card-title"><i class="fa-solid fa-users"></i> Daftar Karyawan Terdaftar</div>
                        </div>
                        <div class="table-responsive">
                            <table class="table">
                                <thead>
                                    <tr>
                                        <th>NIP</th>
                                        <th>Nama</th>
                                        <th>Jabatan</th>
                                        <th>Barcode/QR</th>
                                        <th>Aksi</th>
                                    </tr>
                                </thead>
                                <tbody id="employeeAdminTableBody">
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>

            <!-- SUB TAB 3: INPUT TUGAS & DEADLINE -->
            <div id="tugasSubTab" class="admin-sub-tab" style="display: none;">
                <div class="grid-2">
                    <div class="card">
                        <div class="card-header">
                            <div class="card-title"><i class="fa-solid fa-plus"></i> Tambah Tugas & Deadline Pekerjaan</div>
                        </div>
                        <form id="addTaskForm" onsubmit="handleAddTaskSubmit(event)">
                            <div class="form-group">
                                <label class="form-label">Judul Tugas / Pekerjaan Hukum</label>
                                <input type="text" class="form-control" id="taskTitle" placeholder="Contoh: Menyusun Eksepsi Perkara No. 1372/Pdt.G/2026" required>
                            </div>
                            <div class="form-group">
                                <label class="form-label">Tugaskan Kepada</label>
                                <select class="form-control" id="taskEmployeeSelect" required>
                                </select>
                            </div>
                            <div class="form-group">
                                <label class="form-label">Deadline Tanggal & Jam</label>
                                <input type="datetime-local" class="form-control" id="taskDeadline" required>
                            </div>
                            <div class="form-group">
                                <label class="form-label">Detail Instraksi Pekerjaan</label>
                                <textarea class="form-control" id="taskDesc" placeholder="Tuliskan rincian instruksi pekerjaan..." required></textarea>
                            </div>
                            <button type="submit" class="btn btn-gold" style="width: 100%;">
                                <i class="fa-solid fa-paper-plane"></i> Assign Tugas
                            </button>
                        </form>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <div class="card-title"><i class="fa-solid fa-tasks"></i> Master Daftar Tugas</div>
                        </div>
                        <div class="table-responsive">
                            <table class="table">
                                <thead>
                                    <tr>
                                        <th>Tugas</th>
                                        <th>Penerima</th>
                                        <th>Deadline</th>
                                        <th>Aksi</th>
                                    </tr>
                                </thead>
                                <tbody id="adminTaskTableBody">
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>

            <!-- SUB TAB 4: VERIFIKASI IZIN & SAKIT -->
            <div id="izinSubTab" class="admin-sub-tab" style="display: none;">
                <div class="card">
                    <div class="card-header">
                        <div class="card-title"><i class="fa-solid fa-envelope-open-text"></i> Permohonan Izin & Surat Keterangan Sakit</div>
                    </div>
                    <div class="table-responsive">
                        <table class="table">
                            <thead>
                                <tr>
                                    <th>Tanggal Request</th>
                                    <th>Nama Karyawan</th>
                                    <th>Jenis Izin</th>
                                    <th>Keterangan</th>
                                    <th>Lampiran Surat Sakit</th>
                                    <th>Status</th>
                                    <th>Aksi Konfirmasi</th>
                                </tr>
                            </thead>
                            <tbody id="adminLeaveTableBody">
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>

        </div>

        <!-- WALL BARCODE VIEW -->
        <div id="wallBarcodeView" class="view-section">
            <div class="card" style="text-align: center; max-width: 650px; margin: 0 auto;" id="printable-wall-qr">
                <div style="border: 4px double var(--gold-primary); padding: 2.5rem; border-radius: 12px; background: #FFFDF8;">
                    <div class="brand-logo" style="margin: 0 auto 1rem auto; width: 64px; height: 64px; font-size: 2rem;">
                        <i class="fa-solid fa-scale-balanced"></i>
                    </div>
                    <h1 style="font-family: 'Cinzel', serif; color: var(--maroon-primary); font-size: 1.8rem; margin-bottom: 0.3rem;">KANTOR HUKUM HWL LAW FIRM</h1>
                    <p style="color: var(--text-muted); font-size: 0.9rem; font-weight: 600; text-transform: uppercase; letter-spacing: 1px;">BARCODE PRESENSI RESMI KANTOR</p>
                    <hr style="border: 0; border-top: 2px solid var(--gold-primary); margin: 1.5rem 0;">

                    <div id="officeWallQRCode" style="display: inline-block; padding: 1.2rem; background: white; border: 2px solid var(--maroon-primary); border-radius: 10px;"></div>

                    <p style="margin-top: 1.5rem; font-size: 0.95rem; color: var(--maroon-dark); font-weight: 600;">
                        PETUNJUK: Tempelkan Barcode ini di Dinding Pintu Masuk Kantor.<br>Karyawan wajib melakukan scan melalui Aplikasi HP masing-masing saat tiba & pulang.
                    </p>
                    <div style="margin-top: 1.5rem;" class="no-print">
                        <button class="btn btn-gold" onclick="window.print()"><i class="fa-solid fa-print"></i> Cetak / Print Barcode Dinding</button>
                    </div>
                </div>
            </div>
        </div>

    </div>

    <!-- MODAL: GANTI FOTO PROFIL DENGAN KONFIRMASI NIP / ID -->
    <div class="modal" id="changePhotoModal">
        <div class="modal-content">
            <div class="modal-header">
                <div><i class="fa-solid fa-user-pen"></i> Konfirmasi Identitas & Ganti Foto Profil</div>
                <button class="close-btn" onclick="closeChangePhotoModal()">&times;</button>
            </div>
            <div class="modal-body">
                <div style="background: #FAF4E8; border-left: 4px solid var(--gold-primary); padding: 0.8rem; font-size: 0.82rem; margin-bottom: 1.2rem; color: var(--maroon-dark);">
                    <strong>Keamanan Akun:</strong><br>Masukkan NIP/ID Karyawan dan Nama sesuai data Anda untuk mengunggah foto dari galeri.
                </div>
                <form id="changePhotoForm" onsubmit="handleConfirmAndChangePhoto(event)">
                    <div class="form-group">
                        <label class="form-label">Pilih Karyawan</label>
                        <select class="form-control" id="modalPhotoEmpSelect" required>
                            <option value="">-- Pilih Nama Karyawan --</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label class="form-label">Konfirmasi NIP / ID Karyawan</label>
                        <input type="text" class="form-control" id="modalPhotoNip" placeholder="Contoh: HWL-2026-001 atau EMP-01" required>
                    </div>
                    <div class="form-group">
                        <label class="form-label">Pilih Foto dari Galeri Perangkat</label>
                        <input type="file" class="form-control" id="modalPhotoFile" accept="image/*" required onchange="previewSelectedGalleryPhoto(event)">
                        <img id="modalPhotoPreview" style="width: 100px; height: 100px; border-radius: 50%; object-fit: cover; display: none; margin: 1rem auto 0 auto; border: 3px solid var(--gold-primary);">
                    </div>
                    <div style="margin-top: 1.5rem;">
                        <button type="submit" class="btn btn-gold" style="width: 100%; padding: 0.85rem; font-size: 1rem;">
                            <i class="fa-solid fa-upload"></i> Verifikasi & Simpan Foto Profil
                        </button>
                    </div>
                </form>
            </div>
        </div>
    </div>

    <!-- MODAL: LOGIN ADMIN -->
    <div class="modal" id="adminLoginModal">
        <div class="modal-content">
            <div class="modal-header">
                <div><i class="fa-solid fa-lock"></i> Login Admin HWL Law Firm</div>
                <button class="close-btn" onclick="closeAdminLoginModal()">&times;</button>
            </div>
            <div class="modal-body">
                <div style="background: #FAF4E8; border-left: 4px solid var(--gold-primary); padding: 0.8rem; font-size: 0.82rem; margin-bottom: 1.2rem; color: var(--maroon-dark);" id="adminLoginInfoBox">
                    <strong>Status Akses Admin:</strong><br>
                    <span id="adminLoginInfoText">Default login terisi otomatis. Silakan klik tombol Log In.</span>
                </div>
                <form id="adminLoginForm" onsubmit="handleAdminLogin(event)">
                    <div class="form-group">
                        <label class="form-label">Gmail / Email Admin</label>
                        <input type="email" class="form-control" id="inputAdminEmail" required placeholder="Masukkan Gmail Admin">
                    </div>
                    <div class="form-group">
                        <label class="form-label">Password</label>
                        <input type="password" class="form-control" id="inputAdminPass" required placeholder="Masukkan Password Admin">
                    </div>
                    
                    <div style="margin-top: 1.5rem;">
                        <button type="submit" class="btn btn-maroon" style="width: 100%; padding: 0.85rem; font-size: 1rem;">
                            <i class="fa-solid fa-right-to-bracket"></i> LOG IN
                        </button>
                    </div>
                </form>
            </div>
        </div>
    </div>

    <!-- MODAL: ADMIN SETTINGS -->
    <div class="modal" id="adminSettingsModal">
        <div class="modal-content">
            <div class="modal-header">
                <div><i class="fa-solid fa-sliders"></i> Pengaturan Jam Kerja & Kredensial Admin</div>
                <button class="close-btn" onclick="closeAdminSettingsModal()">&times;</button>
            </div>
            <div class="modal-body">
                <h4 style="color: var(--maroon-primary); margin-bottom: 0.8rem; font-family: 'Cinzel', serif;">1. Jam Kerja Presensi</h4>
                <div class="form-group">
                    <label class="form-label">Jam Masuk Kantor</label>
                    <input type="time" class="form-control" id="settingJamMasuk" value="08:00">
                </div>
                <div class="form-group">
                    <label class="form-label">Jam Pulang Kantor</label>
                    <input type="time" class="form-control" id="settingJamPulang" value="17:00">
                </div>
                <div class="form-group">
                    <label class="form-label">Toleransi Keterlambatan (Menit)</label>
                    <input type="number" class="form-control" id="settingToleransi" value="15">
                </div>

                <hr style="margin: 1.5rem 0; border: 0; border-top: 1px solid var(--border-color);">

                <h4 style="color: var(--maroon-primary); margin-bottom: 0.8rem; font-family: 'Cinzel', serif;">2. Ganti Admin / Kredensial Login</h4>
                <div style="font-size: 0.8rem; color: var(--text-muted); margin-bottom: 0.8rem;">
                    *Verifikasi Email & Password Admin Lama Diperlukan Sebelum Mengganti Admin Baru.
                </div>
                <div class="form-group">
                    <label class="form-label">Password Lama Admin (Verifikasi)</label>
                    <input type="password" class="form-control" id="verifyOldPass" placeholder="Masukkan password saat ini">
                </div>
                <div class="form-group">
                    <label class="form-label">Gmail Admin Baru</label>
                    <input type="email" class="form-control" id="newAdminEmail" placeholder="email.baru@hwllawfirm.com">
                </div>
                <div class="form-group">
                    <label class="form-label">Password Admin Baru</label>
                    <input type="password" class="form-control" id="newAdminPass" placeholder="Password baru">
                </div>
            </div>
            <div class="modal-footer">
                <button class="btn btn-secondary" onclick="closeAdminSettingsModal()">Batal</button>
                <button class="btn btn-gold" onclick="saveAdminSettings()"><i class="fa-solid fa-save"></i> Simpan Semua Pengaturan</button>
            </div>
        </div>
    </div>

    <!-- MODAL: PREVIEW FOTO SURAT SAKIT -->
    <div class="modal" id="imagePreviewModal">
        <div class="modal-content" style="max-width: 600px;">
            <div class="modal-header">
                <div><i class="fa-solid fa-file-medical"></i> Lampiran Surat Keterangan Sakit / Bukti</div>
                <button class="close-btn" onclick="closeImageModal()">&times;</button>
            </div>
            <div class="modal-body" style="text-align: center;">
                <img id="fullImagePreview" style="max-width: 100%; height: auto; border-radius: 8px; border: 2px solid var(--gold-primary);">
            </div>
        </div>
    </div>

    <!-- FOOTER -->
    <footer>
        &copy; 2026 Kantor Hukum HWL Law Firm & Partners. All Rights Reserved. | Real-Time Attendance Engine
    </footer>

    <!-- SCRIPT APPLICATION CODE -->
    <script>
        const DB_BASE_URL = "https://absen-hwl-law-firm-default-rtdb.asia-southeast1.firebasedatabase.app";
        
        let state = {
            adminLoggedIn: false,
            isBarcodeScanned: false,
            settings: {
                adminEmail: "admin@hwllawfirm.com",
                adminPass: "admin123",
                jamMasuk: "08:00",
                jamPulang: "17:00",
                toleransi: 15
            },
            employees: [],
            attendance: [],
            tasks: [],
            leaves: [],
            currentGPS: { lat: null, lng: null, address: "Jl. Perumahan Banuaran Indah No.09 Blok Q, RT.001/RW.012, Banuaran Nan XX, Kec. Lubuk Begalung, Kota Padang, Sumatera Barat 25222" },
            scannerStream: null
        };

        let deferredPrompt;
        let tempGalleryPhotoBase64 = "";

        // Register Service Worker for PWA (Installable App)
        if ('serviceWorker' in navigator) {
            window.addEventListener('load', () => {
                const swCode = `
                    self.addEventListener('install', e => self.skipWaiting());
                    self.addEventListener('activate', e => self.clients.claim());
                    self.addEventListener('fetch', e => e.respondWith(fetch(e.request)));
                `;
                const blob = new Blob([swCode], { type: 'application/javascript' });
                navigator.serviceWorker.register(URL.createObjectURL(blob))
                    .catch(err => console.log('SW Reg Failed:', err));
            });
        }

        window.addEventListener('beforeinstallprompt', (e) => {
            e.preventDefault();
            deferredPrompt = e;
            const btnInstall = document.getElementById('btnInstallPwa');
            if(btnInstall) btnInstall.style.display = 'inline-flex';
        });

        function installPWA() {
            if (deferredPrompt) {
                deferredPrompt.prompt();
                deferredPrompt.userChoice.then((choiceResult) => {
                    if (choiceResult.outcome === 'accepted') {
                        document.getElementById('btnInstallPwa').style.display = 'none';
                    }
                    deferredPrompt = null;
                });
            }
        }

        window.addEventListener('DOMContentLoaded', () => {
            initClock();
            initOfficeWallQR();
            syncDataFromFirebase();
            
            const display = document.getElementById('gpsDisplay');
            if(display) display.value = state.currentGPS.address;

            fetchGPSLocation(false);

            setInterval(syncDataFromFirebase, 5000);
        });

        function initClock() {
            setInterval(() => {
                const now = new Date();
                const hours = String(now.getHours()).padStart(2, '0');
                const minutes = String(now.getMinutes()).padStart(2, '0');
                const seconds = String(now.getSeconds()).padStart(2, '0');
                
                const clockElem = document.getElementById('liveClockDisplay');
                if(clockElem) clockElem.innerText = `${hours}:${minutes}:${seconds}`;

                const days = ['Minggu', 'Senin', 'Selasa', 'Rabu', 'Kamis', 'Jumat', 'Sabtu'];
                const months = ['Januari', 'Februari', 'Maret', 'April', 'Mei', 'Juni', 'Juli', 'Agustus', 'September', 'Oktober', 'November', 'Desember'];
                
                const dayName = days[now.getDay()];
                const dateNum = now.getDate();
                const monthName = months[now.getMonth()];
                const yearNum = now.getFullYear();

                const dateElem = document.getElementById('liveDateDisplay');
                if(dateElem) dateElem.innerText = `${dayName}, ${dateNum} ${monthName} ${yearNum}`;
            }, 1000);
        }

        function initOfficeWallQR() {
            const wallQrDiv = document.getElementById('officeWallQRCode');
            if(wallQrDiv) {
                wallQrDiv.innerHTML = "";
                new QRCode(wallQrDiv, {
                    text: "HWL_LAW_FIRM_OFFICE_OFFICIAL_QR_2026",
                    width: 200,
                    height: 200,
                    colorDark : "#6B0D18",
                    colorLight : "#ffffff",
                    correctLevel : QRCode.CorrectLevel.H
                });
            }
        }

        async function syncDataFromFirebase() {
            try {
                const resSettings = await fetch(`${DB_BASE_URL}/settings.json`);
                if(resSettings.ok) {
                    const settingsData = await resSettings.json();
                    if(settingsData) state.settings = { ...state.settings, ...settingsData };
                }

                const resEmp = await fetch(`${DB_BASE_URL}/karyawan.json`);
                if(resEmp.ok) {
                    const empData = await resEmp.json();
                    state.employees = empData ? Object.values(empData) : getSeedEmployees();
                    if(!empData) await saveDataToFirebase('karyawan', state.employees);
                    renderEmployeeDropdowns();
                    renderEmployeeAdminTable();
                    onEmployeeSelectChange(); // Perbarui profil jika sedang dipilih
                }

                const resAtt = await fetch(`${DB_BASE_URL}/absensi.json`);
                if(resAtt.ok) {
                    const attData = await resAtt.json();
                    state.attendance = attData ? Object.values(attData) : [];
                    renderAttendanceRekapTable();
                }

                const resTasks = await fetch(`${DB_BASE_URL}/tugas_deadline.json`);
                if(resTasks.ok) {
                    const taskData = await resTasks.json();
                    state.tasks = taskData ? Object.values(taskData) : [];
                    renderTasksTables();
                }

                const resLeaves = await fetch(`${DB_BASE_URL}/perizinan.json`);
                if(resLeaves.ok) {
                    const leaveData = await resLeaves.json();
                    state.leaves = leaveData ? Object.values(leaveData) : [];
                    renderLeavesTable();
                }

                updateStatsCount();
                document.getElementById('syncStatus').style.background = 'rgba(46, 204, 113, 0.2)';
            } catch (err) {
                console.warn('Firebase Sync Notice:', err);
            }
        }

        async function saveDataToFirebase(endpoint, data) {
            try {
                await fetch(`${DB_BASE_URL}/${endpoint}.json`, {
                    method: 'PUT',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(data)
                });
            } catch(e) {
                console.error("Firebase save failed:", e);
            }
        }

        function getSeedEmployees() {
            return [
                { id: "EMP-01", nip: "HWL-2026-001", nama: "Bambang HWL, S.H., M.H.", jabatan: "Advokat Utama / Partner", foto: "" },
                { id: "EMP-02", nip: "HWL-2026-002", nama: "Siti Rahmawati, S.H.", jabatan: "Senior Associate", foto: "" },
                { id: "EMP-03", nip: "HWL-2026-003", nama: "Andi Wijaya, S.H.", jabatan: "Paralegal", foto: "" }
            ];
        }

        function switchView(viewId) {
            document.querySelectorAll('.view-section').forEach(el => el.classList.remove('active'));
            document.getElementById(viewId).classList.add('active');
            if(viewId !== 'karyawanView') stopCameraScan();
        }

        function switchAdminSubTab(tabId, btnElem) {
            document.querySelectorAll('.admin-sub-tab').forEach(el => el.style.display = 'none');
            document.getElementById(tabId).style.display = 'block';

            document.querySelectorAll('.admin-tab-btn').forEach(btn => {
                btn.classList.remove('btn-gold');
                btn.classList.add('btn-outline');
                btn.style.color = 'var(--maroon-primary)';
                btn.style.borderColor = 'var(--maroon-primary)';
            });

            btnElem.classList.remove('btn-outline');
            btnElem.classList.add('btn-gold');
            btnElem.style.color = 'var(--maroon-dark)';
        }

        function openAdminLoginModal() {
            if(state.adminLoggedIn) {
                switchView('adminView');
            } else {
                const emailInput = document.getElementById('inputAdminEmail');
                const passInput = document.getElementById('inputAdminPass');
                const infoText = document.getElementById('adminLoginInfoText');

                if(state.settings.adminEmail === "admin@hwllawfirm.com" && state.settings.adminPass === "admin123") {
                    emailInput.value = state.settings.adminEmail;
                    passInput.value = state.settings.adminPass;
                    if(infoText) infoText.innerText = "Kredensial Default terisi otomatis. Cukup klik tombol LOG IN untuk masuk.";
                } else {
                    emailInput.value = "";
                    passInput.value = "";
                    if(infoText) infoText.innerText = "Kredensial telah diperbarui. Silakan masukkan Gmail & Password baru Anda secara manual.";
                }

                document.getElementById('adminLoginModal').classList.add('active');
            }
        }

        function closeAdminLoginModal() {
            document.getElementById('adminLoginModal').classList.remove('active');
        }

        function handleAdminLogin(e) {
            e.preventDefault();
            const email = document.getElementById('inputAdminEmail').value;
            const pass = document.getElementById('inputAdminPass').value;

            if(email === state.settings.adminEmail && pass === state.settings.adminPass) {
                state.adminLoggedIn = true;
                closeAdminLoginModal();
                switchView('adminView');
            } else {
                alert('Gmail atau Password Admin Salah!');
            }
        }

        function logoutAdmin() {
            state.adminLoggedIn = false;
            switchView('karyawanView');
            alert('Admin telah keluar.');
        }

        function openAdminSettingsModal() {
            document.getElementById('settingJamMasuk').value = state.settings.jamMasuk;
            document.getElementById('settingJamPulang').value = state.settings.jamPulang;
            document.getElementById('settingToleransi').value = state.settings.toleransi;
            document.getElementById('adminSettingsModal').classList.add('active');
        }

        function closeAdminSettingsModal() {
            document.getElementById('adminSettingsModal').classList.remove('active');
        }

        async function saveAdminSettings() {
            const oldPass = document.getElementById('verifyOldPass').value;
            const newEmail = document.getElementById('newAdminEmail').value;
            const newPass = document.getElementById('newAdminPass').value;

            if(newEmail || newPass) {
                if(oldPass !== state.settings.adminPass) {
                    alert('Verifikasi Password Lama Gagal! Password lama salah.');
                    return;
                }
                if(newEmail) state.settings.adminEmail = newEmail;
                if(newPass) state.settings.adminPass = newPass;
            }

            state.settings.jamMasuk = document.getElementById('settingJamMasuk').value;
            state.settings.jamPulang = document.getElementById('settingJamPulang').value;
            state.settings.toleransi = parseInt(document.getElementById('settingToleransi').value) || 15;

            await saveDataToFirebase('settings', state.settings);
            alert('Pengaturan & Kredensial Berhasil Disimpan!');
            closeAdminSettingsModal();
            syncDataFromFirebase();
        }

        function fetchGPSLocation(showAlerts = true) {
            const display = document.getElementById('gpsDisplay');
            if(display && showAlerts) display.value = "Memperbarui lokasi real-time...";

            if (navigator.geolocation) {
                const options = {
                    enableHighAccuracy: true,
                    timeout: 8000,
                    maximumAge: 30000
                };

                navigator.geolocation.getCurrentPosition(
                    (pos) => {
                        const lat = pos.coords.latitude.toFixed(6);
                        const lng = pos.coords.longitude.toFixed(6);
                        const acc = pos.coords.accuracy ? Math.round(pos.coords.accuracy) : null;
                        const accText = acc ? ` (±${acc}m)` : '';
                        
                        const fixedAddress = `Jl. Perumahan Banuaran Indah No.09 Blok Q, RT.001/RW.012, Banuaran Nan XX, Kec. Lubuk Begalung, Kota Padang, Sumatera Barat 25222 [Lat: ${lat}, Lng: ${lng}${accText}]`;
                        state.currentGPS = { lat, lng, address: fixedAddress };
                        if(display) display.value = fixedAddress;
                    },
                    (err) => {
                        const fallbackAddress = "Jl. Perumahan Banuaran Indah No.09 Blok Q, RT.001/RW.012, Banuaran Nan XX, Kec. Lubuk Begalung, Kota Padang, Sumatera Barat 25222";
                        state.currentGPS = { lat: "-0.975", lng: "100.375", address: fallbackAddress };
                        if(display) display.value = fallbackAddress;
                        if(showAlerts) alert('Menggunakan lokasi kantor pusat terdaftar.');
                    },
                    options
                );
            } else {
                const defaultAddress = "Jl. Perumahan Banuaran Indah No.09 Blok Q, RT.001/RW.012, Banuaran Nan XX, Kec. Lubuk Begalung, Kota Padang, Sumatera Barat 25222";
                state.currentGPS = { lat: "-0.975", lng: "100.375", address: defaultAddress };
                if(display) display.value = defaultAddress;
            }
        }

        function startCameraScan() {
            const scannerContainer = document.getElementById('interactive-scanner');
            const video = document.getElementById('scanner-video');
            scannerContainer.style.display = 'block';

            navigator.mediaDevices.getUserMedia({ video: { facingMode: "environment" } })
            .then((stream) => {
                state.scannerStream = stream;
                video.srcObject = stream;
                video.setAttribute("playsinline", true);
                video.play();
                requestAnimationFrame(scanQRCodeTick);
            })
            .catch((err) => {
                alert("Kamera tidak dapat diakses atau diizinkan: " + err);
                scannerContainer.style.display = 'none';
            });
        }

        function unlockAttendanceForm() {
            state.isBarcodeScanned = true;
            
            document.getElementById('employeeSelect').disabled = false;
            document.getElementById('agendaInput').disabled = false;
            document.getElementById('btnRefreshGps').disabled = false;
            document.getElementById('btnSubmitAttendance').disabled = false;

            const noticeBox = document.getElementById('scanLockNotice');
            noticeBox.className = "status-box unlocked";
            noticeBox.innerHTML = '<i class="fa-solid fa-lock-open"></i> <span>Barcode Terverifikasi! Form Absensi & Agenda Terbuka.</span>';

            fetchGPSLocation(false);
        }

        function lockAttendanceForm() {
            state.isBarcodeScanned = false;
            
            document.getElementById('employeeSelect').disabled = true;
            document.getElementById('agendaInput').disabled = true;
            document.getElementById('btnRefreshGps').disabled = true;
            document.getElementById('btnSubmitAttendance').disabled = true;

            const noticeBox = document.getElementById('scanLockNotice');
            noticeBox.className = "status-box locked";
            noticeBox.innerHTML = '<i class="fa-solid fa-lock"></i> <span>Scan Barcode Kantor / ID Anda terlebih dahulu untuk membuka form presensi!</span>';
        }

        function scanQRCodeTick() {
            const video = document.getElementById('scanner-video');
            if (video && video.readyState === video.HAVE_ENOUGH_DATA) {
                const canvas = document.createElement("canvas");
                canvas.width = video.videoWidth;
                canvas.height = video.videoHeight;
                const ctx = canvas.getContext("2d");
                ctx.drawImage(video, 0, 0, canvas.width, canvas.height);
                const imageData = ctx.getImageData(0, 0, canvas.width, canvas.height);
                const code = jsQR(imageData.data, imageData.width, imageData.height);

                if (code) {
                    stopCameraScan();
                    
                    if(code.data.startsWith("EMP-")) {
                        unlockAttendanceForm();
                        const empSelect = document.getElementById('employeeSelect');
                        empSelect.value = code.data;
                        onEmployeeSelectChange();
                        alert("Barcode ID Karyawan Berhasil Dideteksi! Form Absensi Telah Terbuka.");
                    } else if(code.data === "HWL_LAW_FIRM_OFFICE_OFFICIAL_QR_2026") {
                        unlockAttendanceForm();
                        alert("Barcode Kantor Resmi Terverifikasi! Form Absensi Telah Terbuka.");
                    } else {
                        alert("Barcode tidak dikenali! Silakan scan Barcode Resmi HWL Law Firm.");
                    }
                    return;
                }
            }
            if(state.scannerStream) {
                requestAnimationFrame(scanQRCodeTick);
            }
        }

        function stopCameraScan() {
            if(state.scannerStream) {
                state.scannerStream.getTracks().forEach(track => track.stop());
                state.scannerStream = null;
            }
            document.getElementById('interactive-scanner').style.display = 'none';
        }

        function renderEmployeeDropdowns() {
            const select1 = document.getElementById('employeeSelect');
            const select2 = document.getElementById('leaveEmployeeSelect');
            const select3 = document.getElementById('taskEmployeeSelect');
            const select4 = document.getElementById('modalPhotoEmpSelect');

            const val1 = select1 ? select1.value : "";
            const val2 = select2 ? select2.value : "";
            const val3 = select3 ? select3.value : "";
            const val4 = select4 ? select4.value : "";

            let html = '<option value="">-- Pilih Karyawan --</option>';
            state.employees.forEach(emp => {
                html += `<option value="${emp.id}">${emp.nip} - ${emp.nama}</option>`;
            });

            if(select1) { select1.innerHTML = html; select1.value = val1; }
            if(select2) { select2.innerHTML = html; select2.value = val2; }
            if(select3) { select3.innerHTML = html; select3.value = val3; }
            if(select4) { select4.innerHTML = html; select4.value = val4; }
        }

        function onEmployeeSelectChange() {
            const empId = document.getElementById('employeeSelect').value;
            const emp = state.employees.find(e => e.id === empId);

            const nameEl = document.getElementById('employeeProfileName');
            const roleEl = document.getElementById('employeeProfileRole');
            const picEl = document.getElementById('employeeProfilePic');
            const qrDiv = document.getElementById('employeePersonalQR');

            if(emp) {
                nameEl.innerText = emp.nama;
                roleEl.innerText = `${emp.nip} | ${emp.jabatan}`;
                picEl.src = emp.foto && emp.foto.trim() !== "" ? emp.foto : `https://via.placeholder.com/110/6B0D18/FFFFFF?text=${encodeURIComponent(emp.nama.charAt(0))}`;
                
                qrDiv.innerHTML = "";
                new QRCode(qrDiv, {
                    text: emp.id,
                    width: 100,
                    height: 100
                });
            } else {
                nameEl.innerText = "Pilih Karyawan";
                roleEl.innerText = "-";
                picEl.src = "https://via.placeholder.com/110?text=Foto";
                qrDiv.innerHTML = "";
            }
        }

        // FUNGSI GANTI FOTO PROFIL DARI GALERI DENGAN KONFIRMASI NIP / ID
        function openChangePhotoModal() {
            tempGalleryPhotoBase64 = "";
            document.getElementById('changePhotoForm').reset();
            document.getElementById('modalPhotoPreview').style.display = 'none';
            document.getElementById('changePhotoModal').classList.add('active');
        }

        function closeChangePhotoModal() {
            document.getElementById('changePhotoModal').classList.remove('active');
        }

        function previewSelectedGalleryPhoto(e) {
            const file = e.target.files[0];
            if(file) {
                const reader = new FileReader();
                reader.onload = function(evt) {
                    tempGalleryPhotoBase64 = evt.target.result;
                    const preview = document.getElementById('modalPhotoPreview');
                    preview.src = tempGalleryPhotoBase64;
                    preview.style.display = 'block';
                };
                reader.readAsDataURL(file);
            }
        }

        async function handleConfirmAndChangePhoto(e) {
            e.preventDefault();
            const empId = document.getElementById('modalPhotoEmpSelect').value;
            const inputNip = document.getElementById('modalPhotoNip').value.trim();

            const emp = state.employees.find(e => e.id === empId);
            if(!emp) {
                alert('Pilih karyawan terlebih dahulu!');
                return;
            }

            // Validasi kecocokan NIP atau ID Karyawan
            if(inputNip !== emp.nip && inputNip !== emp.id) {
                alert('Konfirmasi Gagal! NIP atau ID Karyawan yang Anda masukkan tidak cocok dengan data karyawan yang dipilih.');
                return;
            }

            if(!tempGalleryPhotoBase64) {
                alert('Silakan pilih foto dari galeri terlebih dahulu!');
                return;
            }

            const empIdx = state.employees.findIndex(e => e.id === empId);
            if(empIdx !== -1) {
                state.employees[empIdx].foto = tempGalleryPhotoBase64;
                await saveDataToFirebase('karyawan', state.employees);
                
                alert(`Verifikasi Berhasil!\nFoto Profil untuk ${emp.nama} (${emp.nip}) berhasil diperbarui.`);
                closeChangePhotoModal();
                syncDataFromFirebase();

                // Sinkronkan tampilan jika sedang dipilih di portal utama
                const mainSelect = document.getElementById('employeeSelect');
                if(mainSelect && mainSelect.value === empId) {
                    onEmployeeSelectChange();
                }
            }
        }

        function renderEmployeeAdminTable() {
            const tbody = document.getElementById('employeeAdminTableBody');
            if(!tbody) return;

            let html = '';
            state.employees.forEach(emp => {
                const fotoSrc = emp.foto && emp.foto.trim() !== "" ? emp.foto : `https://via.placeholder.com/40/6B0D18/FFFFFF?text=${encodeURIComponent(emp.nama.charAt(0))}`;
                html += `
                    <tr>
                        <td><strong>${emp.nip}</strong></td>
                        <td>
                            <img src="${fotoSrc}" class="table-profile-img">
                            <strong>${emp.nama}</strong>
                        </td>
                        <td>${emp.jabatan}</td>
                        <td><span class="badge badge-info">${emp.id}</span></td>
                        <td>
                            <button class="btn btn-danger btn-sm" onclick="deleteEmployee('${emp.id}')"><i class="fa-solid fa-trash"></i></button>
                        </td>
                    </tr>
                `;
            });
            tbody.innerHTML = html || '<tr><td colspan="5" style="text-align:center;">Belum ada karyawan.</td></tr>';
        }

        async function handleSaveEmployee(e) {
            e.preventDefault();
            const nip = document.getElementById('empNip').value;
            const nama = document.getElementById('empName').value;
            const jabatan = document.getElementById('empRole').value;

            const newEmp = {
                id: "EMP-" + Date.now().toString().slice(-4),
                nip,
                nama,
                jabatan,
                foto: ""
            };

            state.employees.push(newEmp);
            await saveDataToFirebase('karyawan', state.employees);
            alert('Karyawan Berhasil Ditambahkan!');
            document.getElementById('addEmployeeForm').reset();
            syncDataFromFirebase();
        }

        async function deleteEmployee(id) {
            if(confirm('Apakah Anda yakin ingin menghapus karyawan ini?')) {
                state.employees = state.employees.filter(e => e.id !== id);
                await saveDataToFirebase('karyawan', state.employees);
                syncDataFromFirebase();
            }
        }

        async function handleAttendanceSubmit(e) {
            e.preventDefault();

            if(!state.isBarcodeScanned) {
                alert('Anda Wajib Scan Barcode terlebih dahulu sebelum mengirimkan presensi!');
                return;
            }

            const empId = document.getElementById('employeeSelect').value;
            const agenda = document.getElementById('agendaInput').value;

            if(!empId) {
                alert('Pilih Karyawan!');
                return;
            }

            const emp = state.employees.find(e => e.id === empId);
            const now = new Date();

            const days = ['Minggu', 'Senin', 'Selasa', 'Rabu', 'Kamis', 'Jumat', 'Sabtu'];
            const months = ['Januari', 'Februari', 'Maret', 'April', 'Mei', 'Juni', 'Juli', 'Agustus', 'September', 'Oktober', 'November', 'Desember'];

            const jamStr = String(now.getHours()).padStart(2, '0');
            const mntStr = String(now.getMinutes()).padStart(2, '0');
            const dtkStr = String(now.getSeconds()).padStart(2, '0');

            const timestampFormatted = `${jamStr}:${mntStr}:${dtkStr}`;
            const tanggalFormatted = `${now.getDate()} ${months[now.getMonth()]} ${now.getFullYear()}`;
            const hariFormatted = days[now.getDay()];

            const jamMasukSplit = state.settings.jamMasuk.split(':');
            const targetMin = parseInt(jamMasukSplit[0]) * 60 + parseInt(jamMasukSplit[1]) + state.settings.toleransi;
            const currentMin = now.getHours() * 60 + now.getMinutes();

            const statusShift = (currentMin <= targetMin) ? "Tepat Waktu" : "Terlambat";

            const newAtt = {
                id: "ATT-" + Date.now(),
                empId: emp.id,
                nip: emp.nip,
                nama: emp.nama,
                jabatan: emp.jabatan,
                foto: emp.foto || "",
                detik: dtkStr,
                menit: mntStr,
                jam: jamStr,
                waktuPresisi: timestampFormatted,
                hari: hariFormatted,
                tanggal: tanggalFormatted,
                agenda,
                gps: state.currentGPS.address,
                statusShift
            };

            state.attendance.unshift(newAtt);
            await saveDataToFirebase('absensi', state.attendance);

            alert(`PRESENSI BERHASIL!\n\nWaktu: ${hariFormatted}, ${tanggalFormatted} - ${timestampFormatted}\nLokasi GPS: ${state.currentGPS.address}\nStatus: ${statusShift}`);

            document.getElementById('attendanceForm').reset();
            onEmployeeSelectChange();
            lockAttendanceForm();
            syncDataFromFirebase();
        }

        function renderAttendanceRekapTable() {
            const tbody = document.getElementById('rekapAttendanceTableBody');
            if(!tbody) return;

            let html = '';
            state.attendance.forEach(att => {
                // Ambil foto dari data absensi atau sinkronkan dengan data master karyawan terbaru
                const currentEmp = state.employees.find(e => e.id === att.empId);
                const activeFoto = (currentEmp && currentEmp.foto && currentEmp.foto.trim() !== "") ? currentEmp.foto : (att.foto || "");
                const fotoSrc = activeFoto ? activeFoto : `https://via.placeholder.com/40/6B0D18/FFFFFF?text=${encodeURIComponent(att.nama.charAt(0))}`;
                
                const badgeClass = att.statusShift === "Tepat Waktu" ? "badge-success" : "badge-warning";
                html += `
                    <tr>
                        <td><strong>${att.hari}</strong><br><small>${att.tanggal}</small></td>
                        <td><span style="font-family: monospace; font-weight: bold; color: var(--maroon-primary);">${att.waktuPresisi}</span></td>
                        <td>
                            <img src="${fotoSrc}" class="table-profile-img">
                            <strong>${att.nama}</strong><br><small>${att.nip} (${att.empId || '-'})</small>
                        </td>
                        <td>${att.jabatan}</td>
                        <td>${att.agenda}</td>
                        <td><small>${att.gps}</small></td>
                        <td><span class="badge ${badgeClass}">${att.statusShift}</span></td>
                        <td>
                            <button class="btn btn-danger btn-sm" onclick="deleteAttendance('${att.id}')"><i class="fa-solid fa-trash"></i></button>
                        </td>
                    </tr>
                `;
            });

            tbody.innerHTML = html || '<tr><td colspan="8" style="text-align:center;">Belum ada data presensi.</td></tr>';
        }

        async function deleteAttendance(id) {
            if(confirm('Hapus log presensi ini?')) {
                state.attendance = state.attendance.filter(a => a.id !== id);
                await saveDataToFirebase('absensi', state.attendance);
                syncDataFromFirebase();
            }
        }

        function exportToWordDoc() {
            let tableHTML = `
                <html xmlns:o='urn:schemas-microsoft-com:office:office' xmlns:w='urn:schemas-microsoft-com:office:word' xmlns='http://www.w3.org/TR/REC-html40'>
                <head>
                    <title>Rekap Absensi Karyawan HWL Law Firm</title>
                    <style>
                        body { font-family: Arial, sans-serif; }
                        h2 { color: #6B0D18; text-align: center; }
                        table { width: 100%; border-collapse: collapse; margin-top: 20px; }
                        th { background-color: #6B0D18; color: #ffffff; border: 1px solid #000; padding: 8px; text-align: left; }
                        td { border: 1px solid #000; padding: 8px; text-align: left; }
                    </style>
                </head>
                <body>
                    <h2>KANTOR HUKUM HWL LAW FIRM</h2>
                    <h3 style="text-align: center;">LAPORAN REKAPITULASI PRESENSI KARYAWAN</h3>
                    <p style="text-align: center;">Tanggal Cetak: ${new Date().toLocaleDateString('id-ID')}</p>
                    <hr>
                    <table>
                        <thead>
                            <tr>
                                <th>Hari / Tanggal</th>
                                <th>Waktu Precise</th>
                                <th>NIP</th>
                                <th>Nama Karyawan</th>
                                <th>Jabatan</th>
                                <th>Agenda Kegiatan</th>
                                <th>Lokasi GPS</th>
                                <th>Status</th>
                            </tr>
                        </thead>
                        <tbody>
            `;

            state.attendance.forEach(att => {
                tableHTML += `
                    <tr>
                        <td>${att.hari}, ${att.tanggal}</td>
                        <td>${att.waktuPresisi}</td>
                        <td>${att.nip}</td>
                        <td>${att.nama}</td>
                        <td>${att.jabatan}</td>
                        <td>${att.agenda}</td>
                        <td>${att.gps}</td>
                        <td>${att.statusShift}</td>
                    </tr>
                `;
            });

            tableHTML += `
                        </tbody>
                    </table>
                </body>
                </html>
            `;

            const blob = new Blob(['\ufeff' + tableHTML], { type: 'application/msword' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = `Laporan_Absensi_HWL_Law_Firm_${Date.now()}.doc`;
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
        }

        async function handleAddTaskSubmit(e) {
            e.preventDefault();
            const judul = document.getElementById('taskTitle').value;
            const empId = document.getElementById('taskEmployeeSelect').value;
            const deadline = document.getElementById('taskDeadline').value;
            const deskripsi = document.getElementById('taskDesc').value;

            const emp = state.employees.find(e => e.id === empId);

            const newTask = {
                id: "TSK-" + Date.now(),
                judul,
                empId,
                namaEmp: emp ? emp.nama : "-",
                deadline,
                deskripsi,
                status: "Pending"
            };

            state.tasks.push(newTask);
            await saveDataToFirebase('tugas_deadline', state.tasks);
            alert('Tugas Berhasil Ditugaskan!');
            document.getElementById('addTaskForm').reset();
            syncDataFromFirebase();
        }

        function renderTasksTables() {
            const empTbody = document.getElementById('employeeTaskTableBody');
            if(empTbody) {
                let html = '';
                state.tasks.forEach(t => {
                    html += `
                        <tr>
                            <td><strong>${t.judul}</strong></td>
                            <td>${t.namaEmp}</td>
                            <td>${t.deskripsi}</td>
                            <td><span style="color: #c0392b; font-weight: bold;">${new Date(t.deadline).toLocaleString('id-ID')}</span></td>
                            <td><span class="badge ${t.status === 'Selesai' ? 'badge-success' : 'badge-warning'}">${t.status}</span></td>
                        </tr>
                    `;
                });
                empTbody.innerHTML = html || '<tr><td colspan="5" style="text-align:center;">Tidak ada tugas hari ini.</td></tr>';
            }

            const adminTbody = document.getElementById('adminTaskTableBody');
            if(adminTbody) {
                let html = '';
                state.tasks.forEach(t => {
                    html += `
                        <tr>
                            <td><strong>${t.judul}</strong></td>
                            <td>${t.namaEmp}</td>
                            <td><small>${new Date(t.deadline).toLocaleString('id-ID')}</small></td>
                            <td>
                                <button class="btn btn-danger btn-sm" onclick="deleteTask('${t.id}')"><i class="fa-solid fa-trash"></i></button>
                            </td>
                        </tr>
                    `;
                });
                adminTbody.innerHTML = html || '<tr><td colspan="4" style="text-align:center;">Belum ada tugas.</td></tr>';
            }
        }

        async function deleteTask(id) {
            if(confirm('Hapus tugas ini?')) {
                state.tasks = state.tasks.filter(t => t.id !== id);
                await saveDataToFirebase('tugas_deadline', state.tasks);
                syncDataFromFirebase();
            }
        }

        let tempLeaveProofBase64 = "";

        function previewLeaveProof(e) {
            const file = e.target.files[0];
            if(file) {
                const reader = new FileReader();
                reader.onload = function(evt) {
                    tempLeaveProofBase64 = evt.target.result;
                    const preview = document.getElementById('leaveProofPreview');
                    preview.src = tempLeaveProofBase64;
                    preview.style.display = 'block';
                };
                reader.readAsDataURL(file);
            }
        }

        async function handleLeaveSubmit(e) {
            e.preventDefault();
            const empId = document.getElementById('leaveEmployeeSelect').value;
            const jenis = document.getElementById('leaveType').value;
            const tanggal = document.getElementById('leaveDate').value;
            const keterangan = document.getElementById('leaveReason').value;

            if(!empId) {
                alert('Pilih Karyawan!');
                return;
            }

            const emp = state.employees.find(e => e.id === empId);

            const newLeave = {
                id: "LV-" + Date.now(),
                empId,
                namaEmp: emp.nama,
                jenis,
                tanggal,
                keterangan,
                fotoSurat: tempLeaveProofBase64,
                status: "Pending Verifikasi"
            };

            state.leaves.unshift(newLeave);
            await saveDataToFirebase('perizinan', state.leaves);

            alert('Permohonan Izin / Surat Keterangan Sakit Berhasil Terkirim!');
            document.getElementById('leaveForm').reset();
            document.getElementById('leaveProofPreview').style.display = 'none';
            tempLeaveProofBase64 = "";
            syncDataFromFirebase();
        }

        function renderLeavesTable() {
            const tbody = document.getElementById('adminLeaveTableBody');
            if(!tbody) return;

            let html = '';
            state.leaves.forEach(l => {
                html += `
                    <tr>
                        <td>${l.tanggal}</td>
                        <td><strong>${l.namaEmp}</strong></td>
                        <td><span class="badge badge-info">${l.jenis}</span></td>
                        <td>${l.keterangan}</td>
                        <td>
                            ${l.fotoSurat ? `<button class="btn btn-gold btn-sm" onclick="viewImageModal('${l.id}')"><i class="fa-solid fa-image"></i> Lihat Surat</button>` : 'Tidak Ada'}
                        </td>
                        <td><span class="badge ${l.status === 'Disetujui' ? 'badge-success' : 'badge-warning'}">${l.status}</span></td>
                        <td>
                            <button class="btn btn-gold btn-sm" onclick="updateLeaveStatus('${l.id}', 'Disetujui')"><i class="fa-solid fa-check"></i> Disetujui</button>
                        </td>
                    </tr>
                `;
            });

            tbody.innerHTML = html || '<tr><td colspan="7" style="text-align:center;">Belum ada permohonan izin.</td></tr>';
        }

        function viewImageModal(id) {
            const leave = state.leaves.find(l => l.id === id);
            if(leave && leave.fotoSurat) {
                document.getElementById('fullImagePreview').src = leave.fotoSurat;
                document.getElementById('imagePreviewModal').classList.add('active');
            }
        }

        function closeImageModal() {
            document.getElementById('imagePreviewModal').classList.remove('active');
        }

        async function updateLeaveStatus(id, newStatus) {
            const idx = state.leaves.findIndex(l => l.id === id);
            if(idx !== -1) {
                state.leaves[idx].status = newStatus;
                await saveDataToFirebase('perizinan', state.leaves);
                syncDataFromFirebase();
            }
        }

        function updateStatsCount() {
            document.getElementById('statTotalEmployees').innerText = state.employees.length;
            document.getElementById('statHadirToday').innerText = state.attendance.length;
            document.getElementById('statIzinToday').innerText = state.leaves.length;
            document.getElementById('statPendingTasks').innerText = state.tasks.filter(t => t.status === 'Pending').length;
        }
    </script>
</body>
</html>
