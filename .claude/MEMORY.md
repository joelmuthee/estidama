# Estidama Project Memory

## Rules & Standing Instructions

### OG / WhatsApp Sharing Image
**ALWAYS** use the Estidama logo (`LOGO.png`) resized to 1200×630px as the Open Graph / WhatsApp sharing image.
- Generated file: `og-image.jpg` (1200×630, dark green background `#0D3D0D`, logo centred)
- Live URL: `https://estidama.essenceautomations.com/og-image.jpg`
- Apply to ALL pages: `og:image` and `twitter:image` meta tags
- Regenerate `og-image.jpg` any time the logo changes using PIL:
  ```python
  from PIL import Image
  logo = Image.open('LOGO.png').convert('RGBA')
  canvas = Image.new('RGBA', (1200, 630), (13, 61, 13, 255))
  ratio = min(700/logo.width, 300/logo.height)
  new_size = (int(logo.width*ratio), int(logo.height*ratio))
  logo_r = logo.resize(new_size, Image.LANCZOS)
  canvas.paste(logo_r, ((1200-new_size[0])//2, (630-new_size[1])//2), logo_r)
  canvas.convert('RGB').save('og-image.jpg', 'JPEG', quality=90)
  ```

## Site Info
- Live site: https://estidama.essenceautomations.com
- GitHub: https://github.com/joelmuthee/estidama.git (branch: main)
- Stack: Static HTML/CSS — no framework
- Pages: index.html, about.html, services.html, contact.html

## Nav
- All inner pages use `class="nav hero-nav"` (NOT `scrolled`) so links are visible over dark page-hero
- JS switches to `scrolled` on scroll

## Images
- No white people in any people photos
- Sustainability Consulting: Indian + Black professionals only
- About page: Asian/Indian + Kenyan representation
