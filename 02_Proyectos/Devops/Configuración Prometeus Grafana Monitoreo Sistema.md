**MetaTags:** #_Done
**Tags:** #Prometeus #Grafana #Devops #ToLink 
- - -
## Instalación en Arch Linux e Iniciar servicios

```bash
sudo pacman -S grafana prometheus prometheus-node-exporter

sudo systemctl start grafana
sudo systemctl start prometheus
sudo systemctl start prometheus-node-exporter

# Habilitar al inicio del sistema
sudo systemctl enable grafana
sudo systemctl enable prometheus
sudo systemctl enable prometheus-node-exporter
```

### 3. Configurar Prometheus para recopilar métricas del sistema

Editar `/etc/prometheus/prometheus.yml`:

```yaml
# my global config
global:
  scrape_interval: 15s # Set the scrape interval to every 15 seconds. Default is every 1 minute.
  evaluation_interval: 15s # Evaluate rules every 15 seconds. The default is every 1 minute.
  # scrape_timeout is set to the global default (10s).
# Alertmanager configuration
alerting:
  alertmanagers:
    - static_configs:
        - targets:
          # - alertmanager:9093
# Load rules once and periodically evaluate them according to the global 'evaluation_interval'.
rule_files:
  # - "first_rules.yml"
  # - "second_rules.yml"
# A scrape configuration containing exactly one endpoint to scrape:
# Here it's Prometheus itself.
scrape_configs:
  # The job name is added as a label `job=<job_name>` to any timeseries scraped from this config.
  - job_name: "prometheus"
    # metrics_path defaults to '/metrics'
    # scheme defaults to 'http'.
    static_configs:
      - targets: ["localhost:9090"]
  - job_name: "node"
    static_configs:
      - targets: ["localhost:9100"]
```

### 4. Reiniciar Prometheus tras cambiar su configuración

```bash
sudo systemctl restart prometheus
```

## Configuración de Grafana

### 1. Acceder a Grafana

- Abre http://localhost:3000 en el navegador
- Usuario/contraseña por defecto: admin/admin

### 2. Añadir Prometheus como fuente de datos

- Ve a Configuración → Data Sources
- Añade una nueva fuente de datos
- Selecciona Prometheus
- URL: http://localhost:9090
- Guarda y prueba

### 3. Importar dashboard prediseñado

- Ve a Crear → Import
- Introduce el ID 1860 (Node Exporter Full)
- Selecciona la fuente de datos Prometheus
- Importa el dashboard

## Verificación

### Comprobar que Prometheus está recibiendo datos

- Visita http://localhost:9090/targets
- Verifica que el "node" tenga estado "UP"

### Probar una consulta simple en Prometheus

- Visita http://localhost:9090/graph
- Consulta: `node_cpu_seconds_total` o `node_memory_MemFree_bytes`

- - - 
#### ***Sources:***