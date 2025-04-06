# **📝 Documentación para la Lista de Bloqueo de Pi-hole (Archivo .txt)**

Este archivo `.txt` contiene una lista de dominios que Pi-hole utilizará para bloquear anuncios y sitios no deseados en la red local. El archivo debe seguir un formato específico para que Pi-hole pueda procesarlo adecuadamente.

## **📑 Formato del Archivo:**

- Cada dominio debe estar en una **línea separada**.
- Los dominios deben estar escritos en su **forma simple**, **sin "http://"**, **"https://"**, ni **"www"**. Pi-hole los procesará correctamente si están en su forma base (sin subdirectorios ni protocolos).

### Ejemplo Correcto:
```
example.com
ads.example.net
trackers.example.org
```

### Ejemplo Incorrecto:
```
http://example.com
https://ads.example.net
www.trackers.example.org
```

## **🔧 Instrucciones:**

> [!NOTE]  
> Asegúrate de seguir este formato para evitar errores. Los dominios deben estar limpios y sin caracteres extraños como `http://` o `www`.

### **1. Agregar Dominios**:
   - Cada vez que desees agregar un dominio para bloquear, simplemente agrega una nueva línea con el nombre del dominio, sin ningún prefijo (como "http://" o "www.").
   - **Ejemplo**: `spam.com`

### **2. Evitar Espacios**:
   - No pongas **espacios** al inicio o al final de cada línea. 
   - **Ejemplo Incorrecto**: ` example.com ` o `example.com `.

> [!TIP]  
> Si prefieres usar una lista automática, Pi-hole te permite cargar **listas de bloqueo externas** que contienen miles de dominios para bloquear, por lo que no es necesario agregar dominios manualmente uno por uno.

### **3. Comentarios**:
   - Puedes agregar comentarios en el archivo utilizando el símbolo `#`. Todo lo que siga al símbolo `#` en esa línea será ignorado por Pi-hole.
   - Los comentarios pueden ser útiles para explicar o categorizar dominios en la lista.

   **Ejemplo de comentario**:
   ```txt
   # Bloqueo de anuncios de ejemplo
   example.com
   ads.example.net
   ```

### **4. Archivos de Lista Externos**:
   - Si prefieres no gestionar el archivo manualmente, puedes usar **listas de bloqueo externas** proporcionadas por fuentes confiables (por ejemplo, listas en GitHub o servicios como EasyList).
   - Si estás usando una lista externa, puedes agregar la **URL** de esa lista al archivo de configuración de Pi-hole, en lugar de copiar y pegar dominios individualmente.

### **5. Formateo Adicional**:
   - En caso de querer bloquear un dominio completo con subdominios, puedes usar el **comodín** `*`. Esto bloqueará todos los subdominios de ese dominio.
   
   **Ejemplo**:
   ```
   *.example.com
   ```

   Esto bloquearía tanto `ads.example.com` como `www.example.com` y cualquier otro subdominio de `example.com`.

## **🚀 Subir el Archivo a Pi-hole**:

> [!IMPORTANT]  
> Después de agregar o actualizar el archivo `.txt` con más dominios, asegúrate de **actualizar Pi-hole** para que reciba los cambios. Esto puede hacerse desde la interfaz web de Pi-hole, en **"Pi-hole"** > **"Update Gravity"**.

### **1. Subir el Archivo Manualmente**:
   - Si el archivo está en tu servidor local, puedes cargarlo directamente a Pi-hole desde la **interfaz web** de Pi-hole.
   - Ve a **"Group Management"** > **"Adlists"** y agrega la **URL** de tu archivo `.txt`.

### **2. Actualizar Pi-hole**:
   - Después de añadir o actualizar el archivo `.txt` con más dominios, asegúrate de hacer la actualización para que Pi-hole reciba los cambios. Esto se puede hacer desde **"Pi-hole"** > **"Update Gravity"** en la interfaz web de Pi-hole.

> [!WARNING]  
> Si no actualizas Pi-hole después de agregar nuevos dominios, los cambios no tendrán efecto y los dominios no serán bloqueados.

## **💡 Consejos Adicionales**:

> [!CAUTION]  
> Ten cuidado de no agregar dominios de forma incorrecta, ya que Pi-hole no los procesará correctamente. Revisa que cada dominio esté bien escrito y sin espacios adicionales.

- **Evitar Duplicados**: Asegúrate de no añadir el mismo dominio varias veces. Pi-hole procesará el archivo y eliminará automáticamente los dominios duplicados, pero es una buena práctica revisar que no existan.
- **Uso de Listas Externas**: Si deseas una solución más fácil, puedes usar **listas externas** de bloqueo que están siendo mantenidas y actualizadas regularmente. Pi-hole permite agregar estas listas en la interfaz de administración sin necesidad de cargar un archivo `.txt` manualmente.

## **🌐 Dónde Conseguir Listas Externas**:

- [GitHub - EasyList](https://github.com/easylist/easylist)
- [The Block List Project](https://www.blocklistproject.github.io/)

---

> [!IMPORTANT]  
> **Recuerda**: Puedes utilizar el comodín `*` para bloquear todos los subdominios de un dominio. Por ejemplo, `*.example.com` bloquearía cualquier subdominio de `example.com`.
