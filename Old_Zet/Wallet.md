**Tags:** #_Todo
#ToTag #ToLink 
- - -
Las wallets son herramientas clave para interactuar con la blockchain. Aquí se categorizan según el nivel del usuario, junto con sus pros, contras y consejos adicionales.

---

## 1. **Custodial Wallet / Exchange (Nivel Noob)**

### Ejemplos:
- **Kraken**, **Binance**, **PayPal**, **Coinbase**

### Descripción:
Estas wallets son gestionadas por un tercero (custodial), lo que las hace fáciles de usar para principiantes. Sin embargo, no tienes control total sobre tus fondos.

### **Pros**:
- Fácil de usar, ideal para principiantes.  
- El proveedor puede protegerte si cometes errores.  

### **Contras**:
- **Riesgos de terceros**:
  - El exchange puede hacer "rug pull" (si no tienes las claves, no posees el dinero).  
  - Puede cerrar operaciones o declararse en quiebra.  
  - Puede congelar tu cuenta.  
- **Propiedad limitada**: El exchange actúa como un banco; ellos controlan tu dinero.  
- **Incompatibilidad con dApps**: No puedes interactuar directamente con aplicaciones descentralizadas.  

---

## 2. **Browser Wallet / EOA (Nivel Principiante o para Pequeñas Cantidades)**

### Ejemplos:
- **Metamask**, **Rabby**, **Frame**, **Rainbow**

### Descripción:
Estas wallets, conocidas como "hot wallets", siempre están conectadas a Internet. Almacenan la clave privada en un archivo local cifrado y se descifra al introducir tu contraseña (ERC-2335).

### **Pros**:
- "Tus claves, tu dinero".  
- Compatibles con dApps.  
- Operativa rápida, ideal para manejar pequeñas cantidades (como una billetera real).  

### **Contras**:
- Eres el único punto de seguridad. Si cometes un error, pierdes los fondos.  
- Vulnerable a hackeos de tu computadora.  
- Posible rastreo de datos por parte del proveedor de la wallet.  
- **Ataques de cadena de suministro**: La extensión puede contener malware.  

### **Consejos de Seguridad**:
- Usa firewalls como **Web3 Antivirus** o **Fire.xyz**.  

---

## 3. **Hard Wallet (Nivel Intermedio o para Medianas Cantidades)**

### Descripción:
Estas wallets almacenan tus claves privadas en dispositivos físicos separados de Internet, ofreciendo mayor seguridad. Sin embargo, la interacción con dApps es más compleja.

### **Pros**:
- "Tus claves, tu dinero".  
- Compatibles con dApps.  
- Aisladas de Internet, lo que reduce riesgos.  
- Las claves privadas no se almacenan en tu computadora.  

### **Contras**:
- Vulnerables a **ataques físicos** (ejemplo: robo del dispositivo).  
- Eres el único punto de seguridad.  
- Si cometes un error, pierdes los fondos.  
- Algunos ataques informáticos aún pueden afectarte (ejemplo: malware).  

---

## 4. **Multisig / Social Recovery (Nivel Avanzado o Grandes Cantidades)**

### Ejemplos:
- **Safe**, **Aragon**

### Descripción:
Estas soluciones avanzadas utilizan múltiples firmas (multisig) o recuperación social para proteger fondos, dividiendo el acceso entre varios actores o dispositivos.

### **Multisig**:
- **Pros**:
  - Varios puntos de seguridad.  
  - Recuperación social para manejar claves comprometidas.  
- **Contras**:
  - Menor compatibilidad con dApps.  
  - La dirección puede cambiar en diferentes redes.  

### **Recuperación Social**:
- **Pros**:
  - Varias firmas requieren múltiples pasos para ejecutar acciones.  
  - Si una clave se compromete, puedes reemplazarla sin mover fondos.  
- **Contras**:
  - Más complicado de usar.  

### **Vectores de Amenaza**:
- Necesidad de una gestión más compleja y potenciales riesgos de error humano.  

---

## Consejos para la Gestión de Claves Privadas

1. **Sé discreto**: No reveles cuánto dinero tienes.  
2. **Compra wallets oficiales**: Adquiere hard wallets solo de proveedores confiables (como Ledger o Trezor).  
3. **Rota tus claves privadas** periódicamente.  
4. **Evita almacenar claves en texto plano** o gestores de contraseñas en la nube.  
5. **No uses archivos `.env`** para guardar claves privadas.  
6. **Consulta recursos de seguridad** como [rekt.news](https://rekt.news).

---

## Herramientas para la Autogestión

- **Brain Wallet**: Memorización de frases semilla.  
- **Paper Wallet**: Claves privadas impresas en papel, mantenidas en un lugar seguro.  
- **Herramientas de Auto-Cifrado**: Software para cifrar claves privadas de forma segura.

---

### Explora Más
- [Safe Wallet](https://app.safe.global/welcome): Una de las soluciones líderes para Multisig y gestión avanzada de fondos.


- - - 
## ***Sources:***