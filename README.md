<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Aufi &amp; Almira — Peta Kenangan</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Jost:wght@400;500;600&family=Cormorant+Garamond:ital,wght@0,500;0,600;1,500&display=swap" rel="stylesheet">
<style>
:root{
  --bg-deep:#150c1c;
  --bg-panel:#20142b;
  --bg-panel-2:#2a1a38;
  --gold:#d3ab6a;
  --rose:#e5a9a3;
  --cream:#f4ead9;
  --muted:#b3a1bf;
  --line:rgba(211,171,106,0.25);
}
*{box-sizing:border-box;margin:0;padding:0;}
html,body{height:100%;}
body{
  background:radial-gradient(ellipse at 20% -10%, #2a1a3d 0%, var(--bg-deep) 55%);
  color:var(--cream);
  font-family:'Jost',sans-serif;
  min-height:100vh;
  overflow-x:hidden;
  position:relative;
}
#stars{position:fixed;inset:0;z-index:0;pointer-events:none;}
.star{position:absolute;background:var(--gold);border-radius:50%;opacity:0.6;animation:twinkle 4s ease-in-out infinite;}
@keyframes twinkle{0%,100%{opacity:0.15;transform:scale(0.8);}50%{opacity:0.9;transform:scale(1.2);}}

header{position:relative;z-index:1;text-align:center;padding:70px 20px 40px;}
.eyebrow{font-family:'Jost',sans-serif;letter-spacing:0.35em;text-transform:uppercase;font-size:11px;color:var(--gold);margin-bottom:18px;}
h1{font-family:'Cormorant Garamond',serif;font-weight:600;font-size:clamp(38px,8vw,72px);line-height:1.05;color:var(--cream);}
h1 .amp{font-style:italic;color:var(--rose);font-weight:400;padding:0 14px;}
.subtitle{font-family:'Cormorant Garamond',serif;font-style:italic;font-size:19px;color:var(--muted);margin-top:14px;}
.stat-row{display:flex;justify-content:center;gap:36px;margin-top:28px;font-size:12px;letter-spacing:0.1em;color:var(--muted);text-transform:uppercase;}
.stat-row b{color:var(--gold);font-family:'Jost';font-weight:600;font-size:13px;}

main{position:relative;z-index:1;max-width:1180px;margin:0 auto;padding:0 24px 100px;}

.dropzone{
  border:1px dashed var(--line);
  border-radius:18px;
  background:linear-gradient(180deg, rgba(211,171,106,0.05), transparent);
  padding:38px 24px;
  text-align:center;
  cursor:pointer;
  transition:border-color .25s, background .25s, transform .2s;
  margin-bottom:16px;
}
.dropzone:hover{border-color:var(--gold);transform:translateY(-2px);}
.dropzone.drag{border-color:var(--rose);background:rgba(229,169,163,0.08);}
.dropzone svg{width:30px;height:30px;stroke:var(--gold);margin-bottom:12px;}
.dropzone p{font-size:14px;color:var(--muted);}
.dropzone strong{color:var(--cream);font-weight:500;}
.dropzone .hint{font-size:11.5px;margin-top:8px;color:var(--muted);opacity:0.7;}
#fileInput{display:none;}
.upload-progress{
  text-align:center;font-size:12.5px;color:var(--gold);margin-bottom:40px;
  min-height:16px;letter-spacing:0.03em;
}

.tabs-row{display:flex;align-items:center;gap:8px;flex-wrap:wrap;justify-content:center;margin-bottom:34px;}
.tabs{display:flex;gap:8px;justify-content:center;flex-wrap:wrap;}
.tab{
  padding:8px 20px;border-radius:999px;border:1px solid var(--line);
  background:transparent;color:var(--muted);font-family:'Jost';font-size:13px;
  letter-spacing:0.04em;cursor:pointer;transition:all .2s;
}
.tab.active,.tab:hover{background:var(--gold);color:#20140a;border-color:var(--gold);}
.sort-btn{
  padding:8px 18px;border-radius:999px;border:1px solid var(--line);
  background:transparent;color:var(--muted);font-family:'Jost';font-size:12.5px;
  letter-spacing:0.03em;cursor:pointer;transition:all .2s;display:flex;align-items:center;gap:6px;
  margin-left:auto;
}
.sort-btn:hover{border-color:var(--gold);color:var(--cream);}
@media (max-width:560px){.sort-btn{margin-left:0;}}

.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(210px,1fr));gap:30px 26px;}
.card{
  background:#fdf8ee;padding:12px 12px 44px;border-radius:3px;
  box-shadow:0 10px 24px rgba(0,0,0,0.45), 0 2px 6px rgba(0,0,0,0.3);
  cursor:pointer;transform:rotate(var(--r,-1.5deg));
  transition:transform .3s ease, box-shadow .3s ease;position:relative;
}
.card:nth-child(3n){--r:2deg;}
.card:nth-child(3n+1){--r:-2deg;}
.card:nth-child(3n+2){--r:1deg;}
.card:hover{transform:rotate(0deg) translateY(-6px) scale(1.02);box-shadow:0 18px 34px rgba(0,0,0,0.55);}
.card .pin{
  position:absolute;top:-9px;left:50%;transform:translateX(-50%);
  width:16px;height:16px;border-radius:50%;
  background:radial-gradient(circle at 35% 30%, #f2c48a, var(--gold));
  box-shadow:0 2px 5px rgba(0,0,0,0.5);
}
.card .thumb-wrap{width:100%;aspect-ratio:1/1;overflow:hidden;background:#1a1a1a;display:flex;align-items:center;justify-content:center;}
.card img,.card video{width:100%;height:100%;object-fit:cover;display:block;}
.card .vid-badge{
  position:absolute;top:20px;right:20px;background:rgba(0,0,0,0.55);
  color:#fff;border-radius:50%;width:26px;height:26px;display:flex;
  align-items:center;justify-content:center;font-size:11px;
}
.card .cap{
  font-family:'Cormorant Garamond',serif;font-style:italic;color:#2a2118;
  font-size:14.5px;text-align:center;margin-top:10px;padding:0 4px;
  white-space:nowrap;overflow:hidden;text-overflow:ellipsis;
}
.card .date{position:absolute;bottom:12px;left:0;right:0;text-align:center;font-size:10px;letter-spacing:0.06em;color:#8a7d68;text-transform:uppercase;}

.empty{text-align:center;padding:70px 20px;color:var(--muted);}
.empty svg{width:44px;height:44px;stroke:var(--rose);margin-bottom:16px;}
.empty p{font-family:'Cormorant Garamond',serif;font-style:italic;font-size:19px;}

.lightbox{
  position:fixed;inset:0;background:rgba(9,5,13,0.92);backdrop-filter:blur(6px);
  z-index:50;display:none;align-items:center;justify-content:center;padding:24px;
  opacity:0;transition:opacity .28s ease;
}
.lightbox.open{display:flex;}
.lightbox.show{opacity:1;}
.lb-content{
  max-width:900px;width:100%;max-height:90vh;display:flex;flex-direction:column;
  align-items:center;gap:18px;position:relative;
  transform:scale(0.94) translateY(10px);opacity:0;
  transition:transform .32s cubic-bezier(.2,.8,.2,1), opacity .32s ease;
}
.lightbox.show .lb-content{transform:scale(1) translateY(0);opacity:1;}
.lb-media-wrap{width:100%;display:flex;align-items:center;justify-content:center;min-height:120px;}
.lb-media{max-width:100%;max-height:64vh;border-radius:6px;box-shadow:0 20px 60px rgba(0,0,0,0.6);opacity:0;transition:opacity .35s ease;}
.lb-media.loaded{opacity:1;}
.lb-loading, .lb-error{color:var(--muted);font-family:'Cormorant Garamond',serif;font-style:italic;font-size:16px;padding:40px 0;}
.lb-cap-row{display:flex;align-items:center;gap:10px;justify-content:center;}
.lb-cap{font-family:'Cormorant Garamond',serif;font-style:italic;font-size:20px;color:var(--cream);text-align:center;}
.lb-cap-input{
  font-family:'Cormorant Garamond',serif;font-style:italic;font-size:20px;color:var(--cream);
  background:transparent;border:none;border-bottom:1px solid var(--gold);text-align:center;
  outline:none;padding:2px 4px;min-width:160px;
}
.lb-edit-btn{background:none;border:none;color:var(--muted);cursor:pointer;font-size:14px;opacity:0.7;transition:opacity .2s, color .2s;}
.lb-edit-btn:hover{opacity:1;color:var(--gold);}
.lb-date{font-size:11px;letter-spacing:0.1em;color:var(--muted);text-transform:uppercase;}
.lb-actions{display:flex;gap:12px;margin-top:6px;}
.lb-btn{
  border:1px solid var(--line);background:transparent;color:var(--cream);
  padding:9px 18px;border-radius:999px;font-family:'Jost';font-size:12.5px;
  letter-spacing:0.05em;cursor:pointer;display:flex;align-items:center;gap:6px;transition:all .2s;
}
.lb-btn:hover{background:var(--gold);color:#20140a;border-color:var(--gold);}
.lb-btn.danger:hover{background:#c96a63;border-color:#c96a63;color:#fff;}
.lb-close{
  position:absolute;top:-46px;right:0;background:none;border:none;color:var(--cream);
  font-size:28px;cursor:pointer;line-height:1;opacity:0.7;transition:opacity .2s;
}
.lb-close:hover{opacity:1;}

.toast{
  position:fixed;bottom:26px;left:50%;transform:translateX(-50%) translateY(20px);
  background:var(--bg-panel-2);border:1px solid var(--line);color:var(--cream);
  padding:12px 22px;border-radius:999px;font-size:13px;opacity:0;pointer-events:none;
  transition:all .3s;z-index:60;max-width:90vw;text-align:center;
}
.toast.show{opacity:1;transform:translateX(-50%) translateY(0);}

footer{text-align:center;padding:30px;color:var(--muted);font-size:11px;letter-spacing:0.08em;text-transform:uppercase;position:relative;z-index:1;}

@media (max-width:520px){
  header{padding:50px 16px 30px;}
  .stat-row{gap:22px;}
}
</style>
</head>
<body>

<div id="stars"></div>

<header>
  <div class="eyebrow">Kumpulan Kenangan</div>
  <h1>Aufi<span class="amp">&amp;</span>Almira</h1>
  <div class="subtitle">setiap foto adalah waktu yang berhenti sebentar untuk kita</div>
  <div class="stat-row">
    <span><b id="statTotal">0</b> Kenangan</span>
    <span><b id="statPhoto">0</b> Foto</span>
    <span><b id="statVideo">0</b> Video</span>
  </div>
</header>

<main>
  <div class="dropzone" id="dropzone">
    <svg viewBox="0 0 24 24" fill="none" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 16V4M12 4l-4 4M12 4l4 4"/><path d="M4 16v3a2 2 0 002 2h12a2 2 0 002-2v-3"/></svg>
    <p><strong>Tarik &amp; lepas</strong> foto atau video di sini, atau klik untuk memilih</p>
    <div class="hint">Bisa diakses siapa saja yang membuka link ini — foto/video langsung tersimpan untuk semua orang.</div>
  </div>
  <div class="upload-progress" id="uploadProgress"></div>
  <input type="file" id="fileInput" accept="image/*,video/*" multiple>

  <div class="tabs-row">
    <div class="tabs">
      <div class="tab active" data-filter="all">Semua</div>
      <div class="tab" data-filter="image">Foto</div>
      <div class="tab" data-filter="video">Video</div>
    </div>
    <button class="sort-btn" id="sortBtn">↓ Terbaru dulu</button>
  </div>

  <div class="grid" id="grid"></div>

  <div class="empty" id="emptyState" style="display:none;">
    <svg viewBox="0 0 24 24" fill="none" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 21s-7-4.6-9.5-9A5.5 5.5 0 0112 6a5.5 5.5 0 019.5 6c-2.5 4.4-9.5 9-9.5 9z"/></svg>
    <p>Belum ada kenangan yang tersimpan.<br>Unggah momen pertama kalian berdua.</p>
  </div>
</main>

<div class="lightbox" id="lightbox">
  <div class="lb-content">
    <button class="lb-close" id="lbClose">×</button>
    <div class="lb-media-wrap" id="lbMediaWrap"></div>
    <div class="lb-cap-row">
      <div class="lb-cap" id="lbCap"></div>
      <input class="lb-cap-input" id="lbCapInput" style="display:none;">
      <button class="lb-edit-btn" id="lbEditBtn">✎</button>
    </div>
    <div class="lb-date" id="lbDate"></div>
    <div class="lb-actions">
      <button class="lb-btn" id="lbDownload">Unduh</button>
      <button class="lb-btn danger" id="lbDelete">Hapus</button>
    </div>
  </div>
</div>

<div class="toast" id="toast"></div>

<footer>Galeri Aufi &amp; Almira</footer>

<script type="module">
// =====================================================================
// KONFIGURASI FIREBASE — GANTI dengan config dari project Firebase-mu
// (Firebase Console → Project Settings → General → Your apps → SDK setup)
// =====================================================================
const firebaseConfig = {
  apiKey: "GANTI_DENGAN_API_KEY",
  authDomain: "GANTI.firebaseapp.com",
  projectId: "GANTI_PROJECT_ID",
  storageBucket: "GANTI.appspot.com",
  messagingSenderId: "GANTI",
  appId: "GANTI"
};

import { initializeApp } from "https://www.gstatic.com/firebasejs/10.13.2/firebase-app.js";
import {
  getFirestore, collection, doc, setDoc, updateDoc, deleteDoc,
  getDocs, query, orderBy
} from "https://www.gstatic.com/firebasejs/10.13.2/firebase-firestore.js";
import {
  getStorage, ref, uploadBytesResumable, getDownloadURL, deleteObject
} from "https://www.gstatic.com/firebasejs/10.13.2/firebase-storage.js";

const app = initializeApp(firebaseConfig);
const db = getFirestore(app);
const storage = getStorage(app);
const memoriesCol = collection(db, "memories");

(function(){
  // ---------- starfield ----------
  const starsEl = document.getElementById('stars');
  for(let i=0;i<70;i++){
    const s=document.createElement('div');
    s.className='star';
    const size = Math.random()*2+1;
    s.style.width=size+'px'; s.style.height=size+'px';
    s.style.left=Math.random()*100+'%'; s.style.top=Math.random()*100+'%';
    s.style.animationDelay=(Math.random()*4)+'s';
    starsEl.appendChild(s);
  }

  // ---------- state ----------
  let items = []; // {id, type, caption, date, url, storagePath}
  let currentFilter = 'all';
  let currentSort = 'newest';

  const grid = document.getElementById('grid');
  const emptyState = document.getElementById('emptyState');
  const toastEl = document.getElementById('toast');
  const uploadProgressEl = document.getElementById('uploadProgress');
  const statTotal = document.getElementById('statTotal');
  const statPhoto = document.getElementById('statPhoto');
  const statVideo = document.getElementById('statVideo');

  function toast(msg){
    toastEl.textContent = msg;
    toastEl.classList.add('show');
    clearTimeout(toastEl._t);
    toastEl._t = setTimeout(()=>toastEl.classList.remove('show'), 2800);
  }
  function fmtDate(iso){
    const d = new Date(iso);
    return d.toLocaleDateString('id-ID',{day:'numeric',month:'long',year:'numeric'});
  }
  function makeId(){
    if(window.crypto && crypto.randomUUID) return crypto.randomUUID();
    return 'id_'+Date.now()+'_'+Math.random().toString(36).slice(2,10);
  }

  // ---------- load & render ----------
  async function loadItems(){
    try{
      const q = query(memoriesCol, orderBy('date','desc'));
      const snap = await getDocs(q);
      items = snap.docs.map(d => ({ id: d.id, ...d.data() }));
    }catch(e){
      console.error(e);
      toast('Gagal memuat galeri. Cek koneksi atau konfigurasi Firebase.');
      items = [];
    }
    render();
  }

  function render(){
    const filtered = currentFilter==='all' ? items : items.filter(i=>i.type===currentFilter);
    grid.innerHTML = '';
    emptyState.style.display = filtered.length ? 'none' : 'block';

    const sorted = filtered.slice().sort((a,b)=>{
      const diff = new Date(a.date) - new Date(b.date);
      return currentSort==='newest' ? -diff : diff;
    });

    sorted.forEach(item=>{
      const card = document.createElement('div');
      card.className='card';
      card.dataset.id = item.id;

      const pin = document.createElement('div');
      pin.className='pin';
      card.appendChild(pin);

      const wrap = document.createElement('div');
      wrap.className='thumb-wrap';
      if(item.type==='image'){
        const img=document.createElement('img');
        img.src=item.url; img.loading='lazy';
        wrap.appendChild(img);
      }else{
        const vid=document.createElement('video');
        vid.src=item.url; vid.muted=true;
        wrap.appendChild(vid);
        const badge=document.createElement('div');
        badge.className='vid-badge'; badge.textContent='▶';
        card.appendChild(badge);
      }
      card.appendChild(wrap);

      const cap=document.createElement('div');
      cap.className='cap';
      cap.textContent = item.caption || 'Tanpa judul';
      card.appendChild(cap);

      const date=document.createElement('div');
      date.className='date';
      date.textContent = fmtDate(item.date);
      card.appendChild(date);

      card.addEventListener('click', ()=>openLightbox(item.id));
      grid.appendChild(card);
    });

    statTotal.textContent = items.length;
    statPhoto.textContent = items.filter(i=>i.type==='image').length;
    statVideo.textContent = items.filter(i=>i.type==='video').length;
  }

  // ---------- filter & sort ----------
  document.querySelectorAll('.tab').forEach(tab=>{
    tab.addEventListener('click', ()=>{
      document.querySelectorAll('.tab').forEach(t=>t.classList.remove('active'));
      tab.classList.add('active');
      currentFilter = tab.dataset.filter;
      render();
    });
  });
  const sortBtn = document.getElementById('sortBtn');
  sortBtn.addEventListener('click', ()=>{
    currentSort = currentSort==='newest' ? 'oldest' : 'newest';
    sortBtn.textContent = currentSort==='newest' ? '↓ Terbaru dulu' : '↑ Terlama dulu';
    render();
  });

  // ---------- upload ----------
  const dropzone = document.getElementById('dropzone');
  const fileInput = document.getElementById('fileInput');
  dropzone.addEventListener('click', ()=>fileInput.click());
  dropzone.addEventListener('dragover', e=>{e.preventDefault();dropzone.classList.add('drag');});
  dropzone.addEventListener('dragleave', ()=>dropzone.classList.remove('drag'));
  dropzone.addEventListener('drop', e=>{
    e.preventDefault();
    dropzone.classList.remove('drag');
    handleFiles(e.dataTransfer.files);
  });
  fileInput.addEventListener('change', e=>{ handleFiles(e.target.files); fileInput.value=''; });

  function compressImage(file, maxDim, quality){
    return new Promise((resolve)=>{
      const reader = new FileReader();
      reader.onload = ()=>{
        const img = new Image();
        img.onload = ()=>{
          let { width, height } = img;
          if(width > height && width > maxDim){
            height = height * (maxDim / width);
            width = maxDim;
          } else if(height > maxDim){
            width = width * (maxDim / height);
            height = maxDim;
          }
          const canvas = document.createElement('canvas');
          canvas.width = width; canvas.height = height;
          canvas.getContext('2d').drawImage(img, 0, 0, width, height);
          canvas.toBlob((blob)=> resolve(blob || file), 'image/jpeg', quality);
        };
        img.onerror = ()=> resolve(file);
        img.src = reader.result;
      };
      reader.onerror = ()=> resolve(file);
      reader.readAsDataURL(file);
    });
  }

  function uploadWithProgress(storagePath, blob, contentType){
    return new Promise((resolve, reject)=>{
      const storageRef = ref(storage, storagePath);
      const task = uploadBytesResumable(storageRef, blob, { contentType });
      task.on('state_changed', (snap)=>{
        const pct = Math.round((snap.bytesTransferred / snap.totalBytes) * 100);
        uploadProgressEl.textContent = `Mengunggah… ${pct}%`;
      }, (err)=>reject(err), async ()=>{
        const url = await getDownloadURL(task.snapshot.ref);
        resolve(url);
      });
    });
  }

  async function handleFiles(fileList){
    const files = Array.from(fileList);
    for(const file of files){
      const isImage = file.type.startsWith('image/');
      const isVideo = file.type.startsWith('video/');
      if(!isImage && !isVideo){
        toast(`"${file.name}" bukan foto/video, dilewati.`);
        continue;
      }
      if(isVideo && file.size > 100*1024*1024){
        const proceed = confirm(`"${file.name}" berukuran ${(file.size/1024/1024).toFixed(1)}MB. Video besar akan lebih lama diunggah dan cepat memakai kuota gratis. Lanjutkan?`);
        if(!proceed) continue;
      }
      try{
        const id = makeId();
        let blob = file;
        let ext = file.name.split('.').pop() || (isImage ? 'jpg' : 'mp4');
        let contentType = file.type;
        if(isImage){
          blob = await compressImage(file, 1920, 0.85);
          ext = 'jpg';
          contentType = 'image/jpeg';
        }
        const storagePath = `memories/${id}.${ext}`;
        uploadProgressEl.textContent = `Mengunggah "${file.name}"…`;
        const url = await uploadWithProgress(storagePath, blob, contentType);

        const item = {
          type: isImage ? 'image' : 'video',
          caption: file.name.replace(/\.[^/.]+$/, ''),
          date: new Date().toISOString(),
          url,
          storagePath
        };
        await setDoc(doc(memoriesCol, id), item);
        items.unshift({ id, ...item });
        render();
        toast('Kenangan baru tersimpan ✧');
      }catch(err){
        console.error(err);
        toast(`Gagal mengunggah "${file.name}". ${err.message || ''}`);
      }finally{
        uploadProgressEl.textContent = '';
      }
    }
  }

  // ---------- lightbox ----------
  const lightbox = document.getElementById('lightbox');
  const lbMediaWrap = document.getElementById('lbMediaWrap');
  const lbCap = document.getElementById('lbCap');
  const lbCapInput = document.getElementById('lbCapInput');
  const lbEditBtn = document.getElementById('lbEditBtn');
  const lbDate = document.getElementById('lbDate');
  const lbDownload = document.getElementById('lbDownload');
  const lbDelete = document.getElementById('lbDelete');
  const lbClose = document.getElementById('lbClose');
  let activeItem = null;

  function openLightbox(id){
    const item = items.find(i=>i.id===id);
    if(!item) return;
    activeItem = item;
    exitEditMode();
    lbCap.textContent = item.caption || 'Tanpa judul';
    lbDate.textContent = fmtDate(item.date);
    lbMediaWrap.innerHTML = '<div class="lb-loading">Memuat…</div>';
    lightbox.classList.add('open');
    requestAnimationFrame(()=>lightbox.classList.add('show'));

    let mediaEl;
    if(item.type==='image'){
      mediaEl = document.createElement('img');
      mediaEl.className='lb-media';
      mediaEl.onload = ()=>{ mediaEl.classList.add('loaded'); lbMediaWrap.innerHTML=''; lbMediaWrap.appendChild(mediaEl); };
      mediaEl.onerror = ()=>{ lbMediaWrap.innerHTML = '<div class="lb-error">Gagal memuat media.</div>'; };
      mediaEl.src = item.url;
    }else{
      mediaEl = document.createElement('video');
      mediaEl.className='lb-media';
      mediaEl.controls = true;
      mediaEl.oncanplay = ()=>{ mediaEl.classList.add('loaded'); lbMediaWrap.innerHTML=''; lbMediaWrap.appendChild(mediaEl); };
      mediaEl.onerror = ()=>{ lbMediaWrap.innerHTML = '<div class="lb-error">Gagal memuat media.</div>'; };
      mediaEl.src = item.url;
    }
  }
  function closeLightbox(){
    lightbox.classList.remove('show');
    setTimeout(()=>{
      lightbox.classList.remove('open');
      lbMediaWrap.innerHTML='';
      activeItem=null;
    }, 260);
  }
  lbClose.addEventListener('click', closeLightbox);
  lightbox.addEventListener('click', e=>{ if(e.target===lightbox) closeLightbox(); });
  document.addEventListener('keydown', e=>{ if(e.key==='Escape') closeLightbox(); });

  // ---------- edit caption ----------
  function exitEditMode(){
    lbCapInput.style.display='none';
    lbCap.style.display='';
  }
  lbEditBtn.addEventListener('click', ()=>{
    if(!activeItem) return;
    lbCapInput.value = activeItem.caption || '';
    lbCap.style.display='none';
    lbCapInput.style.display='inline-block';
    lbCapInput.focus();
    lbCapInput.select();
  });
  async function commitCaption(){
    if(!activeItem) return;
    const newCap = lbCapInput.value.trim();
    if(newCap === activeItem.caption){ exitEditMode(); return; }
    activeItem.caption = newCap;
    lbCap.textContent = newCap || 'Tanpa judul';
    exitEditMode();
    try{
      await updateDoc(doc(memoriesCol, activeItem.id), { caption: newCap });
      render();
    }catch(e){
      toast('Gagal menyimpan judul baru.');
    }
  }
  lbCapInput.addEventListener('keydown', e=>{
    if(e.key==='Enter') commitCaption();
    if(e.key==='Escape') exitEditMode();
  });
  lbCapInput.addEventListener('blur', commitCaption);

  // ---------- download & delete ----------
  lbDownload.addEventListener('click', ()=>{
    if(!activeItem) return;
    const a=document.createElement('a');
    a.href=activeItem.url;
    a.target='_blank';
    const ext = activeItem.type==='image' ? 'jpg' : (activeItem.storagePath.split('.').pop() || 'mp4');
    a.download = (activeItem.caption||'kenangan')+'.'+ext;
    document.body.appendChild(a);
    a.click();
    a.remove();
  });
  lbDelete.addEventListener('click', async ()=>{
    if(!activeItem) return;
    if(!confirm('Hapus kenangan ini? Tindakan ini tidak bisa dibatalkan.')) return;
    const id = activeItem.id;
    const storagePath = activeItem.storagePath;
    try{
      await deleteObject(ref(storage, storagePath));
    }catch(e){ /* file mungkin sudah hilang, lanjut hapus datanya */ }
    try{
      await deleteDoc(doc(memoriesCol, id));
      items = items.filter(i=>i.id!==id);
      render();
      closeLightbox();
      toast('Kenangan dihapus.');
    }catch(e){
      toast('Gagal menghapus data. Coba lagi.');
    }
  });

  loadItems();
})();
</script>
</body>
</html>
