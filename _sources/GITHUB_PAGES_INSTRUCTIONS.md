# Instrucciones para actualizar GitHub Pages

Como tienes problemas con jupyter-book en Windows, aquí está la solución alternativa:

## Opción 1: Compilar desde WSL o Linux
Si tienes WSL instalado:
```bash
wsl
cd /mnt/c/Users/OMAR\ DANIEL\ MEDINA\ V/credit_scoring_machine_learning/credit_scoring
pip install jupyter-book
jupyter-book build .
```

## Opción 2: Usar el build existente y agregar notebooks manualmente
Tus notebooks 09, 10 y 11 están listos. Solo necesitas:

1. Ejecutar este comando para convertirlos a HTML:
```bash
jupyter nbconvert --to html notebooks/09_optimizacion_auc.ipynb --output-dir=_build/html/notebooks/
jupyter nbconvert --to html notebooks/10_monotonic_lightgbm.ipynb --output-dir=_build/html/notebooks/
jupyter nbconvert --to html notebooks/11_deep_learning_ligero.ipynb --output-dir=_build/html/notebooks/
```

2. Actualizar el índice HTML manualmente

3. Push a gh-pages:
```bash
cd _build/html
git add .
git commit -m "Add notebooks 09-11"
git push origin gh-pages --force
```

## URL de tu GitHub Pages
https://omedinaavilla.github.io/credit_scoring/

Espera 2-3 minutos después del push para que GitHub actualice el sitio.
