**Tags:** #_Todo
#ToTag #ToLink 
- - -
Sistema de automatización integrado en GitHub. Los workflows (flujos de trabajo) se definen en archivos YAML dentro de `.github/workflows/`.
### Componentes principales
- **Workflows**: Procesos automatizados definidos en YAML
- **Events**: Disparadores que activan workflows (`push`, `pull_request`, etc.)
- **Jobs**: Conjunto de steps que se ejecutan en un runner
- **Steps**: Tareas individuales dentro de un job
- **Runners**: Máquinas virtuales que ejecutan los workflows
### Casos de uso comunes
1. **Integración Continua (CI)**
   - Compilación automática, Ejecución de tests, Análisis de código (linting)
2. **Despliegue Continuo (CD)**
   - Deploy a servidores, Publicación de paquetes, Gestión de releases
3. **Automatización**
   - Gestión de PRs e issues, Notificaciones, Validaciones de seguridad
### Pipeline básico
```yaml
name: Basic CI Pipeline

on:
  push:
    branches: 
      - main
  pull_request:
    branches: 
      - main

jobs:
  test:
    runs-on: ubuntu-latest
    
    steps:
      - name: Checkout repository
        uses: actions/checkout@v3

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
          
      - name: Install dependencies
        run: npm ci
        
      - name: Run tests
        run: npm test
        
      - name: Run linter
        run: npm run lint

  deploy:
    needs: test
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    
    steps:
      - name: Deploy to production
        run: echo "Deploying to production server..."
```
Este workflow:
1. Se activa con push/PR a main
2. Ejecuta tests y linting
3. Si pasa y es main, simula deploy
### Secretos y Variables
```yaml
# Uso de secretos en workflow
steps:
  - name: Deploy
    env:
      API_TOKEN: ${{ secrets.API_TOKEN }}
```
Configura secretos en: Settings → Secrets and variables → Actions
- - - 
## ***Sources:***