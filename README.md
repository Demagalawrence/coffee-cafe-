# Business (Django) Project

A simple Django website for a coffee shop with four pages: Home, About, Products, and Store. Static assets are managed via Django staticfiles.

## Requirements
- Python 3.10+
- pip
- Recommended: virtual environment (venv)

## Setup
1. Create and activate a virtual environment (recommended):
   - Windows (PowerShell):
     - python -m venv .venv
     - .venv\\Scripts\\Activate.ps1
2. Install dependencies:
   - pip install django

Note: A local venv may already exist as `venv2`, but creating your own is fine.

## Running the Project
1. Navigate to the project folder:
   - c:/Users/MEDISOFT/Desktop/business/business
2. Apply migrations (if needed):
   - py -3 manage.py migrate
3. Start the dev server:
   - py -3 manage.py runserver
4. Open in your browser:
   - http://127.0.0.1:8000/

## Pages
- /           → Home
- /about/     → About
- /products/  → Products
- /store/     → Store

## Static Files
- Development: files are served from `business/static/`.
- Collection (optional):
  - py -3 manage.py collectstatic
  - Collected files go to `business/staticfiles/`.

## Project Structure
- business/
  - business/        ← Django project (settings, urls, wsgi)
  - company/         ← App (views, urls)
  - templates/       ← HTML templates (index, about, products, store)
  - static/          ← CSS, JS, images
  - staticfiles/     ← Collected static (auto-generated)
  - manage.py        ← Django management script

## Configuration Notes
- Templates dir is configured as `BASE_DIR / 'templates'` in `settings.py`.
- Static files configured with `STATIC_URL = 'static/'` and `STATICFILES_DIRS = [BASE_DIR / 'static']`.

## Common Issues
- CSS/images not updating:
  - Hard refresh (Ctrl+F5) or open in a private window.
  - Optionally add a cache-busting query (e.g., `styles.css?v=2`) or update the image URL (e.g., `bg.jpg?v=2`).
- 404 on pages:
  - Ensure URLs are defined in `company/urls.py` and included in `business/urls.py`.

## Admin (optional)
- Create a superuser to access /admin/:
  - py -3 manage.py createsuperuser

## License
MIT (theme assets based on Start Bootstrap Business Casual).
