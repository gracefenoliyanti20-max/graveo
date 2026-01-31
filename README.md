<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <title>WebGIS Fakultas Teknik - Universitas Gadjah Mada</title>
    <style>
        .no-scrollbar::-webkit-scrollbar { display: none; }
        .no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
        /* Animasi sederhana untuk titik peta */
        .ping-fast { animation: ping 1.5s cubic-bezier(0, 0, 0.2, 1) infinite; }
    </style>
</head>
<body class="bg-white font-sans flex flex-col min-h-screen">

    <header class="bg-[#003366] text-white">
        <div class="flex flex-col items-center py-12">
            <img src="logo ugm/3a20624ba12e2b24b2d462f1c1974ce9.png" alt="Logo UGM" class="h-20 mb-4">
            <h1 class="text-sm tracking-[0.2em] font-light uppercase">Universitas Gadjah Mada</h1>
        </div>
        <nav class="bg-[#002244] border-t border-yellow-600/30">
            <div class="max-w-6xl mx-auto px-4">
                <ul class="flex justify-center items-center gap-6 py-3 overflow-x-auto no-scrollbar text-[10px] uppercase tracking-widest text-gray-300">
                    <li><a href="#" class="hover:text-yellow-500 transition">Penelitian</a></li>
                    <li><a href="#" class="hover:text-yellow-500 transition">Pengabdian</a></li>
                    <li><a href="#" class="text-yellow-500 transition border-b border-yellow-500">Peta Interaktif</a></li>
                    <li><a href="#" class="hover:text-yellow-500 transition">Departemen</a></li>
                    <li><a href="#" class="hover:text-yellow-500 transition">Kerjasama</a></li>
                    <li><a href="#" class="hover:text-yellow-500 transition">Sebaran alumni</a></li>
                    <li><a href="#" class="hover:text-yellow-500 transition">Fasilitas</a></li>
                    <li><a href="#" class="hover:text-yellow-500 transition">Kontak</a></li>
                    <li><a href="#" class="hover:text-yellow-500 transition font-bold text-white">Login</a></li>
                </ul>
            </div>
        </nav>
    </header>

    <main class="flex-grow flex flex-col md:flex-row h-[700px] border-b bg-gray-50">
        
        <aside class="w-full md:w-80 bg-white border-r shadow-sm p-6 overflow-y-auto">
            <div class="mb-6">
                <h2 class="text-[#0D5F46] font-bold text-xl uppercase tracking-tight">Peta Interaktif FT</h2>
                <p class="text-[11px] text-gray-500 mt-1 italic leading-relaxed">
                    Visualisasi data fasilitas dan sebaran gedung di lingkungan Fakultas Teknik UGM.
                </p>
            </div>

            <div class="space-y-5">
                <div class="bg-gray-50 border border-gray-200 rounded-lg p-4">
                    <div class="flex items-center gap-2 mb-4 text-[#0D5F46] font-bold text-sm">
                        <i class="fas fa-filter"></i>
                        FILTER DATA
                    </div>
                    
                    <div class="space-y-4">
                        <div>
                            <label class="text-[10px] font-bold text-gray-400 uppercase tracking-widest">Departemen</label>
                            <select class="w-full mt-1 bg-white border border-gray-300 rounded p-2 text-sm focus:ring-2 focus:ring-green-500 outline-none">
                                <option>Semua Departemen</option>
                                <option>Teknik Elektro & Teknologi Informasi</option>
                                <option>Teknik Sipil & Lingkungan</option>
                                <option>Teknik Mesin & Industri</option>
                                <option>Arsitektur & Perencanaan</option>
                            </select>
                        </div>
                        <div>
                            <label class="text-[10px] font-bold text-gray-400 uppercase tracking-widest">Jenis Fasilitas</label>
                            <select class="w-full mt-1 bg-white border border-gray-300 rounded p-2 text-sm focus:ring-2 focus:ring-green-500 outline-none">
                                <option>Semua Fasilitas</option>
                                <option>Laboratorium</option>
                                <option>Ruang Kuliah</option>
                                <option>Layanan Umum</option>
                            </select>
                        </div>
                        <button class="w-full bg-[#0D5F46] text-white py-2.5 rounded font-bold text-xs uppercase tracking-widest hover:bg-green-800 transition shadow-lg">
                            Terapkan Filter
                        </button>
                        <button class="w-full bg-white border border-gray-300 text-gray-500 py-2 rounded text-xs font-semibold hover:bg-gray-100 transition">
                            Reset Filter
                        </button>
                    </div>
                </div>

                <div class="px-2 pt-4">
                    <div class="flex justify-between items-end border-b pb-2">
                        <span class="text-xs text-gray-500 font-medium">Statistik Gedung Terdata</span>
                        <span class="text-2xl font-bold text-gray-800">42</span>
                    </div>
                </div>
            </div>
        </aside>

        <section class="flex-grow relative bg-slate-200 overflow-hidden">
            <div class="absolute inset-0 bg-cover bg-center" style="background-image: url('https://upload.wikimedia.org/wikipedia/commons/e/e4/Peta_lokasi_UGM.png'); opacity: 0.4; filter: grayscale(100%);"></div>
            
            <div class="absolute top-[45%] left-[40%] group cursor-pointer">
                <div class="absolute -inset-2 bg-green-500 rounded-full ping-fast opacity-50"></div>
                <div class="relative w-4 h-4 bg-green-700 rounded-full border-2 border-white"></div>
                <div class="absolute bottom-6 left-1/2 -translate-x-1/2 bg-white px-3 py-1 rounded shadow-md text-[10px] font-bold whitespace-nowrap hidden group-hover:block border border-green-700">
                    KPFT (Dekanat Teknik)
                </div>
            </div>

            <div class="absolute bottom-32 right-6 bg-white/90 backdrop-blur-sm p-4 rounded-lg shadow-xl border w-44">
                <p class="text-[10px] font-bold text-gray-400 mb-2 uppercase tracking-tighter border-b pb-1">Layer Peta</p>
                <div class="space-y-2 text-xs text-gray-700">
                    <label class="flex items-center gap-2 cursor-pointer">
                        <input type="radio" name="maplayer" checked class="accent-green-700"> Street View
                    </label>
                    <label class="flex items-center gap-2 cursor-pointer">
                        <input type="radio" name="maplayer" class="accent-green-700"> Satellite
                    </label>
                    <hr class="my-1">
                    <label class="flex items-center gap-2 cursor-pointer font-bold">
                        <input type="checkbox" checked class="accent-green-700 rounded"> Batas Wilayah
                    </label>
                </div>
            </div>

            <div class="absolute bottom-6 right-6 bg-white/90 backdrop-blur-sm p-4 rounded-lg shadow-xl border w-44">
                <p class="text-[10px] font-bold text-gray-400 mb-2 uppercase tracking-tighter border-b pb-1">Legenda</p>
                <div class="space-y-2">
                    <div class="flex items-center gap-3">
                        <div class="w-3 h-3 rounded-full bg-green-600"></div>
                        <span class="text-[10px] font-semibold text-gray-600 uppercase">Gedung FT</span>
                    </div>
                    <div class="flex items-center gap-3">
                        <div class="w-3 h-3 rounded-full bg-yellow-500"></div>
                        <span class="text-[10px] font-semibold text-gray-600 uppercase">Fasilitas Umum</span>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <footer class="bg-[#003366] text-white pt-16">
        <div class="max-w-4xl mx-auto px-4 flex flex-col items-center text-center">
            
            <div class="flex items-center gap-4 mb-8">
                <img src="logo ugm/3a20624ba12e2b24b2d462f1c1974ce9.png" alt="Logo UGM" class="h-16">
                <div class="text-left border-l border-white/30 pl-4 uppercase tracking-tighter leading-tight">
                    <div class="text-lg font-light">Universitas</div>
                    <div class="text-lg font-bold">Gadjah Mada</div>
                </div>
            </div>

            <div class="flex flex-col items-center text-[13px] text-gray-200 space-y-1 mb-6">
                <div class="flex items-center gap-2">
                    <i class="fas fa-map-marker-alt text-black bg-white rounded-sm p-0.5 text-[10px]"></i>
                    <p>Bulaksumur, Caturtunggal, Kec. Depok,</p>
                </div>
                <p>Kabupaten Sleman, Daerah Istimewa</p>
                <p>Yogyakarta 55281</p>
            </div>

            <div class="text-[12px] text-gray-200 mb-12">
                <p>E: info@ugm.ac.id | P: +62(274)588688 | F: +62(274)565223 | WA: +628112869988</p>
            </div>
        </div>

        <div class="w-full mt-4">
            <img src="https://ugm.ac.id/wp-content/themes/ugm-official/images/footer-bg.png" 
                 alt="UGM Illustration" 
                 class="w-full h-auto object-cover max-h-[300px] opacity-50">
        </div>
    </footer>

</body>
</html># graveo
whut the hell is ts
