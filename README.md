<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Aufi & Almira — Peta Kenangan</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;1,500&family=Jost:wght@300;400;500;600&display=swap" rel="stylesheet">
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

  header{
    position:relative;z-index:1;
    text-align:center;
    padding:70px 20px 40px;
  }
  .eyebrow{
    font-family:'Jost',sans-serif;
    letter-spacing:0.35em;
    text-transform:uppercase;
    font-size:11px;
    color:var(--gold);
    margin-bottom:18px;
  }
  h1{
    font-family:'Cormorant Garamond',serif;
    font-weight:600;
    font-size:clamp(38px,8vw,72px);
    line-height:1.05;
    color:var(--cream);
  }
  h1 .amp{
    font-style:italic;
    color:var(--rose);
    font-weight:400;
    padding:0 14px;
  }
  .subtitle{
    font-family:'Cormorant Garamond',serif;
    font-style:italic;
    font-size:19px;
    color:var(--muted);
    margin-top:14px;
  }
  .stat-row{
    display:flex;justify-content:center;gap:36px;
    margin-top:28px;font-size:12px;letter-spacing:0.1em;color:var(--muted);
    text-transform:uppercase;
  }
  .stat-row b{color:var(--gold);font-family:'Jost';font-weight:600;font-size:13px;}

  main{position:relative;z-index:1;max-width:1180px;margin:0 auto;padding:0 24px 100px;}

  /* Upload dropzone */
  .dropzone{
    border:1px dashed var(--line);
    border-radius:18px;
    background:linear-gradient(180deg, rgba(211,171,106,0.05), transparent);
    padding:38px 24px;
    text-align:center;
    cursor:pointer;
    transition:border-color .25s, background .25s, transform .2s;
    margin-bottom:56px;
  }
  .dropzone:hover{border-color:var(--gold);transform:translateY(-2px);}
  .dropzone.drag{border-color:var(--rose);background:rgba(229,169,163,0.08);}
  .dropzone svg{width:30px;height:30px;stroke:var(--gold);margin-bottom:12px;}
  .dropzone p{font-size:14px;color:var(--muted);}
  .dropzone strong{color:var(--cream);font-weight:500;}
  .dropzone .hint{font-size:11.5px;margin-top:8px;color:var(--muted);opacity:0.7;}
  #fileInput{display:none;}

  /* Filter tabs */
  .tabs{
    display:flex;gap:8px;justify-content:center;margin-bottom:34px;flex-wrap:wrap;
  }
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
  .tabs-row{display:flex;align-items:center;gap:8px;flex-wrap:wrap;justify-content:center;margin-bottom:34px;}
  .tabs-row .tabs{margin-bottom:0;}
  @media (max-width:560px){.sort-btn{margin-left:0;}}

  /* Gallery grid — scattered polaroid feel */
  .grid{
    display:grid;
    grid-template-columns:repeat(auto-fill,minmax(210px,1fr));
    gap:30px 26px;
  }
  .card{
    background:#fdf8ee;
    padding:12px 12px 44px;
    border-radius:3px;
    box-shadow:0 10px 24px rgba(0,0,0,0.45), 0 2px 6px rgba(0,0,0,0.3);
    cursor:pointer;
    transform:rotate(var(--r,-1.5deg));
    transition:transform .3s ease, box-shadow .3s ease;
    position:relative;
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
  .card .thumb-wrap{
    width:100%;aspect-ratio:1/1;overflow:hidden;background:#1a1a1a;
    display:flex;align-items:center;justify-content:center;
  }
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
  .card .date{
    position:absolute;bottom:12px;left:0;right:0;text-align:center;
    font-size:10px;letter-spacing:0.06em;color:#8a7d68;text-transform:uppercase;
  }

  .empty{
    text-align:center;padding:70px 20px;color:var(--muted);
  }
  .empty svg{width:44px;height:44px;stroke:var(--rose);margin-bottom:16px;}
  .empty p{font-family:'Cormorant Garamond',serif;font-style:italic;font-size:19px;}

  /* Lightbox */
  .lightbox{
    position:fixed;inset:0;background:rgba(9,5,13,0.92);backdrop-filter:blur(6px);
    z-index:50;display:none;align-items:center;justify-content:center;padding:24px;
    opacity:0;transition:opacity .28s ease;
  }
  .lightbox.open{display:flex;}
  .lightbox.show{opacity:1;}
  .lb-content{
    max-width:900px;width:100%;max-height:90vh;display:flex;flex-direction:column;
    align-items:center;gap:18px;
    transform:scale(0.94) translateY(10px);opacity:0;
    transition:transform .32s cubic-bezier(.2,.8,.2,1), opacity .32s ease;
  }
  .lightbox.show .lb-content{transform:scale(1) translateY(0);opacity:1;}
  .lb-media{max-width:100%;max-height:64vh;border-radius:6px;box-shadow:0 20px 60px rgba(0,0,0,0.6);
    opacity:0;transition:opacity .35s ease;}
  .lb-media.loaded{opacity:1;}
  .lb-cap-row{display:flex;align-items:center;gap:10px;justify-content:center;}
  .lb-cap{font-family:'Cormorant Garamond',serif;font-style:italic;font-size:20px;color:var(--cream);text-align:center;}
  .lb-cap-input{
    font-family:'Cormorant Garamond',serif;font-style:italic;font-size:20px;color:var(--cream);
    background:transparent;border:none;border-bottom:1px solid var(--gold);text-align:center;
    outline:none;padding:2px 4px;min-width:160px;
  }
  .lb-edit-btn{
    background:none;border:none;color:var(--muted);cursor:pointer;font-size:14px;
    opacity:0.7;transition:opacity .2s, color .2s;
  }
  .lb-edit-btn:hover{opacity:1;color:var(--gold);}
  .lb-date{font-size:11px;letter-spacing:0.1em;color:var(--muted);text-transform:uppercase;}
  .lb-actions{display:flex;gap:12px;margin-top:6px;}
  .lb-btn{
    border:1px solid var(--line);background:transparent;color:var(--cream);
    padding:9px 18px;border-radius:999px;font-family:'Jost';font-size:12.5px;
    letter-spacing:0.05em;cursor:pointer;display:flex;align-items:center;gap:6px;
    transition:all .2s;
  }
  .lb-btn:hover{background:var(--gold);color:#20140a;border-color:var(--gold);}
  .lb-btn.danger:hover{background:#c96a63;border-color:#c96a63;color:#fff;}
  .lb-close{
    position:absolute;top:22px;right:26px;background:none;border:none;color:var(--cream);
    font-size:28px;cursor:pointer;line-height:1;opacity:0.7;
  }
  .lb-close:hover{opacity:1;}

  .toast{
    position:fixed;bottom:26px;left:50%;transform:translateX(-50%) translateY(20px);
    background:var(--bg-panel-2);border:1px solid var(--line);color:var(--cream);
    padding:12px 22px;border-radius:999px;font-size:13px;opacity:0;pointer-events:none;
    transition:all .3s;z-index:60;
  }
  .toast.show{opacity:1;transform:translateX(-50%) translateY(0);}

  footer{
    text-align:center;padding:30px;color:var(--muted);font-size:11px;letter-spacing:0.08em;
    text-transform:uppercase;position:relative;z-index:1;
  }

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
  <h1>Aufi<span class="amp">&</span>Almira</h1>
  <p class="subtitle">setiap foto adalah waktu yang berhenti sebentar untuk kita</p>
  <div class="stat-row">
    <span><b id="statTotal">0</b> Kenangan</span>
    <span><b id="statPhoto">0</b> Foto</span>
    <span><b id="statVideo">0</b> Video</span>
  </div>
</header>

<main>
  <div class="dropzone" id="dropzone">
    <svg viewBox="0 0 24 24" fill="none" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M12 3v12"/><path d="M7 8l5-5 5 5"/><path d="M4 17v2a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2v-2"/></svg>
    <p><strong>Tarik & lepas</strong> foto atau video di sini, atau klik untuk memilih</p>
    <p class="hint">Disimpan langsung ke akunmu · file besar (terutama video) mungkin gagal tersimpan jika melebihi batas ±5MB per file</p>
    <input type="file" id="fileInput" accept="image/*,video/*" multiple>
  </div>

  <div class="tabs-row">
    <div class="tabs">
      <button class="tab active" data-filter="all">Semua</button>
      <button class="tab" data-filter="image">Foto</button>
      <button class="tab" data-filter="video">Video</button>
    </div>
    <button class="sort-btn" id="sortBtn">↓ Terbaru dulu</button>
  </div>

  <div class="grid" id="grid"></div>

  <div class="empty" id="emptyState" style="display:none;">
    <svg viewBox="0 0 24 24" fill="none" stroke-width="1.4"><path d="M12 21s-8-5-8-11a5 5 0 0 1 9-3 5 5 0 0 1 9 3c0 6-10 11-10 11z"/></svg>
    <p>Belum ada kenangan tersimpan.<br>Unggah momen pertama kalian berdua.</p>
  </div>
</main>

<footer>Galeri pribadi · Aufi & Almira</footer>

<div class="lightbox" id="lightbox">
  <button class="lb-close" id="lbClose">&times;</button>
  <div class="lb-content">
    <div id="lbMediaWrap"></div>
    <div class="lb-cap-row">
      <div class="lb-cap" id="lbCap"></div>
      <input class="lb-cap-input" id="lbCapInput" style="display:none;">
      <button class="lb-edit-btn" id="lbEditBtn" title="Edit judul">✎</button>
    </div>
    <div class="lb-date" id="lbDate"></div>
    <div class="lb-actions">
      <button class="lb-btn" id="lbDownload">Unduh</button>
      <button class="lb-btn danger" id="lbDelete">Hapus</button>
    </div>
  </div>
</div>

<div class="toast" id="toast"></div>

<script>
(function(){
  // ---------- starfield ----------
  const starsEl = document.getElementById('stars');
  for(let i=0;i<70;i++){
    const s=document.createElement('div');
    s.className='star';
    const size = Math.random()*2+1;
    s.style.width=size+'px';s.style.height=size+'px';
    s.style.left=Math.random()*100+'%';s.style.top=Math.random()*100+'%';
    s.style.animationDelay=(Math.random()*4)+'s';
    starsEl.appendChild(s);
  }

  // ---------- state ----------
  let items = []; // {id, type, caption, date, thumb}
  let currentFilter = 'all';
  let currentSort = 'newest'; // 'newest' | 'oldest'
  const INDEX_KEY = 'gallery-index';

  const grid = document.getElementById('grid');
  const emptyState = document.getElementById('emptyState');
  const toastEl = document.getElementById('toast');
  const statTotal = document.getElementById('statTotal');
  const statPhoto = document.getElementById('statPhoto');
  const statVideo = document.getElementById('statVideo');

  function toast(msg){
    toastEl.textContent = msg;
    toastEl.classList.add('show');
    clearTimeout(toastEl._t);
    toastEl._t = setTimeout(()=>toastEl.classList.remove('show'), 2600);
  }

  function fmtDate(iso){
    const d = new Date(iso);
    return d.toLocaleDateString('id-ID',{day:'numeric',month:'long',year:'numeric'});
  }

  async function loadIndex(){
    try{
      const res = await window.storage.get(INDEX_KEY, false);
      items = res && res.value ? JSON.parse(res.value) : [];
    }catch(e){
      items = [];
    }
    render();
  }

  async function saveIndex(){
    try{
      await window.storage.set(INDEX_KEY, JSON.stringify(items), false);
    }catch(e){
      toast('Gagal menyimpan indeks galeri.');
    }
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
        img.src=item.thumb;
        img.loading='lazy';
        wrap.appendChild(img);
      }else{
        const vid=document.createElement('video');
        vid.src=item.thumb;
        vid.muted=true;
        wrap.appendChild(vid);
        const badge=document.createElement('div');
        badge.className='vid-badge';
        badge.textContent='▶';
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

  // ---------- filters ----------
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
  fileInput.addEventListener('change', e=>handleFiles(e.target.files));

  function readFileAsDataURL(file){
    return new Promise((resolve,reject)=>{
      const r = new FileReader();
      r.onload = ()=>resolve(r.result);
      r.onerror = reject;
      r.readAsDataURL(file);
    });
  }

  function compressImage(dataUrl, maxDim, quality){
    return new Promise((resolve)=>{
      const img = new Image();
      img.onload = ()=>{
        let {width,height} = img;
        if(width>height && width>maxDim){height=height*(maxDim/width);width=maxDim;}
        else if(height>maxDim){width=width*(maxDim/height);height=maxDim;}
        const canvas=document.createElement('canvas');
        canvas.width=width;canvas.height=height;
        canvas.getContext('2d').drawImage(img,0,0,width,height);
        resolve(canvas.toDataURL('image/jpeg', quality));
      };
      img.onerror=()=>resolve(dataUrl);
      img.src = dataUrl;
    });
  }

  async function handleFiles(fileList){
    const files = Array.from(fileList);
    for(const file of files){
      const isImage = file.type.startsWith('image/');
      const isVideo = file.type.startsWith('video/');
      if(!isImage && !isVideo){ toast(file.name+' bukan foto/video, dilewati.'); continue; }

      try{
        const rawDataUrl = await readFileAsDataURL(file);
        // For images: store a compressed version (both as thumb and full — keeps single-key simplicity and stays under size limits)
        let storedDataUrl = rawDataUrl;
        if(isImage){
          storedDataUrl = await compressImage(rawDataUrl, 1600, 0.82);
        }

        const approxBytes = storedDataUrl.length * 0.75;
        if(approxBytes > 4.7*1024*1024){
          toast('"'+file.name+'" terlalu besar untuk disimpan (maks ±5MB). Coba kompres dulu.');
          continue;
        }

        const id = 'm_'+Date.now()+'_'+Math.random().toString(36).slice(2,8);
        const item = {
          id,
          type: isImage?'image':'video',
          caption: file.name.replace(/\.[^/.]+$/,''),
          date: new Date().toISOString(),
          thumb: storedDataUrl
        };

        const res = await window.storage.set('photo:'+id, storedDataUrl, false);
        if(!res){ toast('Gagal menyimpan "'+file.name+'".'); continue; }

        items.push(item);
        await saveIndex();
        render();
        toast('Kenangan baru tersimpan ✧');
      }catch(err){
        toast('Terjadi kesalahan saat mengunggah "'+file.name+'".');
      }
    }
    fileInput.value='';
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

  async function openLightbox(id){
    const item = items.find(i=>i.id===id);
    if(!item) return;
    activeItem = item;
    exitEditMode(false);
    lbCap.textContent = item.caption || 'Tanpa judul';
    lbDate.textContent = fmtDate(item.date);
    lbMediaWrap.innerHTML = '<p style="color:var(--muted);font-size:13px;">Memuat...</p>';
    lightbox.classList.add('open');
    requestAnimationFrame(()=>lightbox.classList.add('show'));

    try{
      const res = await window.storage.get('photo:'+id, false);
      const dataUrl = res ? res.value : item.thumb;
      lbMediaWrap.innerHTML='';
      let mediaEl;
      if(item.type==='image'){
        mediaEl = document.createElement('img');
        mediaEl.className='lb-media';
        mediaEl.onload = ()=>mediaEl.classList.add('loaded');
        mediaEl.src=dataUrl;
      }else{
        mediaEl = document.createElement('video');
        mediaEl.className='lb-media';
        mediaEl.oncanplay = ()=>mediaEl.classList.add('loaded');
        mediaEl.src=dataUrl;
        mediaEl.controls=true;
      }
      lbMediaWrap.appendChild(mediaEl);
      activeItem._fullData = dataUrl;
    }catch(e){
      lbMediaWrap.innerHTML = '<p style="color:var(--rose);">Gagal memuat media.</p>';
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
    activeItem.caption = newCap;
    lbCap.textContent = newCap || 'Tanpa judul';
    exitEditMode();
    await saveIndex();
    render();
  }
  lbCapInput.addEventListener('keydown', e=>{
    if(e.key==='Enter') commitCaption();
    if(e.key==='Escape') exitEditMode();
  });
  lbCapInput.addEventListener('blur', commitCaption);
  lightbox.addEventListener('click', e=>{ if(e.target===lightbox) closeLightbox(); });
  document.addEventListener('keydown', e=>{ if(e.key==='Escape') closeLightbox(); });

  lbDownload.addEventListener('click', ()=>{
    if(!activeItem || !activeItem._fullData) return;
    const a=document.createElement('a');
    a.href=activeItem._fullData;
    const ext = activeItem.type==='image' ? 'jpg' : 'mp4';
    a.download = (activeItem.caption||'kenangan')+'.'+ext;
    document.body.appendChild(a);
    a.click();
    a.remove();
  });

  lbDelete.addEventListener('click', async ()=>{
    if(!activeItem) return;
    if(!confirm('Hapus kenangan ini? Tindakan ini tidak bisa dibatalkan.')) return;
    const id = activeItem.id;
    try{
      await window.storage.delete('photo:'+id, false);
    }catch(e){ /* ignore if already gone */ }
    items = items.filter(i=>i.id!==id);
    await saveIndex();
    render();
    closeLightbox();
    toast('Kenangan dihapus.');
  });

  loadIndex();
})();
</script>

</body>
</html>
