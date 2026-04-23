# agreed.mx — Landing Page

Plataforma legal con IA para México.

## Stack
- HTML/CSS/JS estático — sin dependencias ni build step
- Fonts: Google Fonts (Josefin Sans + DM Sans)
- Deploy: Vercel (static)

## Estructura
```
agreed-site/
├── index.html        ← Landing page completa
├── vercel.json       ← Configuración Vercel
└── README.md
```

## Deploy en Vercel (primera vez)

### Mismo flujo que jaurrieta.mx y oftalmos.mx

### Opción A — CLI (recomendada)
```bash
# 1. Instalar Vercel CLI
npm install -g vercel

# 2. Login
vercel login

# 3. Deploy desde esta carpeta
cd agreed-site
vercel

# 4. Cuando pregunte "Link to existing project?" → No
#    Project name → agreed
#    Directory → ./
#    Override settings → No

# 5. Dominio personalizado (después del primer deploy)
vercel domains add agreed.mx
```

### Opción B — GitHub + Vercel (deploy automático)
```bash
# 1. Crear repo en GitHub
git init
git add .
git commit -m "feat: launch agreed.mx landing page"
git remote add origin https://github.com/TU_USUARIO/agreed-site.git
git push -u origin main

# 2. Ir a vercel.com → Import Project → seleccionar repo
# 3. En Vercel Dashboard → Settings → Domains → agregar agreed.mx
```

## Configurar agreed.mx en IONOS → Vercel

En el panel DNS de IONOS, cambiar:
```
Tipo    Nombre    Valor
A       @         76.76.21.21
CNAME   www       cname.vercel-dns.com
```

Esperar propagación DNS: 15 min — 2 horas.

## Desarrollo local
```bash
# Sin build step necesario — abrir directo en browser
open index.html

# O con servidor local
npx serve .
```

## Próximos pasos
- [ ] Agregar foto de Leslie Robles
- [ ] Conectar form de waitlist (Formspree o Resend)
- [ ] Integrar dashboard de la app (Fase 2)
- [ ] Analytics (Vercel Analytics — gratis)
