<!doctype html>
<html lang="fa" dir="rtl">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>فروشگاه تجهیزات برق قدرت</title>
  <style>
    :root{
      --green: #1fa67a;
      --blue: #2b7dcf;
      --white: #ffffff;
      --muted: #6b7280;
      --card-shadow: 0 6px 18px rgba(15,23,42,0.08);
      --glass: rgba(255,255,255,0.85);
      font-family: 'Vazirmatn', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
    }
    *{box-sizing:border-box}
    body{margin:0;background:linear-gradient(180deg,#f6fbff 0%, #f3fff7 100%);color:#0f172a}
    header{background:var(--white);border-bottom:1px solid #e6eef7;position:sticky;top:0;z-index:50}
    .container{max-width:1100px;margin:0 auto;padding:18px}
    .nav{display:flex;align-items:center;justify-content:space-between;gap:12px}
    .brand{display:flex;align-items:center;gap:12px}
    .logo{width:44px;height:44px;border-radius:8px;background:linear-gradient(135deg,var(--green),var(--blue));display:flex;align-items:center;justify-content:center;color:white;font-weight:700}
    nav a{margin:0 10px;color:var(--muted);text-decoration:none}
    nav a.active{color:var(--blue);font-weight:600}
    .hero{padding:32px 0;display:flex;gap:20px;align-items:center}
    .hero-left{flex:1}
    .hero-right{flex:1}
    .hero h1{font-size:28px;margin:0 0 12px}
    .hero p{margin:0 0 18px;color:var(--muted)}
    .btn{display:inline-block;padding:10px 16px;border-radius:10px;text-decoration:none;color:white;background:var(--green);box-shadow:var(--card-shadow)}
    .btn.secondary{background:var(--blue)}
    .grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(240px,1fr));gap:18px}
    .card{background:var(--white);padding:14px;border-radius:12px;box-shadow:var(--card-shadow);display:flex;flex-direction:column}
    .card img{width:100%;height:160px;object-fit:cover;border-radius:8px}
    .card h3{margin:10px 0 6px;font-size:18px}
    .price{color:var(--green);font-weight:700}
    .meta{font-size:13px;color:var(--muted)}
    footer{padding:24px 0;margin-top:32px;background:transparent}
    .admin-bar{display:flex;gap:8px;align-items:center}
    .chip{padding:6px 10px;border-radius:999px;background:rgba(43,125,207,0.08);color:var(--blue);font-weight:600}
    /* modal */
    .modal-backdrop{position:fixed;inset:0;background:rgba(2,6,23,0.45);display:none;align-items:center;justify-content:center;padding:20px}
    .modal{background:var(--white);max-width:680px;width:100%;border-radius:12px;padding:18px}
    label{display:block;margin:8px 0 6px;font-weight:600}
    input[type=text], input[type=number], textarea, select{width:100%;padding:10px;border-radius:8px;border:1px solid #e8eef8}
    .row{display:flex;gap:12px}
    .row > *{flex:1}
    .small{font-size:13px;color:var(--muted)}
    @media (max-width:800px){
      .hero{flex-direction:column}
      nav{display:none}
    }
    /* simple badge */
    .badge{display:inline-block;padding:6px 8px;border-radius:6px;background:#eef7f3;color:var(--green);font-weight:700}
  </style>
</head>
<body>
  <header>
    <div class="container nav">
      <div class="brand">
        <div class="logo">پ</div>
        <div>
          <div style="font-weight:700">پاورمارکت</div>
          <div style="font-size:12px;color:var(--muted)">فروش تجهیزات برق قدرت</div>
        </div>
      </div>
      <nav>
        <a href="#home" class="active">خانه</a>
        <a href="#products">محصولات</a>
        <a href="#about">درباره ما</a>
        <a href="#contact">تماس</a>
      </nav>
      <div class="admin-bar">
        <button class="btn" id="btn-admin">ورود ادمین</button>
        <a class="btn secondary" id="btn-add-sample">افزودن نمونه</a>
      </div>
    </div>
  </header>

  <main class="container">
    <section id="home" class="hero">
      <div class="hero-left">
        <h1>فروشگاه تجهیزات برق قدرت — ساده، سریع، مطمئن</h1>
        <p>فروشگاه را از پایه طراحی کردم تا مدیریت محصولات و قیمت‌ها برای شما آسان باشد. با پنل مدیریت می‌توانید محصولات را اضافه، ویرایش یا حذف کنید.</p>
        <div style="display:flex;gap:10px">
          <a href="#products" class="btn">مشاهده محصولات</a>
          <a href="#contact" class="btn secondary">تماس با ما</a>
        </div>
      </div>
      <div class="hero-right">
        <div style="background:linear-gradient(135deg,var(--green),var(--blue));padding:18px;border-radius:12px;color:white">
          <h3 style="margin:0">پکیج‌های ویژه نصب و سرویس</h3>
          <p style="margin:6px 0 0">نصب آیفون تصویری، اجاق گاز، تعمیرات لوازم خانگی و خدمات برق صنعتی در مشهد</p>
        </div>
      </div>
    </section>

    <section id="products" style="margin-top:24px">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:12px">
        <h2 style="margin:0">محصولات</h2>
        <div class="small">تعداد محصولات: <span id="product-count">0</span></div>
      </div>
      <div class="grid" id="product-grid">
        <!-- products injected by JS -->
      </div>
    </section>

    <section id="about" style="margin-top:32px">
      <h2>درباره ما</h2>
      <p class="small">ما در پاورمارکت انواع تجهیزات برق قدرت را عرضه می‌کنیم — از کابل‌ها و فیوزها تا تابلوهای کنترل. تمرکز ما روی کیفیت و خدمات پس از فروش است.</p>
    </section>

    <section id="contact" style="margin-top:24px;display:flex;flex-direction:column;gap:8px">
      <h2>تماس با ما</h2>
      <div class="small">ایمیل: info@powermarket.local — تلفن: 051-xxxxxxx</div>
    </section>

    <footer>
      <div style="display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap">
        <div class="small">© 2025 پاورمارکت — کلیه حقوق محفوظ است.</div>
        <div class="small">تم: سبز | سفید | آبی</div>
      </div>
    </footer>
  </main>

  <!-- Modal: Admin login / product editor -->
  <div class="modal-backdrop" id="modal">
    <div class="modal" id="modal-content">
      <div id="admin-login-view">
        <h3>ورود ادمین</h3>
        <p class="small">رمز پیش‌فرض: <strong>1234</strong> (برای تغییر بسته به نیازتان در کد زیر مقدار را تغییر دهید)</p>
        <label>رمز ورود</label>
        <input type="text" id="admin-pass" placeholder="رمز را وارد کنید" />
        <div style="margin-top:12px;display:flex;gap:8px">
          <button class="btn" id="admin-login-btn">ورود</button>
          <button class="btn secondary" id="modal-close">انصراف</button>
        </div>
      </div>

      <div id="admin-panel-view" style="display:none">
        <div style="display:flex;justify-content:space-between;align-items:center">
          <h3>پنل مدیریت</h3>
          <div>
            <button class="btn" id="btn-add">افزودن محصول</button>
            <button class="btn secondary" id="btn-logout">خروج</button>
          </div>
        </div>

        <div id="admin-list" style="margin-top:12px"></div>

        <!-- editor form -->
        <div id="editor" style="margin-top:12px;display:none">
          <h4 id="editor-title">افزودن محصول</h4>
          <label>نام محصول</label>
          <input type="text" id="p-name" />
          <label>قیمت (تومان)</label>
          <input type="number" id="p-price" />
          <label>دسته‌بندی</label>
          <input type="text" id="p-cat" placeholder="مثال: کابل، فیوز، تابلو" />
          <label>توضیح کوتاه</label>
          <textarea id="p-desc" rows="3"></textarea>
          <label>آدرس تصویر (اختیاری)</label>
          <input type="text" id="p-img" placeholder="http://example.com/image.jpg" />
          <div style="display:flex;gap:8px;margin-top:8px">
            <button class="btn" id="save-product">ذخیره</button>
            <button class="btn secondary" id="cancel-edit">انصراف</button>
          </div>
        </div>
      </div>
    </div>
  </div>

  <script>
    // Simple product store using localStorage
    const ADMIN_PASS = '1234'; // change this if needed
    const STORAGE_KEY = 'power_market_products_v1';

    // sample default products if none exist
    const defaultProducts = [
      {id:uid(),name:'کابل برق 6mm',price:450000,cat:'کابل',desc:'کابل قدرتمند مناسب تاسیسات صنعتی',img:'https://picsum.photos/seed/cable/800/600'},
      {id:uid(),name:'فیوز مینیاتوری 16A',price:80000,cat:'فیوز',desc:'فیوز مینیاتوری استاندارد',img:'https://picsum.photos/seed/fuse/800/600'},
      {id:uid(),name:'پنل کنترل تکفاز',price:1250000,cat:'تابلو',desc:'تابلوی کنترل با کیفیت بالا',img:'https://picsum.photos/seed/panel/800/600'}
    ];

    function uid(){return 'p_'+Math.random().toString(36).slice(2,9)}

    function saveProducts(arr){localStorage.setItem(STORAGE_KEY,JSON.stringify(arr))}
    function loadProducts(){
      try{const s=localStorage.getItem(STORAGE_KEY);return s?JSON.parse(s):null}catch(e){return null}
    }

    function ensureProducts(){
      let p = loadProducts();
      if(!p){p = defaultProducts; saveProducts(p)}
      return p;
    }

    // render product grid
    function renderProducts(){
      const grid = document.getElementById('product-grid');
      const products = ensureProducts();
      grid.innerHTML = '';
      products.forEach(prod=>{
        const card = document.createElement('div');card.className='card';
        card.innerHTML = `
          <img src="${prod.img||'https://picsum.photos/seed/'+prod.id+'/800/600'}" alt="${escapeHtml(prod.name)}"/>
          <h3>${escapeHtml(prod.name)}</h3>
          <div class="meta">${escapeHtml(prod.cat)} • <span class="price">${numberWithCommas(prod.price)} تومان</span></div>
          <p class="small">${escapeHtml(prod.desc)}</p>
          <div style="margin-top:auto;display:flex;gap:8px;justify-content:flex-end">
            <button class="btn" onclick="openAdminAndEdit('${prod.id}')">ویرایش</button>
          </div>
        `;
        grid.appendChild(card);
      })
      document.getElementById('product-count').textContent = products.length;
    }

    // utilities
    function numberWithCommas(x){return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g,',')}
    function escapeHtml(s){return (s||'').toString().replace(/[&<>"']/g,function(c){return {'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":"&#39;"}[c]})}

    // Admin modal controls
    const modal = document.getElementById('modal');
    const modalClose = document.getElementById('modal-close');
    const btnAdmin = document.getElementById('btn-admin');
    const adminLoginBtn = document.getElementById('admin-login-btn');
    const adminPassIn = document.getElementById('admin-pass');
    const adminLoginView = document.getElementById('admin-login-view');
    const adminPanelView = document.getElementById('admin-panel-view');
    const btnLogout = document.getElementById('btn-logout');
    const adminList = document.getElementById('admin-list');
    const editor = document.getElementById('editor');
    const editorTitle = document.getElementById('editor-title');
    const btnAdd = document.getElementById('btn-add');
    const btnAddSample = document.getElementById('btn-add-sample');

    let editId = null;

    btnAdmin.addEventListener('click',()=>{modal.style.display='flex';adminLoginView.style.display='block';adminPanelView.style.display='none';adminPassIn.value=''});
    modalClose.addEventListener('click',()=>{modal.style.display='none'});
    btnAddSample.addEventListener('click',()=>{addSampleProduct();renderProducts();});

    adminLoginBtn.addEventListener('click',()=>{
      const v = adminPassIn.value.trim();
      if(v===ADMIN_PASS){
        adminLoginView.style.display='none';adminPanelView.style.display='block';renderAdminList();
      }else{alert('رمز اشتباه است')}
    });

    btnLogout.addEventListener('click',()=>{modal.style.display='none';adminLoginView.style.display='block';adminPanelView.style.display='none'});

    btnAdd.addEventListener('click',()=>{openEditorForNew()});

    function renderAdminList(){
      const products = ensureProducts();
      adminList.innerHTML='';
      products.forEach(p=>{
        const row = document.createElement('div');
        row.style.display='flex';row.style.alignItems='center';row.style.justifyContent='space-between';row.style.padding='8px 0';row.style.borderBottom='1px solid #f0f6ff';
        row.innerHTML = `<div><strong>${escapeHtml(p.name)}</strong><div class="small">${escapeHtml(p.cat)} — ${numberWithCommas(p.price)} تومان</div></div>
          <div style="display:flex;gap:8px">
            <button class="btn" onclick="openEditor('${p.id}')">ویرایش</button>
            <button class="btn secondary" onclick="deleteProduct('${p.id}')">حذف</button>
          </div>`;
        adminList.appendChild(row);
      })
      const clearBtn = document.createElement('div');clearBtn.style.marginTop='12px';
      clearBtn.innerHTML = '<button class="btn secondary" id="clear-storage">پاک کردن همه داده‌ها</button>';
      adminList.appendChild(clearBtn);
      document.getElementById('clear-storage').addEventListener('click',()=>{if(confirm('آیا مطمئن هستید؟ همه محصولات حذف خواهند شد.')){localStorage.removeItem(STORAGE_KEY);ensureProducts();renderAdminList();renderProducts()}})
    }

    // editor logic
    document.getElementById('save-product').addEventListener('click',()=>{
      const name = document.getElementById('p-name').value.trim();
      const price = Number(document.getElementById('p-price').value||0);
      const cat = document.getElementById('p-cat').value.trim();
      const desc = document.getElementById('p-desc').value.trim();
      const img = document.getElementById('p-img').value.trim();
      if(!name){alert('نام محصول ضروری است');return}
      let products = ensureProducts();
      if(editId){
        const idx = products.findIndex(x=>x.id===editId);
        if(idx>-1){products[idx].name=name;products[idx].price=price;products[idx].cat=cat;products[idx].desc=desc;products[idx].img=img}
      }else{
        products.push({id:uid(),name,price,cat,desc,img});
      }
      saveProducts(products);renderAdminList();renderProducts();closeEditor();
    });

    document.getElementById('cancel-edit').addEventListener('click',()=>{closeEditor()});

    function openEditorForNew(){editId=null;editorTitle.textContent='افزودن محصول';editor.style.display='block';document.getElementById('p-name').value='';document.getElementById('p-price').value='';document.getElementById('p-cat').value='';document.getElementById('p-desc').value='';document.getElementById('p-img').value=''}
    function openEditor(id){
      const products = ensureProducts();
      const p = products.find(x=>x.id===id);if(!p)return;editId=id;editorTitle.textContent='ویرایش محصول';editor.style.display='block';document.getElementById('p-name').value=p.name;document.getElementById('p-price').value=p.price;document.getElementById('p-cat').value=p.cat;document.getElementById('p-desc').value=p.desc;document.getElementById('p-img').value=p.img||''}
    function closeEditor(){editor.style.display='none';editId=null}

    function deleteProduct(id){if(!confirm('آیا این محصول حذف شود؟'))return;let p=ensureProducts();p=p.filter(x=>x.id!==id);saveProducts(p);renderAdminList();renderProducts()}

    // helper to open admin modal and edit a product directly
    function openAdminAndEdit(id){modal.style.display='flex';adminLoginView.style.display='none';adminPanelView.style.display='block';renderAdminList();openEditor(id)}
    window.openAdminAndEdit = openAdminAndEdit; // expose to inline onclick
    window.openEditor = openEditor;window.deleteProduct=deleteProduct;

    function addSampleProduct(){
      const p=ensureProducts();p.push({id:uid(),name:'پمپ ایستاده صنعتی',price:2150000,cat:'تاسیسات',desc:'پمپ توان بالا برای کاربردهای صنعتی',img:'https://picsum.photos/seed/newprod/800/600'});saveProducts(p);renderAdminList();
    }

    // init
    renderProducts();

    // close modal on backdrop click
    document.getElementById('modal').addEventListener('click',(e)=>{if(e.target===document.getElementById('modal')){modal.style.display='none'}})
  </script>
</body>
</html>
